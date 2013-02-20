# Explanation #

This is the private Portfile for installing RawTherapee by MacPorts.

# File layout #

```
/Applications/
  MacPorts/
    RawTherapee.app

/opt/
  local/
    bin/
      rawtherapee (Launcher)
    libexec/
      rawtherapee-4.0.9/
        rawtherapee
        other resources
    share/
      doc/
        rawtherapee/
          RawTherapeeManual_en.pdf (PDF manual)
      man/
        man1/
          rawtherapee.1
```

## How to install RawTherapee ##

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

### App bundle ###

Open `/Applications/MacPorts/RawTherapee.app` on Finder.

### Terminal ###

```bash
rawtherapee
# OR
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
# もしくは
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
