# Script generated with Bloom
pkgdesc="ROS - ROS node base implementation for CANopen chains with support for management services and diagnostics"
url='http://wiki.ros.org/canopen_chain_node'

pkgname='ros-lunar-canopen-chain-node'
pkgver='0.7.6_1'
pkgrel=1
arch=('any')
license=('LGPLv3'
)

makedepends=('ros-lunar-canopen-master'
'ros-lunar-catkin'
'ros-lunar-diagnostic-updater'
'ros-lunar-message-generation'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-roslib'
'ros-lunar-socketcan-interface'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
)

depends=('ros-lunar-canopen-master'
'ros-lunar-diagnostic-updater'
'ros-lunar-message-runtime'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-roslib'
'ros-lunar-socketcan-interface'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
)

conflicts=()
replaces=()

_dir=canopen_chain_node
source=()
md5sums=()

prepare() {
    cp -R $startdir/canopen_chain_node $srcdir/canopen_chain_node
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

