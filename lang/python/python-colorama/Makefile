include $(TOPDIR)/rules.mk

PKG_NAME:=colorama
PKG_VERSION:=0.4.6
PKG_RELEASE:=1

PYPI_NAME:=$(PKG_NAME)
PKG_HASH:=08695f5cb7ed6e0531a20572697297273c47b8cae5a63ffc6d6ed5c201be6e44

PKG_MAINTAINER:=Daniel Danzberger <daniel@dd-wrt.com>
PKG_LICENSE:=MIT

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-colorama
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=colorama
  URL:=https://github.com/tartley/colorama
  DEPENDS:=+python3
endef

define Package/python3-colorama/description
Makes ANSI escape character sequences
(for producing colored terminal text and cursor positioning) work under MS Windows.
endef

$(eval $(call Py3Package,python3-colorama))
$(eval $(call BuildPackage,python3-colorama))
$(eval $(call BuildPackage,python3-colorama-src))
