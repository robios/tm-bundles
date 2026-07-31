# robios bundles

A TextMate *tap*: a list of bundles hosted on GitHub, in `Taps/bundles.plist`.

Adding the tap shows what it offers; it installs nothing on its own, and nothing
it offers updates itself unless you ask it to.

## Using it

In TextMate, **Settings → Bundles**, press **+** under the source list, type

```
robios/tm-bundles
```

and press Return. The bundles below appear in the list above, ready to install.

## What is in it

| Bundle | Repository | What it is |
| --- | --- | --- |
| C | [robios/c.tmbundle](https://github.com/robios/c.tmbundle) | A fork of the official C bundle whose header completion tools run on current Ruby. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| CMake | [robios/cmake.tmbundle](https://github.com/robios/cmake.tmbundle) | A fork of the official CMake bundle with its support library repaired for current Ruby. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| Git | [robios/git.tmbundle](https://github.com/robios/git.tmbundle) | A fork of the official Git bundle whose gitk / git gui launchers work again on current Ruby. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| HTML | [robios/html.tmbundle](https://github.com/robios/html.tmbundle) | A fork of the official HTML bundle whose Tidy warnings filter runs on current Ruby. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| JSON | [robios/json.tmbundle](https://github.com/robios/json.tmbundle) | JSON language support. A fork of the official bundle whose Validate Syntax runs on system Ruby instead of Python. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| LaTeX | [robios/latex.tmbundle](https://github.com/robios/latex.tmbundle) | A fork of the official LaTeX bundle: dialogs go through TextMate's own dialog server instead of the long-gone CocoaDialog, the table dialog works on first use, and LaTeX Watch runs without Rosetta. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| Mail | [robios/mail.tmbundle](https://github.com/robios/mail.tmbundle) | Compose mail in TextMate. A fork of the official bundle whose Unwrap Paragraphs runs on current Ruby. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| Man Pages | [robios/man-pages.tmbundle](https://github.com/robios/man-pages.tmbundle) | Read and cross-reference man pages inside TextMate. A fork of the official bundle whose section lookup works with current macOS man(1). |
| Merge Markers | [robios/merge-markers.tmbundle](https://github.com/robios/merge-markers.tmbundle) | Highlights git conflict markers in any file via an injection grammar. Pure grammar, no runtime code. A fork of [noniq/Merge-Markers.tmbundle](https://github.com/noniq/Merge-Markers.tmbundle). |
| Ninja | [robios/ninja.tmbundle](https://github.com/robios/ninja.tmbundle) | Ninja build files: grammar and a build command. A fork of the official bundle that finds ninja in the Apple Silicon Homebrew prefix. |
| OCaml | [robios/ocaml.tmbundle](https://github.com/robios/ocaml.tmbundle) | A fork of the official OCaml bundle whose wrap-section commands run on current Ruby. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| PHP | [robios/php.tmbundle](https://github.com/robios/php.tmbundle) | A fork of the official PHP bundle: the documentation command runs on current Ruby and generate.rb no longer hardcodes a 2012 Homebrew interpreter. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| Python | [robios/python.tmbundle](https://github.com/robios/python.tmbundle) | Python language support — run scripts, syntax checking via pycheckmate, pydoc lookup. A fork of the official bundle ported to Python 3: commands, templates and checkers run on python3, and the defunct DocMate browser is retired. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| Ruby | [robios/ruby.tmbundle](https://github.com/robios/ruby.tmbundle) | A fork of the official Ruby bundle repaired for current Ruby: Run Rake Task, Insert Missing Requires and Reformat Document work again. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| Regular Expressions | [robios/regularexpressions.tmbundle](https://github.com/robios/regularexpressions.tmbundle) | Test and highlight regular expressions against sample text. A fork of the official bundle with its match and substitution testers repaired. |
| Objective-C | [robios/objective-c.tmbundle](https://github.com/robios/objective-c.tmbundle) | A fork of the official Objective-C bundle whose Insert NSLog() command runs on current Ruby. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| TextMate | [robios/textmate.tmbundle](https://github.com/robios/textmate.tmbundle) | A fork of the official TextMate bundle: syntax-highlighted HTML and RTF export on current Ruby, and the dead pastie.org paste command removed. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| VHDL | [robios/vhdl.tmbundle](https://github.com/robios/vhdl.tmbundle) | A fork of the official VHDL bundle: one-line symbols for processes, functions and procedures, declaration lookup that ignores optional keywords, and a Tidy command that leaves Emacs backup files alone. Keeps the official bundle's UUID, so installing it replaces that bundle. |
| Xcode 26 Theme | [robios/xcode-26-theme.tmbundle](https://github.com/robios/xcode-26-theme.tmbundle) | Xcode 26 Dark and Light editor themes. Closest with SF Mono Medium, 12 pt. |
| YAML | [robios/yaml.tmbundle](https://github.com/robios/yaml.tmbundle) | A fork of the official YAML bundle differing in one key: Sort Keys Alphabetically sits on F6, next to the other sort commands, instead of on F5, which this TextMate uses to jump to the next diagnostic. Keeps the official bundle's UUID, so installing it replaces that bundle. |

## Adding a bundle to the catalogue

One dictionary per bundle in `Taps/bundles.plist`:

| Key | |
| --- | --- |
| `uuid` | The bundle's own UUID, from its `info.plist`. Required. |
| `name` | Display name. Required. |
| `url` | `https://github.com/<owner>/<repository>`. Required, and GitHub only. |
| `ref` | Branch, tag, or revision to install. Optional; `main` if omitted. |
| `category` | `Languages`, `Themes`, `Build`, `SCM`, `Testing`, `Other`. Optional. |
| `description` | One or two sentences. Optional. |
| `grammars` | What the bundle can open, so TextMate can offer it for a file it has no support for. Each needs `uuid`, `name`, and `scope`; `fileTypes` and `firstLineMatch` are optional. |

A bundle whose UUID matches one already installed is not installed silently:
TextMate either refuses it or offers to replace the official copy, which is why
the entries above say what they replace.

There is no signature. A `.tmbundle` contains commands that run as you, so a tap
is a statement about who you trust.
