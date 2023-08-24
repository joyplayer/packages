include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=python-libmodbus
PKG_VERSION:=0.6.2
PKG_RELEASE:=2

PKG_LICENSE:=BSD-3-Clause
PKG_MAINTAINER:=Daniel Golle <daniel@makrotopia.org>

PYPI_NAME:=pylibmodbus
PKG_HASH:=7989af81f57cc7593c86b2d74201978e931bc80f6bbe62564273477fc7059c20

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-libmodbus
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=pylibmodbus
  URL:=https://pypi.org/project/pylibmodbus
  DEPENDS:=+libmodbus \
     +python3-light \
     +python3-cffi
endef

define Package/python3-libmodbus/description
	Python Interface for libmodbus written with CFFI.
endef

$(eval $(call Py3Package,python3-libmodbus))
$(eval $(call BuildPackage,python3-libmodbus))
