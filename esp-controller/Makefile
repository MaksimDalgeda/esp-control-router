include $(TOPDIR)/rules.mk

PKG_NAME:=esp-controller
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/MaksimDalgeda/ESP-microcontroller-control-via-UBUS.git
PKG_SOURCE_VERSION:=7ab24e9edcc2333bb358e3c53f9df6222379f192

PKG_MIRROR_HASH:=skip

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/esp-controller
	CATEGORY:=Base system
	TITLE:=ESP UBUS Controller
	DEPENDS:=+libubus +libubox +libblobmsg-json +libserialport
endef

define Package/esp-controller/description
	UBUS controller for ESP microcontrollers connected over serial
endef

define Build/Configure
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CC="$(TARGET_CC)" \
		AR="$(TARGET_AR)" \
		STAGING_DIR="$(STAGING_DIR)"
endef

define Package/esp-controller/install
	$(INSTALL_DIR) $(1)/usr/sbin

	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/build/esp-controller \
		$(1)/usr/sbin/esp-controller

	$(INSTALL_DIR) $(1)/etc/init.d

	$(INSTALL_BIN) ./files/etc/init.d/esp-controller \
		$(1)/etc/init.d/esp-controller
endef

$(eval $(call BuildPackage,esp-controller))