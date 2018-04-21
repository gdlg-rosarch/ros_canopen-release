# Script generated with Bloom
pkgdesc="ROS - Provides nodes to convert messages from SocketCAN to a ROS Topic and vice versa."
url='http://wiki.ros.org/socketcan_bridge'

pkgname='ros-lunar-socketcan-bridge'
pkgver='0.7.6_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-can-msgs'
'ros-lunar-catkin'
'ros-lunar-roscpp'
'ros-lunar-roslint'
'ros-lunar-rostest'
'ros-lunar-rosunit'
'ros-lunar-socketcan-interface'
)

depends=('ros-lunar-can-msgs'
'ros-lunar-roscpp'
'ros-lunar-socketcan-interface'
)

conflicts=()
replaces=()

_dir=socketcan_bridge
source=()
md5sums=()

prepare() {
    cp -R $startdir/socketcan_bridge $srcdir/socketcan_bridge
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

