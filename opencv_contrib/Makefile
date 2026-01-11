#Copyright (C) 2013-2014 wrtnode.com
# Copyright (C) 2015-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=opencv_contrib
PKG_VERSION:=4.9.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/opencv/opencv_contrib
PKG_SOURCE_VERSION:=c7602a8f74205e44389bd6a4e8d727d32e7e27b4

PKG_MAINTAINER:=
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

#CMAKE_INSTALL:=1
CMAKE_BINARY_SUBDIR:=build
#PKG_BUILD_PARALLEL:=1
#PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/opencv_contrib/Default/description
 OpenCV (Open Source Computer Vision Library) is an open source computer
 vision and machine learning software library. OpenCV was built to provide
 a common infrastructure for computer vision applications and to accelerate
 the use of machine perception in the commercial products. Being a
 BSD-licensed product, OpenCV makes it easy for businesses to utilize
 and modify the code.
endef

define Package/opencv_contrib
  SECTION:=libs
  CATEGORY:=bml
  TITLE:=OpenCV contrib
  URL:=https://opencv.org/
  DEPENDS:=+libpthread +librt +libatomic +libstdcpp +zlib +libjpeg
endef

#PKG_INSTALL:=1

#CMAKE_OPTIONS += \
#	-DBUILD_opencv_gpu:BOOL=OFF \
#	-DWITH_1394:BOOL=OFF -DBUILD_opencv_stitching:BOOL=OFF \
#	-DBUILD_opencv_superres:BOOL=OFF -DBUILD_opencv_ts:BOOL=OFF \
#	-DBUILD_opencv_highgui:BOOL=OFF \
#	-DBUILD_opencv_videostab:BOOL=OFF \
#	-DWITH_FFMPEG:BOOL=OFF \
#	-DWITH_GSTREAMER:BOOL=ON \
#	-DWITH_LIBV4L:BOOL=OFF \
#	-DWITH_PNG:BOOL=OFF \
#	-DWITH_GTK:BOOL=OFF \
#	-DWITH_TIFF:BOOL=OFF \
#	-DCMAKE_VERBOSE:BOOL=OFF \
#	-DENABLE_PRECOMPILED_HEADERS=OFF \
#	-DOPENCV_GENERATE_PKGCONFIG=ON \

TARGET_LDFLAGS += -latomic

define Build/Compile
#	$(call Build/Prepare/Default)
endef

$(eval $(call BuildPackage,opencv_contrib))
