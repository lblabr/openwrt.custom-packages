include $(TOPDIR)/rules.mk

PKG_NAME:=librtmp
PKG_VERSION:=0.2.6
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://git.ffmpeg.org/rtmpdump.git
PKG_SOURCE_VERSION:=138fdb258d9fc26f1843fd1b891180416c9dc575

#PKG_BUILD_DIR:=librtmp

TARGET_CFLAGS += $(FPIC)
XCFLAGS += $(FPIC)

include $(INCLUDE_DIR)/package.mk
#include $(INCLUDE_DIR)/cmake.mk

define Package/librtmp
	SECTION:=multimedia
	CATEGORY:=bml
	TITLE:=librtmp
	URL:=https://git.ffmpeg.org/rtmpdump.git
	DEPENDS:=+libopenssl +zlib
	MAINTAINER:=Ballmanufaktur Leipuig<contact@emqx.io>
endef

#define Package/Prepare
#	mkdir -p $(PKG_BUILD_DIR)
#	$(CP) ./* $(PKG_BUILD_DIR)/
#endef

define Package/librtmp/decription
    librtmp
endef

#define Build/InstallDev
#	$(INSTALL_DIR) $(1)/usr/{lib/pkgconfig,include/librtmp-0.2.6/librtmp}
#
#	$(CP) \
#		$(PKG_INSTALL_DIR)/usr/lib/librtmp.so* \
#		$(1)/usr/lib/
#
#	$(INSTALL_DATA) \
#		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/* \
#		$(1)/usr/lib/pkgconfig/
#
#	$(INSTALL_DATA) \
#		$(PKG_INSTALL_DIR)/usr/include/librtmp-0.2.6/libsoup/*.h \
#		$(1)/usr/include/librtmp-0.2.6/librtmp/
#endef

#define Build/InstallDev
#	$(call Build/InstallDev/cmake,$(1))
#	$(SED) 's,/usr/include,$$$${prefix}/include,g' $(1)/usr/lib/pkgconfig/re2.pc
#	$(SED) 's,/usr/lib,$$$${exec_prefix}/lib,g' $(1)/usr/lib/pkgconfig/re2.pc
#endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig/
	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/
	$(INSTALL_DIR) $(1)/usr/include/librtmp/

	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/

	cp $(PKG_BUILD_DIR)/librtmp/librtmp.pc $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/librtmp.pc
	$(CP) $(PKG_BUILD_DIR)/librtmp/librtmp.pc $(1)/usr/lib/pkgconfig/
endef

define Build/Compile
	$(call Build/Compile/Default)
	make -C $(PKG_BUILD_DIR)/librtmp librtmp.pc
endef

define Package/librtmp/install
	echo "install"
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
	echo "install"

	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include/librtmp/
	$(INSTALL_DIR) $(STAGING_DIR)/usr/include/librtmp

	$(CP) $(PKG_BUILD_DIR)/librtmp/*.so* $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/librtmp/*.h $(1)/usr/include/librtmp/
	$(CP) $(PKG_BUILD_DIR)/librtmp/*.h $(STAGING_DIR)/usr/include/librtmp/

	$(CP) $(1)/usr/lib/*.so* $(STAGING_DIR)/usr/lib
	$(CP) $(1)/usr/lib/*.so* $(PKG_INSTALL_DIR)/usr/lib
endef

$(eval $(call BuildPackage,librtmp))
