#
# Copyright (C) 2008-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=micropython-lib
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/micropython/micropython-lib.git
PKG_SOURCE_VERSION:=7128d423c2e7c0309ac17a1e6ba873b909b24fcc
PKG_SOURCE_DATE:=20230522
PKG_MIRROR_HASH:=1f094aac257d2094ee91b457164f845f6461df1cf1d0ed7ee556c98f273f5afb

PKG_MAINTAINER:=Jeffery To <jeffery.to@gmail.com>
PKG_LICENSE:=MIT PSF-2.0
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/micropython-lib
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=micropython-lib
  URL:=https://github.com/micropython/micropython-lib
  DEPENDS:=+micropython
endef

define Package/micropython-lib/description
  This is a repository of libraries designed to be useful for writing
  MicroPython applications.
endef

Build/Compile:=:

define Package/micropython-lib/install
	for dir in micropython python-ecosys python-stdlib unix-ffi; do \
		$(INSTALL_DIR) $(1)/usr/lib/micropython/$$$$dir ; \
		$(CP) $(PKG_BUILD_DIR)/$$$$dir/* $(1)/usr/lib/micropython/$$$$dir/ ; \
	done
	$(FIND) $(1)/usr/lib/micropython \
		-not -type d \( -not -name '*.py' -o -name 'test_*' -o -name 'setup.py' \) -delete
	$(FIND) $(1)/usr/lib/micropython -mindepth 1 -empty -type d -delete
endef

$(eval $(call BuildPackage,micropython-lib))
