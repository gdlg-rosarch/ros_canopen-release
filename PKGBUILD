# Script generated with Bloom
pkgdesc="ROS - ROS node base implementation for CANopen chains with support for management services and diagnostics"
url='http://wiki.ros.org/canopen_chain_node'

pkgname='ros-kinetic-canopen-chain-node'
pkgver='0.7.6_1'
pkgrel=1
arch=('any')
license=('LGPLv3'
)

makedepends=('ros-kinetic-canopen-master'
'ros-kinetic-catkin'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-message-generation'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-socketcan-interface'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
)

depends=('ros-kinetic-canopen-master'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-message-runtime'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-socketcan-interface'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
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

