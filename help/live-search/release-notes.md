---
title: "[!DNL Live Search] Release Notes"
description: "The latest release information for [!DNL Live Search] from Adobe Commerce."
exl-id: 2a581e43-35f5-48ce-9752-844430ccdebf
---
# [!DNL Live Search] Release Notes

These release notes describe the latest versions of [!DNL Live Search] and include:

* ![New](../assets/new.svg) - New features
* ![Fix](../assets/fix.svg) - Fixes and improvements
* ![Bug](../assets/bug.svg) - Known issues

## [!DNL Live Search] 2.0.3

* Compatible with Adobe Commerce (EE): 2.4.x
* Compatible with Adobe Commerce for Cloud (ECE): 2.4.x
* Stability: Stable

* ![New](../assets/new.svg) - Live Search now supports B2B features by honoring category permissions, shared catalogs, and customer group-specific pricing.

Merchants must upgrade the Live Search extension version >= 2.0.3 to access these features.

We advise users to upgrade and test before pushing to production. Consider upgrading the production environment during off-peak hours after verifying their testing environment results.

>[!NOTE]
>
>B2B support will be added in a phased manner starting August 9th on the backend services, with an expected migration to be completed by the end of August. If the Live Search extension is not upgraded, your storefront will continue to work normally but without B2B features.

### Known Limitations / Bugs:

* ![Bug](../assets/bug.svg) - Suggestions are sourced from products not displayable to the customer group.
* ![Bug](../assets/bug.svg) - Products are not displayed if not added to the "Default shared catalog".
* B2B with Live Search for PWA Studio will not be available until PWA Studio adds support for it.
* Product overrides and product attributes feed may have sync issues requiring admins to run `bin/magento indexer:reset` and `bin/magento indexer:reindex` to re-sync correctly.

## [!DNL Live Search] 2.0

* Compatible with Adobe Commerce (EE): 2.4.x
* Compatible with Adobe Commerce for Cloud (ECE): 2.4.x
* Stability: Stable

Existing [!DNL Live Search] installations must be upgraded to [!DNL Live Search] 2.0.0 to take advantage of the following new features, fixes, and improvements:

* ![New](../assets/new.svg) - [!DNL Live Search] now supports PHP 8.1 for installations running Adobe Commerce 2.4.4.
* ![New](../assets/new.svg) - The `Magento_ElasticsearchCatalogPermissionsGraphQl` module is added to the list of modules that are disabled during the installation.
* ![New](../assets/new.svg) - The number of available lines in the [[!DNL storefront popover]](quick-tour.md) can be configured from the *Admin*.
* ![New](../assets/new.svg) - Beta [PWA](https://developer.adobe.com/commerce/pwa-studio/) compatibility for [!DNL Live Search].
* ![New](../assets/new.svg) - The [!DNL Live Search] installation process is updated with advanced process changes.
* ![Fix](../assets/fix.svg) - [Advanced Search](https://docs.magento.com/user-guide/catalog/search-advanced.html) link removed from the storefront footer.
* ![Bug](../assets/bug.svg) - The following product attributes are not supported by [Magento GraphQL API](https://devdocs.magento.com/guides/v2.4/graphql) when used in relation to the beta release of PWA: `description`, `name`, `short_description`
* ![Bug](../assets/bug.svg) - The beta release of PWA for [!DNL Live Search] does not support [event handling](https://devdocs.magento.com/shared-services/storefront-events-sdk.html).

## [!DNL Live Search] 1.3.1

* Compatible with Adobe Commerce (EE): 2.4.x
* Compatible with Adobe Commerce for Cloud (ECE): 2.4.x
* Stability: Stable

* ![Fix](../assets/fix.svg) - [Custom price attribute](https://docs.magento.com/user-guide/stores/attributes-input-types.html) no longer returns an error when configured as a [facet]({% link live-search/facets-add.md %}).
* ![Fix](../assets/fix.svg) - Fixed issue that caused an error to occur when no [currency symbol](https://docs.magento.com/user-guide/stores/currency-symbols.html) (`data-currency-symbol`) is available.
* ![Fix](../assets/fix.svg) - [[!DNL Storefront popover]](storefront-popover.md) now shows the [Special Price](https://docs.magento.com/user-guide/catalog/product-price-special.html) (minimum final price) when available.

## [!DNL Live Search] 1.3.0

* Compatible with Adobe Commerce (EE): 2.4.x
* Compatible with Adobe Commerce for Cloud (ECE): 2.4.x
* Stability: Stable

* ![New](../assets/new.svg) - [Performance](performance.md) reporting dashboard provides insight into search terms that shoppers use.
* ![New](../assets/new.svg) - [!DNL Live Search] [Storefront Events SDK](https://devdocs.magento.com/shared-services/storefront-events-sdk.html) provides access to a common data layer with event publishing and subscription services, and metrics.
* ![Fix](../assets/fix.svg) - The [[!DNL Storefront Popover]](https://devdocs.magento.com/live-search/storefront-popover.html) has a new `active` class for the `.search-autocomplete` container that controls visibility.
* ![Fix](../assets/fix.svg) - In the storefront, the [Search Terms](https://docs.magento.com/user-guide/marketing/search-terms-popular.html) footer link is removed and its cache disabled for [!DNL Live Search] installations.
* ![Bug](../assets/bug.svg) - Patch for Search adapter handles duplicate products.
* ![Bug](../assets/bug.svg) - [!DNL Live Search] supports [single-source](https://docs.magento.com/user-guide/catalog/inventory-sources.html) (physical) inventory locations with multiple (virtual) [stocks](https://docs.magento.com/user-guide/catalog/inventory-stock.html). Multiple inventory sources are not supported at this time.

## [!DNL Live Search] 1.2.0

* Compatible with Adobe Commerce (EE): 2.4.x
* Compatible with Adobe Commerce for Cloud (ECE): 2.4.x
* Stability: Stable

* ![New](../assets/new.svg) - [[!DNL Storefront popover]](storefront-popover.md) displays suggested products and thumbnail images of top search results as shoppers type queries into the Search box.
* ![New](../assets/new.svg) - Commerce *Admin* session stays open during extended periods of keyboard inactivity
* ![New](../assets/new.svg) - [!DNL Live Search] is automatically enabled after onboarding
* ![Fix](../assets/fix.svg) - Initial indexing time is less than an hour
* ![Fix](../assets/fix.svg) - Incremental product updates near real time (after install and setup)
* ![Fix](../assets/fix.svg) - Sortable columns in Synonym editor
* ![Fix](../assets/fix.svg) - [!DNL Live Search] no longer throws an error if search criteria contains empty sort order value
* ![Fix](../assets/fix.svg) - Range filtering no longer breaks if attribute codes contain strings "to" or "from"

## [!DNL Live Search] 1.1.0

* Compatible with Adobe Commerce (EE): 2.4.x
* Compatible with Adobe Commerce for Cloud (ECE): 2.4.x
* Stability: Stable

* ![Bug](../assets/bug.svg) - The [!DNL Live Search] service supports only the [base currency](https://docs.magento.com/user-guide/stores/currency-configuration.html) of the Adobe Commerce installation.
* ![Bug](../assets/bug.svg) - When adding a facet, the Product Attributes Feed does not update correctly when set to `Update on Save`. To avoid this problem, go to [Index Management](https://docs.magento.com/user-guide/system/index-management.html) and set Product Attributes Feed to `Update by Schedule`.
* ![Bug](../assets/bug.svg) - [!DNL Live Search] synonyms are defined per store view, but are currently stored per website and identified with a combination of `environmentId` + `storeViewCode`. As a result, all websites and store views within the Adobe Commerce installation share the same set of synonyms. The most recently created set of synonyms for the store view takes precedence.
* ![Bug](../assets/bug.svg) - If a synonym term contains multiple words, each word is treated as a separate synonym. For example, if you define “time piece” as a synonym of “watch”, both “time” and “piece” are treated as synonyms of watch.

## Documentation

To learn more:

* [Adobe Commerce Developer Documentation](https://devdocs.magento.com/)
* [Adobe Commerce User Guide](https://docs.magento.com/user-guide/)
* [[!DNL Live Search] on Marketplace](https://marketplace.magento.com/magento-live-search.html)
