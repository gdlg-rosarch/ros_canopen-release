# Script generated with Bloom
pkgdesc="ROS - CiA(r) CANopen 301 master implementation with support for interprocess master synchronisation."
url='http://wiki.ros.org/canopen_master'

pkgname='ros-lunar-canopen-master'
pkgver='0.7.6_1'
pkgrel=1
arch=('any')
license=('LGPLv3'
)

makedepends=('boost'
'ros-lunar-catkin'
'ros-lunar-class-loader'
'ros-lunar-rosunit'
'ros-lunar-socketcan-interface'
)

depends=('boost'
'ros-lunar-class-loader'
'ros-lunar-socketcan-interface'
)

conflicts=()
replaces=()

_dir=canopen_master
source=()
md5sums=()

prepare() {
    cp -R $startdir/canopen_master $srcdir/canopen_master
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

