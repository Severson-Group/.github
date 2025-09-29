# How to Contribute <!-- omit from toc -->

**Guidelines for contributing content to the repository.**

## Table of Contents <!-- omit from toc -->

- [Purpose of Document](#purpose-of-document)
- [1. File Structure and Conventions](#1-file-structure-and-conventions)
  - [File Structure](#file-structure)
    - [File Naming](#file-naming)
    - [Large Files](#large-files)
- [2. Markdown](#2-markdown)
  - [Language](#language)
  - [Development Environment](#development-environment)
  - [Style](#style)
  - [Markdown Documentation Template](#markdown-documentation-template)
- [3. How to Use Git to Contribute to the Repository](#3-how-to-use-git-to-contribute-to-the-repository)
  - [Git Workflow](#git-workflow)
  - [Branch Naming](#branch-naming)
  
## Purpose of Document

This document explains the procedures, policies, and best-practices for contributing content to the knowledge base.

## 1. File Structure and Conventions

### File Structure

Every folder should have a `README.md` file that acts like a landing page for that folder and explains its contents.

#### File Naming

Files should be named following best practices for their file type.

##### Markdown Documentation (and any other file type not called out below) <!-- omit from toc -->

Use the `dash-case` naming convention:

- Do this: `this-is-my-amazing-file.md` (all lower case, hyphens instead of spaces)
- Not this `thisIsMyAmazingFile.md` nor this `This Is My Amazing File.md`, etc.

Follow this same naming convention for supporting files linked into markdown docs, i.e., images and PDF files.

See the [docs.amdc.dev repository](https://github.com/Severson-Group/docs.amdc.dev) as an example.

##### MATLAB / Simulink <!-- omit from toc -->

Follow the Camel Case naming convention described in the [Knowledgebase's MATLAB article](https://github.com/Severson-Group/KnowledgeBase/blob/main/code/matlab/README.md#style-guidelines).

##### Python <!-- omit from toc -->

Follow the naming convention described in the [Knowledgebase's Python article](https://github.com/Severson-Group/KnowledgeBase/blob/main/code/python/README.md#style-guidelines), which is [snake case](https://en.wikipedia.org/wiki/Snake_case) for most file types.

##### Software <!-- omit from toc -->

When committing software, use the naming convention of the software:

- MATLAB naming convention is [listed here](code/matlab/README.md#style-guidelines)
- Python naming convention is [listed here](code/python/README.md#style-guidelines)

#### Large Files

Don't do it! **Files larger than 15MB should never be committed** *(files less than 300kB are preferred; and files larger than 1 MB should be avoided)*. Large files can be stored in Google Drive and linked into Markdown articles.

In the future, we may also explore using [Git Large File Storage](https://git-lfs.github.com/).

If you accidentally committed a file larger than 15MB:

1. submit a new commit that eliminates this file (i.e., replace it with a smaller file),
2. ensure that the PR is merged via a `Squash and Merge` so that the large file does not appear in the repo history.

## 2. Markdown

### Language

[Markdown](https://en.wikipedia.org/wiki/Markdown) is the primary language for writing documentation in the repository. New contributors are recommended to read up on the Markdown language. [The Markdown Guide](https://www.markdownguide.org/getting-started/) is a particularly complete resource. We recommend keeping their [Cheat Sheet](https://www.markdownguide.org/cheat-sheet/) handy.

### Development Environment

We recommend writing Markdown using Visual Studio Code configured with the Markdown extensions listed [here](tools/VS_Code.md#recommended-extensions). If you are new to Markdown, please set up your workspace in this manner. If you are experienced and know better, we'll leave this to you to decide (consider telling us to revise our KB instructions!)

Users can also edit Markdown directly within GitHub. If you do this, you will need to be careful to ensure that you properly use the Markdown language.

### Style

When you set up you [Development Environment](#development-environment) with [the recommended Markdown extensions](tools/VS_Code.md#recommended-extensions), Visual Studio Code will make style suggestions to you, such as including a blank line before lists and after headings. Please follow these suggestions.

### Markdown Documentation Template

All markdown articles should use the same template as is used for this article. You can copy-paste the following code into a new article as a starter:

```markdown
# Article Name <!-- omit from toc -->

**Brief one sentence mission statement for article.**

## Table of Contents <!-- omit from toc -->

- [Purpose of Document](#purpose-of-document)
- [First Section](#first-section)
- [Second Section](#second-section)
- [Related Issues / PRs](#relevant-issues--prs)

## Purpose of Document

*1 - 3 sentence section describing the purpose of this article.*

## First Section

*First section of article.*

## Second Section

*Second section of article.*
...

## Related Issues / PRs

*Bullet list of all relevant issues to facilitate future readers in learning more about the material of the article.*

- _Issue #120: Route traces for the flux capacitor <-- make this a link to the relevant issue_
- _Issue #130: Create a report on the flux capacitor <-- make this a link to the relevant issue_
- _PR #142: Add report on the flux capacitor field lines <-- make this a link to the relevant PR_
```

## 3. How to Use Git to Contribute to the Repository

### Git Workflow

Content is created and maintained following the typical git workflow outlined in the [group git tutorial](//github.com/Severson-Group/severson_group_git). Please be sure to review the sections on [Pull Requests](https://github.com/Severson-Group/severson_group_git?tab=readme-ov-file#3ii-pull-requests) and [Commit Messages](https://github.com/Severson-Group/severson_group_git#sub_commit_msg).

The contribution steps are as follows:

1. If it doesn't already exist, create an issue for the feature / fix you are planning to implement and assign yourself.
2. Create a separate branch to hold your work in progress and give it a descriptive name. Use [the guidelines below](#branch-naming) for branch naming.
3. Create a [pull request on GitHub](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) to merge your branch into `main` and assign reviewers that are relevant to the topic. Mark the PR as a draft, since it is not yet ready for review. You are asked to create your pull request draft immediately upon creating the branch to facilitate peer review during content creation.
4. Create your content. Markdown documents and Jupyter lab notebooks are the preferred content format. Other existing material (pdfs, word docs) are acceptable, but should be used only when necessary. In these cases, links to source material in the appropriate Shared Drive or Overleaf project are recommended.
5. Request peer review of your PR. Remove the draft attribute of the PR and make a comment to the reviewers stating that it is ready for their attention. Be attentive to review requests until you have sufficient approvals to merge the PR.
6. When your PR is approved, merge via a `Squash and Merge` to create a linear commit history.

### Branch Naming

Branch names should use the following naming convention:

- **Feature branch:** `feature/foo_bar` – shared feature development; other users are allowed to commit. *This is the recommended branch type.*
- **User branch:** `user/my_user_name/foo_bar` – “private” development sandbox per user (if another user wants to add material to this branch, they should use a PR and not commit directly).
