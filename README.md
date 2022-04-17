# Bark Action

![](https://img.shields.io/github/license/monlor/bark-action.svg)
![](https://img.shields.io/badge/language-shell-89E051.svg)
![](https://img.shields.io/github/stars/monlor/bark-action.svg?label=stars&logo=github)
![](https://img.shields.io/github/forks/monlor/bark-action.svg?label=forks&logo=github)

Fork from https://github.com/shink/bark-action

An action for [Finb/Bark](https://github.com/Finb/Bark)

[Chinese document | 中文文档](README_zh.md)

## Usage

```yml
name: Bark Action

on: [push]

jobs:
  job:
    name: Push notification job
    runs-on: ubuntu-latest
    steps:
      - name: Push notifications
        uses: monlor/bark-action@v3
        with:
          host: ${{ secrets.BARK_HOST}} # not required
          key: ${{ secrets.BARK_KEY }}   # Your secret key
          title: Message title
          body: Message body
          sound: alarm
          isArchive: 1
          url: https://www.monlor.com
          automaticallyCopy: 1
          copy: Content copied to clipboard
          group: Message group
          icon: Message icon url
```

> Among them, only the `key` parameter is required

- `host`: bark service host, default is https://api.day.app
- `title`: Message title (a bit thicker than the content font size)
- `body`: Message content
- `sound`: [Push notification sound](https://github.com/Finb/Bark/tree/master/Sounds)
- `isArchive`: Whether to save to the historical record (`1` means save)
- `url`: The address that will be redirected to the url (when sending, URL parameters need to be encoded)
- `automaticallyCopy`: When this parameter is carried, the content will be automatically copied to the clipboard
- `copy`: When carrying this parameter, only the value of this parameter will be copied
- `group`: Message group
- `icon`: Message icon url

## License

[MIT](LICENSE)
