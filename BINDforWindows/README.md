# BIND for Windows

Windows向けのBIND 9.10 DNSサーバーのアーカイブです。

## 📋 目次

- [概要](#概要)
- [ディレクトリ構造](#ディレクトリ構造)
- [使用方法](#使用方法)
- [背景](#背景)
- [現状とWindows対応について](#現状とwindows対応について)
- [代替手段](#代替手段)
- [注意事項](#注意事項)
- [参考リンク](#参考リンク)

## 🎯 概要

このアーカイブには、ISC公式から配布されていた最後のWindows向けBIND 9.10が含まれています。BIND 9.18以降ではWindows公式サポートが終了したため、歴史的価値と継続利用のためにアーカイブされています。

**アーカイブ内容**: BIND 9.10.x for Windows (最終公式配布版)

<img width="371" height="413" alt="BIND for Windows インストーラー画面" src="https://github.com/user-attachments/assets/4000c665-c5ae-44e7-9a63-e3783746be5e" />

## 📂 ディレクトリ構造

```
ISC BIND 9/
└── bin/
    ├── arpaname.exe
    ├── bindevt.dll
    ├── BINDInstall.exe
    ├── delv.exe
    ├── dig.exe
    ├── host.exe
    ├── InstallFiles
    ├── InstallFlags
    ├── libbind9.dll
    ├── libcrypto-1_1-x64.dll
    ├── libdns.dll
    ├── libirs.dll
    ├── libisc.dll
    ├── libisccc.dll
    ├── libisccfg.dll
    ├── libns.dll
    ├── libssl-1_1-x64.dll
    ├── libxml2.dll
    ├── mdig.exe
    ├── nslookup.exe
    ├── nsupdate.exe
    └── uv.dll
```

## 🚀 使用方法

### 基本的な使用手順

1. **アーカイブの解凍**
   - `ISC BIND 9.zip` を適当なフォルダに解凍してください
   - 推奨解凍先: `C:\Program Files\ISC BIND 9\` または `C:\BIND\`

2. **環境変数PATHの設定**
   
   **方法1: システム環境変数で設定（推奨）**
   - `Win + R` → `sysdm.cpl` → `環境変数` をクリック
   - システム環境変数の `Path` を選択して `編集`
   - `新規` をクリックして `C:\Program Files\ISC BIND 9\bin` を追加
   - `OK` でダイアログを閉じる

   **方法2: コマンドプロンプトで一時的に設定**
   ```cmd
   set PATH=%PATH%;C:\Program Files\ISC BIND 9\bin
   ```

3. **動作確認**
   
   新しいコマンドプロンプトを開いて以下のコマンドで確認：
   ```cmd
   nslookup www.google.com
   dig www.google.com
   host www.google.com
   ```

### 主なツール

- **nslookup.exe**: DNSクエリツール（Windows標準のnslookupと同じ）
- **dig.exe**: より詳細なDNSクエリツール
- **host.exe**: シンプルなDNSルックアップツール
- **nsupdate.exe**: 動的DNS更新ツール
- **BINDInstall.exe**: インストーラー（管理者権限が必要）

### インストーラーの使用

#### BINDInstall.exe について
- **ファイル**: BINDInstall.EXE (2.65 MB)
- **バージョン**: 3.0.0.0 (BIND 9.10.0用)
- **説明**: ISC BIND 9 Install Utility

#### インストール手順

1. **管理者権限でコマンドプロンプトを開く**
   - `Win + R` → `cmd` → `Ctrl + Shift + Enter`

2. **インストーラーを実行**
   ```cmd
   cd "C:\path\to\extracted\ISC BIND 9\bin"
   BINDInstall.exe
   ```

3. **インストール後の確認**
   ```cmd
   # サービスの確認
   sc query "ISC BIND"
   
   # BINDバージョンの確認
   named -v
   ```

#### インストーラーの機能
- BIND 9 DNSサーバーをWindowsサービスとして登録
- 必要なレジストリエントリの作成
- 自動起動設定の構成
- アンインストール情報の登録

#### 既知の問題・制限事項
- Windows 10/11では互換性問題が発生する可能性があります
- 一部のセキュリティソフトが実行を阻止する場合があります
- UAC（ユーザーアカウント制御）により実行が拒否される場合があります

> ⚠️ **重要**: インストーラーは2014年版のため、最新のWindowsでは正常に動作しない場合があります。トラブルを避けるため、**手動での解凍・設定を強く推奨**します。

## 🔎 背景

かつては BIND for Windows（BIND9.x.x.x.zip の Windows バイナリ）が ISC 公式から配布されていました。

しかし BIND 9.18 系以降（LTS 現行系列）では Windows サポートが打ち切られています。

### ISC 公式のアナウンス

> 「Windows はテストやサポートが難しいため、今後のリリースでは Windows バイナリを提供しない」

※ ビルドは理論的には可能だが、ISC は公式にビルドもテストもしていない

## 🖥️ 現状とWindows対応について

- **公式サイト（ISC）**: Linux/Unix 系（主に Linux, FreeBSD, macOS）が対象
- **BIND 9.16 まで**: Windows バイナリが配布されていた
- **BIND 9.18 以降**: Windows 公式サポート終了

## 🔄 代替手段

Windows で BIND を使用したい場合の選択肢：

### 1. WSL (Windows Subsystem for Linux) を使用
- WSL 上で Linux 版 BIND を動かす
- **推奨される方法**

### 2. 自分でビルド
- ソースコードから Windows 向けにビルドする
- 高度な技術知識が必要

### 3. Windows DNS サーバー機能を使用
- Active Directory Domain Services (AD DS)
- Windows 単体DNSサービス

## ⚠️ 注意事項

- このアーカイブは**歴史的価値と継続利用**のために保存されています
- BIND 9.10 は**開発が終了**しており、セキュリティアップデートは提供されません
- 本番環境での使用前に、**セキュリティリスクを十分に評価**してください
- 可能な限り、**現在もサポートされている代替手段の使用を推奨**します
- **使用は自己責任でお願いします**

### ライセンス（重要）

- 本ディレクトリの BIND 9.10.x (Windows) は **第三者ソフトウェア（ISC 配布物）**です。権利は ISC および各依存ライブラリの著作権者に帰属します。
- 現在このリポジトリに同梱されている `ISC BIND 9.zip` / `ISC BIND 9/` は **バイナリ中心で、LICENSE / NOTICE 等のライセンス条文ファイルが同梱されていません**。
- 利用・再配布の可否・条件は upstream のライセンスに従ってください（第三者依存も含む）。

参照:
- ISC BIND: https://www.isc.org/bind/ / https://www.isc.org/downloads/
- OpenSSL: https://www.openssl.org/source/license.html

## 📚 参考リンク

- [ISC BIND 公式サイト](https://www.isc.org/bind/)
- [BIND ダウンロードページ](https://www.isc.org/downloads/)

---

*このアーカイブは教育および研究目的で維持されています。*

