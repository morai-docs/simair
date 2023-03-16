# Welcome to MORAI SIM Air Documentation 👍
This document is a user guide for **MORAI SIM: AiR** Beta version provided to [CIRRUS AIRCRAGT](https://cirrusaircraft.com)


Take a look the [MORAI SIM: Air]'s concept and features.  <br>
Start MORAI SIM: Air by reading the **[introductory tutorial]**, then check the **[user guide]** for more information.

[MORAI SIM: Air]: intro/morai-simair.md
[introductory tutorial]: getting-started/
[user guide]: user-guide/

<div class="text-center">
<ul>
  <li>
   <b>To checkout MORAI SIM: Air</b>, Go to <a href="intro/morai-simair" class="btn btn-primary" role="button">Introduction</a>
  </li>
  <li>
    <b>To start MORAI SIM: Air</b>, Go to <a href="getting-started/" class="btn btn-primary" role="button">Getting Started</a>
  </li>
  <li>
    <b>To use MORAI SIM: Air</b>, Go to <a href="user-guide/" class="btn btn-primary" role="button">User Guide</a>
  </li>
</ul>
</div>

<br>
>  ℹ️ <span style="color:#247CFF"> ***NOTE*** </span> <br> All documentation source files for this guide are > written in Markdown, and configured with a single YAML configuration file. 
<!-- -->


> EXAMPLE: **Advanced example:**
>
> This produces warnings based on the Markdown content (and warnings are fatal in [strict](#strict) mode):
>
> ```python
> import logging, re
> import mkdocs.plugins
>
> log = logging.getLogger('mkdocs')
>
> @mkdocs.plugins.event_priority(-50)
> def on_page_markdown(markdown, page, **kwargs):
>     path = page.file.src_uri
>     for m in re.finditer(r'\bhttp://[^) ]+', markdown):
>         log.warning(f"Documentation file '{path}' contains a non-HTTPS link: {m[0]}")
> ```
<!-- -->
> NOTE: **Suggested useful configurations:**
>
> *   GitHub Wiki:  
>     (e.g. `https://github.com/project/repo/wiki/foo/bar/_edit`)
>
>     ```yaml
>     repo_url: 'https://github.com/project/repo/wiki'
>     edit_uri_template: '{path_noext}/_edit'
>     ```
>
> *   BitBucket editor:  
>     (e.g. `https://bitbucket.org/project/repo/src/master/docs/foo/bar.md?mode=edit`)
>
>     ```yaml
>     repo_url: 'https://bitbucket.org/project/repo/'
>     edit_uri_template: 'src/master/docs/{path}?mode=edit'
>     ```
>
> *   GitLab Static Site Editor:  
>     (e.g. `https://gitlab.com/project/repo/-/sse/master/docs%2Ffoo%2bar.md`)
>
>     ```yaml
>     repo_url: 'https://gitlab.com/project/repo'
>     edit_uri_template: '-/sse/master/docs%2F{path!q}'
>     ```
>
> *   GitLab Web IDE:  
>     (e.g. `https://gitlab.com/-/ide/project/repo/edit/master/-/docs/foo/bar.md`)
>
>     ```yaml
>     edit_uri_template: 'https://gitlab.com/-/ide/project/repo/edit/master/-/docs/{path}'

<!-- -->

> and `theme.name` is set to `null`, then the entire theme configuration must
> be defined in the [theme] configuration option in the `mkdocs.yml` file.
>
> However, when a theme is [packaged] up for distribution, and loaded using
> the `theme.name` configuration option, then a `mkdocs_theme.yml` file
> is required for the theme.
