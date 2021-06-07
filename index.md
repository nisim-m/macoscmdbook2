# ［新版 zsh&bash対応］macOS×コマンド入門
──ターミナルとコマンドライン、基本の力

[技術評論社](https://gihyo.jp/book/2020/978-4-297-11225-7/)<br/>
[Amazon](https://www.amazon.co.jp/exec/obidos/ASIN/4297112256/?ie=UTF8&linkCode=shr&tag=utopia33-22)  
2020.4.18

## macOS Big Sur（11.4）およびApple M1チップ搭載Macについて

本書の動作確認はmacOS Catalina（10.15）で行っています。
本書で取り上げているコマンドの多くは、
macOS Mojave（10.14）以前のバージョンにも収録されていますが、
実際に使用する際には各コマンドのマニュアルやヘルプもあわせて確認してください。
マニュアルやヘルプの確認方法は、3.3 節「コマンドの基礎知識」で解説しています。

次バージョンであるmacOS Big Sur（11.0）および
2020年末に発売されたApple M1チップ搭載のMac（以下、M1 Mac）においても、
本書で扱っているコマンドおよびコマンドラインについては共通です。

### Big SurおよびM1 Macに関する補足情報

バージョンアップに伴う補足情報は以下のとおりです。
なお、本項はmacOS Big Sur バージョン11.4での実行内容に基づいています。

| ページ | 内容 |
| ---- | ---- |
| 4.2(p.65) | パーティションの作成方法が変更されており、デフォルトの状態では、ディスクユーティリティで「Macintosh HD」がグレーで表示され、その下に「com.apple.update-XXXX」が表示されます。ディスクユーティリティの操作方法および本書で解説しているdiskutilコマンドの使用方法は共通です。インストールの状況によりdisk1～等の番号が変わりますので、お使いの環境に合わせて読み替えてください。|
|5.2(p.86)|_bashを使っている環境では、「.bash_history」のほかに「.bash_sessions」というディレクトリがある。_ 👉 zshでも同様に「.zsh_sessions」ディレクトリが作成されるようになりました。|
|10.2(p.257、259)|ネットワークユーティリティ（Network Utility.app）は廃止されました[<a href="images/networkutility.png">画像</a>]。本書で解説しているifconfigコマンドやnetworksetupコマンドは共通です。|
|10.1(p.244)|[参考情報]M1 Macの場合、`uname -a`で表示されるハードウェア情報は`arm64`、`uname -p`で表示されるCPUアーキテクチャは`arm`になります。【`uname -a`例】`Darwin mbpro 20.5.0 Darwin Kernel Version 20.5.0: Sat May  8 05:10:31 PDT 2021; root:xnu-7195.121.3~9/RELEASE_ARM64_T8101 arm64`|

## Homebrew 3.0 について

本書は執筆時点の最新バージョンであるHomebrew 2.2に基づいて制作しておりますが、
2021年2月にリリースされた Homebrew 3.0 では以下の点が変更されています。

- `brew cask` が廃止されました。
- M1 Macに対応しました。M1 Mac環境でインストールした場合、インストール先のディレクトリは`/opt/homebrew/`となります。
参考：[Homebrew 3.0.0](https://brew.sh/2021/02/05/homebrew-3.0.0/)

M1 Mac環境でインストールした場合、PATHの追加が必要です。
インストール時のメッセージに追加用のコマンドが表示されているので、`echo`の行を実行してください。
すぐにbrewコマンドを使用したい場合は、その次の`eval`の行を実行してください。
`eval`は、引数を連結してシェルで実行するというコマンドです（クイックリファレンス p.297）。

ユーザ名や設定ファイル名は実行時の環境に合わせて表示されるので、
ターミナル（Terminal.app)で実行している場合はマウスで範囲選択→コピー＆ペーストして実行するのが確実です。

参考：PATHについて👉p.172、p.3463.3章(p.45)、シェルの設定ファイル👉p.172、p.346zsh：7.2章、bash7.3章

<div class="language-plaintext highlighter-rouge"><div class="highlight"><pre class="highlight"><code>
==> <strong>Installation successful!</strong>
<span style="color:silver;">＜略＞</span>
==> <strong>Next steps:</strong>
- Add Homebrew to your PATH in /Users/ユーザ名/.zprofile:
    echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/ユーザ名/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
- Run `brew help` to get started
- Further documentation: 
    https://docs.brew.sh
</code></pre></div></div>

| ページ | 内容 |
| ---- | ---- |
|11.1(p.279)|**[M1 Mac]** パッケージは `/usr/local`下にインストールされます。👉 パッケージは`/opt/homebrew`下にインストールされます。<br />（以下適宜読み替えてください。`/usr/local/Cellar`👉`/opt/homebrew/Cellar`等）|
|11.3(p.288)|**[3.0以降]** `brew cask install パッケージ名` 👉 `brew install パッケージ名 --cask`（`--cask`は省略可能、以下同様）|

## 正誤表

| ページ | 内容 |
| ---- | ---- |
|10.2(p.258)| 本文中の ipconfig は ifconfig の誤りです。|

## 履歴

- 2020.4 サポートページ公開
- 2021.6.7 正誤表 (p.258）追加
- 2021.6.7 「macOS Big Sur（11.4）およびApple M1チップ搭載Macについて」「Big SurおよびM1 Macに関する補足情報」追加
- 2021.6.7 「Homebrew 3.0 について」追加

----
[［新版 zsh&bash対応］macOS×コマンド入門 ──ターミナルとコマンドライン、基本の力](https://nisim-m.github.io/macoscmdbook2/)
