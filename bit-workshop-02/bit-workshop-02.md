
# BIT Workshop 02

## Agenda

- Git staging patches
- Git rewriting history

### Git staging patches

Have you ever written a lot of code, forgotten to commit but want to commit each part of your code separately? **Git** has a solution for you. You can stage specific parts of your file(s) while temporarily ignoring the rest. For example, you make two changes to `index.html`, i.e., add `<p>Welcome to BIT Code Club</p>` & `<h1>Hello, my name is John Doe</h1>`, you can stage one of the changes, i.e., `<p>Welcome to BIT Code Club</p>` & not the other, i.e., `<h1>Hello, my name is John Doe</h1>`. 

To achieve this, run the following command: `git add -i`. The `-i` flag will open interactive mode providing you will a lot of useful options. The option we are concerned with is **patch**. To **patch**, type `p` or `5` & press <kbd>enter</kbd>. Alternatively, you run the following command: `git add --patch` or `git add -p` (my preference). **Git** will ask you to select the files you wish to partially stage. For each file selected, it will display **hunks** of the file **diff** & ask you to stage them one by one.

```bash
diff --git a/bit-workshop-02/index.html b/bit-workshop-02/index.html
index 9434309..104cda0 100644
--- a/bit-workshop-02/index.html
+++ b/bit-workshop-02/index.html
@@ -7,6 +7,8 @@
     <title>BIT Workshop 02: Git Staging Patches & Git Rebase Interactive Mode</title>
 </head>
 <body>
+    <h1>Hello, my name is John Doe</h1>
     <p>Hello, World!</p>
+    <p>Welcome to BIT Code Club</p>
 </body>
 </html>
\ No newline at end of file
Stage this hunk [y,n,q,a,d,/,s,e,?]?
```

Here is a list of options:

- `y` - stage this unk
- `n` - do not stage this hunk
- `q` - quit
- `a` - stage this and all the remaining hunks in the file
- `d` - do not stage this hunk nor any of the remaining hunks in the file
- `/` - search for a hunk matching the given regex
- `s` - split the current hunk into smaller hunks
- `e` - manually edit the current hunk
- `?` - print help

There are other options that are not in this list. For more information, refer to the resource below.

**Resource:** <https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging>

### Git rewriting history

There are many commands that enable you to rewrite your **Git** history - `git commit --amend`, `git rebase` & `git reflog`. We will only discuss the first two mechanism. 

We often make a mistakes when writing commit messages. The `git commit --amend` command enables you to either edit the staged commit's message or edit the previous commit's message. Also, it is easy to forget to stage a file. Again, you can use the same command to commit the files you wish to stage without changing the commit's message. For example:

```bash
# Edit index.html & main.js
git add index.html
git commit -m "some message" 
# Whoops, I forgot to stage main.js
git add main.js 
git commit --amend --no-edit
```

**Note:** Do not amend an existing commit. 

