# The ARK Identifier Scheme

This is the working area for the individual Internet-Draft, "The ARK Identifier Scheme".

* [Editor's Copy](https://arks-org.github.io/arkspec/#go.draft-kunze-ark.html)
* [Datatracker Page](https://datatracker.ietf.org/doc/draft-kunze-ark)
* [Individual Draft](https://datatracker.ietf.org/doc/html/draft-kunze-ark)
* [Compare Editor's Copy to Individual Draft](https://arks-org.github.io/arkspec/#go.draft-kunze-ark.diff)


## Contributing

All editing is focused on just one file: draft-kunze-ark.md (formerly .xml).
See the
[guidelines for contributions](https://github.com/arks-org/arkspec/blob//CONTRIBUTING.md).

Contributions can be made by creating pull requests.
The GitHub interface supports creating pull requests using the Edit (✏) button.

## Command Line Usage

Formatted text and HTML versions of the draft can be built using `make`.

```sh
$ make
```

Review the formatted versions in the usual ways, such as,

```sh
$ more draft-kunze-ark-35.txt         # open with text-based pager
$ open draft-kunze-ark-35.html        # open with local web browser
```

If things get stuck in a weird state, other "make" targets may help
to get them unstuck:

```sh
$ make diff
$ make lint
```

See [features](https://github.com/martinthomson/i-d-template/blob/main/doc/FEATURES.md) for more.
Command line usage requires that you have the necessary software installed.  See
[the instructions](https://github.com/martinthomson/i-d-template/blob/main/doc/SETUP.md).

Note: For building locally on my Mac it was necessary to manually install the
Ruby dependencies. Run `make` from the root folder once. It will install
a bunch of dependencies and will likely fail when trying to run `kramdown-rfc`.
When that happens, run the following to install the remaining dependencies:

```sh
$ export BUNDLE_PATH="$(pwd)/lib/.gems"
$ export PATH="${BUNDLE_PATH}/bin:${PATH}"
$ bundle install --gemfile="$(pwd)/lib/Gemfile"
```

Running `make` then worked as expected.

## Submitting Drafts to the Official IETF Site

You can do this manually or automatically. The latter uses GitHub Actions
to manage the process, which you initiate by committing and pushing the
post-review draft, then pushing a tag to create a release.
The tag you use has to include the full name of the draft (without
the ".md" or ".xml") and ending in the _next_ revision number, XY. So if the
latest public revision number is 31, the next is 32.

```sh
$ make
$ git commit -m "cold fusion fixed"
$ git push origin main
$ git tag -a draft-kunze-ark-XY
$ git push origin draft-kunze-ark-XY
```

## Updating the actions

If there's a change of author email, draft title, or draft filename, you must
manually run the "Update generated files" (update.yml) workflow at github.
This workflow, which does not run automatically, will update other workflows
and will overwrite any customizations made to the files

```sh
README.md
CONTRIBUTING.md
.note.xml
.github/CODEOWNERS
Makefile
```
