---
title: "WMF 5.1 のインストールと構成 (プレビュー)"
ms.date: 2016-05-16
keywords: PowerShell, DSC, WMF
description: 
ms.topic: article
contributor: kriscv
manager: dongill
ms.prod: powershell
ms.technology: WMF
translationtype: Human Translation
ms.sourcegitcommit: 26da6c80568327faadc6746099ac9869f2018fcf
ms.openlocfilehash: 8a10903c421f62311a28c9f32e352bba75f21052

---

# WMF 5.1 のインストールと構成 (プレビュー) #

***注意:*** 
*このコンテンツはプレースホルダーです。以下のリンクは WMF 5.0 バージョンを指し、バイナリがリリースされたときに更新されます。*

インストールするオペレーティング システムとアーキテクチャに合わせて WMF 5.1 パッケージをダウンロードします。

| オペレーティング システム       | アーキテクチャ | パッケージ名              |
|------------------------|--------------|---------------------------|
| Windows Server 2012 R2 | x64      | [Win8.1AndW2K12R2-KB3156422-x64.msu](http://go.microsoft.com/fwlink/?LinkId=717507) |
| Windows Server 2012    | x64      | [W2K12-KB3156423-x64.msu](http://go.microsoft.com/fwlink/?LinkId=717506) |
| Windows Server 2008 R2 | x64      | [Win7AndW2K8R2-KB3156424-x64.msu](http://go.microsoft.com/fwlink/?LinkId=717504) |
| Windows 8.1            | x64          | [Win8.1AndW2K12R2-KB3156422-x64.msu](http://go.microsoft.com/fwlink/?LinkId=717507) |
| Windows 8.1            | x86          | [Win8.1-KB3156422-x86.msu](http://go.microsoft.com/fwlink/?LinkID=717963) |
| Windows 7 SP1          | x64          | [Win7AndW2K8R2-KB3156424-x64.msu](http://go.microsoft.com/fwlink/?LinkId=717504) |
| Windows 7 SP1          | x86          | [Win7-KB3156424-x86.msu](http://go.microsoft.com/fwlink/?LinkID=717962) |


## Windows エクスプローラー (または Windows Server 2012 R2 または Windows 8.1 ではファイル エクスプローラー) から WMF 5.1 をインストールする

1. MSU ファイルをダウンロードしたフォルダーに移動します。

2. MSU をダブルクリックして実行します。

## コマンド プロンプトから WMF 5.1 をインストールする##

1. コンピューターのアーキテクチャに適切なパッケージをダウンロードした後、管理者特権 (管理者として実行) を使ってコマンド プロンプト ウィンドウを開きます。 Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 SP1 の Server Core インストール オプションで、既定で管理者特権でコマンド プロンプトが開きます。

2. WMF 5.1 のインストール パッケージをダウンロードまたはコピーしたフォルダーにディレクトリを変更します。

3. 次のいずれかのコマンドを実行します。
    - Windows Server 2012 R2 または Windows 8.1 x64 を実行しているコンピューターの場合は、`Win8.1AndW2K12R2-KB3156422-x64.msu /quiet` を実行します。
    - Windows Server 2012 を実行しているコンピューターの場合は、`W2K12-KB3156423-x64.msu /quiet` を実行します。
    - Windows Server 2008 R2 SP1 または Windows 7 SP1 x64 を実行しているコンピューターの場合は、`Win7AndW2K8R2-KB3156424-x64.msu /quiet` を実行します。
    - Windows 8.1 x86 を実行しているコンピューターの場合は、`Win8.1-KB3156422-x86.msu /quiet` を実行します。
    - Windows 7 SP1 x86 を実行しているコンピューターの場合は、`Win7-KB3156424-x86.msu /quiet` を実行します。

## Windows Server 2008 SP1 および Windows 7 SP1 でのインストールに関する追加の注記##
Windows Server 2008 SP1 または Windows 7 SP1 に WMF 5.1 をインストールするには、以下をインストールする必要があります。
- 最新のサービス パック。
- [WMF 4.0](http://www.microsoft.com/en-us/download/details.aspx?id=40855)

> **WinRM の依存関係** - Windows PowerShell Desired State Configuration (DSC) は、WinRM に依存します。 WinRM は、Windows Server 2008 R2 および Windows 7 では既定で無効になっています。 WinRM を有効にするには、Windows PowerShell 管理者特権セッションで `Set-WSManQuickConfig` を実行します。




<!--HONumber=Jul16_HO2-->


