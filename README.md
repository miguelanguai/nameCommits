# Name Commits

This guide is a compilation of how to name commits, to help you in your future
work.  It's not meant to be strict rules, but rather guidelines that will make
it easier.

Every piece of information written here is referenced at the end of this guide.

## Index of contents

- Main idea of naming a commit
- Summary of best practice
- Teacher thoughts
- Conventional Commits
- ProGit
- Commit advice gcapes (How to write a Good Commit message)
- Git Project Documentation
- Tim Pope Template
- Good practice to write commits in Git - midudev
- Fix Github Issues
- Interesting Repositories to see
- Devil's Advocate - "Git commit messages are useless", Eli Schleifer
- References

## Main idea of naming a commit

A commit must transmit the changes one has made into a repo. One must write
them thinking about who would read them: someone who wants to understand
what he did (i.e., himself), and someone else who wants to know why this change
was done. The latter person should be able to look at the diff between two tags
and see what changed. If it takes more than five lines for him to do so, then
the commit needs rewriting. Well written commit messages make reviewing code
easier.

There are many conventions for creating commit messages. I'll show them all and
give some examples of each one.

## Summary of best practice (7.3 Git No Excuses - Commit advices gcapes)

1. Separate the subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

An example of this would be :

```commit
Change headings for SEO

All headings from H1 to H2 to make site more accessible
```

### Teacher thoughts

- Start focusing on good subjects is a key to write a good commit message.
- Although this guide tells us 50ch is the limit for commit messages, 72 is the
  real (hard) limit. If we overcome 50ch, we musn't overcome 72ch.
- Start with the most important keywords. If we overcome the character limit,
  the end may be truncated.
- On capitalizing, there will be conflicts with other conventions
- Choose one popular convention for life and be consistent.
- Override your choice if in a project, there is another one. You must fit in
  the team, not the contrary.

## Conventional Commits

It's a lightweight convention on top of comit messages. This convention
dovetails with SemVer (for more info, see SemVer class notes section, the
previous one to Conventional Commits section, or go to [Official SemVer
Docs](https://semver.org/)), by describing the features, fixes and breaking
changes
made in commit messages. The commit message should be structured as follows:

>\<type>[optional scope]: \<description>
>
> [optional body]
>
> [optional footer(s)]
The commit contains the following structural elements, to communicate intent to
the consumers of your library (or collaborators, or so):

- fix: A commit of type `fix` patches a bug in the code (it correlates with
  PATCH in SemVer).
- feat: A commit of type `feat` introduces a new feature (MINOR).
- BREAKING CHANGE: If a commit has BREAKING CHANGE in the footer or appends a !
  after the type/scope, introduces a breaking API change (MAJOR). It can be part
  of commits of any type.
- types other than  `fix:` and `feat:` are allowed, as `build`, `chore`, `ci:`,
  `docs:`, `style:`, `refactor:`, `perf:`, `test:` and others
- footers other than BREAKING CHANGE may be provided and follow a convention
  similar to git trailer format.

### Examples

Now, some examples with Conventional Commits:

- Commit message with description and breaking change footer

```git
feat: add user image

BREAKING CHANGE: The user has an image from now on
```

- Commit message with ! to draw attention to breaking change

```git
feat!: send an email to the user every week to show new products on the web
```

- Commit message with both ! and BREAKING CHANGE footer

```git
feat!: senda an email to the user every week to show new products on the web

BREAKING CHANGE: Now users receive  emails every week informing them of new products added to the website
```

- Commit message with no body

```git
docs: add guide howToUseAPI.md
```

- Commit message with scope

```git
feat(lang): add Spanish language
```

- Commit message with multi-paragraph body and multiple footers

```git
refactor: change the function sum

Change the function sum to be able to have more than 2 parameters. 
```

### Relation to Semantic Versioning

`fix` type commits should be translated to PATCH releases. `feat` type commits
should be translated to MINOR releases. Commits with `BREAKING CHANGE` in the
commits, regardless of type, should be translated to MAJOR releases.

## ProGit (ProGit book)

The [ProGit](http://progit.org/book/) book doesn't have a really good section
that explains the name of the commits, but it talks about it in
 "Contributing to a Project/Commit Guidelines". In this one, it references to
official documentation of Git Project:
> The Git project provides a document that lays out a number
of good tips for creating commits from which to submit patches — you can read it
in the Git source code in the Documentation/SubmittingPatches file.

(see Git Project Documentation section)

Also, it says:
> As a general rule, your messages should start with a single line that's no
> more than about 50 characters and that describes the changeset concisely,
> followed by a blank line, followed by a more detailed explanation. The Git
> project requires that the more detailed explanation include your motivation
> for the change and contrast its implementation with previous behavior. [...]
> Write your commit message in the imperative: "Fix bug" and not "Fixed bug" or
> "Fixes bug".

As a warning, the authors here also inform the reader the examples of commits'
messages given throughout the book are not nicely-formatted, but that's for the
sake of brevity.

It also provides an adaptation of a template created by Tim Pope (see Tim Pope
Template section).

## Commit advice gcapes (How to write a Good Commit message)

These are the same as the ones in the classnotes (Summary of Best Practice). It
also has another tips, like Commit anything that cannot be automatically
recreated or when to commit changes. But, as they aren't related to the subject
I'm describing in this guide,  I won't put them here.

## Git Project Documentation

In the official documentation of Git, it doesn't really explain so much of how
to write a good commit, but how the commit
message works in it. To write a good commit, it says the next at the begginning
of the section:
> it’s a good idea to begin the commit message with a single short (no more than
> 50 characters) line summarizing the change, followed by a blank line and then
> a more thorough description.

## Tim Pope Template

Here's a model Git commit message:
> Capitalized, short (50 chars of less summary)

- The first line is treated as the subject of an email and the rest of the text
  as the body.
- The blank line separating the summary from the body is critical
(unless you omit the body entirely).
- Write your commit message in the imperative:  "Fix bug for xyz", not "fixes
  bug for xyz" or "fixed bug for xyz".
  - Why this convention? it matches up with commit messages generated by
    commands like git merge and git revert.
- Further paragraphs come after blank lines

Then he talks about the reason of why wrapping commit messages to 72ch is
important and which adjustments to perform to solve some problems that may
arise. Then he says:
> More important than the mechanics of formatting the body is the practice of
> having a subject line [...] and always, always follow it with a blank line.
> This first line should be a concise summary of the changes introduced by the
> commit; if there are any technical details that cannot be expressed in these
> strict size constraints, put them in the body instead.

As we can see, it is not different from the Pro Git book guidelines.

Example:

```commit
Change headings for SEO

All headings from H1 to H2 to make site more accessible
```

## Good practice to write commits in Git - midudev

This are the recommended practices by midudev, a good-known person in the
development industry:

1. Use imperatives (Add, Change, Fix, Remove,...)
   Understand each commit, not as a message of what we have done, but as an
   instruction to change the status of the project. It's better for
   understanding with this sentence:
   "If I apply this commit, then this commit will...":
   - Add a new search feature
   - Fix a problem with the nav
   - Change the background color
   - Remove a variable
2. Don't use period in your messages.
   Only commas are necessary (not always) for our commit messages. Each char
   counts when creating a commit message. Don't waste them needlessly.
3. Use 50 characters as maximum for your commit message
   Make your message clear, direct and concise.
4. Add all the necessary context in the commit body.
   When adding a body to our commit, it's better to use `git commit` than
    `git commit -m "only the commit title here"`
5. Use a prefix for your commits to make them more semantic.

   ```git
    <commit-type>[scope]: <description>
   ```

   and these would be the prefixes:
   - feat
   - fix
   - perf
   - build
   - ci
   - docs
   - refactor
   - style
   - test
6. Consider using utilities to do commit.
With [commitlint](https://commitlint.js.org/#/), you can make your commits
semantic, easy-to-read and follow the
convention you choose. If not, it tells you where you are failing in:

```bash
# Install commitlint cli and conventional config
npm install --save-dev @commitlint/{config-conventional,cli}
# For Windows:
npm install --save-dev @commitlint/config-conventional @commitlint/cli

# Add hook to resend the commit message
npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'
```

With [commitizen](https://commitizen-tools.github.io/commitizen/), you can use a
command line to make you choose the type of
commit. Thus, you won't depend on doing this manually in the commit message.

## Fix Github Issues

There is a special feature commits have:  they close issues when pushed to
GitHub. This means that if you include the issue number in the commit message
like so:

```git
git commit -m "fix: function sum. Fixes #4"
```

You will close  Issue #4 in your Github Remote Repository with this commit! You
can also reference multiple issues by adding more `#` symbols before the issue
number.
You can close issues with words `Fixes`,`Fixed`, `Resolves`, or `Resolved`.

For more information see [Closing Issues via Commit
Messages](https://github.blog/2013-01-22-closing-issues-via-commit-messages/)

## Interesting Repositories to see

I have searched throughout GitHub repositories to see if there was a guide made
to name repositories like I'm making at the moment, but I didn't find anything
similar to the thing I was looking for. In my searching, however, I have found
very interesting repositories that can help you in the naming of your commits:

- [Requirements for commit
  names](https://github.com/Oleg-Kolosov/Requirements-for-Commit-Names)
  - This repository shows how to name commits according to the AngularJS commit
    message convention:

      ```git

      init   (hw_3):    add solutions for tasks
      <type> (<scope>):  <short summary>
        │       │             │
        │       │             └─⫸ Summary in present tense. Not capitalized. No period at the end.
        │       │
        │       └─⫸ Commit Scope: hw_1|hw_2|hw_3|hw_4|hw_5
        │
        └─⫸ Commit Type: build|docs|feat|fix|perf|refactor|test|init
        
      ```

    - Type section: Must be of the following
      - build
      - ci
      - docs
      - feat
      - fix
      - perf
      - refactor
      - test
    - Scope section: The name of the npm package affected (as regular
      repositories can be others than Angular, its use is optional).
    - Summary: For providing a short description of the change. What is the
      change and why is it made.
  - Example:

  ```git
    git commit -m "docs: adding new feature to README.md"
  ```

- [Smart commit](https://github.com/sbimochan/smart-commit)
  - This repository is a shell script that creates a commit prefixed with the
    current branch name you are working in. Example:

    ```shell
    # We are working in tests branch
    commit "test85"
    # translates to
    git commit -m "tests: test85"
    ```

- [Commit Message Guidelines](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53)
Another guideline of recommendations of how to write a commit. It's really
similar to ProGit book explanation. The only difference is in the characters
limit for the summary (ProGit says 50, robert here is more flexible and asks for
72). Instead, he wrote a set of tips that are really useful:
  - Describe why a change is being made.
- How does it address the issue?
- What effects does the patch have?
- Do not assume the reviewer understands what the original problem was.
- Do not assume the code is self-evident/self-documenting.
- Read the commit message to see if it hints at improved code structure.
- The first commit line is the most important.
- Describe any limitations of the current code.
- Do not include patch set-specific comments.

> NOTE: this guide is not in Robert's Github profile, it is in Github Gist
> profile.

## Devil's Advocate - "Git commit messages are useless", Eli Schleifer

> DISCLAIMER:  The following section contains a 3rd opinion, which may not
> reflect the
views of the author of this guidelines or any other party.

[Git commit messages are
useless](https://trunk.io/blog/git-commit-messages-are-useless?utm_source=tldrwebdev)
tells us how commit messages have no meaning nowadays. BUT, not all of them. He
says that commits at the main branch are smart, logical and needed, but not the
ones in "your random PR branch which will be squash-merged into the main",
because they are only relevant for the author, and no one else.

In the article,
he also shows how to configure git not to make commits mandatory.

## References

- Git No Excuses (Dani Profe)
- [Conventional Commits](conventionalCommits.com)
- [Official SemVer Docs](https://semver.org/)
- [ProGit book](https://git-scm.com/book/en/v2)
- [Commit advice gcapes- How to write a Good Commit
  message](https://gcapes.github.io/git-course/05-commit-advice/#how-to-write-a-good-commit-message)
- [Git Docs](https://git-scm.com/docs/git-commit)
- [Tim Pope
  template](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
- [Buenas prácticas para escribir commits en Git - midudev](https://midu.dev/buenas-practicas-escribir-commits-git/)
- [Git commit messages are
useless](https://trunk.io/blog/git-commit-messages-are-useless?utm_source=tldrwebdev)
- [commitizen](https://commitizen-tools.github.io/commitizen/)
- [commitlint](https://commitlint.js.org/#/)
- [Closing Issues via Commit
Messages](https://github.blog/2013-01-22-closing-issues-via-commit-messages/)
