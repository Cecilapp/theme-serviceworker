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

1. Add `serviceworker` in the `themes` section of your `config.yml`:

```yaml
theme:
  - serviceworker
```

2. Add and configure the [web manifest](https://developer.mozilla.org/fr/docs/Web/Manifest):

**`<head>`:**
```twig
<link rel="manifest" href="{{ url('manifest') }}">
```

**`config.yml`:**

```yaml
manifest:
  background_color: '#FFFFFF'
  theme_color: '#202020'
  icons:
    - src: icon-512x512.png
      sizes: 512x512
      type: image/png
```

3. [Register the service worker](https://developers.google.com/web/fundamentals/primers/service-workers/registration#common_registration_boilerplate) in the main template file:  

```twig
{% include 'partials/regsw.js.twig' %}
```

4. Enable the service worker and define pre-cached files list in your `config.yml`:  

```yaml
serviceworker:
  enabled: true
  precache:
    - icon-512x512.png
    - css/style.css
```
