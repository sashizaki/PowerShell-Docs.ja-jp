---
title: 管理 OData Web サービスにリソースを追加する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e620bf6d-76be-47b0-a7a8-f43418f30c60
caps.latest.revision: 6
ms.openlocfilehash: b81a32b867795ae51c3f5308c2f82c31ed2747fa
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359821"
---
# <a name="adding-resources-to-a-management-odata-web-service"></a>Management OData Web サービスにリソースを追加する

この例では、管理用の OData スキーマデザイナーを使用して、既存の管理 OData web サービスにリソースを追加する方法を示します。 [Pswsroleベースのプラグイン](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)のサンプルでは、プロセスリソースとサーバーリソースを公開する web サービスを作成します。 この例では、仮想マシン (VM) リソースを web サービスに追加します。

## <a name="prerequisites"></a>必要条件

このトピックでは、「 [Windows PowerShell Web サービスの作成](./creating-a-management-odata-web-service.md)」で説明されているように[Pswsroleñプラグイン](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプルをダウンロードしてインストールし、 [Management OData スキーマデザイナー](https://marketplace.visualstudio.com/items?itemName=jlisc0.ManagementODataSchemaDesigner)をダウンロードしてインストールしたことを前提としています。 また、このトピックでは、Management Odata エンドポイントを設定するコンピューターに Hyper-v Windows PowerShell モジュールがインストールされていることを前提としています。

## <a name="adding-vm-as-a-resource-to-the-web-service"></a>VM をリソースとして Web サービスに追加する

最初の手順では、既存の管理 OData エンドポイントからスキーマデザイナーにスキーマをインポートします。 次の手順では、その方法について説明します。

#### <a name="importing-an-existing-schema-into-the-schema-designer"></a>スキーマデザイナーへの既存のスキーマのインポート

1. 管理用の OData スキーマデザイナーを開きます。

2. **[ファイル]** メニューの **[ファイル]** を選択します。**新規**;**ファイル**。 **[新しいファイル]** ダイアログボックスが表示されます。

3. [**管理] [OData モデル**] の順にクリックし、 **[開く]** をクリックします。

4. メインウィンドウ内を右クリックし、 **[スキーマファイル]** をクリックします。**インポート**。 **[開く]** ダイアログボックスが表示されます。

5. [Pswsroleベースプラグイン](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプル用の管理 OData web サービスを設定するフォルダーに移動します。 このサンプルに用意されている Windows PowerShell スクリプトを使用して、スクリプトを変更せずにエンドポイントを設定した場合、そのフォルダーは**C:\inetpub\wwwroot\Modata**になります。 スキーマ .mof を選択し、**開く** をクリックします。

   この時点で、スキーマの .mof ファイルと Schema .xml ファイルをテキストエディターで開き、プロセスとサービスリソースのマッピングが含まれていることを確認します。 スキーマ .mof ファイルは、[分散管理タスクフォース](https://www.dmtf.org/)(DTMF) 管理オブジェクト (mof) 標準を使用します。 スキーマ .xml ファイルは、「[リソースマッピングスキーマ](./resource-mapping-schema.md)」で説明されている xml スキーマを使用します。

   次の手順では、の Hyper-v コマンドレットをスキーマモデルにインポートする方法について説明します。

#### <a name="importing-cmdlets-into-the-schema"></a>スキーマへのコマンドレットのインポート

1. スキーマデザイナーウィンドウの空白部分を右クリックし、 **[コマンドレットのインポート]** をクリックします。 **[コマンドレットのインポートウィザード]** ダイアログボックスが表示されます。

2. **[ローカルコンピューター]** が選択されていることを確認し、 **[次へ]** をクリックします。

3. インストールされている Windows PowerShell モジュールが選択されていることを確認し、ドロップダウンリストから [Hyper-v] を選択します。 **[次へ]** をクリックします。 **[次へ]** をクリックします。

4. **[コマンドレットの名詞]** ボックスの一覧で、 **[VM]** を選択します。 **[次へ]** をクリックします。

5. この例では、コマンドレットを使用して Get コマンドと Delete コマンドだけをバインドします。 [**作成**と**更新**] チェックボックスをオフにし、 **[取得]** および **[削除]** チェックボックスがオンになっていることを確認します。 **GET**用に `Get-VM` コマンドレットが選択されていること、`Remove-VM` コマンドレットが**削除**対象として選択されていることを確認します。

6. VM コマンドレットのメタデータには出力の種類が指定されていないため、コマンドレットを実行して出力の種類を指定する必要があります。 **[出力の種類を指定]** を選択し、 **[コマンドレットの実行]** をクリックします。 **[コマンドレットの実行]** ダイアログが表示されます。 **[実行]** をクリックします。 **[CLR 型]** ボックスに `VirtualMachine` 型が設定されます。 **[OK]** をクリックし、 **[次へ]** をクリックします。

7. 既定では、VirtualMachine オブジェクトのすべてのプロパティが選択されています。 このリソースを web サービスから要求したときに返されるデータの一部としては、必要のないプロパティはクリアできます。 **[次へ]** をクリックします。

8. キーとして使用するプロパティを少なくとも1つ選択する必要があります。 一覧で **[名前]** を選択し、 **[次へ]** をクリックします。

9. 次のウィンドウでは、管理用の OData リソースのプロパティを、基になるコマンドレットのプロパティにマップできます。 既定では、同じ名前のプロパティがマップされます。 たとえば、リソースの `ComputerName` プロパティは、コマンドレットの `ComputerName` プロパティにマップされます。  これにより、web サービスへの要求で `ComputerName` プロパティを指定し、指定した値を `Get-VM` コマンドレットに渡すことができます。 `Id` と `Name` も既定でマップされます。

   10. **[次へ]** をクリックし、 **[完了]** をクリックします。

       これで、VM リソースがスキーマデザイナーウィンドウに表示されます。 リソースに関連付けられているプロパティと操作を確認できます。 次に、更新されたスキーマファイルを web サービスの仮想ディレクトリにエクスポートします。

#### <a name="exporting-schema-files-from-the-schema-designer"></a>スキーマデザイナーからのスキーマファイルのエクスポート

1. スキーマデザイナーウィンドウの空白の領域を右クリックし、 **[スキーマファイル]** をクリックします。**エクスポート**。 **[名前を付けて保存]** ダイアログボックスが表示されます。

2. MOF ファイルをインポートしたディレクトリに移動します。 ファイルに元の MOF ファイルと同じ名前を付け (既定では Schema .mof)、 **[保存]** をクリックします。 既存のファイルを上書きすることを確認します。

   **[名前を付けて保存]** ダイアログに明示的に指定されていませんが、スキーマの .mof ファイルとスキーマ .xml ファイルの両方を置き換えます。

## <a name="next-steps"></a>次の手順

管理 OData web サービスから新しい VM リソースにアクセスする前に、「[ロールベースの承認を構成](./configuring-role-based-authorization.md)する」で説明されているように、Hyper-v Windows PowerShell モジュールへのアクセスを許可するように、RbacConfiguration .xml ファイルを更新する必要があります。また、web サービスを再起動する必要もあります。