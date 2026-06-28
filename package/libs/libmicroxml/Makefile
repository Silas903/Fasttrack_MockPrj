# SPDX-License-Identifier: LGPL-2.1

include $(TOPDIR)/rules.mk

PKG_NAME:=libmicroxml
PKG_VERSION:=1.0
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/pivasoftware/microxml.git
PKG_SOURCE_VERSION:=80a15162f3a8318c70e8688d8ecbfc38676bd9a2
PKG_MIRROR_HASH:=3b064cd66259581a6a26c8c8e793d6061656f6d36c1dfd3b4794ed67e86707ab
PKG_MAINTAINER:=OpenWrt Build <openwrt@local>
PKG_LICENSE:=LGPL-2.1
PKG_LICENSE_FILES:=COPYING

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/autotools.mk

define Package/libmicroxml
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=microxml XML parser library
  URL:=https://github.com/pivasoftware/microxml
  ABI_VERSION:=1
endef

define Package/libmicroxml/description
 A small XML parser library used by EasyCwmp.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/microxml.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/libmicroxml.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/microxml.pc $(1)/usr/lib/pkgconfig/
endef

define Package/libmicroxml/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/libmicroxml.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libmicroxml))
