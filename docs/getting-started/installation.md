# MORAI SIM AIR Installation

For Latest and Previous versions

---

## Latest

To upgrade MkDocs to the latest version, use pip:

```bash
pip install -U mkdocs
```

You can determine your currently installed version using `mkdocs --version`:

```console
$ mkdocs --version
mkdocs, version 1.0 from /path/to/mkdocs (Python 3.6)
```

### Version 1.0 (2023-03-20)

*   Officially support Python 3.11 (#3020)

    NEW: **Tip:** Simply upgrading to Python 3.11 can cut off 10-15% of your site's build time.

*   Support multiple instances of the same plugin (#3027)

    If a plugin is specified multiple times in the list under the `plugins:` config, that will create 2 (or more) instances of the plugin with their own config each.

    Previously this case was unforeseen and, as such, bugged.

    Now even though this works, by default a warning will appear from MkDocs anyway, unless the plugin adds a class variable `supports_multiple_instances = True`.

*   Bugfix (regression in 1.4.1): Don't error when a plugin puts a plain string into `warnings` (#3016)

*   Bugfix: Relative links will always render with a trailing slash (#3022)

    Previously under `use_directory_urls`, links *from* a sub-page *to* the main index page rendered as e.g. `<a href="../..">` even though in all other cases the links look like `<a href="../../">`. This caused unwanted behavior on some combinations of Web browsers and servers. Now this special-case bug was removed.

*   Built-in "mkdocs" theme now also supports Norwegian language (#3024)

*   Plugin-related warnings look more readable (#3016)

See [commit log](https://github.com/mkdocs/mkdocs/compare/1.4.1...1.4.2).


#### Customize event order for plugin event handlers (#2973)

Plugins can now choose to set a priority value for their event handlers. This can override the old behavior where for each event type, the handlers are called in the order that their plugins appear in the [`plugins` config](../user-guide/configuration.md#plugins).

If this is set, events with higher priority are called first. Events without a chosen priority get a default of 0. Events that have the same priority are ordered as they appear in the config.

Recommended priority values: `100` "first", `50` "early", `0` "default", `-50` "late", `-100` "last".  
As different plugins discover more precise relations to each other, the values should be further tweaked.

See [**documentation**](../dev-guide/plugins.md#event-priorities).


#### New events that persist across builds in `mkdocs serve` (#2972)

The new events are `on_startup` and `on_shutdown`. They run at the very beginning and very end of an `mkdocs` invocation.  
`on_startup` also receives information on how `mkdocs` was invoked (e.g. `serve` `--dirtyreload`).

See [**documentation**](../dev-guide/plugins.md#events).


#### Replace `File.src_path` to not deal with backslashes (#2930)

The property `src_path` uses backslashes on Windows, which doesn't make sense as it's a virtual path.  
To not make a breaking change, there's no change to how *this* property is used, but now you should:

* Use **`File.src_uri`** instead of `File.src_path`
* and **`File.dest_uri`** instead of `File.dest_path`.

See more [examples in **documentation**](../dev-guide/plugins.md#examples-of-config-definitions).


##### Updated: `config_options.SubConfig` (#2807)

`SubConfig` used to silently ignore all validation of its config options. Now you should pass `validate=True` to it or just use new class-based configs where this became the default.

So, it can be used to validate a nested sub-dict with all keys pre-defined and value types strictly validated.

See [examples in **documentation**](../dev-guide/plugins.md#examples-of-config-definitions).


#### Other changes to config options

`URL`'s default is now `None` instead of `''`. This can still be checked for truthiness in the same way - `if config.some_url:` (#2962)

`FilesystemObject` is no longer abstract and can be used directly, standing for "file or directory" with optional existence checking (#2938)

Bug fixes:

* Fix `SubConfig`, `ConfigItems`, `MarkdownExtensions` to not leak values across different instances (#2916, #2290)
* `SubConfig` raises the correct kind of validation error without a stack trace (#2938)
* Fix dot-separated redirect in `config_options.Deprecated(moved_to)` (#2963)

Tweaked logic for handling `ConfigOption.default` (#2938)

Deprecated config option classes: `ConfigItems` (#2983), `OptionallyRequired` (#2962), `RepoURL` (#2927)


## Previous Versions

NOTE: This release has big changes to the implementation of plugins and their configs. But, the intention is to have zero breaking changes in all reasonably common use cases. Or at the very least if a code fix is required, there should always be a way to stay compatible with older MkDocs versions. Please report if this release breaks something.