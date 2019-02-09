#
# Copyright (C) 2019 Jeffery To
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=golang-package-test
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/jefferyto/openwrt-golang-package-test-code.git
PKG_SOURCE_VERSION:=9b88a3f52b9837783a354e7305de0b1d11742fa6
PKG_SOURCE_DATE:=20190209
PKG_MIRROR_HASH:=

PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Jeffery To <jeffery.to@gmail.com>

PKG_BUILD_DEPENDS:=golang/host
PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0

GO_PKG:=github.com/jefferyto/openwrt-golang-package-test-code
GO_PKG_INSTALL_EXTRA:=extra_file extra_dir
GO_PKG_EXCLUDES:=excluded

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/golang/golang-package.mk

define Package/golang-package-test/Default
  TITLE:=Package for testing Go software packaging in OpenWrt
  URL:=https://github.com/jefferyto/openwrt-golang-package-test-code
  DEPENDS:=$(GO_ARCH_DEPENDS)
endef

define Package/golang-package-test
$(call Package/golang-package-test/Default)
$(call GoPackage/GoSubMenu)
endef

define Package/golang-github-jefferyto-openwrt-golang-package-test-code-dev
$(call Package/golang-package-test/Default)
$(call GoPackage/GoSubMenu)
  TITLE+= (source files)
  PKGARCH:=all
endef

define Package/golang-package-test/Default/description
This package is for testing Go software packaging in OpenWrt. It does
nothing useful.
endef

define Package/golang-package-test/description
$(call Package/golang-package-test/Default/description)

This package contains the binaries.
endef

define Package/golang-github-jefferyto-openwrt-golang-package-test-code-dev/description
$(call Package/golang-package-test/Default/description)

This package provides the source files.
endef

$(eval $(call GoBinPackage,golang-package-test))
$(eval $(call BuildPackage,golang-package-test))

$(eval $(call GoSrcPackage,golang-github-jefferyto-openwrt-golang-package-test-code-dev))
$(eval $(call BuildPackage,golang-github-jefferyto-openwrt-golang-package-test-code-dev))
