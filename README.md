# giscus_test

Trying out `giscus` for comments on Quarto sites.

1. Go to https://github.com/apps/giscus, click install. Select account, and then all or specific repositories. Seems sucessful - `Okay, giscus was installed on the @amyheather account.`.
2. Went to my repository settings, on General settings page scrolled down to "Features", ticked "Discussions" to enable it.
3. Went to https://giscus.app/. Entered the repository name, `amyheather/giscus_test`, and it said "Success! This repository meets all of the above criteria" (i.e. public, app installed, discussions enabled). I chose a Discussion category, then scrolled down to Enable giscus which had created:

```
<script src="https://giscus.app/client.js"
        data-repo="amyheather/giscus_test"
        data-repo-id="R_kgDOPiZ0gg"
        data-category="Announcements"
        data-category-id="DIC_kwDOPiZ0gs4Cuec6"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="en"
        crossorigin="anonymous"
        async>
</script>
```

4. I created a basic Quarto site hosted on GitHub pages with GitHub actions.

5. I tried adding the raw script above which worked perfectly, locally, without deployment.

6. I then edited _quarto.yml to do it via Quarto. And that worked fine too:

```
website:
  title: "Giscus test"
  comments:
    giscus:
      repo: "amyheather/giscus_test"
      repo-id: "R_kgDOPiZ0gg"
      category: "Announcements"
      category-id: "DIC_kwDOPiZ0gs4Cuec6"
      mapping: "pathname"
      reactions-enabled: true
      loading: "lazy"
      input-position: "bottom"
      theme: "preferred_color_scheme"
      language: "en"
```