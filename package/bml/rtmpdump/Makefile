include $(TOPDIR)/rules.mk

PKG_NAME:=rtmpdump
PKG_VERSION:=0.2.6
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://git.ffmpeg.org/rtmpdump.git
PKG_SOURCE_VERSION:=138fdb258d9fc26f1843fd1b891180416c9dc575

XCFLAGS += $(FPIC)

include $(INCLUDE_DIR)/package.mk
#include $(INCLUDE_DIR)/cmake.mk

define Package/rtmpdump
	SECTION:=multimedia
	CATEGORY:=bml
	TITLE:=rtmpdump
	URL:=https://git.ffmpeg.org/rtmpdump.git
	DEPENDS:=+libopenssl +librtmp +zlib
	MAINTAINER:=Ballmanufaktur Leipuig<contact@emqx.io>
endef

define Package/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./* $(PKG_BUILD_DIR)/
endef

define Package/rtmpdump/decription
    rtmpdumps
endef

define Package/rtmpdump/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/rtmpdump $(1)/usr/bin
endef

$(eval $(call BuildPackage,rtmpdump))
