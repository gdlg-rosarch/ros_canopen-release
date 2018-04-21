# Script generated with Bloom
pkgdesc="ROS - A generic canopen implementation for ROS"
url='http://ros.org/wiki/ros_canopen'

pkgname='ros-lunar-ros-canopen'
pkgver='0.7.6_1'
pkgrel=1
arch=('any')
license=('LGPL'
)

makedepends=('ros-lunar-catkin'
)

depends=('ros-lunar-can-msgs'
'ros-lunar-canopen-402'
'ros-lunar-canopen-chain-node'
'ros-lunar-canopen-master'
'ros-lunar-canopen-motor-node'
'ros-lunar-socketcan-bridge'
'ros-lunar-socketcan-interface'
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
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

