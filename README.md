# Instruction

This repo holds tips for FPGA project management.


# Project file managment structure

- \<pj\_name\>

    - algorithm
    - fixed_point
    - data
    - docs
    - refs
    - fpga
        - \<eda\_name\>\_\<pj\_name\>
        - sim
            - \<module_name\>
            - ...
        - src
        - tb
            - \<module_name\>
            - ...
        - testcase
            - \<module_name\>
            - ...
        - \<others\>
    - \<others\>


# Semantic versioning

X.Y.Z

X is the **major** version, corresponding to solution changes.

Y is the **minor** version, corresponding to functionallity changes.

Z is the **patch** version, corresponding to bug fixing.

Referenced from [Semantic Versioning](https://semver.org/).


# Git specification

Atomic commit should be the first choice for version and file management with Git.
Atomic commit signifies that a commit should be the smallest complete unit of change.

The branch mergence should be finished by `git commit` operation.
On the other hand,
`git rebase` should be considered when facing git error correcting or similar issues.
Project error should be fixed with another commit with corresponding messages.


## Git message format

Git message format is referenced from
[conventionalcommits](https://github.com/conventional-commits/conventionalcommits.org/blob/master/content/v1.0.0/index.md)
and [angular](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines).

```
<type>[(<scope>)][!]: <description>

[<body>]

[<footer>]
```

`<type>` must be one of following:
- chore, changes not directly affect main design
- docs, changes of documentations
- feat, changes for a new feature
- fix, changes to fix a bug
- perf, changes to improve performance
- refactor, changes of codes structure not affecting functions
- revert, revert changes with `git revert`
- style, changes about formatting code style
- test, changes of verification or validation

Optional `<scope>` could be:
- alg, algorithm
- fxp, fixed-point modeling
- rtl, register transmission level
- onb, onboard

Optional `!` could be used to mark significant changes.

`<description>` must contain succinct description of the change.
Use lowercase words, imperative tense, and no dot `.` at the end.

Optional `<body>` could include the motivation for the change and more details about the change.

Optional `<footer>` could contain other information about siginificant changes,
such as corresponding issues etc.


