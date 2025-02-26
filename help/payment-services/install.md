---
title: Install [!DNL Payment Services]
description: Install the Payments Services extension.
exl-id: babaa91a-9376-4acb-b934-a89f9df52016
---
# Install [!DNL Payment Services]

Downloading and installing the [!DNL Payment Services] extension for [!DNL Adobe Commerce] and [!DNL Magento Open Source] is a prerequisite step for using [!DNL Payment Services].

![[!DNL Payment Services] extension Admin view](assets/admin-view.png)

## Download the extension

You must first download the extension from [Commerce Marketplace](https://experienceleague.adobe.com/docs/commerce-admin/start/resources/commerce-marketplace.html) before installing it.

1. Navigate to the [Payment Services extension in the Commerce Marketplace](https://marketplace.magento.com/magento-payment-services.html).
1. To choose the edition and version, toggle **[!UICONTROL Edition]** and **[!UICONTROL Your store version]** to your preferred selections.
1. Click **[!UICONTROL Add to Cart]**.
1. Complete checkout and click **[!UICONTROL Place Order]**.
1. Check the email associated with your Marketplace download for order confirmation and details.

## Install the extension

You can install the [!DNL Payment Services] extension for both [!DNL Adobe Commerce] on cloud infrastructure and on-premises instances, which are linked to the Magento ID ([mageid](https://devdocs.magento.com/marketplace/sellers/profile-personal.html#field-descriptions)) provided in the signup process, with Composer keys. [!DNL Magento] Open Source customers use the on-premises instructions.

Composer uses these keys during the initial installation of [!DNL Adobe Commerce], or in situations in which the Composer keys were not previously saved to the `auth.json` file.

See [Get your authentication keys](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html) for more information about obtaining Composer keys.

See [Install an extension](https://devdocs.magento.com/guides/v2.4/install-gde/install/cli/extensions.html) for more information about what to consider before downloading and installing an extension.

### [!DNL Adobe Commerce] on cloud infrastructure

This method is used for installing the [!DNL Payment Services] extension for a Commerce Cloud instance.

1. Update your `composer.json` file:

   ```bash
   composer require magento/payment-services --no-update
   ```

1. Update dependencies and install the extension:

   ```bash
   composer update
   ```

   The `composer update` command updates all dependencies. If you do not want to update all dependencies at the same time, use this command instead: `composer require magento/payment-services`.

1. Commit and push your changes.

### On-premises and other configurations

This method is used for installing the [!DNL Payment Services] extension for an on-premises instance and [!DNL Magento] Open Source customers.

1. To obtain the extension, run these commands:

   ```bash
   composer require magento/payment-services --no-update
   ```

1. Update dependencies and install the extension:

   ```bash
   composer update
   ```

   The `composer update` command updates all dependencies. If you do not want to update all dependencies at the same time, use this command instead: `composer require magento/payment-services`.

1. Upgrade your instance:

   ```bash
   bin/magento setup:upgrade
   ```

1. Clear the cache:

   ```bash
   bin/magento cache:clean
   ```

1. Commit changes.
1. To ensure that the committed code is deployed, update your instance .

## Upgrade the extension

When a new version of [!DNL Payment Services] is released, you can easily upgrade your extension.

1. To obtain the most recent version of the package:

   ```bash
   composer update
   ```

   The `composer update` command updates all dependencies. If you do not want to update all dependencies at the same time, use this command instead: `composer update magento/payment-services`.

1. Commit and push your changes.

## Troubleshooting

You may see errors when attempting to install the [!DNL Payment Services] extension. Use the following troubleshooting methods to resolve the errors.

### Incorrect Composer keys

If you see the following error denoting that you have the incorrect Composer keys:

```terminal
Could not find a matching version of package magento/payment-services. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (stable).
```

Verify that your Composer keys are linked to the Magento ID used during [!DNL Payment Services] registration.

To see which Composer keys are configured:

1. Find the location of the `auth.json` file:

   ```bash
   composer config --global home
   ```

1. View the `auth.json` file:

   ```bash
   cat /path/to/auth.json
   ```

1. See [which keys are associated with your Magento ID](https://devdocs.magento.com/guides/v2.4/install-gde/prereq/connect-auth.html).

### Not enough memory for PHP

If you see the following error denoting you do not have enough memory for PHP:

```terminal
Fatal error: Allowed memory size of 2146435072 bytes exhausted (tried to allocate 4096 bytes) in phar:///usr/local/bin/composer/src/Composer/DependencyResolver/RuleWatchGraph.php on line 52
```

[Increase the memory limit](https://devdocs.magento.com/cloud/project/magento-app-php-ini.html#increase-php-memory-limit) for PHP on your environment in `php.ini`.

Alternatively, you can specify the memory limit using this command: `php -d memory_limit=-1 [path to composer]/composer require magento/payment-services`.

For example:

```bash
php -d memory_limit=-1 vendor/bin/composer require magento/payment-services
```
