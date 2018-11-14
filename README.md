# PHPoole component theme: Service Worker

> This theme should help to implement a [service worker](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers#what_is_a_service_worker) to run a [PHPoole](https://phpoole.org) static website as a [Progressive Web App](https://developers.google.com/web/progressive-web-apps/).

## Prerequisites
* A [PHPoole](https://phpoole.org) website
* A [supported browser](https://developer.microsoft.com/en-us/microsoft-edge/platform/status/serviceworker/)
* HTTPS

## Installation

```bash
composer require phpoole/theme-serviceworker
```

## Usage

1. Add theme in your `phpoole.yml`:  
```yaml
theme:
  - serviceworker
```
2. Add `<link>` to manifest in head:  
```html
<link rel="manifest" href="{{ url('manifest.webmanifest') }}">
```
4. [Register the service worker](/layouts/includes/regsw.js.twig) in the main template file:  
`{% if site.serviceworker is defined and site.serviceworker.enabled %}
{% include 'includes/regsw.js.twig' %}
{% endif %}`
5. Enable the service worker and define pre-cached files list in config file:  
```yaml
site:
    serviceworker:
       enabled: true
       precache:
           - img/icon.png
           - css/style.css
```
