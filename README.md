# @hatena/prettier-config-hatena

Shareable Prettier Config for @hatena

## インストール

```bash
yarn add -D @hatena/prettier-config-hatena prettier
```

## 使い方

`package.json` に記述する場合

```json
{
  "name": "your-app",
  "version": "0.0.1",
  "prettier": "@hatena/prettier-config-hatena"
}
```

`.prettierrc.json` に記述する場合:

```json
"@hatena/prettier-config-hatena"
```

`.prettierrc.js` に記述する場合:

```js
module.exports = {
  ...require('@hatena/prettier-config-hatena'),
  // You can override the options of a shared prettier
  // configuration in `.prettierrc.js`
  semi: false,
};
```

## リリース方法 (メンテナー向け)

```console
$ git switch master
$ git pull
$ yarn version --no-git-tag-version
$ git commit -am "vX.X.X"

$ # リリースPR作成
$ gh pr create --web --base master --title "Release vX.X.X"
$ # マージすると CI により自動で publish されます
$ # Breaking Changes がある場合など、必要に応じて GitHub の
$ # Release を作成してリリースノートを書きましょう
```
