_Facsimile Skeleton_ Project
==========================

The _skeleton_ project maintains build files common to all other _Facsimile_ projects (termed _client_ projects), and is
intended to ensure the following:

- Common set of _SBT_ plugins, all configured to use the current supported version.
- Common core build, so that all _Facsimile_ projects are built with the same version of the _Scala_ compiler, and use
the same compiler settings, test tools, etc.
- Common source formatting and configuration, so that all _Facsimile_ sources appear consistent across projects.

# How to use.

Files common to all _Facsimile_ projects should be included as part of this project, after which they are maintained as
part of this project, with changes being merged into _client_ projects.

**Under no circumstances should client project make local changes to _skeleton_-maintained files. This will lead to
_git_ conflicts and inconsistencies.**

In order to import changes to _skeleton_-maintained files into _client_ applications, the client applications should
define a remote repository as follows:

```
git remote add skeleton https://github.com/Facsimile/skeleton.git
```

After this has been done, changes to _skeleton_ files can be merged into the _client_ project with the following
command:

```
git pull skeleton skeleton
```

**Under no circumstances can a _client_ project `push` changes to the _skeleton_ project!**

# Making Changes to _Skeleton_ Files

## The `skeleton` Branch

Changes to files belonging to the _skeleton_ project must be made on the `skeleton` branch of this project; files in
this branch will be merged into the _skeleton_ `master` branch (see below) as well as into _client_ projects.

## The `master` branch

The `master` branch of the _skeleton_ project contains files—such as this `README.md` file—that *must not* be merged
into _client_ projects, as well as the files maintained by the `skeleton` branch.