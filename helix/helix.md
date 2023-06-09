## Adding hoon to helix

1. Copy the `languages.toml` file/contents to your config folder. (`~/.config/helix` on linux/mac and `%AppData%\helix` on windows)
2. Copy the `highlights.scm` file to the `helix/runtime/queries/hoon` folder. Or create the directory if it doesn't already exist.
3. Run `hx --grammar fetch`
4. Run `hx --grammar build`
5. Use `hx --health` to check if hoon is installed correctly

More info [here](https://docs.helix-editor.com/guides/adding_languages.html#adding-new-languages-to-helix)
