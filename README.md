# Alias for ls that displays a note

If I'm SSHing into some machine I don't use a lot, or going into a new directory, I run `ls` to see what's inside. Sometimes I'll have some kind of file like DO_THIS.txt, but more often I'll have to rack my brain to figure out what I'm looking at or what I need to do in this directory.

So I thought maybe I should alias `ls` so that it displays a `.note` file, should it exist, right above the files.

Here is how you would install it for bash:

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
