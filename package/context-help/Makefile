# $Id:  $

include $(TOPDIR)/rules.mk

PKG_NAME:=context-help
PKG_RELEASE:=1
PKG_VERSION:=1.1.8
PKG_SOURCE_URL:=http://sigrand.ru/temp/doc/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_CAT:=bzcat
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(TOPDIR)/package/rules.mk

$(eval $(call PKG_template,CONTEXT_HELP,context-help,$(PKG_VERSION)-$(PKG_RELEASE),$(ARCH)))

$(PKG_BUILD_DIR)/.configured:
	touch $@

$(PKG_BUILD_DIR)/.built:
	touch $@

$(IPKG_CONTEXT_HELP):
	install -d -m0755 $(IDIR_CONTEXT_HELP)/www/help
	install -d -m0755 $(IDIR_CONTEXT_HELP)/www/help/img
	install -m0755 $(PKG_BUILD_DIR)/*.html $(IDIR_CONTEXT_HELP)/www/help
	install -m0755 $(PKG_BUILD_DIR)/img/* $(IDIR_CONTEXT_HELP)/www/help/img
	echo "Depends: $(PKG_DEPEND)" >> $(IDIR_CONTEXT_HELP)/CONTROL/control
	$(IPKG_BUILD) $(IDIR_CONTEXT_HELP) $(PACKAGE_DIR)
