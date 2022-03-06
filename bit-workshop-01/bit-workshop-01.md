
# BIT Workshop 01

## Agenda

- Git commit message naming conventions
- Git submodules
- GitHub Campus Expert program

### Git commit message naming conventions

You have written many commit messages thus far in your **BIT** degree. However, based on my observations, you could format your messages more concisely, and it only takes a little bit of care. We will discuss a message convention (not a standard) heavily adopted in the industry.

A message is broken down into four components - type, scope (optional), subject, extended description (optional) & footer (optional).

List of types:
* build: build related change, i.e., installing application dependencies.
* chore: change that an end-user will not see, i.e., configuring files for but not limited to code formatting, code linting & version control.
* feat: a new feature or piece of functionality that an end-user will see, i.e., a register or login page.
* fix: a bug fix, i.e. an issue with the register or login page.
* docs: documentation related change, i.e., changing **README.md** file.
* refactor: something that is neither a feat nor fix, i.e., a semantic code change.
* style: style-related change, i.e., formatting a file or piece of code.
* test: an automation test change, i.e., adding a new test file or updating an existing test file.

What is a scope? A noun referring to functionality in your codebase, i.e., authentication. 

Familiarise yourself with this convention, particularly if you are currently enrolled in my courses. However, if you are not, then it is something you should consider adding to your existing **Git** skills & knowledge.

You are probably wondering, how do I write a message using this convention. A **Git** commit looks like this:

```bash
git commit -m "<type> (optional scope): <subject>" -m "<optional extended description>" -m <optional footer>
```

Let us see this in action!

Here is a **Git** commit example:

```bash
git commit -m "style (login): format jsx"
```

Here is a **Git** commit example with an extended description & footer:

```bash
git commit -m "style (login): format jsx" -m "additional information" -m "PR Close #12345"
```

When should I use an extended description? When a message is greater than 50 characters. **Note:** This convention is recommended by **GitHub**. However, this can vary from company to company.

What happens if I want view a commit with a specific type or scope? 

```bash
git log --oneline | grep <type>
```

Here is a Git log example:

```bash
git log --oneline | grep style
```

Here is a Git example with multiple types:
 
```bash
git log --oneline --grep "^build\|^feat\|^style"
```

### Git submodules

You probably have encountered the following:

What is happening? You have a repository with a repository.

**Git submodules** refer to a specified **Git** repository at a particular snapshot, i.e., commit in time. Also, **submodules** enable a host **Git** repository to track the commit history of the specified repository.

Our applications often depend on external code. The code can be implemented in various ways, i.e., copying & pasting into a host **Git** repository or using a package manager, i.e., **Gems**, **NPM** or **Pip**. Both of these approaches have downsides, such as a loss of upstream changes to the specified repository & version management.

**Submodules** do not track **Git** refs & branches. Also, **submodules** do not automatically update when a host **Git** repository is updated.

When should I use **Git submodules**? When you need to maintain a strict version management of your external code's dependencies.

Let us see this in action!

```bash
cd bit-workshop-01
git submodule add https://github.com/Grayson-Orr/op-bit-workshops-external-code
git status
```

What is happening? 
- Change directory to `bit-workshop-01`.
- When the command `git submodule add <url>` is run, **Git** will clone the specified repository as a **submodule**. 
- View the current state of the host **Git** repository.

You will notice a `.gitmodules` file & `op-bit-workshops-external-code` directory have been created. View the `.gitmodules` file. You see the following:

```md

```

### GitHub Campus Expert program