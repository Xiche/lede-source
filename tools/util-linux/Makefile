#
# Copyright (C) 2007-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=util-linux
PKG_VERSION:=2.28
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@KERNEL/linux/utils/$(PKG_NAME)/v2.28
PKG_HASH:=395847e2a18a2c317170f238892751e73a57104565344f8644090c8b091014bb

HOST_BUILD_PARALLEL:=0

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/host-build.mk

HOST_CONFIGURE_ARGS += \
	--disable-all-programs \
	--enable-libblkid	\
	--enable-libuuid	\
	--disable-bash-completion 	\
	--disable-nls	 	\
	--disable-rpath 	\
	--without-ncurses	\
	--without-python	\
	--without-readline	\
	--without-systemd	\
	--without-udev

HOST_CFLAGS += $(FPIC) -std=gnu99

define Host/Clean
	rm -rf $(STAGING_DIR_HOST)/include/blkid
	rm -f $(STAGING_DIR_HOST)/lib/libblkid.*
	rm -f $(STAGING_DIR_HOST)/lib/pkgconfig/blkid.pc
	rm -rf $(STAGING_DIR_HOST)/include/uuid
	rm -f $(STAGING_DIR_HOST)/lib/libuuid.*
	rm -f $(STAGING_DIR_HOST)/lib/pkgconfig/uuid.pc
endef

$(eval $(call HostBuild))
