---
title: "Hugo"
---

## Snippets

### Tags
```
<ul id="tags">
  {{ range .Params.tags }}
    <li><a href="{{ $.Site.BaseURL }}tags/{{ . | urlize }}">{{ . }}</a> </li>
  {{ end }}
</ul>
```

### List per month
```
{{define "main"}} 
{{ range (.Data.Pages.GroupByDate "2006-01") }}

<h3>{{ .Key }}</h3>

{{ range .Pages }}
<movies>
  <li>
    {{.Title}} <div class="star" style="width:{{.Params.rating}}"></div> <date>{{.Date.Format "2006-01-02"}}</date>
  </li>
</movies>
{{ end }}

{{ end }}
{{ end }}
```

### Raw HTML
```
In your config enter:

[markup.goldmark.renderer]
unsafe= true
```
