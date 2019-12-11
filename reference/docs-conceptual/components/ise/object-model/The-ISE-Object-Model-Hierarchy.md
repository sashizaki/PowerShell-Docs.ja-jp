---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISE オブジェクト モデルの階層
ms.openlocfilehash: 0159707b1050c412a74da3d3ca02a46cea982556
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "62057725"
---
# <a name="the-ise-object-model-hierarchy"></a>ISE オブジェクト モデルの階層

このトピックでは、Windows PowerShell Integrated Scripting Environment (ISE) の一部であるオブジェクトの階層について説明します。
Windows PowerShell ISE は、Windows PowerShell 3.0 と Windows PowerShell 4.0 に付属しています。
オブジェクトをクリックすると、そのオブジェクトを定義するクラスのリファレンス ドキュメントに移動します。

## <a name="psise-object"></a>$psISE オブジェクト

**$psISE** オブジェクトは、Windows PowerShell ISE オブジェクト階層の[ルート オブジェクト](The-ObjectModelRoot-Object.md)です。
最上位のこのオブジェクトでは、スクリプト作成に次のオブジェクトを使用できます。

## <a name="psisecurrentfilethe-isefile-objectmd"></a>[$psISE.CurrentFile](The-ISEFile-Object.md)

**$PsISE.CurrentFile** オブジェクトは、[ISEFile](The-ISEFile-Object.md) クラスのインスタンスです。

## <a name="psisecurrentpowershelltabthe-powershelltab-objectmd"></a>[$psISE.CurrentPowerShellTab](The-PowerShellTab-Object.md)

**$psISE.CurrentPowerShellTab** オブジェクトは、[PowerShellTab](The-PowerShellTab-Object.md) クラスのインスタンスです。

## <a name="psisecurrentvisiblehorizontaltool"></a>$psISE.CurrentVisibleHorizontalTool

**$psISE.CurrentVisibleHorizontalTool** オブジェクトは [ISEAddOnTool](The-ISEAddOnTool-Object.md) クラスのインスタンスで、
現在 [Windows PowerShell ISE] ウィンドウの上端にドッキングされているインストール済みのアドオンを表しています。

## <a name="psisecurrentvisibleverticaltool"></a>$psISE.CurrentVisibleVerticalTool

**$psISE.CurrentVisibleHorizontalTool** オブジェクトは [ISEAddOnTool](The-ISEAddOnTool-Object.md) クラスのインスタンスで、
現在 [Windows PowerShell ISE] ウィンドウの右端にドッキングされているインストール済みのアドオンを表しています。

## <a name="psiseoptionsthe-iseoptions-objectmd"></a>[$psISE.Options](The-ISEOptions-Object.md)

**$psISE.Options** オブジェクトは、[ISEOptions](The-ISEOptions-Object.md) クラスのインスタンスです。
ISEOptions オブジェクトは、Windows PowerShell ISE のさまざまな設定を表します。
これは Microsoft.PowerShell.Host.ISE.ISEOptions クラスのインスタンスです。

## <a name="psisepowershelltabsthe-powershelltabcollection-objectmd"></a>[$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md)

**$psISE.PowerShellTabs** オブジェクトは [PowerShellTabCollection](The-PowerShellTabCollection-Object.md) クラスのインスタンスです。
これは現在開いているすべての PowerShell タブのコレクションで、ローカル コンピューターまたは接続されているリモート コンピューターで利用可能な Windows PowerShell の実行環境を表しています。
コレクション内の個々のメンバーは [PowerShellTab](The-PowerShellTab-Object.md) クラスのインスタンスです。

## <a name="see-also"></a>参照

- [Windows PowerShell ISE スクリプト オブジェクト モデルの目的](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)