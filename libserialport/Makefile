include $(TOPDIR)/rules.mk

PKG_NAME:=libserialport
PKG_VERSION:=0.1.1
PKG_RELEASE:=1

PKG_SOURCE:=libserialport-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://sigrok.org/download/source/libserialport

PKG_HASH:=skip

PKG_LICENSE:=LGPL-3.0
PKG_LICENSE_FILES:=COPYING

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libserialport
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=Cross-platform serial port library
endef

define Package/libserialport/description
	Serial port access library
endef

CONFIGURE_ARGS += \
	--enable-shared \
	--enable-static

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libserialport.h $(1)/usr/include/

	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libserialport.so* $(1)/usr/lib/
endef

define Package/libserialport/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libserialport.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libserialport))