Windows 向けの Bind 9.10 です。

<img width="371" height="413" alt="image" src="https://github.com/user-attachments/assets/4000c665-c5ae-44e7-9a63-e3783746be5e" />


ディレクトリ構造は以下です

\ISC BIND 9
\---bin
        arpaname.exe
        bindevt.dll
        BINDInstall.exe
        delv.exe
        dig.exe
        host.exe
        InstallFiles
        InstallFlags
        libbind9.dll
        libcrypto-1_1-x64.dll
        libdns.dll
        libirs.dll
        libisc.dll
        libisccc.dll
        libisccfg.dll
        libns.dll
        libssl-1_1-x64.dll
        libxml2.dll
        mdig.exe
        nslookup.exe
        nsupdate.exe
        uv.dll

        -----------------------------------------------------------
        🔎 背景

かつては BIND for Windows（BIND9.x.x.x.zip の Windows バイナリ）が ISC 公式から配布されていました。

しかし BIND 9.18 系以降（LTS 現行系列）では Windows サポートが打ち切られています。

ISC 公式のアナウンスでは：

「Windows はテストやサポートが難しいため、今後のリリースでは Windows バイナリを提供しない」
（ビルドは理論的には可能だが、ISC は公式にビルドもテストもしていない）

🖥️ 現状

公式サイト（ISC）: Linux/Unix 系（主に Linux, FreeBSD, macOS）が対象

Windows で使う場合:

自分でソースからビルドする

WSL (Windows Subsystem for Linux) 上で Linux 版 BIND を動かす

代替として Windows DNS サーバー機能（AD DSや単体DNSサービス）を使う

✅ まとめ

昔はあった → 今はない

BIND 9.16 ぐらいまでは Windows バイナリ配布されていた

BIND 9.18 以降は Windows 非サポート

使いたければ WSL 上で Linux 版を使うのが現実的
