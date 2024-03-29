include $(TOPDIR)/rules.mk

PKG_NAME:=pdns-recursor
PKG_VERSION:=4.9.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://downloads.powerdns.com/releases/
PKG_HASH:=d36f162843e367646a661a785ca0becde9b68552855bf40532aebafa103966f3

PKG_MAINTAINER:=Peter van Dijk <peter.van.dijk@powerdns.com>
PKG_LICENCE:=GPL-2.0-only
PKG_LICENCE_FILES:=COPYING
PKG_CPE_ID:=cpe:/a:powerdns:recursor

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/pdns-recursor
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=IP Addresses and Names
  USERID:=pdns:pdns
  TITLE:=PowerDNS Recursor
  DEPENDS:=+boost +boost-context +boost-filesystem +libatomic +liblua +libopenssl +libfstrm
  URL:=https://www.powerdns.com/recursor.html
endef

define Package/pdns-recursor/description
  High-performance resolving name server, utilizing multiple
  processor and including Lua scripting capabilities.
endef

define Package/pdns-recursor/conffiles
/etc/powerdns/pdns-recursor.conf
/etc/init.d/pdns-recursor
endef

# not everything groks --disable-nls
DISABLE_NLS:=

CONFIGURE_ARGS += \
	--sysconfdir=/etc/powerdns \
	--with-lua=lua \
	--without-libcap \
	--without-libsodium \
	--without-net-snmp \
	--enable-reproducible \
	--disable-silent-rules

define Package/pdns-recursor/install
	$(INSTALL_DIR) $(1)/etc/powerdns
	$(INSTALL_CONF) ./files/recursor.conf-dist $(1)/etc/powerdns/
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/pdns-recursor.init $(1)/etc/init.d/pdns-recursor
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/rec_control $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/pdns_recursor $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,pdns-recursor))
