# BIND for Windows

Windows向けのBIND 9.10 DNSサーバーのアーカイブです。

## 📋 目次

- [概要](#概要)
- [背景](#背景)
- [ディレクトリ構造](#ディレクトリ構造)
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

## 📚 参考リンク

- [ISC BIND 公式サイト](https://www.isc.org/bind/)
- [BIND ダウンロードページ](https://www.isc.org/downloads/)

---

*このアーカイブは教育および研究目的で維持されています。*
