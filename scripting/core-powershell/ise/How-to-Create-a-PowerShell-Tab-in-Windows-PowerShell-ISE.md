---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: "Windows PowerShell ISE で PowerShell タブを作成する方法"
ms.technology: powershell
ms.assetid: c10c18c7-9ece-4fd0-83dc-a19c53d4fd83
ms.openlocfilehash: 1c57e557e2fefbdf67b6a3c71721cd2a916a0ec5
ms.sourcegitcommit: 8acbf9827ad8f4ef9753f826ecaff58495ca51b0
translationtype: HT
---
# <a name="how-to-create-a-powershell-tab-in-windows-powershell-ise"></a>Windows PowerShell ISE で PowerShell タブを作成する方法
Windows PowerShell® Integrated Scripting Environment (ISE) のタブを使うと、同じアプリケーション内で複数の実行環境を同時に作成して使用することができます。 PowerShell の各タブは、独立した実行環境またはセッションに対応します。

> [!NOTE]
> 1 つのタブで作成した変数、関数、別名が、他のタブに引き継がれることはありません。 それらのタブは、別々の Windows PowerShell セッションです。

Windows PowerShell でタブを開いたり閉じたりするには、次の手順を実行します。 タブの名前を変更するには、Windows PowerShell タブのスクリプト オブジェクトで [DisplayName](The-PowerShellTab-Object.md#Displayname) プロパティを設定します。

## <a name="to-create-and-use-a-new-powershell-tab"></a>新しい PowerShell タブを作成して使用するには
**[ファイル]** メニューで、**[PowerShell タブの新規作成]** をクリックします。 新しい PowerShell タブは、常にアクティブなウィンドウとして表示されます。 PowerShell のタブには、開かれた順に番号が付けられます。 各タブは、それぞれ独自の Windows PowerShell コンソール ウィンドウに関連付けられます。 独自のセッションを持つ PowerShell タブは、最大 32 個まで (Windows PowerShell ISE 2.0 では 8 個まで) を同時に開くことができます。

なお、ツール バーの **[新規作成]** または **[開く]** アイコンをクリックしても、新しいタブで別のセッションを作成できないことにご注意ください。  代わりに、これらのボタンを使うと、セッションを持つ現在アクティブなタブ上で、新規または既存のスクリプト ファイルが開きます。 各タブおよびセッションでは、複数のスクリプト ファイルを開くことができます。 セッションのスクリプト タブは、関連付けられたセッションがアクティブな場合にのみ、セッションのタブの下に表示されます。

PowerShell タブをアクティブにするには、タブをクリックします。 開かれているすべての PowerShell タブの中から選択するには、**[表示]** メニューで、使う PowerShell タブをクリックします。

## <a name="to-create-and-use-a-new-remote-powershell-tab"></a>新しいリモート PowerShell タブを作成して使用するには
**[ファイル]** メニューの **[リモート PowerShell タブの新規作成]** をクリックすると、リモート コンピューターでセッションが確立されます。 ダイアログ ボックスが表示され、リモート接続を確立するために必要な詳細情報を入力するように求められます。 リモート タブの機能はローカルの PowerShell タブと同様ですが、コマンドとスクリプトはリモート コンピューター上で実行されます。

## <a name="to-close-a-powershell-tab"></a>PowerShell タブを閉じるには
タブを閉じるには、次の手法のいずれかを使います。

-   終了するタブをクリックします。

-   **[ファイル]** メニューの **[PowerShell タブを閉じる]** をクリックするか、アクティブなタブの閉じるボタン (**X**) をクリックして、タブを閉じます。

閉じようとしている PowerShell タブに未保存のファイルがあると、そのファイルを保存するか破棄するかを求められます。 スクリプトを保存する方法について詳しくは、「[スクリプトを保存する方法](https://technet.microsoft.com/library/162f594d-efd3-4234-9960-45e56e6eadc8)」をご覧ください。

## <a name="see-also"></a>参照
- [Windows PowerShell ISE の使用](Using-the-Windows-PowerShell-ISE.md)
- [Windows PowerShell ISE でコンソール ウィンドウを使用する方法](How-to-Use-the-Console-Pane-in-the-Windows-PowerShell-ISE.md)

