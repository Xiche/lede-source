#
# Copyright (C) 2006-2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=zlib
PKG_VERSION:=1.2.10
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=http://www.zlib.net @SF/libpng
PKG_HASH:=9612bf086047078ce3a1c154fc9052113fc1a2a97234a059da17a6299bd4dd32

include $(INCLUDE_DIR)/host-build.mk

define Host/Configure
	(cd $(HOST_BUILD_DIR); \
		./configure \
			--prefix=$(STAGING_DIR_HOST) \
			--shared \
			--uname=Linux \
	)
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/include/zlib.h
	rm -f $(STAGING_DIR_HOST)/lib/libz.*
	rm -f $(STAGING_DIR_HOST)/lib/pkgconfig/zlib.pc
	rm -f $(STAGING_DIR_HOST)/share/man/man3/zlib.3
endef

$(eval $(call HostBuild))
