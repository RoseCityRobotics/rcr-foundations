# Editors: nano and vim

Editing text files is a routine task when programming and administering
systems.  Two popular terminal editors are **nano** and **vim**.

## Nano (beginner‑friendly)

Nano is simple and intuitive.  To create or edit a file, run:

```bash
nano README.md
```

The bottom two lines of the screen show shortcuts.  Use **Ctrl+O**
(**Write Out**) to save, **Enter** to confirm, and **Ctrl+X** to exit.

Nano is ideal when you just need to quickly edit configuration files or
write small scripts.

## Vim (powerful once learned)

Vim has a steeper learning curve but offers unparalleled efficiency
once you master it.  Open a file:

```bash
vim README.md
```

Vim has modes.  When you start, you are in **normal mode**.  Press
**i** to enter **insert mode** and start typing.  Press **Esc** to
return to normal mode.  Common commands in normal mode:

* `:w` – save the file.
* `:q` – quit Vim.
* `:wq` – save and quit.
* `u` – undo the last change.

There are many tutorials online (see the resources) to help you learn
Vim’s modal editing and navigation.

## Exercise

1. Use nano to create a file called `todo.txt` and write a shopping
   list.  Save and exit.
2. Open the file in Vim and append another item.  Save and quit.