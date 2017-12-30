#
# Copyright (C) 2006-2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=zlib
PKG_VERSION:=1.2.11
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@SF/libpng http://www.zlib.net
PKG_HASH:=4ff941449631ace0d4d203e3483be9dbc9da454084111f97ea0a2114e19bf066

include $(INCLUDE_DIR)/host-build.mk

HOST_CONFIGURE_ARGS := \
	--prefix=$(HOST_BUILD_PREFIX) \
	--shared \
	--uname=Linux

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/include/zlib.h
	rm -f $(STAGING_DIR_HOST)/lib/libz.*
	rm -f $(STAGING_DIR_HOST)/lib/pkgconfig/zlib.pc
	rm -f $(STAGING_DIR_HOST)/share/man/man3/zlib.3
endef

$(eval $(call HostBuild))
