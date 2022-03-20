
# BIT Workshop 02

## Agenda

- Git staging patches
- Git rebase interactive mode

### Git staging patches

Have you ever written a lot of code, forgotten to commit but want to commit each part of your code separately? **Git** has a solution for you. You can stage specific parts of your file(s) while temporarily ignoring the rest. For example, you make two changes to `index.html`, i.e., add `<p>Welcome to BIT Code Club</p>` & `<h1>Hello, my name is John Doe</h1>`, you can stage one of the changes, i.e., `<p>Welcome to BIT Code Club</p>` & not the other, i.e., `<h1>Hello, my name is John Doe</h1>`. 

To achieve this, run the following command: `git add -i`. The `-i` flag will open interactive mode providing you will a lot of useful options. The option we are concerned with is **patch**. To **patch**, type `p` or `5` & press <kbd>enter</kbd>. Alternatively, you run the following command: `git add --patch` or `git add -p` (my preference). **Git** will ask you to select the files you wish to partially stage. For each file selected, it will display **hunks** of the file **diff** & ask you to stage them one by one.

**Resource:** <https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging>

### Git rebase interactive mode