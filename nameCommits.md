# Name Commits

This guide is a compilation of how to name commits, to help you in your future
work.  It's not meant to be strict rules, but rather guidelines that will make
it easier.
In the guide, every reference taken is written at the end of it. Every section
of the guide cites the reference it is taken from too.

## Main idea of naming a commit

A commit must transmit the changes one has made into his repo. One must write
them thinking  about who would read them: someone who wants to understand
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

### Dani thoughts

- Start focusing on good subjects is a key to write a good commit message.
- Although this guide tells us 50ch is the limit for commit messages, 72 is the
  real (hard) limit. If we overcome 50ch, we musn't overcome 72ch.
- Start with the most important keywords. If we overcome the character limit,
  the end may be truncated.
- On capitalizing, there will be conflicts with other conventions
- Choose one popular convention for life and be consistent.
- Override your choice if in a project, there is another one. You must fit in
  the team, not the contrary.

## Conventional Commits (Conventional Commits)

## ProGit (ProGit book)

The [ProGit](http://progit.org/book/) book doesn't have a really good section
that explains the name of the commits, but it talks about it in section
"Contributing to a Project/Commit Guidelines". In this section, it references to
official documentation of Git Project:
> The Git project provides a document that lays out a number
of good tips for creating commits from which to submit patches — you can read it in the Git source
code in the Documentation/SubmittingPatches file.

Also, it says
> As a general rule, your messages should start with a single line that's no
> more than about 50 characters and that describes the changeset concisely,
> followed by a blank line, followed by a more detailed explanation. The Git
> project requires that the more detailed explanation include your motivation
> for the change and contrast its implementation with previous behavior. [...]
> Write your commit message in the imperative: "Fix bug" and not "Fixed bug" or
> "Fixes bug".

It also provides an adaptation of a template created by Tim Pope (Tim Pope
Template).
As a warning, the authors here also inform the reader the examples of commits'
messages given throughout the boo are not nicely-formatted, but that's for the
sake of brevity.

## Commit advice gcapes (How to write a Good Commit message)

## Git Project Documentation

In the official documentation of Git, it doesn't really explain so much of how to write a good commit, but how the commit
message works in it. To write a good commit, it says the next at the begginning
of the section:
> it’s a good idea to begin the commit message with a single short (no more than 50 characters) line summarizing the change, followed by a blank line and then a more thorough description.

## Tim Pope Template

## References

- [Git No Excuses (Dani Profe)](01-git-noexcuses.draft.html)
- [Conventional Commits](conventionalCommits.com)
- [ProGit book] (<https://git-scm.com/book/en/v2>)
- [Commit advice gcapes- How to write a Good Commit message] (<https://gcapes.github.io/git-course/05-commit-advice/#how-to-write-a-good-commit-message>)
- [Git Docs](https://git-scm.com/docs/git-commit)
- [Tim Pope template](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)
