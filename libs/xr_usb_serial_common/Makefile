include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=usb-serial-xr_usb_serial_common
PKG_SOURCE_DATE:=2023-03-21
PKG_SOURCE_VERSION:=90ad530166f096347a5a57b6f9eb21c422a40fd9
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/kasbert/epsolar-tracer
PKG_MIRROR_HASH:=0cea56120542d3d546028d17389a3419ca930448005a9208728c40583ccf027d

PKG_MAINTAINER:=Daniel Golle <daniel@makrotopia.org>
PKG_LICENSE:=GPL-2.0-or-later
PKG_LICENSE_FILES:=LICENSE
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define KernelPackage/usb-serial-xr_usb_serial_common
	SECTION:=kernel
	CATEGORY:=Kernel modules
	SUBMENU:=USB Support
	TITLE:=Support for Exar USB to RS-485/RS-422
	URL:=https://www.exar.com/content/document.ashx?id=21651
	FILES:=$(PKG_BUILD_DIR)/xr_usb_serial_common-1a/xr_usb_serial_common.$(LINUX_KMOD_SUFFIX)
	AUTOLOAD:=$(call AutoProbe,xr_usb_serial_common)
	DEPENDS+=kmod-usb-serial
endef

define Build/Compile
	+$(MAKE) $(PKG_JOBS) -C "$(LINUX_DIR)" \
		ARCH="$(LINUX_KARCH)" \
		CROSS_COMPILE="$(TARGET_CROSS)" \
		M="$(PKG_BUILD_DIR)/xr_usb_serial_common-1a" \
		modules
endef

$(eval $(call KernelPackage,usb-serial-xr_usb_serial_common))
