[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![JCS-ELPA](https://raw.githubusercontent.com/jcs-emacs/badges/master/elpa/v/send-to-osx-grammarly.svg)](https://jcs-emacs.github.io/jcs-elpa/#/send-to-osx-grammarly)

# send-to-osx-grammarly.el
> simple plugin to send text to/from Grammarly [OSX]

[![CI](https://github.com/emacs-grammarly/send-to-osx-grammarly/actions/workflows/test.yml/badge.svg)](https://github.com/emacs-grammarly/send-to-osx-grammarly/actions/workflows/test.yml)

![](docs/demo.gif)

**Grammarly has to be opened and a new document has to be opened.**

Install Grammarly App (OSX version in this case) https://www.grammarly.com/native/mac

The plugin is using Apple Scripts, thus works only on macOS.

This is a proof of concept. Feel free to send pull requests or fork it.

Read more at https://www.reddit.com/r/emacs/comments/6x0ezx/emacs_grammarly_a_simple_plugin/

## 💾 Install

Insert this code into your `.emacs`:

```el
;; load el file in your .emacs, e.g.
(load-file "~/.emacs.d/plugins/send-to-osx-grammarly/send-to-osx-grammarly.el")
```

in the plugin code set path to pull and push script, for me this is:

```el
(call-process-shell-command "osascript ~/.emacs.d/plugins/send-to-osx-grammarly/pull.scpt")
```

and allow Emacs to use Accessibility (for Apple Scripts):

![](docs/configure.png)

## ⌨️ Keybinding

You can bind key using the following snippets.

```el
(define-key global-map (kbd "C-c C-g h") #'send-to-osx-grammarly-push)
(define-key global-map (kbd "C-c C-g l") #'send-to-osx-grammarly-pull)
```

## 🛠️ Contribute

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Elisp styleguide](https://img.shields.io/badge/elisp-style%20guide-purple)](https://github.com/bbatsov/emacs-lisp-style-guide)
[![Donate on paypal](https://img.shields.io/badge/paypal-donate-1?logo=paypal&color=blue)](https://www.paypal.me/jcs090218)
[![Become a patron](https://img.shields.io/badge/patreon-become%20a%20patron-orange.svg?logo=patreon)](https://www.patreon.com/jcs090218)

If you would like to contribute to this project, you may either
clone and make pull requests to this repository. Or you can
clone the project and establish your own branch of this tool.
Any methods are welcome!

### 🔬 Development

To run the test locally, you will need the following tools:

- [Eask](https://emacs-eask.github.io/)
- [Make](https://www.gnu.org/software/make/) (optional)

Install all dependencies and development dependencies:

```sh
eask install-deps --dev
```

To test the package's installation:

```sh
eask package
eask install
```

To test compilation:

```sh
eask compile
```

**🪧 The following steps are optional, but we recommend you follow these lint results!**

The built-in `checkdoc` linter:

```sh
eask lint checkdoc
```

The standard `package` linter:

```sh
eask lint package
```

*📝 P.S. For more information, find the Eask manual at https://emacs-eask.github.io/.*

## ⚜️ License

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

See [`LICENSE`](./LICENSE.txt) for details.
