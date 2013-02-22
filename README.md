# Explanation #

This is the private Portfile for installing RawTherapee by MacPorts.

# Destination #

```
/Applications/
  MacPorts/
    RawTherapee.app/
      Info.plist
      Contents/
        MacOS/
          rawtherapee (Launcher)
        Resources/
          Icons.icns

/opt/
  local/
    bin/
      rawtherapee (Launcher)
    libexec/
      rawtherapee-4.0.9/
        rawtherapee (Original executable)
        other resources
    share/
      doc/
        rawtherapee/
          RawTherapeeManual_en.pdf (PDF manual)
      man/
        man1/
          rawtherapee.1
```

# Launcher details #

```bash
#!/bin/bash
DYLD_LIBRARY_PATH=/opt/local/lib/gcc47 /opt/local/libexec/rawtherapee-4.0.9/rawtherapee "$@"
```

# How to use Portfile #

## Install ##

Download Portfile or clone this repository. Run `sudo port install` on terminal. If you download Portfile, recommend to make work directory.

### download ###

```bash
mkdir build
cd build
curl -O https://raw.github.com/mattintosh4/MP-RawTherapee/master/Portfile
sudo port install
```

### git clone ###

```bash
git clone git://github.com/mattintosh4/MP-RawTherapee.git
cd MP-RawTherapee
sudo port install
```

## Run ##

### From app bundle ###

Open `/Applications/MacPorts/RawTherapee.app` on Finder.

### From terminal ###

```bash
rawtherapee
```

or

```bash
/opt/local/bin/rawtherapee
```

You can also directly open the image file.

```bash
/opt/local/bin/rawtherapee <image file>
```

## Uninstall ##

```bash
sudo port uninstall rawtherapee
```

## How to use Quartz backend (native) ##

MacPorts _gtk2_ port uses X11 backend by default. If you want to use Quartz backend (native), install following ports with variants options before installing rawtherapee.

```bash
sudo port install \
	cairo +quartz -x11 \
	pango +quartz -x11 \
	gdk-pixbuf2 -x11 \
	gtk2 +quartz \
	libsigcxx2
```

_gtkmm_ port maybe fail to install. Use `-s` (source mode) option.

```bash
sudo port -s install gtkmm
```

## How to change the build type and processor target ##

### Build type ###

Default is `RELWITHDEBINFO`. This type add `-O2 -g -DNDEBUG` flags. If you want to change the build type, edit value of `build_type` variable.

```tcl
#set build_type RELWITHDEBINFO
set build_type RELEASE
```

### Processor target ###

Default is number 2. This number add `-march=native` flags. If you want to change the processor target, edit value of `proc_target` variable.

- 0: none
- 1: -mtune=generic
- 2: -march=native
- 5: -march=core2
- 6: -march=corei7

```tcl
#set proc_target 2
set proc_target 1
```

***

# 解説 #

これは MacPorts で RawTherapee をインストールするためのプライベートポートファイルです。

## インストール ##

Portfile をダウンロードするか、このリポジトリを複製して下さい。準備ができたらターミナルで `sudo port install` を実行して下さい。Portfile をダウンロードした場合は作業用ディレクトリを作成することをお勧めします。

### ダウンロードを利用する場合 ###

```bash
mkdir build
cd build
curl -O https://raw.github.com/mattintosh4/MP-RawTherapee/master/Portfile
sudo port install
```

### git clone を利用する場合 ###

```bash
git clone git://github.com/mattintosh4/MP-RawTherapee.git
cd MP-RawTherapee
sudo port install
```

## 実行 ##

### アプリケーションバンドルによる起動 ###

Finder で `/Applications/MacPorts/RawTherapee.app` を実行して下さい。

### ターミナルによる起動 ###

```bash
rawtherapee
```
もしくは

```bash
/opt/local/bin/rawtherapee
```

画像を直接開くこともできます。

```bash
rawtherapee <image file>
```

## アンインストール ##

```bash
sudo port uninstall rawtherapee
```

## Quartz バックエンドを使用するには (native) ##

MacPorts の _gtk2_ ポートは標準で X11 バックエンドを使用します。もし Quartz バックエンドを使用したい場合は RawTherapee をインストールする前に以下のポートをバリアントオプションを併用してインストールして下さい。

```bash
sudo port install \
	cairo +quartz -x11 \
	pango +quartz -x11 \
	gdk-pixbuf2 -x11 \
	gtk2 +quartz \
	libsigcxx2
```

_gtkmm_ ポートはバイナリモードの場合、インストールに失敗する可能性があります。`-s` オプション（ソースモード）を使用して下さい。

```bash
sudo port -s install gtkmm
```

## ビルドタイプとターゲットプロセッサの変更について ##

### ビルドタイプ ###

デフォルトは `RELWITHDEBINFO` です。このタイプは `-O2 -g -DNDEBUG` フラグを追加します。もしビルドタイプを変更したい場合は `build_type` 変数の値を変更して下さい。

```tcl
#set build_type RELWITHDEBINFO
set build_type RELEASE
```

### ターゲットプロセッサ ###

デフォルトは 2 です。この番号は `-march=native` フラグを追加します。もしターゲットプロセッサを変更したい場合は `proc_target` 変数の値を変更して下さい。

- 0: none
- 1: -mtune=generic
- 2: -march=native
- 5: -march=core2
- 6: -march=corei7

```tcl
#set proc_target 2
set proc_target 1
```
