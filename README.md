# Git StyleGuide

## TOC
- [About](#about)
- [Git Projects](#git-projects)
- [README Template](#readme-template)
- [LICENSE_Template](#license-template)
- [Contributing_Template](#contributing-template)
- [Commit Message Format](#commit-message-format)
- [Tag Message Format](#tag-message-format)
- [Notes](#notes)
- [Git config and GPGsign](#git-config-and-gpgsign)
- [Suggested Emojis](#suggested-emojis)
- [Tools](#tools)
- [Fun Emoji Usages](#fun-emoji-usages)
- [Contributing](#contributing)
- [License](#license)
- [Thanks to](#thanks-to)


## About
This is an attempt to standardize the format of commit messages, for the sake of **uniformity** in git log, **best practices** for writing commit messages & **fun**!

Using emojis at the beginning of commit messages, other than being fun, provides a simple way to indicate the intention of that commit, an ease for the eyes when browsing/reviewing git log. It's also a simple measure of the fact that how much that commit is focused on a single purpose, which is a good practice.

## Git Principle
Please make as many commits as possible. The principle here is small commits. A version tag must then be set for each related change.

* Every change **must** commit.
* All related changes **must** be combined in a new version.
* Every new version **must** be tagged.

## Git Projects

+ Every project name **must** must be lower case.
+ Every project **must** have an easily recognizable name. The blanks in the project name are filled in with the character **_**.
+ Every project **must** have a description.
+ Every project **must** have a project avatar.
+ Projects that belong together must be marked with a project description. For example: **chef_example_cookbook**

## README Template

Please use the [README_template](README_template.md) for **normal** projects.
Please use the [README_chef_template](README_chef_template.md) for **chef** projects.

## LICENSE Template

Please use the [GNU Affero General Public License v3.0](LICENSE) for normal projects.

## Contributing Template

Please use the [CONTRIBUTING](CONTRIBUTING.md) for for projects.

## Commit Message Format

All Git Commit Messages **MUST** be signed!

All Git Commit Messages **MUST** meet with this Text Format:
```
:emoji1: :emoji2: Subject
(Only One NewLine)
Message Body
(Only One NewLine)
Ref <###>
```

## Tag Message Format

All Git Tag Messages **MUST** be signed!

All Git Tag Messages **MUST** meet with this Text Format:
```
Release vSemVer
```

### Rules

1. Capitalize the _Subject_.
2. Do not end the _Subject_ line with a period.
3. Message _Subject_ **SHOULD** Begin with _at-least_ One Emoji(see below for [list of Suggested Emojis](#suggested-emojis)).
4. Message Body **SHOULD** End with _at-least_ One Issue Tracking ID Reference([GitHub Issues](https://github.com/features#issues)/[GitLab Issues](https://docs.gitlab.com/ee/user/project/issues/)/[Phabricator Tasks](http://phacility.com/phabricator/maniphest/)), Ex. `Issue #27`, `Ref T27` or `Ref T27, T56` or `Fixes T8`.
It's also [recommanded](/../../issues/19) to use _Full URL to Issues_, instead of just Issue ID Number; Doing so will ease browsing issues from terminal.
5. Total Characters of the _Subject Line_ **MUST** be _Less_ than or _Equal_ to **50** Chars Long.
6. Wrap the _Message body_ at **72** characters.
7. Use Valid [MarkDown](https://daringfireball.net/projects/markdown/basics) format in _Message Body_.
8. Use the **Present Tense** ("Add feature" not "Added feature").
9. Use the **Imperative Mood** ("Move cursor to..." not "Moves cursor to...").
10. Use the _Message body_ to explain **what** and **why** vs. how.
11. All WIP(Work In Progress) Commits **MUST** have the WIP Emoji(see below).

## Notes

+ All **WIP** Commits **Should** be Avoided!.
+ Refrencing Issues by using special keywords like `Fixes` or `Resolves` will mark them as closed automatically! For more  information about automatic issue closing using ketwords see: [GitHub](https://help.github.com/articles/closing-issues-via-commit-messages/)/[GitLab](https://docs.gitlab.com/ee/user/project/issues/automatic_issue_closing.html)/[Phabricator](https://secure.phabricator.com/book/phabricator/article/diffusion_autoclose/).
+ There is a **Space** Character between Multiple Emojis!.
+ There is **NO** New-Line After the _Task ID Reference_ Line.
+ Every Raw Emoji Text(`:emoji:`) is Counted as One Char!.
+ See [ToDo Grammar StyleGuide](https://github.com/slashsBin/styleguide-todo-grammar) for more Information on `@XXX` Comment Tags.

## Git config and GPGsign

All commit messages and tags **must** be signed!

`gpg --list-secret-keys --keyid-format LONG`

```
sec   ed25519 2018-02-26 [SC] [expires: 2022-02-25]
      101D2615211421D8D22218DFD68251B5B79A051A
uid           [ultimate] Robert Ressl <robert.ressl@safematix.ch>
ssb   cv25519 2018-02-26 [E] [expires: 2022-02-25]
```

`git config --global user.signingkey 101D2615211421D8D22218DFD68251B5B79A051A`

`git config --global user.name "Ressl Robert"`

`git config --global user.email "robert.ressl@safematix.ch"`

`git config --global commit.gpgsign true`

`git config --global tag.gpgsign true`


## Suggested Emojis

### Most used

| Emoji | Raw Emoji Code | Description |
|:---:|:---:|---|
| :tada: | `:tada:` | **Initial** Commit |
| :art: | `:art:` | when improving the **format**/structure of the code |
| :sparkles: | `:sparkles:` | when introducing **New** Features |
| :newspaper: | `:newspaper:` | when creating a **new file** |
| :pencil: | `:pencil:` | when **performing minor changes/fixing** the code or language |
| :books: | `:books:` | when writing **docs** |
| :bug: | `:bug:` | when reporting a **bug**, with [`@FIXME`](https://github.com/slashsBin/styleguide-todo-grammar#bug-report)Comment Tag |
| :ambulance: | `:ambulance:` | when fixing a **bug** |
| :fire: | `:fire:` | when **removing code** or files, _maybe_ with `@CHANGED` Comment Tag |
| :tractor: | `:tractor:` | when **change file structure**. Usually together with :art: |
| :hammer: | `:hammer:` | when **refactoring** code |
| :umbrella: | `:umbrella:` | when adding **tests** |
| :gem: | `:gem:` | New **Release** |
| :bookmark: | `:bookmark:` | Version **Tags** |
| :snowflake: | `:snowflake:` | changing **Configuration**, Usually together with :penguin: or :ribbon: or :rocket: |
| :ribbon: | `:ribbon:` | Customer requested application **Customization**, with `@HACK` Comment Tag |
| :rocket: | `:rocket:` | Anything related to Deployments/**DevOps** |
| :handshake: | `:handshake:` | when **Merge files** |
| :file_folder: | `:file_folder:` | when working with **Git Submodules** |

### Complete list

| Emoji | Raw Emoji Code | Description |
|:---:|:---:|---|
| :art: | `:art:` | when improving the **format**/structure of the code |
| :newspaper: | `:newspaper:` | when creating a **new file** |
| :pencil: | `:pencil:` | when **performing minor changes/fixing** the code or language |
| :racehorse: | `:racehorse:` | when improving **performance** |
| :books: | `:books:` | when writing **docs** |
| :bug: | `:bug:` | when reporting a **bug**, with [`@FIXME`](https://github.com/slashsBin/styleguide-todo-grammar#bug-report)Comment Tag |
| :ambulance: | `:ambulance:` | when fixing a **bug** |
| :penguin: | `:penguin:` | when fixing something on **Linux** |
| :apple: | `:apple:` | when fixing something on **Mac OS** |
| :checkered_flag: | `:checkered_flag:` | when fixing something on **Windows** |
| :fire: | `:fire:` | when **removing code** or files, _maybe_ with `@CHANGED` Comment Tag |
| :tractor: | `:tractor:` | when **change file structure**. Usually together with :art: |
| :hammer: | `:hammer:` | when **refactoring** code |
| :umbrella: | `:umbrella:` | when adding **tests** |
| :microscope: | `:microscope:` | when adding **code coverage** |
| :green_heart: | `:green_heart:` | when fixing the **CI** build |
| :lock: | `:lock:` | when dealing with **security** |
| :arrow_up: | `:arrow_up:` | when upgrading **dependencies** |
| :arrow_down: | `:arrow_down:` | when downgrading **dependencies** |
| :fast_forward: | `:fast_forward:` | when **forward-porting features** from an older version/branch |
| :rewind: | `:rewind:` | when **backporting features** from a newer version/branch |
| :shirt: | `:shirt:` | when removing **linter**/strict/deprecation warnings |
| :lipstick: | `:lipstick:` | when improving **UI**/Cosmetic |
| :wheelchair: | `:wheelchair:` | when improving **accessibility** |
| :globe_with_meridians: | `:globe_with_meridians:` | when dealing with **globalization**/internationalization/i18n/g11n |
| :construction: | `:construction:` | **WIP**(Work In Progress) Commits, _maybe_ with `@REVIEW` Comment Tag |
| :gem: | `:gem:` | New **Release** |
| :bookmark: | `:bookmark:` | Version **Tags** |
| :tada: | `:tada:` | **Initial** Commit |
| :speaker: | `:speaker:` | when Adding **Logging** |
| :mute: | `:mute:` | when Reducing **Logging** |
| :sparkles: | `:sparkles:` | when introducing **New** Features |
| :zap: | `:zap:` | when introducing **Backward-InCompatible** Features, _maybe_ with `@CHANGED` Comment Tag |
| :bulb: | `:bulb:` | New **Idea**, with `@IDEA` Comment Tag |
| :snowflake: | `:snowflake:` | changing **Configuration**, Usually together with :penguin: or :ribbon: or :rocket: |
| :ribbon: | `:ribbon:` | Customer requested application **Customization**, with `@HACK` Comment Tag |
| :rocket: | `:rocket:` | Anything related to Deployments/**DevOps** |
| :elephant: | `:elephant:` | **PostgreSQL** Database specific (Migrations, Scripts, Extensions, ...)  |
| :dolphin: | `:dolphin:` | **MySQL** Database specific (Migrations, Scripts, Extensions, ...) |
| :leaves: | `:leaves:` | **MongoDB** Database specific (Migrations, Scripts, Extensions, ...) |
| :bank: | `:bank:` | **Generic Database** specific (Migrations, Scripts, Extensions, ...) |
| :whale: | `:whale:` | **Docker** Configuration |
| :handshake: | `:handshake:` | when **Merge files** |
| :file_folder: | `:file_folder:` | when working with **Git Submodules** |

## Tools

- [Commit](https://github.com/jakeasmith/commit)(CLI): This is a nifty CLI tool to aid in standardizing commit messages based on this document, thanks to @jakeasmith.
- [gitMoji](https://github.com/louisgrasset/git-moji)(Chrome Extension): Enhance your commits with emojis!, thanks to @louisgrasset.


## Fun Emoji Usages
- [CodeEmoji](https://codemoji.org/): Mozilla’s Codemoji enciphers your messages with emoji for fun and profit
- [Emoji Based Diagram](https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service/#send_data): Emoji Based Diagram of Data Bearing Subscription Updates(WebPush VAPID)


## Contributing

Please read [CONTRIBUTING](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

[Ask](https://github.com/safematix/styleguide_git/issues) to Be [Creative](https://www.emojicopy.com/)!

To add a new Emoji to the list: [Create an Issue](https://github.com/safematix/styleguide_git/issues).

## Versioning

* **v1.0.0** - Initial work
* **v1.0.1** - fix CONTRIBUTING and add template, version list
* **v1.1.0** - add add Git Principle and fix typo
* **v1.2.0** - add add Emoji :file_folder:
* **v1.3.0** - add add CHANGELOG_template.md

## Authors

* **Robert Ressl** - *Initial work & improvement* - [Robert Ressl](https://github.com/safematix)

## License

The Code is licensed under the [GNU Affero General Public License v3.0](LICENSE)

## Thanks to…

* [slashsBin](https://github.com/slashsBin) and his [styleguide-git-commit-message](https://github.com/slashsBin/styleguide-git-commit-message)
* [PurpleBooth](https://gist.github.com/PurpleBooth) and his [README-Template.md](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2)
* [Coraline Ada Ehmke](https://www.contributor-covenant.org) and his [Contributor Covenant Code of Conduct](http://contributor-covenant.org/version/1/4/)
