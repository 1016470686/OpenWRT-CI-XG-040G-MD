# SPDX-License-Identifier: Apache-2.0
#
# 文件型（预构建）包：内容原样取自网盘固件里的
#   luci-app-airoha-npu 1.2.1-r1  +  luci-i18n-airoha-npu-zh-cn 1.2.1
# 上游公开仓库 rchen14b/luci-app-airoha-npu 只到 1.0.1，且没有中文翻译，
# 所以这里把 1.2.1 的 4 个文件 + 中文 .lmo 直接打包，不做任何编译。
#
# 来源文件（网盘固件 immortalwrt-...-nokia_xg-040g-md-ubi...itb）：
#   /usr/libexec/rpcd/luci.airoha_npu
#   /usr/share/luci/menu.d/luci-app-airoha-npu.json
#   /usr/share/rpcd/acl.d/luci-app-airoha-npu.json
#   /www/luci-static/resources/view/airoha_npu/status.js
#   /usr/lib/lua/luci/i18n/luci-app-airoha-npu.zh-cn.lmo

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-airoha-npu
PKG_VERSION:=1.2.1
PKG_RELEASE:=1
PKG_LICENSE:=Apache-2.0
PKG_MAINTAINER:=Ryan Chen <rchen14b@gmail.com>
PKGARCH:=all

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-airoha-npu
  SECTION:=luci
  CATEGORY:=LuCI
  SUBMENU:=3. Applications
  TITLE:=LuCI Airoha SoC Status (NPU, CPU, Frame Engine)
  DEPENDS:=+luci-base
endef

define Package/luci-app-airoha-npu/install
	$(INSTALL_DIR) $(1)/usr/libexec/rpcd
	$(INSTALL_BIN) ./files/usr/libexec/rpcd/luci.airoha_npu $(1)/usr/libexec/rpcd/
	$(INSTALL_DIR) $(1)/usr/share/luci/menu.d
	$(INSTALL_DATA) ./files/usr/share/luci/menu.d/luci-app-airoha-npu.json $(1)/usr/share/luci/menu.d/
	$(INSTALL_DIR) $(1)/usr/share/rpcd/acl.d
	$(INSTALL_DATA) ./files/usr/share/rpcd/acl.d/luci-app-airoha-npu.json $(1)/usr/share/rpcd/acl.d/
	$(INSTALL_DIR) $(1)/www/luci-static/resources/view/airoha_npu
	$(INSTALL_DATA) ./files/www/luci-static/resources/view/airoha_npu/status.js $(1)/www/luci-static/resources/view/airoha_npu/
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/i18n
	$(INSTALL_DATA) ./files/usr/lib/lua/luci/i18n/luci-app-airoha-npu.zh-cn.lmo $(1)/usr/lib/lua/luci/i18n/
endef

# 纯文件包，没有下载与编译步骤
Build/Prepare = true
Build/Compile = true

$(eval $(call BuildPackage,luci-app-airoha-npu))
