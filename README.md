# Cecil component theme: Service Worker

> This theme should help to implement a [service worker](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers#what_is_a_service_worker) to run a [Cecil](https://cecil.app) static website as a [Progressive Web App](https://developers.google.com/web/progressive-web-apps/).

## Prerequisites
* A [Cecil](https://cecil.app) website
* A [supported browser](https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers#Compatibilit%C3%A9_des_navigateurs)
* HTTPS

## Installation

```bash
composer require cecil/theme-serviceworker
```

## Usage

1. Add theme in your `config.yml`:  
```yaml
theme:
  - serviceworker
```
2. Add `<link>` to manifest in head:  
```html
<link rel="manifest" href="{{ url('manifest') }}">
```
3. [Register the service worker](/layouts/parials/regsw.js.twig) in the main template file:  
```html
{% include 'partials/regsw.js.twig' %}
```
4. Enable the service worker and define pre-cached files list in config file:  
```yaml
serviceworker:
  enabled: true
  precache:
    - img/icon.png
    - css/style.css
```
