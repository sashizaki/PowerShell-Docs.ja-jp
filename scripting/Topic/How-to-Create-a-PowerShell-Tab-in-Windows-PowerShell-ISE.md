---
title: Windows PowerShell ISE で PowerShell タブを作成する方法
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c10c18c7-9ece-4fd0-83dc-a19c53d4fd83
---
# Windows PowerShell ISE で PowerShell タブを作成する方法
[!INCLUDE[ise_1](../Token/ise_1_md.md)] のタブを使うと、同じアプリケーション内で複数の実行環境を作成して同時に使うことができます。 PowerShell の各タブは、独立した実行環境またはセッションに対応します。

> [!NOTE]
> 1 つのタブで作成した変数、関数、別名が、他のタブに引き継がれることはありません。 それらのタブは、別々の Windows PowerShell セッションです。

[!INCLUDE[wps_2](../Token/wps_2_md.md)] でタブを開いたり閉じたりするには、次の手順を実行します。 タブの名前を変更するには、[!INCLUDE[wps_2](../Token/wps_2_md.md)] タブのスクリプト オブジェクトで [DisplayName](assetId:///a9b58556-951b-4f48-b3ae-b351b7564360#Displayname) プロパティを設定します。

## 新しい PowerShell タブを作成して使用するには
**[ファイル]** メニューで、**[PowerShell タブの新規作成]** をクリックします。 新しい PowerShell タブは、常にアクティブなウィンドウとして表示されます。 PowerShell のタブには、開かれた順に番号が付けられます。 各タブは、それぞれ独自の Windows PowerShell コンソール ウィンドウに関連付けられます。 独自のセッションを持つ PowerShell タブは、最大 32 個まで ([!INCLUDE[ise_2](../Token/ise_2_md.md)] 2.0 では、8 個まで) 同時に開くことができます。

なお、ツール バーの **[新規作成]** または **[開く]** アイコンをクリックしても、新しいタブで別のセッションを作成できないことにご注意ください。  代わりに、これらのボタンを使うと、セッションを持つ現在アクティブなタブ上で、新規または既存のスクリプト ファイルが開きます。 各タブおよびセッションでは、複数のスクリプト ファイルを開くことができます。 セッションのスクリプト タブは、関連付けられたセッションがアクティブな場合にのみ、セッションのタブの下に表示されます。

PowerShell タブをアクティブにするには、タブをクリックします。 開かれているすべての PowerShell タブの中から選択するには、**[表示]** メニューで、使う PowerShell タブをクリックします。

## 新しいリモート PowerShell タブを作成して使用するには
**[ファイル]** メニューの **[リモート PowerShell タブの新規作成]** をクリックすると、リモート コンピューターでセッションが確立されます。 ダイアログ ボックスが表示され、リモート接続を確立するために必要な詳細情報を入力するように求められます。 リモート タブの機能はローカルの PowerShell タブと同様ですが、コマンドとスクリプトはリモート コンピューター上で実行されます。

## PowerShell タブを閉じるには
タブを閉じるには、次の手法のいずれかを使います。

-   終了するタブをクリックします。

-   **[ファイル]** メニューの **[PowerShell タブを閉じる]** をクリックするか、アクティブなタブの閉じるボタン (**X**) をクリックして、タブを閉じます。

閉じようとしている PowerShell タブに未保存のファイルがあると、そのファイルを保存するか破棄するかを求められます。 スクリプトを保存する方法について詳しくは、「[スクリプトを保存する方法](assetId:///162f594d-efd3-4234-9960-45e56e6eadc8)」をご覧ください。

## 参照
[Windows PowerShell ISE の使用](../Topic/Using-the-Windows-PowerShell-ISE.md)
[Windows PowerShell ISE でコンソール ウィンドウを使用する方法](../Topic/How-to-Use-the-Console-Pane-in-the-Windows-PowerShell-ISE.md)



<!--HONumber=Apr16_HO1-->


