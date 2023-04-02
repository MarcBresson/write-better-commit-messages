# Write better commit messages

Guidelines and template to write better commit messages

- [Description](#description)
  - [Subject line](#subject-line)
  - [Body](#body)
  - [Footers](#footers)
  - [Common commits type](#common-commit-types)
- [Example](#example)
- [Guidelines summary](#guidelines-summary)
- [Commit template](#commit-template)
  - [Template file](#template-file)
  - [Configure git](#configure-git)

## Description

Inspired from [https://www.conventionalcommits.org/en/v1.0.0/#summary](https://www.conventionalcommits.org/en/v1.0.0/#summary)

### Subject line

A good commit consists of a subject line where you can find:
- the mandatory [commit type](#common-commit-types) which must be a noun.
- an optional scope inside parenthesis which must be a noun. A commit may not refer to the entire project but just the API for example.
- if the commit include a breaking change, either a `!` must be inserted before the colon or `BREAKING CHANGE` must be in the footers.
- the mandatory subjet description. It is written using the imperative tense (e.g. `add new colour format`). It is separated from the commit and scope by a colon and space.

The subject line must be kept short (typically under 50 characters).

### Body

The body is separated from the subject by a blank line. It provides additional context and explain *what* and *why* the change has been made.
It is free form and can be of multiple separated paragraphs that should be wrapped at 72 characters for the sake of lisibility.

### Footers

A commit can have multiple footers separated from the body by a blank line. It consists of tokens written in [Kebab-case](https://en.wiktionary.org/wiki/kebab_case#English) (hyphens in place of whitespace characters), followed by either `: `(colon space) or ` #`(space hash), followed by a value.

If used, the token `BREAKING CHANGE` must be written in uppercase and can use a whitespace or a hyphen.

### Common commit types

Inspired from [https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type)

- doc: Documentation only changes
- feat: A new feature
- fix: A bug fix
- perf: A code change that improves performance
- refactor: A code change that neither fixes a bug nor adds a feature
- style: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- test: Adding missing tests or correcting existing tests
- build: Changes that affect the build system or external dependencies
- ci: Changes to the CI configuration files and scripts

## Example

```
doc(api): create a commit guidelines template

Too often we see different commits conventions used inside one
project. This set of easy rules is there for creating an explicit
commit history.

And this is another body paragraph because why not ?

BREAKING-CHANGE: the template only works with git>=1.0
Reviewed-by: SomeOne
Refs: #123
```

## Guidelines summary

Inspired from [https://chris.beams.io/posts/git-commit/](https://chris.beams.io/posts/git-commit/)

1. Start the subject by a commit type
2. (optional) Specify a scope after the type
3. Use the imperative tense in the subject line
4. Limit the subject line to 50 characters
5. Separate subject from body with a blank line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how
8. Separate footers from body with a blank line
9. Footer's tokens are written in Kebab-case and followed by `: `

## Commit template

Whenever you commit using `git commit`, git opens your favorite text editor with a template. You can create a custom template to always remember the guidelines aforementioned.

### Template file

Put the next template inside a `.gitmessage` file in your home directory (in windows `C:\users\username`, in macOS `/users/username`)

```
# from https://github.com/MarcBresson/write-better-commit-messages
# (e.g. "doc(api): create a commit guidelines template")
# No more than 50 chars. ### 50 chars is here:  #
<type>(<optional scope>): <subject>
# Blank line between title and body.

# Wrap at 72 chars. ####################### which is here:  #
<Explain *what* and *why* (not *how*)>
# Blank line between body and footer.

# Optional footers (e.g. Refs: #123)

# 1. Start the subject by a commit type
# 2. (optional) Specify a scope after the type
# 3. Use the imperative tense in the subject line
# 4. Limit the subject line to 50 characters
# 5. Separate subject from body with a blank line
# 6. Wrap the body at 72 characters
# 7. Use the body to explain what and why vs. how
# 8. Separate footers from body with a blank line
# 9. Footer's tokens are written in Kebab-case and followed by `: `
```

### Configure git

After having saved your template file, just type the following command in a console:

```bash
git config --global commit.template ~/.gitmessage
```
