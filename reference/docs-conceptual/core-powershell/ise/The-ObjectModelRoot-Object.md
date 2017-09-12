---
ms.date: 2017-08-25
keywords: "PowerShell, コマンドレット"
title: "ObjectModelRoot オブジェクト"
ms.openlocfilehash: eb3424ff147c35364fa08543d59ebd30f6d2d857
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="the-objectmodelroot-object"></a>ObjectModelRoot オブジェクト

Windows PowerShell® Integrated Scripting Environment (ISE) のプリンシパル ルート オブジェクトである **$PsISE** オブジェクトは、Microsoft.PowerShell.Host.ISE.ObjectModelRoot クラスのインスタンスです。
このトピックでは、**ObjectModelRoot** オブジェクトのプロパティについて説明します。

## <a name="properties"></a>プロパティ

### <a name="currentfile"></a>CurrentFile

> Windows PowerShell ISE 2.0 以降でサポートされています。 

現在フォーカスしているこのホスト オブジェクトに関連付けられているファイルを取得する読み取り専用のプロパティ。

### <a name="currentpowershelltab"></a>CurrentPowerShellTab

> Windows PowerShell ISE 2.0 以降でサポートされています。

フォーカスしている PowerShell タブを取得する読み取り専用のプロパティ。

### <a name="currentvisiblehorizontaltool"></a>CurrentVisibleHorizontalTool

> Windows PowerShell ISE 2.0 以降でサポートされています。

エディターの下部にある水平方向のツール ウィンドウに現在表示されている Windows PowerShell ISE アドオン ツールを取得する読み取り専用のプロパティ。

### <a name="currentvisibleverticaltool"></a>CurrentVisibleVerticalTool

> Windows PowerShell ISE 2.0 以降でサポートされています。 

エディターの右側にある垂直方向のツール ウィンドウに現在表示されている Windows PowerShell ISE アドオン ツールを取得する読み取り専用のプロパティ。

### <a name="options"></a>オプション

> Windows PowerShell ISE 2.0 以降でサポートされています。 

Windows PowerShell ISE の設定を変更することができるさまざまなオプションを取得する読み取り専用のプロパティ。

### <a name="powershelltabs"></a>PowerShellTabs

> Windows PowerShell ISE 2.0 以降でサポートされています。 

Windows PowerShell ISE で開かれている PowerShell タブのコレクションを取得する読み取り専用のプロパティ。 既定では、このオブジェクトには 1 つの PowerShell タブが含まれています。ただし、スクリプトまたは Windows PowerShell ISE のメニューを使用して、このオブジェクトに他の PowerShell タブを追加することができます。

## <a name="see-also"></a>参照

- [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md)
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)
