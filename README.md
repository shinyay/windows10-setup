# Windows Setup

1. Msys2
2. ConEmu
3. Atom Beta
4. SDKMAN!
5. Hain

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

- vim
- git
- zip
- unzip
- tar

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
  - `set CHERE_INVOKING=1 & MSYSTEM=MSYS & C:\tools\msys64\usr\bin\bash.exe --login -i -new_console:C:\tools\msys64\msys2.ico`

#### ConEmu Here

- **Settings** -> **Integration** -> **Command**
  - `set CHERE_INVOKING=1 & set MSYSTEM=MINGW64 & C:\msys\usr\bin\bash.exe --login -i -new_console:C:\msys\msys2.ico -new_console:d:C:\msys\home\syanagih`

### 基本設定

#### Main

- **Settings** -> **Main**

##### Font

- Font: Myrica P
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
$ apm start --install
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
