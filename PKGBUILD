# Script generated with Bloom
pkgdesc="ROS - The roomblock_bringup package"


pkgname='ros-kinetic-roomblock-bringup'
pkgver='0.0.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-roslaunch'
'ros-kinetic-rostest'
)

depends=('python2-pyserial'
'ros-kinetic-controller-manager'
'ros-kinetic-create-node'
'ros-kinetic-image-transport'
'ros-kinetic-joy'
'ros-kinetic-robot-pose-ekf'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-roomblock-description'
'ros-kinetic-rplidar-ros'
'ros-kinetic-rviz'
'ros-kinetic-teleop-twist-joy'
)

conflicts=()
replaces=()

_dir=roomblock_bringup
source=()
md5sums=()

prepare() {
    cp -R $startdir/roomblock_bringup $srcdir/roomblock_bringup
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

