---
title: "Open Hugo Links in New Tabs using target _blank"
date: 2020-09-03T22:31:50-05:00
tags: ["static website", "hugo", "partials"]
description: "Open Hugo Links with target=_blank"
draft: false
---

## Motivation
By default Hugo links drive visitors off your website.  I don't like that so I figured out how to open links using `target="_blank"`.

## Change the Default Markup
In your Hugo theme add the file `themes/your-theme/layouts/_default/_markup/render-link.html` and make it look like the this.

```html
<!-- themes/your-theme/layouts/_default/_markup/render-link.html -->
<a href="{{ .Destination | safeURL }}"{{ with .Title}} title="{{ . }}"{{ end }}{{ if strings.HasPrefix .Destination "http" }} rel="noopener noreferrer" target="_blank"{{ end }}>{{ .Text }}</a>
```

Now all [links](https://krishamoud.me) will open in new tabs.
