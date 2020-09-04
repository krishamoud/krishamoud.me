---
title: "The Most Useful Hugo Theme Partial"
date: 2020-08-23T13:20:43-05:00
tags: ["static website", "hugo", "partials"]
images: ["/hugo-partial.jpg"]
draft: false
---

If you're building a new [Hugo](https://gohugo.io/) theme, this is the most useful partial for debugging purposes.  It will show the page variables available to you on any given page.


## Output
{{< rawhtml >}}
<div class="h-40 mb-4 py-4 px-4 overflow-y-auto scrolling-touch border-t border-gray-200">
    <table class="w-full text-left table-auto table-collapse border-gray-200">
        <caption class="text-left pb-2">Hugo Variables for the current page.</caption>
        <thead>
            <tr class="p-2 font-semibold bg-gray-100 border-t ">
                <th>Variable</th>
                <th>Value</th>
            </tr>
        </thead>
        <tbody>
            <tr class="p-2 border-t">
                <td>.Name</td>
                <td>"The Most Useful Hugo Theme Partial"</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Title</td>
                <td>"The Most Useful Hugo Theme Partial"</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Kind</td>
                <td>"page"</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Type</td>
                <td>"posts"</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.IsPage</td>
                <td>true</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.IsHome</td>
                <td>false</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Next</td>
                <td><nil></td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Prev</td>
                <td>Page(/examples/clare-example-section.md)</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Params</td>
                <td>
                    <table>
                        <tr>
                            <td class="text-right italic pr-2">"date":</td>
                            <td>time.Time{wall:0x0, ext:63733803643, loc:(*time.Location)(0x6e24420)}</td>
                        </tr>
                        <tr>
                            <td class="text-right italic pr-2">"draft":</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td class="text-right italic pr-2">"iscjklanguage":</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td class="text-right italic pr-2">"lastmod":</td>
                            <td>time.Time{wall:0x0, ext:63733803643, loc:(*time.Location)(0x6e24420)}</td>
                        </tr>
                        <tr>
                            <td class="text-right italic pr-2">"publishdate":</td>
                            <td>time.Time{wall:0x0, ext:63733803643, loc:(*time.Location)(0x6e24420)}</td>
                        </tr>
                        <tr>
                            <td class="text-right italic pr-2">"tags":</td>
                            <td>[]string{"static website", "hugo", "partials"}
                            </td>
                        </tr>
                        <tr>
                            <td class="text-right italic pr-2">"title":</td>
                            <td>"The Most Useful Hugo Theme Partial"
                            </td>
                        </tr>
                    </table>
                </td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Section</td>
                <td>"posts"</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.CurrentSection</td>
                <td>Page(/posts)</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Pages</td>
                <td>
                    <table>
                        <tr>
                            <td class="text-right italic pr-2">.Pages</td>
                            <td>Pages(0)</td>
                        </tr>
                    </table>
                </td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Resources</td>
                <td>[]</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.File</td>
                <td>posts/useful-hugo-theme-partial.md</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.File.Dir</td>
                <td>"posts/"</td>
            </tr>
        </tbody>
    </table>
</div>
{{< /rawhtml >}}

## HTML
```html
<!-- themes/your-theme/layouts/partials/hugo-variables.html -->
<div class="h-40 mb-4 py-4 px-4 overflow-y-auto scrolling-touch border-t border-gray-200">
    <table class="w-full text-left table-auto table-collapse border-gray-200">
        <caption class="text-left pb-2">Hugo Variables for the current page.</caption>
        <thead>
            <tr class="p-2 font-semibold bg-gray-100 border-t ">
                <th>Variable</th>
                <th>Value</th>
            </tr>
        </thead>
        <tbody>
            <tr class="p-2 border-t">
                <td>.Name</td>
                <td>{{ printf "%#v" .Name }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Title</td>
                <td>{{ printf "%#v" .Title }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Kind</td>
                <td>{{ printf "%#v" .Kind }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Type</td>
                <td>{{ printf "%#v" .Type }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.IsPage</td>
                <td>{{ printf "%#v" .IsPage }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.IsHome</td>
                <td>{{ printf "%#v" .IsHome }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Next</td>
                <td>{{ printf "%v" .Next }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Prev</td>
                <td>{{ printf "%v" .Prev }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Params</td>
                <td>
                    <table>
                        {{ range $k,$v := .Params }}
                        <tr>
                            <td class="text-right italic pr-2">{{ printf "%#v:" $k }}</td>
                            <td>{{ printf "%#v" $v }}</td>
                        </tr>
                        {{ end }}
                    </table>
                </td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Section</td>
                <td>{{ printf "%#v" .Section }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.CurrentSection</td>
                <td>{{ printf "%v" .CurrentSection }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Pages</td>
                <td>
                    {{ printf "%v" .Pages }}
                    <table>
                        {{- range $k,$v := .Pages }}
                        <tr>
                            <td class="text-right italic pr-2">{{ printf "%#v:" $k }}</td>
                            <td>{{ printf "%v" $v }}</td>
                        </tr>
                        {{ end -}}
                    </table>
                </td>
            </tr>
            <tr class="p-2 border-t">
                <td>.Resources</td>
                <td>{{ printf "%v" .Resources }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.File</td>
                <td>{{ if .File }}{{ printf "%v" .File }}{{ else}}""{{ end }}</td>
            </tr>
            <tr class="p-2 border-t">
                <td>.File.Dir</td>
                <td>{{ if .File }}{{ printf "%#v" .File.Dir }}{{ else}}""{{ end }}</td>
            </tr>
        </tbody>
    </table>
</div>
```

## Final

Now you can use your partial wherever you want.  I keep mine in my `_baseof.html`

```html
<!DOCTYPE html>
<html lang='{{ .Site.LanguageCode }}'>
    {{ partial "head.html" . }}
    <body>
        {{- partial "header.html" . -}}
        {{- block "main" . }}{{- end }}
        {{- partial "hugo-variables.html" . -}}
        {{- partial "footer.html" . -}}
    </body>
</html>
```
