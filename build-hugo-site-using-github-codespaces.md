# Build Hugo Site Using Github Codespaces

## [2024-07-22] Plan to stop using Hugo with PaperMod

PaperMod is my favourite Hugo theme, but I found if I use the v7.0 release, the date will not display properly. This
[issue](https://github.com/adityatelange/hugo-PaperMod/issues/1325) has been solved after the release of v7.0 so it will
not be a problem if I use the master branch instead of v7.0 release. However, I do not prefer to use the master branch
as it may contain unexpected features that I am not aware of. Also, I do not want to switch to other themes I am not
familiarly with. Therefore, I plan to stop using Hugo to build my site.

## Steps

1. Verify Hugo version

    ```bash
    hugo version
    ```

1. Create a new Hugo site

    ```bash
    hugo new site . --force --format yaml
    ```

1. Install PaperMod theme

    ```bash
    git submodule add -b master https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
    git -C themes/PaperMod checkout v7.0
    git submodule update --init --recursive
    echo "theme: PaperMod" >> hugo.yaml
    ```

1. Add content

    ```bash
    hugo new content content/posts/my-first-post.md
    ```

1. Start Hugo’s development server

    ```bash
    hugo server --baseURL "https://${CODESPACE_NAME}-1313.app.github.dev" --buildDrafts --appendPort=false --debug
    ```

1. [Host on GitHub Pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

## Reference

1. Hugo: <https://gohugo.io/getting-started/quick-start/>
1. PaperMod: <https://github.com/adityatelange/hugo-PaperMod>
