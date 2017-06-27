# Windows Setup

1. Msys2
2. ConEmu
3. Atom Beta
4. SDKMAN!
5. Hain
6. Screenpresso
7. GifCam
8. VirtualBox
9. Notepad++
10. Pandoc
11. Node.js
12. Ruby
13. Docker for Windows

---

## 1. Msys2

### 1.1. pacmanパッケージ管理

#### 1.1.1. パッケージのアップグレード(yum update)

```
$ pacman -Syu
```

- S: --sync(同期)
- y: --refresh(リポジトリデータベースと同期)
- u: --upgrades(更新)

#### 1.1.2. リポジトリデータベースの最新情報取得

```
$ pacman -Syy
```

#### 1.1.3. パッケージのインストール(yum install)

- 通常インストール:

```
$ pacman -S git
```

- サイレント・インストール:

```
$ pacman -S --noconfirm vim
```

#### 1.1.4. パッケージのアンインストール(yum remove)

- 依存関係を含めたアンインストール:

```
$ pacman -Rsn php
```

- s: --search(依存関係を検索)
- n: バックアップを削除

#### 1.1.5. リポジトリデータベースのパッケージの検索(yum search)

```
$ pacman -Ss ruby
```

#### 1.1.6. リポジトリデータベースのパッケージの詳細情報表示(yum info)

```
$ pacman -Si ruby
```

#### 1.1.7. インストール済みパッケージのリストアップ

```
$ pacman -Qqe
```

### 1.2. pacman 設定ファイル

- /etc/pacman.conf

#### 1.2.1. 色表示

- Color のコメントを外す

```
# Misc options
#UseSyslog
Color
#TotalDownload
```

### 1.3. pacman パッケージ・インストール

- git
- vim
- zip
- unzip
- tar
- python3
- diffutils
- openssh

```
$ pacman -S git vim zip unzip tar python3 diffutils openssh
```

#### 1.3.1. python3

##### pip

- インストール確認

```
$ python -m pip -V
```

- インストール

```
$ curl -kL https://bootstrap.pypa.io/get-pip.py | python
```

##### PSM CLI

```
$ curl -X GET -u ${USERNAME}:${PASSWORD} -H X-ID-TENANT-NAME:${IDDOMAIN} https://psm.us.oraclecloud.com/paas/core/api/v1.1/cli/${IDDOMAIN}/client -o p smcli.zip
```

```
$ pip install -U psmcli.zip
```

#### 1.3.2. Git

##### Alias: git log

```
$ git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all"
```

### 1.4. Configuration

#### 1.4.1. SSH

```
$ ssh-keygen -t rsa -b 4096 -C "shinya.com@gmail.com"
```

- ~/.ssh/id_rsa.pub をgithub へ登録
- 登録後の確認:

```
$ ssh -T git@github.com
```

## 2. ConEmu

### Msys2 の登録

#### Startup

- **Settings** -> **Startup** -> **Tasks**
  - `Msys2::bash`
  - `set CHERE_INVOKING=1 & set MSYSTEM=MINGW64 & C:\msys2\usr\bin\bash.exe --login -i -new_console:C:\msys2\msys2.ico -new_console:d:C:\msys2\home\syanagih`

#### ConEmu Here

- **Settings** -> **Integration** -> **Command**
  - `set CHERE_INVOKING=1 & set MSYSTEM=MINGW64 & C:\msys2\usr\bin\bash.exe --login -i -new_console:C:\msys2\msys2.ico -new_console:d:C:\msys2\home\syanagih`

### 基本設定

#### Main

- **Settings** -> **Main**

##### Font

- Font: MyricaM M
  - [プログラミングフォント Myrica](https://myrica.estable.jp/)
- Size: 16
- Anti aliasing: Clear Type

##### Monospace

- Monospace: OFF

#### Main::Size & Pos

##### Aligmment

- Center console in workspace: ON
- Pad size (pixels): 10

#### Main::Appearance

##### Title bar

- Hide caption always: ON

#### Features::Colors

##### Schemes

- Schemes: <Solarized (John Doe)>

#### Integration

##### Command

```
set MSYSTEM=MINGW64 & C:\msys2\usr\bin\bash.exe -c "export CONEMU_CURRENT=$PWD && /c/msys2/usr/bin/bash.exe --login"
```

##### Icon file

`C:\msys2\msys2.ico`

##### /etc/profile

以下を末尾に追加

```
if [ -n ${CONEMU_CURRENT} ]; then
    cd ${CONEMU_CURRENT}
else
    cd ~
fi
```

#### Keys & Macro::Mark/Copy

##### Select text with keybord

- Start selection with Shift + Arrow: ON

#### Keys & Macro::Paste

##### Paste mode

- Shift+Instert: Do nothing
- Ctrl+v: Multi lines

##### Mouse button actions

- Right: <None>

## 3. Atom Beta

### Atom Packages Synchronization with apm stars

```
$ apm login
$ apm stars --installed
$ apm stars --install
```

#### git-plus

- git のパスを設定
  - `C:\msys\usr\bin\git.exe`

### 個別インストール

- atom-beautify

## 4. SDKMAN!

```
$ curl -s "https://get.sdkman.io" | bash
$ source "/home/syanagih/.sdkman/bin/sdkman-init.sh"
```

### 4.1. Maven

```
$ sdk install Maven
```

### 4.2. Activator

```
sdk install activator
```

## 5. Hain

- [Hain](https://github.com/appetizermonster/hain)
  - Alternative: [Cerebro](https://github.com/KELiON/cerebro)

## 6. Screenpresso
- [Screenpresso](https://www.screenpresso.com/)

## 7. GifCam
- [GifCam](http://blog.bahraniapps.com/gifcam/)
  - VClip

## 8. VirtualBox
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## 9. Notepad++
- [Notepad++](https://notepad-plus-plus.org/)

## 10. Pandoc
- [Pandoc](https://github.com/jgm/pandoc/releases)

1. 一度インストールした後に `pandoc.exe` を /usr/bin/に移動
2. その後アンインストールする

## 11. Node.js 環境
### 11.1. nodist
バージョン管理ツール
- [v0.8.8 as if Apr-29-2017](https://github.com/marcelklehr/nodist/releases/)
- インストールディレクトリ: `C:\\Apps\\Nodist`

#### 環境変数設定
- .bash_cutom

```bash
export PATH=/c/Apps/Nodist/bin:$PATH
export NODIST_PREFIX=/c/Apps/Nodist
export NODE_PATH=/c/Apps/Nodist/node_modules
export NODIST_X64=1
```
#### nodist コマンド
- `nodist update`: nodist 依存ファイルのアップデート
- `nodist dist`: インストール可能バージョン
- `nodist ls`: インストール済みリスト
- `nodist add vX.X.X`: 特定バージョンのインストール
- `nodist rm vX.X.X`: 特定バージョンのアンインストール
- `nodist vX.X.X`: 特定バージョンへの切り替え

### 11.2. npm
Node.js パッケージ管理

#### npm 更新
```
$ cd $NODIST_PREFIX
$ npm update -g npm
```

## 12. Ruby
### 手順
#### 12.1. MSYS - MINGW64 開発環境

##### MSYS 更新
```
$ pacman -Syuu
```
##### MINGW64 GCC

**base-devel** インストール
```
$ pacman -S base-devel
選択して下さい (デフォルト=all): all
```

```
$ pacman -S mingw-w64-x86_64-toolchain
選択して下さい (デフォルト=all): all
```

#### 12.2. RubyInstaller2
RubyInstaller2 ダウンロード
- https://github.com/oneclick/rubyinstaller2/releases
  - RubyInstaller-2.4.1-1 - 2017-05-25
```
$ wget https://github.com/oneclick/rubyinstaller2/releases/download/2.4.1-1/rubyinstaller-2.4.1-1-x64.exe
```
- Install: /c/Ruby/Ruby24-x64
- Defaul External Encodinf: UTF-8

```
$ ruby -v
ruby 2.4.1p111 (2017-03-22 revision 58053) [x64-mingw32]
```
#### 12.3. Rails
```
$ gem install rails
```

```
$ rails -v
Rails 5.1.1
```

## 13. Docker for Windows
- 前提: Windows 10 Pro

### Windows 10 Pro - Hyper-V 有効化設定

1. コントロールパネル
2. プログラムと機能
3. Windowsの機能の有効火または無効化
4. **Hyper-V** にチェック
5. 再起動

### Docker for Windows(Stabke)
- https://docs.docker.com/docker-for-windows/install/#download-docker-for-windows
  - [Stable channel](https://download.docker.com/win/stable/InstallDocker.msi)
- インストール

### 確認
1. スタートボタン
2. Windows管理ツール
3. Hyper-Vマネージャを起動
4. Hyper-vマネージャ -> マシン名
5. **MobyLinuxVM** の追加が確認できる

### 環境変数
**/c/Program Files/Docker/Docker/Resources/bin** を PATHに追加

### Kitematic
1. タスクトレイのDockerを右クリック
2. Open Kitematic
3. Download Kitematic
4. **/c/Program Files/Docker/Kitematic** に展開