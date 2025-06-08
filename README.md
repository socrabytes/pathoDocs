# Hextra Starter Template

[![Deploy Hugo site to Pages](https://github.com/imfing/hextra-starter-template/actions/workflows/pages.yaml/badge.svg)](https://github.com/imfing/hextra-starter-template/actions/workflows/pages.yaml)
[![Netlify Status](https://api.netlify.com/api/v1/badges/6e83fd88-5ffe-4808-9689-c0f3b100bfe3/deploy-status)](https://app.netlify.com/sites/hextra-starter-template/deploys)
![Vercel Deployment Status](https://img.shields.io/github/deployments/imfing/hextra-starter-template/production?logo=vercel&logoColor=white&label=vercel&labelColor=black&link=https%3A%2F%2Fhextra-starter-template.vercel.app%2F)


🐣 Minimal template for getting started with [Hextra](https://github.com/imfing/hextra)

![hextra-template](https://github.com/imfing/hextra-starter-template/assets/5097752/c403b9a9-a76c-47a6-8466-513d772ef0b7)

[🌐 Demo ↗](https://imfing.github.io/hextra-starter-template/)

## Quick Start

Use this template to create your own repository:

<img src="https://docs.github.com/assets/cb-77734/mw-1440/images/help/repository/use-this-template-button.webp" width=400 />

You can also quickly start developing using the following online development environment:

- [GitHub Codespaces](https://github.com/codespaces) 
    
    [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/imfing/hextra-starter-template)

    Create a new codespace and follow the [Local Development](#local-development) to launch the preview

- [Gitpod](https://gitpod.io)

    [![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/imfing/hextra-starter-template)


## Deployment

### GitHub Pages

A GitHub Actions workflow is provided in [`.github/workflows/pages.yaml`](./.github/workflows/pages.yaml) to [publish to GitHub Pages](https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/) for free. 

For details, see [Publishing with a custom GitHub Actions workflow](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow).

Note: in the settings, make sure to set the Pages deployment source to **GitHub Actions**:

<img src="https://github.com/imfing/hextra-starter-template/assets/5097752/99676430-884e-42ab-b901-f6534a0d6eee" width=600 />

[Run the workflow manually](https://docs.github.com/en/actions/using-workflows/manually-running-a-workflow) if it's not triggered automatically.

### Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/imfing/hextra-starter-template)

### Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fimfing%2Fhextra-starter-template&env=HUGO_VERSION)

Override the configuration:

<img src="https://github.com/imfing/hextra-starter-template/assets/5097752/e2e3cecd-c884-47ec-b064-14f896fee08d" width=600 />

## Local Development for pathoDocs

This section outlines how to set up and run the `pathoDocs` project locally.

**Pre-requisites:**
*   [Hugo (Extended version)](https://gohugo.io/getting-started/installing/)
*   [Go](https://golang.org/doc/install)
*   [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

**1. Clone the Repository (if you haven't already):**
```shell
git clone https://github.com/socrabytes/pathoDocs.git
cd pathoDocs
```

**2. Install/Update Hugo Modules (including Hextra theme):**
If this is your first time or you need to ensure modules are up to date:
```shell
hugo mod tidy  # Cleans up go.mod and go.sum
hugo mod get -u # Updates modules to their latest versions
```
*(Note: `hugo mod tidy` removes unused module versions and `hugo mod get -u` updates them. These are useful for managing the Hextra theme module.)*

**3. Running the Local Server:**

*   **Standard Development:**
    For most development tasks, you can start the Hugo server with:
    ```shell
    hugo server -NF
    ```
    The site will typically be available at `http://localhost:1313/`.

*   **Testing Content with GitHub Pages Paths:**
    If you are testing content that includes hardcoded paths for the GitHub Pages deployment (e.g., interactive reviews in `static/` linked with a `/pathoDocs/` prefix), you need to run the local Hugo server with a specific `baseURL` to simulate the GitHub Pages environment:
    ```shell
    # Replace 1313 with your desired port if different
    hugo server -NF --baseURL "http://localhost:1313/pathoDocs/"
    ```
    Your site will then be accessible at `http://localhost:1313/pathoDocs/`, and links prefixed with `/pathoDocs/` will resolve correctly. For example, an interactive review page might be at `http://localhost:1313/pathoDocs/clinical-resources/pharmtx/chXX/interactive-review/`.

**4. Updating the Hextra Theme:**
To specifically update the Hextra theme (or other Hugo modules) to their latest versions:
```shell
hugo mod get -u
hugo mod tidy
```

See [Update modules](https://gohugo.io/hugo-modules/use-modules/#update-modules) for more details on managing Hugo modules.

