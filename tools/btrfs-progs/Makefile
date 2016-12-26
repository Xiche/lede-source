#
# Copyright (C) 2009-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=btrfs-progs
PKG_VERSION:=4.7.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-v$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@KERNEL/linux/kernel/people/kdave/btrfs-progs/
PKG_MD5SUM:=f49bc9e143ffe60260c5bd70ef3b624576673f8b50f41e309892a425f7fbe60f

HOST_BUILD_DIR:=$(BUILD_DIR_HOST)/$(PKG_NAME)-v$(PKG_VERSION)

HOST_BUILD_PARALLEL:=1

HOST_FIXUP:=autoreconf

include $(INCLUDE_DIR)/host-build.mk

HOST_CONFIGURE_ARGS += \
	--disable-backtrace \
	--disable-convert \
	--disable-documentation

define Host/Compile
	$(call Host/Compile/Default,mkfs.btrfs)
endef

define Host/Install
	$(INSTALL_BIN) $(HOST_BUILD_DIR)/mkfs.btrfs $(STAGING_DIR_HOST)/bin/mkfs.btrfs
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/bin/mkfs.btrfs
endef

$(eval $(call HostBuild))
