# Script generated with import_catkin_packages.py
# For more information: https://github.com/bchretien/arch-ros-stacks
pkgdesc="ROS - rqt_common_plugins metapackage provides ROS backend graphical tools suite that can be used on/off of robot runtime."
url='http://ros.org/wiki/rqt_common_plugins'

pkgname='ros-hydro-rqt-common-plugins'
pkgver='0.3.9'
_pkgver_patch=0
arch=('any')
pkgrel=1
license=('BSD')

ros_makedepends=(ros-hydro-catkin)
makedepends=('cmake' 'git' 'ros-build-tools'
  ${ros_makedepends[@]})

ros_depends=(ros-hydro-rqt-dep
  ros-hydro-rqt-image-view
  ros-hydro-rqt-bag-plugins
  ros-hydro-rqt-web
  ros-hydro-rqt-service-caller
  ros-hydro-rqt-py-console
  ros-hydro-rqt-bag
  ros-hydro-rqt-reconfigure
  ros-hydro-rqt-msg
  ros-hydro-rqt-srv
  ros-hydro-rqt-plot
  ros-hydro-rqt-top
  ros-hydro-rqt-action
  ros-hydro-rqt-topic
  ros-hydro-rqt-py-common
  ros-hydro-rqt-graph
  ros-hydro-rqt-publisher
  ros-hydro-rqt-logger-level
  ros-hydro-rqt-launch
  ros-hydro-rqt-console
  ros-hydro-rqt-shell)
depends=(${ros_depends[@]})

_tag=release/hydro/rqt_common_plugins/${pkgver}-${_pkgver_patch}
_dir=rqt_common_plugins
source=("${_dir}"::"git+https://github.com/ros-gbp/rqt_common_plugins-release.git"#tag=${_tag})
md5sums=('SKIP')

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/hydro/setup.bash ] && source /opt/ros/hydro/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/hydro \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}
