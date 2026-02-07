# Obsidian TODO
Create an entry in a TODO document in an Obsidian vault without opening Obsidian.

# Dependencies
- Gnu `getopt`. Installed by default on most Linux distros. You may be able to
  install it on MacOS with `brew install gnu-getopt` or `brew install util-linux`,
  though I have not verified this.

# Configuration
- Modify todo.conf so the variable `todopath` contains the absolute path to the
  TODO markdown file in your obsidian vault (replace the `/path/to/todo.md` with
  the actual path).
- Either copy `todo` and `todo.conf` into a directory in your `$PATH`, or
  symbolically link to `todo` from a directory in `$PATH`.

# Use
Use `todo --help` to get the list of command line arguments.

Example:
```shell
todo "make a valid example of using the todo script"
```
will add the following line at the end of your TODO markdown file:
```markdown
- [ ] make a valid example of using the todo script
```

Example with due date:
```shell
todo --due 2026-02-07 "create a shell script to add todos to Obsidian"
```
will add the following line at the end of your TODO markdown file:
```markdown
- [ ] create a shell script to add todos to Obsidian [due::2026-02-07]
```

Example with a hidden tag:
```shell
todo --tag foo::bar "calibrate the frobozinator"
```
will add the following line at the end of your TODO markdown file:
```markdown
- [ ] calibrate the frobozinator (foo::bar)
```
Multiple tags are supported.
