# Script generated with Bloom
pkgdesc="ROS - Provides manipulator cartesian jogging."
url='http://wiki.ros.org/jog_arm'

pkgname='ros-kinetic-jog-arm'
pkgver='0.0.3_3'
pkgrel=1
arch=('any')
license=('specified in-file'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-geometry-msgs'
'ros-kinetic-joy'
'ros-kinetic-moveit-ros-manipulation'
'ros-kinetic-moveit-ros-move-group'
'ros-kinetic-moveit-ros-planning-interface'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
)

depends=('ros-kinetic-cmake-modules'
'ros-kinetic-geometry-msgs'
'ros-kinetic-joy'
'ros-kinetic-moveit-ros-manipulation'
'ros-kinetic-moveit-ros-move-group'
'ros-kinetic-moveit-ros-planning-interface'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=jog_arm
source=()
md5sums=()

prepare() {
    cp -R $startdir/jog_arm $srcdir/jog_arm
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

