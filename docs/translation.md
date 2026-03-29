# Translation ![](https://hosted.weblate.org/widgets/CutToTheChase/-/CutToTheChase/svg-badge.svg)

![](https://hosted.weblate.org/widgets/CutToTheChase/zh_Hans/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/cs/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/sl/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/it/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/ko/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/de/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/nl/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/fi/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/zh_Hant/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/et/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/fr/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/he/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/hu/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/id/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/lt/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/nb_NO/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/nn/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/fa/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/pl/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/pt/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/pt_BR/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/ro/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/ru/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/sr/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/es/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/sv/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/tr/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/uk/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/vi/CutToTheChase/svg-badge.svg)
![](https://hosted.weblate.org/widgets/CutToTheChase/sk/CutToTheChase/svg-badge.svg)

Thanks to everyone who helped translate the app! 🙌

View a status of [all translations here](https://hosted.weblate.org/projects/CutToTheChase/CutToTheChase/). You are welcome to help translate the app in [Weblate](https://hosted.weblate.org/projects/CutToTheChase/CutToTheChase/). **Do not submit a PR** yourself with translations. Weblate will automatically push translations as a Pull Request in this repo, but this PR is not merged immediately by maintainers.

Master language is English and i18n keys are the English strings.

## Testing translations locally

Because the Weblate PR with translation updates is not merged immediately, your changes made in Weblate will not appear automatically in the nightly build. If you want test new weblate translations you made in the app, you need to:

1. Download the translation for your language from Weblate: **Files -> Download translation**
2. Rename the downloaded `.json` file to: `translation.json`
3. Create a [folder structure](https://github.com/mifi/lossless-cut/tree/master/src/main/locales) somewhere on your computer that looks like this:

```
translations/locales/localeCode
```

You can find a list of the available [`localeCode`s here](https://github.com/mifi/lossless-cut/tree/master/src/main/locales). In our example we will use `nb_NO` (Norwegian 🇳🇴) with this path:

```
/Users/mifi/Desktop/translations/locales/nb_NO
```

4. Now move your `translation.json` file into the folder:

```
/Users/mifi/Desktop/translations/locales/nb_NO/translation.json
```

5. Now run CutToTheChase from the [command line](cli.md), with the special command line argument `--locales-path`. Use the path to the **folder containing the locales folder**, e.g.:

```bash
./CutToTheChase --locales-path /Users/mifi/Desktop/translations
```

Now CutToTheChase will use your language local file.

## Weblate

Note to CutToTheChase maintainers: Weblate [does not allow](https://github.com/WeblateOrg/weblate/issues/7081) any pushes to the weblate CutToTheChase github repository (`https://hosted.weblate.org/git/CutToTheChase/CutToTheChase/`). This means if their repo becomes out of sync with this repo, the translations will be locked and the `master` branch here needs to be synced with their branch. This should normally not happen unless the weblate PR has been accidentally merged with a squash commit.
