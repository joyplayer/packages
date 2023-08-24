#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=gnu-efi
PKG_VERSION:=3.0.17
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/vathpela/gnu-efi.git
PKG_SOURCE_DATE:=2023-06-11
PKG_SOURCE_VERSION:=64027ee9864d8a8685ae187eb91ddc519d18cedb
PKG_MIRROR_HASH:=738addbaba775ca1fc8d31a4bb2cbea1b8a0ac9aa888434f36264b2b0ce1dc5b
PKG_BUILD_PARALLEL:=1

PKG_MAINTAINER:=Oskari Rauta <oskari.rauta@gmail.com>
PKG_LICENSE_FILES:=README.efilib

include $(INCLUDE_DIR)/package.mk

define Package/gnu-efi
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=GNU's EFI library
  URL:=https://github.com/vathpela/gnu-efi
  HIDDEN:=1
  DEPENDS:=@TARGET_x86_64
endef

define Package/gnu-efi/description
  GNU's EFI library
endef

define Build/Install
	$(MAKE_VARS) \
	$(MAKE) -C $(PKG_BUILD_DIR)/$(MAKE_PATH) \
		$(MAKE_INSTALL_FLAGS) \
		INSTALLROOT=$(PKG_INSTALL_DIR) \
		install
endef

define Package/gnu-efi/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/local/lib/** $(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib $(1)/usr/include/efi
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/local/lib/** $(1)/usr/lib/
	cp -aR $(PKG_INSTALL_DIR)/usr/local/include/efi/** $(1)/usr/include/efi/
endef

$(eval $(call BuildPackage,gnu-efi))
