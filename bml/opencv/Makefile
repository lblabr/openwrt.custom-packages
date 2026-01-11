#Copyright (C) 2013-2014 wrtnode.com
# Copyright (C) 2015-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=opencv
PKG_VERSION:=4.9.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/opencv/opencv
PKG_SOURCE_VERSION:=dad8af6b17f8e60d7b95a1203a1b4d22f56574cf

PKG_MAINTAINER:=
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

CMAKE_INSTALL:=1
CMAKE_BINARY_SUBDIR:=build
#PKG_BUILD_PARALLEL:=1
#PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/opencv/Default/description
 OpenCV (Open Source Computer Vision Library) is an open source computer
 vision and machine learning software library. OpenCV was built to provide
 a common infrastructure for computer vision applications and to accelerate
 the use of machine perception in the commercial products. Being a
 BSD-licensed product, OpenCV makes it easy for businesses to utilize
 and modify the code.
endef

define Package/opencv
  SECTION:=libs
  CATEGORY:=bml
  TITLE:=OpenCV
  URL:=https://opencv.org/
  DEPENDS:=+libpthread +librt +libatomic +libstdcpp +zlib +libjpeg +libfreetype +glib2 +harfbuzz +libwebp
endef

#PKG_INSTALL:=1

CMAKE_OPTIONS += \
	-DBUILD_opencv_gpu:BOOL=OFF \
	-DWITH_1394:BOOL=OFF -DBUILD_opencv_stitching:BOOL=OFF \
	-DBUILD_opencv_superres:BOOL=OFF -DBUILD_opencv_ts:BOOL=OFF \
	-DBUILD_opencv_highgui:BOOL=OFF \
	-DBUILD_opencv_videostab:BOOL=OFF \
	-DBUILD_opencv_dnn:BOOL=OFF \
	-DBUILD_opencv_bioinspired:BOOL=ON \
	-DBUILD_opencv_face:BOOL=ON \
	-DBUILD_opencv_flann:BOOL=ON \
	-DBUILD_opencv_ml:BOOL=OFF \
	-DBUILD_opencv_phaseunwrapping:BOOL=OFF \
	-DBUILD_opencv_rgbd:BOOL=ON \
	-DBUILD_opencv_stereo:BOOL=ON \
	-DBUILD_opencv_surface_matching:BOOL=ON \
	-DBUILD_opencv_ximgproc:BOOL=OFF \
	-DBUILD_opencv_xphoto:BOOL=OFF \
	-DBUILD_opencv_xobjdetect:BOOL=OFF \
	-DBUILD_opencv_xfeatures2d:BOOL=OFF \
	-DBUILD_opencv_gapi:BOOL=OFF \
	-DWITH_FFMPEG:BOOL=OFF \
	-DWITH_GSTREAMER:BOOL=OFF \
	-DWITH_LIBV4L:BOOL=OFF \
	-DWITH_PNG:BOOL=OFF \
	-DWITH_GTK:BOOL=OFF \
	-DWITH_TIFF:BOOL=OFF \
	-DCMAKE_VERBOSE:BOOL=OFF \
	-DENABLE_PRECOMPILED_HEADERS=OFF \
	-DOPENCV_GENERATE_PKGCONFIG=ON \
	-DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib-4.9.0/modules \

TARGET_LDFLAGS += -latomic

define Build/Compile
	$(call Build/Compile/Default)
#        make -C $(PKG_BUILD_DIR)/librtmp librtmp.pc
endef

define Build/InstallDev
	echo "installDev"
	echo "1: $(1)"
	echo "PKG_BUILD_DIR: $(PKG_BUILD_DIR)"
	echo "PKG_INSTALL_DIR: $(PKG_INSTALL_DIR)"
	echo "INSTALL_DIR: $(INSTALL_DIR)"
	echo "INSTALL_DATA: $(INSTALL_DATA)"
	echo "HOST_BUILD_DIR: $(HOST_BUILD_DIR)"
	echo "STAGING_DIR:$(STAGING_DIR)"
	echo "STAGING_DIR_HOST: $(STAGING_DIR_HOST)"
	echo "STAGING_DIR_HOSTPKG: $(STAGING_DIR_HOSTPKG)"
	echo "STAGING_DIR_TARGET: $(STAGING_DIR_TARGET)"
	echo "LIB_DIR: $(LIB_DIR)"
	echo "TARGET_DIR_NAME: $(TARGET_DIR_NAME)"
	echo "installDev"

	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig/
	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/
#	$(INSTALL_DIR) $(1)/usr/include/opencv2/
#	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
#	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/opencv2
#	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
#	$(CP) $(PKG_INSTALL_DIR)/usr/include/opencv/* $(1)/usr/include/

#	cp $(PKG_INSTALL_DIR)/pkgconfig/*.pc $(PKG_INSTALL_DIR)/usr/lib/pkgconfig
#	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/*.pc $(STAGING_DIR)/usr/lib/pkgconfig/

endef

define Package/opencv/install
	echo "install"
	echo "1: $(1)"
	echo "PKG_BUILD_DIR: $(PKG_BUILD_DIR)"
	echo "PKG_INFO_DIR: $(PKG_INFO_DIR)"
	echo "PKG_INSTALL_DIR: $(PKG_INSTALL_DIR)"
	echo "INSTALL_DIR: $(INSTALL_DIR)"
	echo "INSTALL_DATA: $(INSTALL_DATA)"
	echo "HOST_BUILD_DIR: $(HOST_BUILD_DIR)"
	echo "STAGING_DIR:$(STAGING_DIR)"
	echo "STAGING_DIR_HOST: $(STAGING_DIR_HOST)"
	echo "STAGING_DIR_HOSTPKG: $(STAGING_DIR_HOSTPKG)"
	echo "STAGING_DIR_TARGET: $(STAGING_DIR_TARGET)"
	echo "LIB_DIR: $(LIB_DIR)"
	echo "TARGET_DIR_NAME: $(TARGET_DIR_NAME)"
	echo "install"

#	$(INSTALL_DIR) $(1)/usr/lib
#	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include/opencv/
	
	$(INSTALL_DIR) $(PKG_BUILD_DIR)/opencv
	$(INSTALL_DIR) $(STAGING_DIR)/usr/include/opencv

#	$(CP) $(PKG_BUILD_DIR)/opencv/*.so* $(1)/usr/lib
#	$(CP) $(PKG_BUILD_DIR)/opencv/*.h $(1)/usr/include/opencv/
#	$(CP) $(PKG_BUILD_DIR)/opencv/*.h $(STAGING_DIR)/usr/include/

#	$(CP) $(1)/usr/lib/*.so* $(STAGING_DIR)/usr/lib
#	$(CP) $(1)/usr/lib/*.so* $(PKG_INSTALL_DIR)/usr/lib

#	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libopencv* $(1)/usr/lib/
#	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/*.pc $(STAGING_DIR)/usr/lib/pkgconfig/

	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig/
	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/
	$(INSTALL_DIR) $(1)/usr/include/opencv2/

	$(INSTALL_DIR) $(STAGING_DIR)/usr/share/opencv4/data

#	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
#	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/opencv2
#	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
#	$(CP) $(PKG_INSTALL_DIR)/usr/include/opencv/* $(1)/usr/include/

	$(CP) $(PKG_BUILD_DIR)/data/* $(STAGING_DIR)/usr/share/opencv4/data

	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*  $(1)/usr/lib
#	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include

	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*  $(STAGING_DIR)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(STAGING_DIR)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(STAGING_DIR)/usr/include/opencv2
#	$(CP) $(PKG_BUILD_DIR)/opencv/*.so* $(1)/usr/lib

	$(CP) $(PKG_INSTALL_DIR)/usr/include/opencv4/opencv2/* $(STAGING_DIR)/usr/include/opencv2

	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/*.pc $(STAGING_DIR)/usr/lib/pkgconfig/
endef

$(eval $(call BuildPackage,opencv,+libfreetype))
