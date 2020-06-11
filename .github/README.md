# Push With Hooks
[heading__top]:
  #push-with-hooks
  "&#x2B06; Bash script calls pre-push and/or post-push Git hooks"



Bash script calls pre-push and/or post-push Git hooks


## [![Byte size of Push With Hooks][badge__master__push_with_hooks__source_code]][push_with_hooks__master__source_code] [![Open Issues][badge__issues__push_with_hooks]][issues__push_with_hooks] [![Open Pull Requests][badge__pull_requests__push_with_hooks]][pull_requests__push_with_hooks] [![Latest commits][badge__commits__push_with_hooks__master]][commits__push_with_hooks__master]


------


- [:arrow_up: Top of Document][heading__top]

- [:building_construction: Requirements][heading__requirements]

- [:zap: Quick Start][heading__quick_start]

  - [&#x1F9F0; Usage][heading__usage]

- [&#x1F5D2; Notes][heading__notes]

- [:card_index: Attribution][heading__attribution]

- [:balance_scale: Licensing][heading__license]


------



## Requirements
[heading__requirements]:
  #requirements
  "&#x1F3D7; Prerequisites and/or dependencies that this project needs to function properly"


This repository makes use of Git Submodules for tracking dependencies, to avoid incomplete downloads clone with the _`--recurse-submodules`_ option...


```Bash
git clone --recurse-submodules git@github.com:git-utilities/push-with-hooks.git
```


To update tracked Git Submodules issue the following commands...


```Bash
git pull

git submodule update --init --merge --recursive
```


To force upgrade of Git Submodules...


```Bash
git submodule update --init --merge --recursive --remote
```


> Note, forcing and update of Git Submodule tracked dependencies may cause instabilities and/or merge conflicts; if however everything operates as expected after an update please consider submitting a Pull Request.

___


## Quick Start
[heading__quick_start]:
  #quick-start
  "&#9889; Perhaps as easy as one, 2.0,..."


Symbolically link the `git-push-wh` script to a directory accessible within currently logged-in user's _`PATH`_, eg...


```Bash
cd ~/git/hub/git-utilities/push-with-hooks

ln -s "${PWD}/git-push-wh" "${HOME}/bin/git-push-wh"
```



### Usage
[heading__usage]:
  #usage
  "&#x1F9F0;"


Changed directories to a Git repository that has `pre-push` and/or `post-push` Git hooks scripts...


```Bash
cd ~/git/hub/__org__/__repo__
```


Run _`git push-wh <parameters...>`_ instead of _`git push <parameters...>`_, eg...


```Bash
git push-wh srv gh-pages
```


If `pre-push` or `post-push` script(s) are detected (and executable) within the `.git/hooks` or `hooks` directory, then either or both will be called with push arguments.


___


## Notes
[heading__notes]:
  #notes
  "&#x1F5D2; Additional things to keep in mind when developing"


This repository may not be feature complete and/or fully functional, Pull Requests that add features or fix bugs are certainly welcomed.


- if `pre-push` returns an error then the `git-push-wh` script will exit before running _`git push`_ or _`post-push`_

- if `git push` returns an error then the `git-push-wh` script will exit before running _`post-push`_



To test the `git-push-wh` script, try adding the following scripts to a repository...


**`.git/hooks/pre-push`**


```Bash
#!/usr/bin/env bash

printf 'pre-push script called with -> %s\n' "${*}"
```


**`.git/hooks/post-push`**


```Bash
#!/usr/bin/env bash

printf 'post-push script called with -> %s\n' "${*}"
```


... then provide executable permissions to each...


```Bash
chmod u+x .git/hooks/pre-push
chmod u+x .git/hooks/post-push
```


... then run _`git push-wh`_ with or without any additional Git arguments.


___


## Attribution
[heading__attribution]:
  #attribution
  "&#x1F4C7; Resources that where helpful in building this project so far."


- [GitHub -- `github-utilities/make-readme`](https://github.com/github-utilities/make-readme)


___


## License
[heading__license]:
  #license
  "&#x2696; Legal side of Open Source"


```
Bash script calls pre-push and/or post-push Git hooks
Copyright (C) 2020 S0AndS0

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, version 3 of the License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

```


For further details review full length version of [AGPL-3.0][branch__current__license] License.



[branch__current__license]:
  /LICENSE
  "&#x2696; Full length version of AGPL-3.0 License"


[badge__commits__push_with_hooks__master]:
  https://img.shields.io/github/last-commit/git-utilities/push-with-hooks/master.svg

[commits__push_with_hooks__master]:
  https://github.com/git-utilities/push-with-hooks/commits/master
  "&#x1F4DD; History of changes on this branch"


[push_with_hooks__community]:
  https://github.com/git-utilities/push-with-hooks/community
  "&#x1F331; Dedicated to functioning code"

[push_with_hooks__gh_pages]:
  https://github.com/git-utilities/push-with-hooks/tree/
  "Source code examples hosted thanks to GitHub Pages!"

[badge__gh_pages__push_with_hooks]:
  https://img.shields.io/website/https/git-utilities.github.io/push-with-hooks/index.html.svg?down_color=darkorange&down_message=Offline&label=Demo&logo=Demo%20Site&up_color=success&up_message=Online

[gh_pages__push_with_hooks]:
  https://git-utilities.github.io/push-with-hooks/index.html
  "&#x1F52C; Check the example collection tests"

[issues__push_with_hooks]:
  https://github.com/git-utilities/push-with-hooks/issues
  "&#x2622; Search for and _bump_ existing issues or open new issues for project maintainer to address."

[pull_requests__push_with_hooks]:
  https://github.com/git-utilities/push-with-hooks/pulls
  "&#x1F3D7; Pull Request friendly, though please check the Community guidelines"

[push_with_hooks__master__source_code]:
  https://github.com/git-utilities/push-with-hooks/
  "&#x2328; Project source!"

[badge__issues__push_with_hooks]:
  https://img.shields.io/github/issues/git-utilities/push-with-hooks.svg

[badge__pull_requests__push_with_hooks]:
  https://img.shields.io/github/issues-pr/git-utilities/push-with-hooks.svg

[badge__master__push_with_hooks__source_code]:
  https://img.shields.io/github/repo-size/git-utilities/push-with-hooks
