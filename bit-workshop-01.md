
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

Familiarise yourself with this convention, particularly if you are currently enrolled in my courses. However, if you are not, then it is something you should consider adding to your existing Git skills & knowledge.

You are probably wondering, how do I write a message using this convention. A Git commit looks like this:

```bash
git commit -m "<type> (optional scope): <subject>" -m "<optional extended description>" -m <optional footer>
```

Let us see this in action!

Here is a Git commit example:

```bash
git commit -m "style (login): format jsx”
```

Here is a Git commit example with an extended description & footer:

```bash
git commit -m "style (login): format jsx” -m "additional information" -m "PR Close #12345"
```

When should I use an extended description? When a message is greater than 50 characters. Note: This convention is recommended by **GitHub**. However, this can vary from company to company.

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

### GitHub Campus Expert program
