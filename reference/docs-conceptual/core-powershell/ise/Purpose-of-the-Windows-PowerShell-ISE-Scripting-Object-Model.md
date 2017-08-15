---
ms.date: 2017-06-05T00:00:00.000Z
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell ISE スクリプト オブジェクト モデルの目的"
ms.assetid: d176a131-ab0c-43ee-80c1-f824ab8e4a05
ms.openlocfilehash: 65535948d681ec63c6cc36583c6d145cfa19b937
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="purpose-of-the-windows-powershell-ise-scripting-object-model"></a>Windows PowerShell ISE スクリプト オブジェクト モデルの目的
  オブジェクトは、Windows PowerShell Integrated Scripting Environment (ISE) のフォームと機能に関連付けられます。 オブジェクト モデル リファレンスは、これらのオブジェクトが公開するメンバー プロパティとメソッドに関する詳細を提供します。 これらのメソッドとプロパティに直接アクセスするためのスクリプトを使用する方法を示す例が提供されています。 スクリプト オブジェクト モデルを使用すると、次のさまざまなタスクが容易になります。

## <a name="customizing-the-appearance-of-windows-powershell-ise"></a>Windows PowerShell ISE の外観のカスタマイズ
 オブジェクト モデルを使用して、アプリケーションの設定およびオプションを変更することができます。 たとえば、次のように変更できます。

-   エラー、警告、詳細出力、デバッグ出力の色を変更することができます。

-   コマンド ウィンドウ、出力ウィンドウ、スクリプト ウィンドウの背景色を取得および設定することができます。

-   出力ウィンドウの前景色を設定することができます。

-   Windows PowerShell ISE のフォント名とフォント サイズを設定することができます。

-   警告を構成することができます。 この設定には、複数の PowerShell タブでファイルが開かれている場合や、ファイルが保存される前にそのファイル内のスクリプトを実行する場合に発行される警告が含まれます。

-   スクリプト ウィンドウと出力ウィンドウが並べて表示されるビューと、スクリプト ウィンドウが出力ウィンドウの上に表示されるビューを切り替えることができます。 コマンド ウィンドウは、出力ウィンドウの上部または下部にドッキングできます。

## <a name="enhancing-the-functionality-of-windows-powershell-ise"></a>Windows PowerShell ISE の機能の拡張
 オブジェクト モデルを使用して、Windows PowerShell ISE の機能を拡張することができます。 たとえば、次のように操作できます。

-   Windows PowerShell ISE 自体のインスタンスを追加して変更します。 たとえば、新しいメニュー項目を追加し、そのメニュー項目をスクリプトにマップして、メニューを変更することができます。

-   Windows PowerShell ISE のメニュー コマンドやボタンを使用して実行できる一部のタスクを実行するスクリプトを作成します。 たとえば、PowerShell タブの追加、削除、選択をすることができます。

-   メニュー コマンドやボタンを使用して実行できるタスクを補完します。 たとえば、PowerShell タブの名前を変更することができます。

-   ファイルに関連付けられているコマンド ウィンドウ、出力ウィンドウ、スクリプト ウィンドウのテキスト バッファーを操作します。 たとえば、次のように操作できます。

    -   すべてのテキストを取得または設定します。

    -   選択テキストを取得または設定します。

    -   スクリプトまたはスクリプトの選択した部分を実行します。

    -   行をスクロールして表示します。

    -   カーソル位置にテキストを挿入します。

    -   テキストのブロックを選択します。

    -   最後の行番号を取得します。

-   ファイル操作を実行します。 たとえば、次のように操作できます。

    -   ファイルを開いたり、ファイルを保存したり、別の名前を使用してファイルを保存したりします。

    -   最後に保存された後、ファイルが変更されたかどうかを判別します。

    -   ファイル名を取得します。

    -   ファイルを選択します。

## <a name="automating-tasks"></a>タスクの自動化
 スクリプト オブジェクト モデルを使用して、よく行う操作のキーボード ショートカットを作成することができます。

## <a name="see-also"></a>参照
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md) 
- [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)

  
