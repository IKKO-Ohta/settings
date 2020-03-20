## 設定ファイルリポジトリ

1. 基本ツールのセットアップ
2. zshをカスタマイズして使用する
3. VSCodeを設定する


### 1. 基本ツールのセットアップ
 homebrew, emacs, (必要なら)zshのデフォルト化を行う。

```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
$ brew install emacs
$ chsh -s /bin/zsh
```

- chrome
https://www.google.com/intl/ja_jp/chrome/

- iTerm2
https://www.iterm2.com/

### 2. zshをカスタマイズして使用する

#### prezto インストール
https://github.com/sorin-ionescu/prezto

```
$ git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
$ setopt EXTENDED_GLOB
for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
  ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
done
```

#### powerline導入 / powerlevel9kテーマ

```
$ git clone https://github.com/powerline/fonts.git && cd fonts && ./install.sh
$ pip install --user powerline-shell
```

iTerm2の設定を開き、profileのテキストタブから

- Roboto Mono for Powerline
- 14pt

に変更。 
さらにカラーテーマを

- Pastel(Dark background)

に変更。


```
$ cp ~/myconfig/zsh/zpreztorc ~/
$ cp ~/myconfig/zsh/zshrc ~/
```

ターミナルを再起動してテーマが`powerlevel9k`になっていることを確認する。

### vscodeを設定する

https://azure.microsoft.com/ja-jp/products/visual-studio-code/

ダウンロードするプラグイン:
- Material Theme

```
$ cp ~/myconfig/vscode/setting/json ~/Library/Application\ Support/Code/User/settings.json
```

