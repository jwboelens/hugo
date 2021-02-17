---
title: "Movies Page"
date: 2020-12-03
---

# Movies Page

I decided to make a list of movies I watch, and what better place to do it than on my own website. 
Using the Hugo list function it's easy to list all movies based on watch date and grouped by month.

Here is the code for the <a href="/movies">/movies</a> page, which collects all the posts in the movies section.

```
{{define "main"}} 
{{ range (.Data.Pages.GroupByDate "January 2006") }}

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
It's named list.html and it's located inside the themes/layouts/movies folder.

The "star" class in my css converts the rating in the frontmatter of the movie to the actual stars. I set the rating in increments of 13px. 
Where 13px is one star, 26px is 2 stars etc.

---

Here is the frontmatter for **Blade Runner 2049** where I set a rating of 52px.

```
---
title: "Blade Runner 2049"
date: 2020-10-04
year: 2017
rating: 52px
---
```

---

This bit of css makes the rating of 52px in the frontmatter look like a 4 star rating, because 52px divided by 13px is 4.

```
.star {
    width: 13px;
    height: 12px;
    display: inline-block;
    background: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTMiIGhlaWdodD0iMTIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTYuMzA5IDkuMjJMMi40MDkgMTJsMS40NC00LjU2N0wwIDQuNTgzbDQuNzg4LS4wNDJMNi4zMDggMCA3LjgzIDQuNTRsNC43ODkuMDQ0LTMuODUgMi44NDlMMTAuMjA5IDEyeiIgZmlsbC1ydWxlPSJldmVub2RkIi8+PC9zdmc+);
}
```
