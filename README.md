# @hatena/prettier-config-hatena

Shareable Prettier Config for @hatena

## インストール

パッケージが GitHub Packages 上でホストされている関係で、インストールするには以下のような手順を踏む必要があります。

1. https://github.com/settings/tokens から `read:packages` にチェックの入ったトークンを発行する
2. パッケージのインストール先のリポジトリにある `.npmrc` か `~/.npmrc` を以下のように書き換える

```
//npm.pkg.github.com/:_authToken=<1で発行されたトークンをここに貼る>
@hatena:registry=https://npm.pkg.github.com/
```

`.npmrc` を書き換えたら以下のコマンドでインストールできます。

```bash
npm install -D @hatena/prettier-config-hatena prettier
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
$ git switch main
$ git pull
$ pnpm version --no-git-tag-version
$ git commit -am "vX.X.X"

$ git push
$ # push すると CI により自動で publish されます
$ # Breaking Changes がある場合など、必要に応じて GitHub の
$ # Release を作成してリリースノートを書きましょう
```
