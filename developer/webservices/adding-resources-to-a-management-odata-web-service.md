---
title: リソース管理の OData Web サービスへの追加 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e620bf6d-76be-47b0-a7a8-f43418f30c60
caps.latest.revision: 6
ms.openlocfilehash: b81a32b867795ae51c3f5308c2f82c31ed2747fa
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858368"
---
# <a name="adding-resources-to-a-management-odata-web-service"></a>Management OData Web サービスにリソースを追加する

この例では、Management OData スキーマ デザイナーを使用して、既存の管理の OData web サービスにリソースを追加する方法を示します。 [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプルは、プロセスとサーバーのリソースを公開する web サービスを作成します。 この例では、web サービスに仮想マシン (VM) リソースを追加します。

## <a name="prerequisites"></a>前提条件

このトピックでは、ダウンロードおよびインストールすることが前提としています、 [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) 」の説明に従ってサンプル[Windows PowerShell Web サービスを作成する](./creating-a-management-odata-web-service.md)、ダウンロードしてインストールして、[Management OData スキーマ デザイナー](https://marketplace.visualstudio.com/items?itemName=jlisc0.ManagementODataSchemaDesigner)します。 このトピックでは、Management Odata エンドポイントのセットアップ先コンピューターにインストールされている HYPER-V Windows PowerShell モジュールがあることも想定しています。

## <a name="adding-vm-as-a-resource-to-the-web-service"></a>VM をリソースとして Web サービスに追加します。

最初の手順では、スキーマ デザイナーに既存の管理の OData エンドポイントからスキーマをインポートします。 次の手順では、その方法について説明します。

#### <a name="importing-an-existing-schema-into-the-schema-designer"></a>スキーマ デザイナーへの既存のスキーマのインポート

1. Management OData スキーマ デザイナーを開きます。

2. **ファイル**メニューの **ファイル**;**新しい**;**ファイル**します。 **新しいファイル**ダイアログが表示されます。

3. クリックして**管理 OData モデル**、順にクリックします**オープン**します。

4. メイン ウィンドウを右クリックし、をクリックして**スキーマ ファイル**;**インポート**します。 **オープン**ダイアログが表示されます。

5. Management OData web サービスを設定する場所のフォルダーに移動し、 [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)サンプル。 サンプルに用意されている Windows PowerShell スクリプトを使用して、スクリプトを変更することがなく、エンドポイントを設定した場合に、そのフォルダーは**C:\inetpub\wwwroot\Modata**します。 Schema.mof を選択し、クリックして**オープン**します。

   この時点では、テキスト エディターで、Schema.mof ファイルと Schema.xml ファイルを開くし、プロセスおよびサービスのリソースのマッピングが含まれることに注意してください。 .Schema.mof ファイルを使用して[Distributed Management Task Force](https://www.dmtf.org/) (DTMF) 管理オブジェクト (MOF) 標準です。 Schema.xml ファイルで説明されている XML スキーマを使用する[リソース マッピング スキーマ](./resource-mapping-schema.md)します。

   次の手順では、スキーマ モデルでの HYPER-V コマンドレットをインポートする方法について説明します。

#### <a name="importing-cmdlets-into-the-schema"></a>スキーマにコマンドレットをインポートします。

1. スキーマのデザイナー ウィンドウの空白の領域を右クリックし、をクリックして**インポート コマンドレット**します。 **コマンドレットのインポート ウィザード**ダイアログが表示されます。

2. 確認**ローカル コンピューター**が選択されているし、をクリックして**次**します。

3. インストールされている Windows PowerShell モジュールが選択されていることを確認し、ドロップダウン リストから、HYPER-V を選択します。 クリックして**次**します。 **[次へ]** をクリックします。

4. **コマンドレットの名詞**一覧で、 **VM**します。 **[次へ]** をクリックします。

5. この例では、コマンドレットの Get および Delete コマンドのみをバインドします。 クリア、**作成**と**更新**チェック ボックス、ことを確認します、**取得**と**削除**のチェック ボックスをオンします。 確認します、`Get-VM`コマンドレットが選択されている**取得**、および`Remove-VM`コマンドレットが選択されている**削除**します。

6. VM のコマンドレットのメタデータが出力の種類を指定しないので、出力の種類を指定するコマンドレットを実行する必要があります。 選択**出力の種類を提供する** をクリック**コマンドレットを実行**します。 **コマンドレットの実行**ダイアログが表示されます。 クリックして**実行**します。 **CLR 型**ボックスが表示された、`VirtualMachine`型。 をクリックして**OK**、順にクリックします**次**。

7. 既定では、VirtualMachine オブジェクトのプロパティをすべて選択されます。 Web サービスをこのリソースを要求するときに返されるデータの一部としてたくない任意のプロパティをオフにすることができます。 **[次へ]** をクリックします。

8. キーとして使用するには少なくとも 1 つのプロパティを選択する必要があります。 選択**名前** をクリックし、一覧で**次**。

9. 次のウィンドウでは、Management OData リソースのプロパティを基になるコマンドレットのプロパティにマップできます。 ウィザードでは、既定で同じ名前のプロパティがマップされます。 たとえば、`ComputerName`リソースのプロパティのマップ先、`ComputerName`コマンドレットのプロパティ。  指定できます、 `ComputerName` 、web サービスへの要求でプロパティに指定した値が渡される、`Get-VM`コマンドレット。 `Id` `Name`も既定でマップされます。

   10. をクリックして**次**、順にクリックします**完了**します。

       VM リソースは、スキーマ デザイナー ウィンドウに表示されます。 リソースに関連付けられている操作とプロパティを調べることができます。 次に、web サービス用の仮想ディレクトリに、更新されたスキーマ ファイルをエクスポートします。

#### <a name="exporting-schema-files-from-the-schema-designer"></a>スキーマ デザイナーからスキーマ ファイルをエクスポートします。

1. スキーマのデザイナー ウィンドウの空白の領域を右クリックし、をクリックして**スキーマ ファイル**;**エクスポート**します。 **付けて**ダイアログが表示されます。

2. MOF ファイルをインポートするには、同じディレクトリに移動します。 ファイルの名前を元の MOF ファイル (既定で *.schema.mof) と同じにして**保存**します。 既存のファイルを上書きすることを確認します。

   明示的に指定されていないが、**名前を付けて保存**ダイアログ ボックスで、この Schema.mof と Schema.xml ファイルを置き換えます。

## <a name="next-steps"></a>次の手順

Management OData web サービスから新しい VM リソースにアクセスする前に」の説明に従って、HYPER-V Windows PowerShell モジュールへのアクセスを許可する RbacConfiguration.xml ファイルを更新する必要があります[を構成するロール ベースの承認](./configuring-role-based-authorization.md)、web サービスを再起動することも必要があります。