#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=mcp251x
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define KernelPackage/mcp251x
  SUBMENU:=CAN Support
  TITLE:=MCP251x devices
  DEPENDS:=+kmod-can
  FILES:=$(LINUX_DIR)/drivers/net/can/spi/mcp251x.ko
  KCONFIG:=CONFIG_MCP251X=m
endef

define KernelPackage/mcp251x/description
  The MCP 251X SPI CAN controller driver
endef

MAKE_OPTS:= \
    ARCH="$(LINUX_KARCH)" \
    CROSS_COMPILE="$(TARGET_CROSS)" \
    SUBDIRS="$(PKG_BUILD_DIR)" \
    EXTRA_CFLAGS="$(EXTRA_CFLAGS)" \
    $(EXTRA_KCONFIG)

$(eval $(call KernelPackage,mcp251x))