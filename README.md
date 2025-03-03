# Show a note when running the ls command

If I'm SSHing into some machine I don't use a lot, or going into a new directory, I run `ls` to see what's inside. Sometimes I'll have some kind of file like DO_THIS.txt, but more often I'll have to rack my brain to figure out what I'm looking at or what I need to do in this directory.

So I thought maybe I should alias `ls` so that it displays the contents of a `.note` file, should it exist, right above the files.

If I need to remember something, I can write a `.note` file in the directory. Later, running `ls` will automatically show me (or others) the note! Using an alias of `ls` rather than a different executable makes sure that I force my future self to see the note even if I forget I made the alias on that machine in the first place. I thought maybe this concept would be useful for others, so I've put instructions on how to do it here.

Here is how you would modify your `ls` command for bash:

```
echo 'ls() { [ -f .note ] && echo -e "📌 Note: $(cat .note)\n"; command ls "$@"; }' >> ~/.bashrc
```

and for zshell:

```
echo 'ls() { [ -f .note ] && echo -e "📌 Note: $(cat .note)\n"; command ls "$@"; }' >> ~/.zshrc
```

To reload the shell and apply your changes, run:

```
source ~/.bashrc  # or source ~/.zshrc for zsh
```
