# deploy-static-site

Template repository for building static sites (HTML + CSS + JS) with deno deploy.

# How To Use

1. Click [[Use this template]](https://github.com/ayame113/deploy-static-site/generate) button.
2. Go to https://dash.deno.com/new, select your repository, then select "via GitHub Action".


![image](https://user-images.githubusercontent.com/40050810/169900711-0b61a6fc-7a32-4f1b-b619-25df89bbf6d5.png)

3. Rewrite `project` in [./.github/workflows/deploy.yml](./.github/workflows/deploy.yml) to your project name.

```diff

    steps:
      - name: Clone repository
        uses: actions/checkout@v2
      - name: Upload to Deno Deploy
        uses: denoland/deployctl@v1
        with:
-          project: "deploy-static-site-test" # The name of your project in deno deploy
+          project: "<your-project-name>" # The name of your project in deno deploy
          entrypoint: "https://deno.land/std/http/file_server.ts"
```

4. Go to `https://<your-project-name>.deno.dev/` and make sure your website is public.
5. Edit [index.html](./index.html) and build your site.
