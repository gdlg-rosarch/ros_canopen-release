# Script generated with Bloom
pkgdesc="ROS - A generic canopen implementation for ROS"
url='http://ros.org/wiki/ros_canopen'

pkgname='ros-kinetic-ros-canopen'
pkgver='0.7.6_1'
pkgrel=1
arch=('any')
license=('LGPL'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-can-msgs'
'ros-kinetic-canopen-402'
'ros-kinetic-canopen-chain-node'
'ros-kinetic-canopen-master'
'ros-kinetic-canopen-motor-node'
'ros-kinetic-socketcan-bridge'
'ros-kinetic-socketcan-interface'
)

conflicts=()
replaces=()

_dir=ros_canopen
source=()
md5sums=()

prepare() {
    cp -R $startdir/ros_canopen $srcdir/ros_canopen
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

