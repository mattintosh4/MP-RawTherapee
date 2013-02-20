# Private Portfile #

これは RawTherapee を MacPorts でインストールするためのプライベートポートファイルです。

This is the private Portfile for installing RawTherapee by MacPorts.

## How to install RawTherapee ##

Portfile をダウンロードするか、このリポジトリを複製して下さい。準備ができたらターミナルで `sudo port install` を実行して下さい。Portfile をダウンロードした場合は作業用ディレクトリを作成することをお勧めします。

Download Portfile or clone this repository. Run `sudo port install` on terminal.

note: If you download Portfile, recommend to make work directory.

### Download ###

```sh
mkdir build
cd build
curl -O https://raw.github.com/mattintosh4/MP-RawTherapee/master/Portfile
sudo port install
```

### Git clone ###

```sh
git clone git://github.com/mattintosh4/MP-RawTherapee.git
cd MP-RawTherapee
sudo port install
```

## Run ##

### App file (アプリケーションファイルによる起動) ###

open `/Applications/MacPorts/RawTherapee.app`.

`/Applications/MacPorts/RawTherapee.app` を実行して下さい。


### Terminal (ターミナルによる起動) ###

```sh
rawtherapee
# OR
/opt/local/bin/rawtherapee
```

__Direct open__

```sh
/opt/local/bin/rawtherapee <image file>
```


## Uninstall ##

```sh
sudo port uninstall rawtherapee
```