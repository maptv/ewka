# Ewka, a custom iosevka font

To create your own custom font,
1. go to https://typeof.net/Iosevka/customizer and generate a `private-build-plans.toml`.
2. build the font in a clone of the iosevka repository as described here: https://github.com/be5invis/Iosevka#customized-build

```
git clone https://github.com/be5invis/Iosevka ~/be5invis/Iosevka --depth=1
cd ~/be5invis/Iosevka
cp ~/mskar/ewka/private-build-plans.toml ~/be5invis/Iosevka
npm run build -- contents::ewka
```

3. `git clone https://github.com/ryanoasis/nerd-fonts ~/ryanoasis/nerd-fonts --depth=1`
4. `brew install fontforge`
5. patch your custom font using the nerd-font font-patcher: https://github.com/ryanoasis/nerd-fonts#font-patcher

```
cd ~/be5invis/Iosevka/dist/ewka
mkdir nerd
cd nerd
for f in ../ttf/*.ttf; do; fontforge -script ~/ryanoasis/nerd-fonts/font-patcher --complete $f; done
```

6. Copy the patched font into the right place (which on macOS is `~/Library/Fonts`)

`cp ~/be5invis/Iosevka/dist/ewka/nerd/* ~/Library/Fonts`


