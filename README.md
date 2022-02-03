Repro for https://github.com/nesbox/TIC-80/issues/1827

## How to reproduce

- `cd` into this directory
- Launch TIC-80 with the following command:
```sh
path\to\tic80.exe --fs=. --cmd "load game.js & load code.js code & run" --keepcmd
```

### Normal behavior:

- Change the "HELLO WORLD" text
- CTRL+R inside TIC-80
- Check that the text has changed

### Buggy behavior:

- ESC > "Close game"
- Go inside the sprites editor and change a sprite
- CTRL+R **twice** to bypass the confirmation screen
- Now all changes inside code.js will be ignored

❗ This bug will persist if you reload TIC-80 with the same `load...` argument. To clear it:

- Either close and relaunch TIC-80 without any argument
- Or close TIC-80, change the code, and relaunch TIC-80 with the `load ...` argument
