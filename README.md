# Windows Setup

1. Msys2
2. ConEmu
3. Atom Beta

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

## 2. ConEmu

## 3. Atom Beta
