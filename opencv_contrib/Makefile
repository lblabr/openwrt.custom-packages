#Copyright (C) 2013-2014 wrtnode.com
# Copyright (C) 2015-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

PKG_NAME:=opencv_contrib
PKG_VERSION:=4.9.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/opencv/opencv_contrib
PKG_SOURCE_VERSION:=c7602a8f74205e44389bd6a4e8d727d32e7e27b4

PKG_MAINTAINER:=
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE

DEBUG:=all
CMAKE_INSTALL:=0
#CMAKE_BINARY_SUBDIR:=build

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/package.mk
#include $(INCLUDE_DIR)/cmake.mk
#include $(INCLUDE_DIR)/download.mk

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
  DEPENDS:=
endef

#PKG_HOST_ONLY:=1
PKG_INSTALL:=0

#define Build/Prepare
#	echo "Build/Prepare"
#	$(call Build/Prepare/Default)
#endef

#define Build/Compile
#	echo "Download"
#	$(call Download,opencv_contrib)
#	$(call Build/Prepare/Default)
#	$(call Download,opencv_contrib)
#	$(call Build/DefaultTargets)
#	echo "compile"
#	$(call Build/Compile/Default)
#endef

#clean:
#	echo "Build/Prepare/Default"
#	$(eval $(call Build/Prepare/Default))
#	$(eval $(call Build/Prepare,opencv_contrib))
#	echo "Package/Default"
##	$(eval $(call Package/Default))
#	echo "Download/Default"
#	$(eval $(call Download/default))
#	$(eval $(call Download,opencv_contrib))
#	
#	$(eval $(call Package/opencv_contrib))
#	echo "test"
#	$(call Build/Compile/Default)
#	$(call BuildPackage1,opencv_contrib)
#	$(eval $(call BuildPackage,opencv_contrib))
#	echo "Build/Target"
#	$(eval $(call Build/Target,opencv_contrib))

define Build/DefaultTargets1
  $(if $(PKG_SKIP_DOWNLOAD),,$(if $(strip $(PKG_SOURCE_URL)),$(call Download,default)))
#  $(if $(DUMP),,$(Build/CoreTargets))

  define Build/DefaultTargets1
  endef
endef

define BuildPackage1
  $(eval $(Package/Default))
  $(eval $(Package/$(1)))
  $(echo "asdasd")
#  BUILD_PACKAGES += $(1)
#  $(STAMP_PREPARED): $$(if $(QUILT)$(DUMP),,$(call find_library_dependencies,$(1)))

#  $(foreach FIELD, TITLE CATEGORY SECTION VERSION,
#    ifeq ($($(FIELD)),)
#      $$(error Package/$(1) is missing the $(FIELD) field)
#    endif
#  )

#  $(if $(DUMP), \
#    $(if $(CHECK),,$(Dumpinfo/Package)), \
#    $(foreach target, \
#      $(if $(Package/$(1)/targets),$(Package/$(1)/targets), \
#        $(if $(PKG_TARGETS),$(PKG_TARGETS), ipkg) \
#      ), $(BuildTarget/$(target)) \
#    ) \
#  )

  $(if $(PKG_HOST_ONLY),,$(call Build/DefaultTargets1,$(1)))
endef

test:
#	echo "Build/Prepare/Default"
#	$(eval $(call Build/Prepare/Default))
#	$(eval $(call Build/Prepare,opencv_contrib))
#	echo "Package/Default"
##	$(eval $(call Package/Default))
#	echo "Download/Default"
#	$(eval $(call Download/default))
#	$(eval $(call Download,opencv_contrib))
#	
#	$(eval $(call Package/opencv_contrib))
#	echo "test"
#	$(call Build/Compile/Default)
#	$(call BuildPackage1,opencv_contrib)
  $(eval $(call BuildPackage1,opencv_contrib))
#	echo "Build/Target"
#	$(eval $(call Build/Target,opencv_contrib))

#$(eval $(call Build/DefaultTargets,opencv_contrib))
$(eval $(call BuildPackage1,opencv_contrib))
