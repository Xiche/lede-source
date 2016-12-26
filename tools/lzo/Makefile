#
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lzo
PKG_VERSION:=2.09
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.oberhumer.com/opensource/lzo/download/
PKG_HASH:=f294a7ced313063c057c504257f437c8335c41bfeed23531ee4e6a2b87bcb34c

HOST_FIXUP:=autoreconf

HOST_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/host-build.mk

define Host/Configure
	$(call Host/Configure/Default, \
		--enable-shared \
		--enable-static \
	)
endef

define Host/Clean
	rm -rf $(STAGING_DIR_HOST)/include/lzo
	rm -f $(STAGING_DIR_HOST)/lib/liblzo2.*
	rm -rf $(STAGING_DIR_HOST)/share/doc/lzo
endef

$(eval $(call HostBuild))
