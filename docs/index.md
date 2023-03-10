# Welcome to MORAI SIM Air Documentation
The user guide of MORAI SIM: Air Beta provided to [CIRRUS AIRCRAGT](https://cirrusaircraft.com)



Take a look the [MORAI SIM: Air]'s concept and features.  <br>
And start MORAI SIM: Air by reading the **[introductory tutorial]**, then check the **[user guide]** for more information.

[MORAI SIM: Air]: intro/morai-simair.md
[introductory tutorial]: getting-started/
[user guide]: user-guide/

These Documentation source files are written in Markdown, and configured with a single YAML configuration file. 
<div class="text-center">
<ul>
  <li>
   To checkout MORAI SIM: Air, Go to <a href="intro/morai-simair" class="btn btn-primary" role="button">Introduction</a>
  </li>
  <li>
  To start MORAI SIM: Air, Go to <a href="getting-started/" class="btn btn-primary" role="button">Getting Started</a>
  </li>
  <li>
  To use MORAI SIM: Air, Go to <a href="user-guide/" class="btn btn-primary" role="button">User Guide</a>
  </li>
</ul>
</div>


## Conventions

    NOTE:
    > On a few known hosts (specifically GitHub, Bitbucket and GitLab), the
    > `edit_uri` is derived from the 'repo_url' and does not need to be set
    > manually. Simply defining a `repo_url` will automatically populate the
    > `edit_uri` configs setting.
    >
    > For example, for a GitHub- or GitLab-hosted repository, the `edit_uri`
    > would be automatically set as `edit/master/docs/` (Note the `edit` path
    > and `master` branch).
    > 
    > For a Bitbucket-hosted repository, the equivalent `edit_uri` would be
    > automatically set as `src/default/docs/` (note the `src` path and `default`
    > branch).
    >
    > To use a different URI than the default (for example a different branch),
    > simply set the `edit_uri` to your desired string. If you do not want any
    > "edit URL link" displayed on your pages, then set `edit_uri` to an empty
    > string to disable the automatic setting.




<div markdown="span" class="bs-callout bs-callout-{{include.type}}">
    <span style="color:#1d5dbd">
        <i class="fa fa-info-circle"></i>
        <span class="calloutTitle">{{include.title}}</span><br /></span>
        <span class="calloutText">{{include.content}}</span>
</div>

<div markdown="span" class="bs-callout bs-callout-{{include.type}}">
  <span style="color:#5cb85c">
    <i class="fa fa-check-square-o"></i>
    <span class="calloutTitle">**Note**</span><br>
  </span>    
  <span class="calloutText">{{include.content}}</span>
</div>

{% include callout.html title=" **Note**" content="This is my callout. It has a border on the left whose color you define by passing a type parameter. I typically use this style of callout when I have more information that I want to share, often spanning multiple paragraphs. " type="primary" %}

{% include callout_tip.html title=" **Tip**" content="This is my callout. It has a border on the left whose color you define by passing a type parameter. I typically use this style of callout when I have more information that I want to share, often spanning multiple paragraphs. " type="success" %} 

{% include callout_warning.html title= " **Warning**" content="This is my **danger** type." type="danger" level=3 %}


> ℹ️ <span style="color:#247CFF"> ***NOTE*** </span> <br>
> `>` 다음줄에 `>>`, 그 다음 줄에 `>>>`를 기입하면 여러 계층의 인용구로 작성할 수 있다.

xdd


> ✅ <span style="color:#5cb85c"> ***TIPS*** </span> <br>
> `>` 다음줄에 `>>`, 그 다음 줄에 `>>>`를 기입하면 여러 계층의 인용구로 작성할 수 있다.


xdd

> ⚠️ <span style="color:#f0ad4e"> ***Warning*** </span> <br>
> `>` 다음줄에 `>>`, 그 다음 줄에 `>>>`를 기입하면 여러 계층의 인용구로 작성할 수 있다.

fff

>? EXAMPLE: **Advanced example:**
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

fff

>? NOTE: **Suggested useful configurations:**
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


d

WARNING:
On GitHub and GitLab, the default "edit" path (`edit/master/docs/`) opens
the page in the online editor. This functionality requires that the user
have and be logged in to a GitHub/GitLab account. Otherwise, the user will
be redirected to a login/signup page. Alternatively, use the "blob" path
(`blob/master/docs/`) to open a read-only view, which supports anonymous
access.