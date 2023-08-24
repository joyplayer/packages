include $(TOPDIR)/rules.mk

PKG_NAME:=botocore
PKG_VERSION:=1.31.7
PKG_RELEASE:=1

PYPI_NAME:=botocore
PKG_HASH:=f4473f66c153c262b8262404d737f4249366daf00fb068b495577a24b830ebcb

PKG_MAINTAINER:=Daniel Danzberger <daniel@dd-wrt.com>
PKG_LICENSE:=MIT

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-botocore
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=botocore
  URL:=https://github.com/boto/botocore
  DEPENDS:=+python3 \
	+python3-urllib3 \
	+python3-docutils \
	+python3-dateutil \
	+python3-jmespath \
	+python3-requests
endef

define Package/python3-botocore/description
A low-level interface to a growing number of Amazon Web Services.
The botocore package is the foundation for the AWS CLI as well as boto3.
endef

$(eval $(call Py3Package,python3-botocore))
$(eval $(call BuildPackage,python3-botocore))
$(eval $(call BuildPackage,python3-botocore-src))
