# Script generated with Bloom
pkgdesc="ROS - This package contains a generic CAN interface description with helpers for filtering and driver implementation. Further a socketcan implementation based on boost::asio is included."
url='http://wiki.ros.org/socketcan_interface'

pkgname='ros-lunar-socketcan-interface'
pkgver='0.7.6_1'
pkgrel=1
arch=('any')
license=('LGPLv3'
)

makedepends=('boost'
'linux-api-headers'
'ros-lunar-catkin'
'ros-lunar-class-loader'
'ros-lunar-rosunit'
)

depends=('boost'
'linux-api-headers'
'ros-lunar-class-loader'
)

conflicts=()
replaces=()

_dir=socketcan_interface
source=()
md5sums=()

prepare() {
    cp -R $startdir/socketcan_interface $srcdir/socketcan_interface
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

