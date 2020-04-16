# Sourcegraph for JetBrains IDEs [![JetBrains Plugin](https://img.shields.io/badge/JetBrains-Sourcegraph-green.svg)](https://plugins.jetbrains.com/plugin/9682-sourcegraph)

The Sourcegraph plugin for JetBrains IDEs enables you to quickly open and search code on Sourcegraph easily and efficiently in JetBrains IDEs such as IntelliJ. This plugin works with most JetBrains IDEs:

- IntelliJ IDEA
- IntelliJ IDEA Community Edition
- PhpStorm
- WebStorm
- PyCharm
- PyCharm Community Edition
- RubyMine
- AppCode
- CLion
- GoLand
- DataGrip
- Rider
- Android Studio


## Installation

- Select `IntelliJ IDEA` then `Preferences` (or use <kbd>⌘,</kbd>)
- Click `Plugins` in the left-hand pane.
- Choose `Browse repositories...`
- Search for `Sourcegraph` -> `Install`


## Usage

Right click any code or selection and choose `Sourcegraph: Open` or `Sourcegraph: Search`.

Keyboard Shortcuts:

| Description                     | Mac                 | Linux / Windows  |
|---------------------------------|---------------------|------------------|
| Open file in Sourcegraph        | <kbd>Option+A</kbd> | <kbd>Alt+A</kbd> |
| Search selection in Sourcegraph | <kbd>Option+S</kbd> | <kbd>Alt+S</kbd> |


## Settings

The plugin is configurable by creating a `sourcegraph-jetbrains.properties` in your home directory. For example, modify the following URL to match your on-premises Sourcegraph instance URL:

```
url = https://sourcegraph.com
```

By default, the plugin will use the `origin` git remote to determine which repository on Sourcegraph corresponds to the local repository. You may configure this by adding a `sourcegraph` remote which will take priority.

## Questions & Feedback

Please file an issue: https://github.com/sourcegraph/sourcegraph-jetbrains/issues/new


## Uninstallation

- Select `IntelliJ IDEA` then `Preferences` (or use <kbd>⌘,</kbd>)
- Click `Plugins` in the left-hand pane.
- Search for `Sourcegraph` -> Right click -> `Uninstall` (or uncheck to disable)


## Development

- Start IntelliJ and choose `Check out from Version Control` -> `Git` -> `https://github.com/sourcegraph/sourcegraph-jetbrains`
- Develop as you would normally (hit Debug icon in top right of IntelliJ).
- To create `sourcegraph.jar`:
  1. Update `plugin.xml` (change version AND describe changes in change notes).
  2. Update `Util.java` (change `VERSION` constant).
  3. Update `README.md` (copy changelog from plugin.xml).
  5. choose `Build` -> `Prepare Plugin Module 'sourcegraph' For Deployment`
  6. `git commit -m "all: release v<THE VERSION>"` and `git push` and `git tag v<THE VERSION>` and `git push --tags`
  7. Upload the jar to the releases tab of this repository.
  8. Publish according to http://www.jetbrains.org/intellij/sdk/docs/basics/getting_started/publishing_plugin.html (note: it takes ~2 business days for JetBrains support team to review the plugin).


## Version History

#### v1.2.0

- The search menu entry is now no longer present when no text has been selected.
- When on a branch that does not exist remotely, `master` will now be used instead.
- Menu entries (Open file, etc.) are now under a Sourcegraph sub-menu.
- Added a "Copy link to file" action.
- The Project storage API is now used for loading configuration.

(special thanks to @oliviernotteghem for this release)

#### v1.1.2

- Fixed an error that occurred when trying to search with no selection.
- The git remote used for repository detection is now `sourcegraph` and then `origin`, instead of the previously poor choice of just the first git remote.

#### v1.1.1

- Fixed search shortcut; Updated the search URL to reflect a recent Sourcegraph.com change.

#### v1.1.0

- Added support for using the plugin with on-premises Sourcegraph instances.

#### v1.0.0

- Initial Release; basic Open File & Search functionality.
