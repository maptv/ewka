# Ewka, a custom iosevka font

To create your own custom font,
1. go to https://typeof.net/Iosevka/customizer and generate a `private-build-plans.toml`.
2. `git clone https://github.com/be5invis/Iosevka ~/be5invis/Iosevka --depth=1`
3. `git clone https://github.com/ryanoasis/nerd-fonts ~/ryanoasis/nerd-fonts --depth=1`
4. build the font in a clone of the iosevka repository as described here: https://github.com/be5invis/Iosevka#customized-build

`npm run build -- contents::iosevka-custom `

5. patch your custom font using the nerd-font font-patcher: https://github.com/ryanoasis/nerd-fonts#font-patcher

`for f in ../ttf/*.ttf; do; fontforge -script ~/ryanoasis/nerd-fonts/font-patcher --complete $f; done`


