# 開発環境構築資料
======

## はじめに

この資料は実習で使用している開発環境の導入に関する資料です。可能であれば環境構築を自力で試してみて下さい。

## VirtualBox に Ubuntu 導入

環境としては Microsoft Windows を想定しています。ので、仮想環境を用意してそこに Linux を導入し、それを開発環境とします。

### VirtualBox 導入

以下から VirtualBox for Windows hosts のインストール用ファイルを download し、実行します。
- [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)

導入後、仮想ホストを作成しておきます。新規作成を選択して、基本的にはデフォルト設定で作成して問題ありません。

### Ubuntu 13.03 導入

以下より導入用 DVD イメージを download しておきます。
- [Download Ubuntu Desktop](http://www.ubuntu.com/download/desktop)

その後、download したイメージファイルを導入対象となっている仮想ホストの光学ドライブに設定して電源を投入。ユーザアカウントの入力以外は基本的にデフォルト設定で構いません。

## sublime text 2 導入

以下ドキュメントを参照しつつ、パッケージを導入します。
- [SublimeText2 の導入](http://blog.lindwurm.biz/2013/04/how-to-install-sublime.html)

## rvm, ruby, rails 導入

ruby 1.9.3 の導入までは以下ドキュメントを参考に導入のこと。
- [Ubuntu Server 12.04 LTS + RVM + ruby1.9 + Rails3の環境を構築してみた](http://blog.opensquare.jp/?p=1667)

手順としては以下となります。

### 必要なツールの導入

    $ sudo apt-get -y install build-essential libssl-dev curl git-core

### rvm の導入

    $ wget http://raw.github.com/wayneeseguin/rvm/master/binscripts/rvm-installer
    $ bash rvm-installer

### 最終行の確認

    $ cat .bashrc

### .bashrc を読み込みます

    $ source .bashrc

### 必要なライブラリをインストールします

    $ sudo apt-get install build-essential openssl libreadline6 libreadline6-dev curl ¥
    git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev ¥
    libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion

### ruby 1.9.3 を導入します

    $ rvm install 1.9.3

### 確認

    $ rvm list

### 設定の追加

以下の行を .bashrc に追加します。

    source $HOME/.rvm/scripts/rvm

その後、設定ファイルを読み込んでおきます。

    $ source .bashrc

### 導入した 1.9.3 をデフォルトにする

    $ rvm use 1.9.3 --default

### 動作確認

    $ ruby -v

### gem のバージョン変更

    $ gem update --system 1.8.24

### .gemrc を作成して内容を以下にしておきます

    $ cat .gemrc
    install: --no-rdoc --no-ri
    update: --no-rdoc --no-ri

### rails 導入

    $ gem install rails -v 3.2.13

## rails プロジェクト作成時に注意が必要な事項について

rails プロジェクト作成後、Gemfile の以下の部分を有効にする必要があります。

    gem 'therubyracer', :platforms => :ruby

以下、参考まで。
-[rails server 時に `autodetect': Could not find a JavaScript runtime が出たら。](http://kiyotakagoto.hatenablog.com/entry/2013/05/28/235727)
