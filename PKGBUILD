# Script generated with Bloom
pkgdesc="ROS - This package extends the canopen_chain_node with specialized handling for canopen_402 devices. It facilitates interface abstraction with ros_control."
url='http://wiki.ros.org/canopen_motor_node'

pkgname='ros-lunar-canopen-motor-node'
pkgver='0.7.6_1'
pkgrel=1
arch=('any')
license=('LGPLv3'
)

makedepends=('muparser'
'ros-lunar-canopen-402'
'ros-lunar-canopen-chain-node'
'ros-lunar-catkin'
'ros-lunar-controller-manager'
'ros-lunar-controller-manager-msgs'
'ros-lunar-filters'
'ros-lunar-hardware-interface'
'ros-lunar-joint-limits-interface'
'ros-lunar-urdf'
)

depends=('muparser'
'ros-lunar-canopen-402'
'ros-lunar-canopen-chain-node'
'ros-lunar-controller-manager'
'ros-lunar-controller-manager-msgs'
'ros-lunar-filters'
'ros-lunar-hardware-interface'
'ros-lunar-joint-limits-interface'
'ros-lunar-urdf'
)

conflicts=()
replaces=()

_dir=canopen_motor_node
source=()
md5sums=()

prepare() {
    cp -R $startdir/canopen_motor_node $srcdir/canopen_motor_node
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

