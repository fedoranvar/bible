# Development tags

To comply [TDD](test-driven-development.md) you must do commits with the following updates only. Use Text code or Emoji-code


| Name                                                      | :wink:        | Emoji-code      | Notes                                                                                             |
|-----------------------------------------------------------|---------------|-----------------|---------------------------------------------------------------------------------------------------|
| [Preparation](test-driven-development.md#preparation)     | :memo:        | `:memo:`        | Plan, docs, code templates, etc.                                                                  |
| [Error catchers](test-driven-development.md#tests)        | :fire:        | `:fire:`        | Be sure that code adds new or fixes existing error catcher. Otherwise consider to use another tag |
| [Passing tests](test-driven-development.md#passing-tests) | :fire_engine: | `:fire_engine:` | Must have reference to error log or test name that passes after this commit                       |
| Views                                                     | :tv:          | `:tv:`          | **Basic** backend UI (views, menus, etc.). Don't use it for website templates, assets, qweb, etc. |
| Access control                                            | :lock:        | `:lock:`        | Security updates (**ir.model.access.csv**, **ir.rule**, **res.groups**, attribute **groups**)     |
| Cleaning                                                  | :bath:        | `:bath:`        | Cleanup, refactoring or finalizing of the **covered** code or docs                                           |
| Fixing lints                                              | :green_heart: | `:green_heart:` | Fixing lint errors                                                                                |
| Adding demo                                               | :cat:         | `:cat:`         |                                                                                                   |


* Use :bomb: `:bomb:` for the rest (messy commits, non TDD updates, etc.). This tag means that it's potentially **dangerous** and has to be avoided.

# Release tags

For releases use Emoji-code

| Name          | :wink:         | Emoji-code       | Notes                                                                                 |
|---------------|----------------|------------------|---------------------------------------------------------------------------------------|
| New Module    | :tada:         | `:tada:`         |                                                                                       |
| New Feature   | :zap:          | `:zap:`          |                                                                                       |
| Major Update  | :sparkles:     | `:sparkles:`     | breaking updates, i.e. when version is change at the highest level (e.g. 4.3.2 -> 5.0.0) |
| Cleanup       | :rainbow:      | `:rainbow:`      | works in the same way, but code is better organized, **refactored**, **commented** or cleaned up     |
| Fix           | :ambulance:    | `:ambulance:`    | before the commit it didn't work correctly                                            |
| Improvement   | :heart_eyes:   | `:heart_eyes:`   | before the commit it worked in expected way, but now it works better (quicker, nicer) |
| Tiny Update   | :cherries:     | `:cherries:`     | Mostly for updates in spelling, logs                                                  |
| Documentation | :book:         | `:book:`         | updates in rst files, ``static/description`` and doc-related attributes of manifest.  |
| Price updating| :euro:         | `:euro:`         | updates of price attribute in manifest.                                               |
| Translation   | :handshake:    | `:handshake:`    |                                                                                       |
| CI            | :shield:       | `:shield:`       | improve coverage or configure ci tools                                                |
| Port          | :arrow_up:     | `:arrow_up:`     |                                                                                       |
| BackPort      | :arrow_down:   | `:arrow_down:`   |                                                                                       |
| Migration scripts | :ghost:   | `:ghost:`   | Migrations scripts that are used to migrate database to next odoo version                   |
| Removing      | :x:            | `:x:`            |                                                                                       |
| Help is needed| :sos:          | `:sos:`          | On marking modules as **non-instalable** or on adding **new TODO**                    |
| Conflict resolving | :peace_symbol:          | `:peace_symbol:`          | Conflict resolving after merging. Mostly for automatic resolvings |
| Proprietary code | :see_no_evil:  | `:see_no_evil:`  | Update proprietary part of mixed code                                                   |

*  **Don't use** :heart_eyes: until you are sure that the updates is not a *New Feature*, not a *Fix* and not a *Refactoring*. **Definitely use** it for demonstration improvements, UI/UX improvements and similar 

# Version tags

Version tags has to be used after key tags, for example ``:arrow_up::one::two:`` . The version is required for following updates:

* :tada: New Module
* :arrow_up: Port / :arrow_down: Backport
* :x: Removing
* :sos: Marking modules as non-installable
* :shield: Updating version-related updates in CI files
* :book: Updating version in docs (e.g. links) 

| :wink:  | Emoji-code |
|---------|------------|
| :zero:  | `:zero:`   |
| :one:   | `:one:`    |
| :two:   | `:two:`    |
| :three: | `:three:`  |
| :four:  | `:four:`   |
| :five:  | `:five:`   |
| :six:   | `:six:`    |
| :seven: | `:seven:`  |
| :eight: | `:eight:`  |
| :nine:  | `:nine:`   |

# Changelog tags

Use text-only bold tags:

* `**Init version**`
* `**New:** <description of the new feature`
* `**Fix:** <description of the fixed problem> `
* `**Improvement:** <description of the improvement>`

# Updating Docs

Following type of updates require to include doc updates (``README.rst`` or ``doc/index.rst``):

* :zap: New feature -- e.g. describe in ``doc/index.rst`` how to use (check) new feature
* :sparkles:  Major update -- e.g. describe in ``README.rst`` 
  what are the difference between versions from development point of view. 
  If it's a new big feature, then you defenitly have to add info about it to ``doc/index.rst``

# Pull Requests

* **New Modules**: only dev tags are allowed
* **New Features**: dev-only tags approach is *highly recommended*
* **Updating PR by reviewers**: it's recommended to make :cherries:-type updates only. Otherwise just ask developer for changes. 
* **Stable branches**: *only release* tags are allowed
* **Merging PR to Stable branches**: pull request must be remade by developer *(until the updates shall not be splitter into several commits)* in following cases:
  * There is a commit with **Dev tag**
  * There is a commit with **incorrect description** or wrongly choosen release **tag**
  * There are commits that has to be **squashed**:
     * commit with documentation or version updates and commit with corresponding code updates
     * commit that fixes another commit
     * test and new features itself are in different commits
  * There is commit that has to be **splitted**:
     * Different type of updates, e.g. fix and new feature
     * Updates of different modules without shared idea
