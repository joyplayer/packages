#
# Copyright (C) 2019-2O21 CZ.NIC, z. s. p. o. (https://www.nic.cz/)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-markdown
PKG_VERSION:=3.4.4
PKG_RELEASE:=1

PYPI_NAME:=Markdown
PKG_HASH:=225c6123522495d4119a90b3a3ba31a1e87a70369e03f14799ea9c0d7183a3d6

PKG_MAINTAINER:=Josef Schlehofer <josef.schlehofer@nic.cz>
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE.md

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-markdown
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Markdown implementation in Python
  URL:=https://python-markdown.github.io/
  DEPENDS:= \
	+python3-light \
	+python3-logging
endef

define Package/python3-markdown/description
  A fast and complete Python implementation of Markdown.
endef

$(eval $(call Py3Package,python3-markdown))
$(eval $(call BuildPackage,python3-markdown))
$(eval $(call BuildPackage,python3-markdown-src))
