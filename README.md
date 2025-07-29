# Shopware Fastly-Meta

A Composer meta package that streamlines the integration of [Fastly](https://www.fastly.com/) as the CDN layer for Shopware. It automates the deployment and management of Fastly VCL (Varnish Configuration Language) snippets and ensures best-practice Shopware CDN cache handling in scalable, modern shop setups.

- **Performance:** Fastly caches HTTP responses at edge locations closest to your customers, reducing latency and load on your servers.
- **Resource Savings:** Cache hits at the edge reduce backend requests and lower cloud infrastructure demands.
- **Modern Caching:** Fastly replaces local Redis cache use for HTTP caching, resulting in more scalable and reliable storefront performance.

This is not an official [Fastly](https://www.fastly.com/) project but a Shopware-specific implementation.

## Install

```bash
composer require shopware/fastly-meta
```

## Setup

1. **Set required environment variables:**
   - `FASTLY_API_KEY` — Your Fastly API key
   - `FASTLY_SERVICE_ID` — The Fastly Service ID

2. **Integrate with your deployment process:**
   - If using [Shopware Deployment Helper](https://developer.shopware.com/docs/guides/hosting/installation-updates/deployments/deployment-helper.html), the Fastly meta package will enable auto-deployment of Fastly VCL snippets.

3. **Enable Fastly for your Shopware project:**
   - Push your updated code and configuration containing the meta package and Fastly env variables to your environment.
   - Fastly CDN will be integrated for HTTP caching.

## Usage

Once set up, VCL snippets are managed automatically during your deployment process. You can manage Fastly snippets manually with [Deployment Helper CLI commands](https://developer.shopware.com/docs/guides/hosting/installation-updates/deployments/deployment-helper.html):

```bash
# List deployed VCL snippets
./vendor/bin/shopware-deployment-helper fastly:snippet:list

# Remove a VCL snippet by name
./vendor/bin/shopware-deployment-helper fastly:snippet:remove 
```

## Related Documentation

More info is available at [Shopware Fastly Integration Guide](https://developer.shopware.com/docs/products/paas/shopware-paas/fastly.html), [Shopware Deployment Helper](https://developer.shopware.com/docs/guides/hosting/installation-updates/deployments/deployment-helper.html), and [Shopware PaaS Fastly Setup](https://developer.shopware.com/docs/products/paas/shopware-paas/fastly.html).