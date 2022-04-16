# Bark Action

![](https://img.shields.io/github/license/shink/bark-action.svg)
![](https://img.shields.io/badge/language-shell-89E051.svg)
![](https://img.shields.io/github/stars/shink/bark-action.svg?label=stars&logo=github)
![](https://img.shields.io/github/forks/shink/bark-action.svg?label=forks&logo=github)

An action for [Finb/Bark](https://github.com/Finb/Bark)

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
        uses: shink/bark-action@v1
        with:
          host: ${{ secrets.BARK_HOST}} # not required
          key: ${{ secrets.KEY }}   # Your secret key
          title: Message title
          body: Message body
          sound: alarm
          isArchive: 1
          url: https://yuanhaoji.com
          automaticallyCopy: 1
          copy: Content copied to clipboard
          group: Message group
          icon: Message icon url
```

> 其中，只有 `key` 字段是必填的

- `host`: 推送地址, 默认值 https://api.day.app
- `title`: 标题（比内容字号粗一点）
- `body`: 内容
- `sound`: [推送铃声](https://github.com/Finb/Bark/tree/master/Sounds)
- `isArchive`: 是否保存到历史记录（`1` 为保存，其他值为不保存）
- `url`: 将跳转到 url 的地址（发送时，URL 参数需要编码）
- `automaticallyCopy`: 携带该参数时，将自动复制推送内容到剪贴板
- `copy`: 携带该参数时，只复制该参数的值
- `group`: 消息分组
- `icon`: 消息图标地址

## License

[MIT](LICENSE)
