---
title: コマンドレットの説明を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47af9d57-bd63-4596-816a-0b717418476b
caps.latest.revision: 10
ms.openlocfilehash: a2e4c4d42566d5a52006924eab02295c37cf3159
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083520"
---
# <a name="how-to-add-a-cmdlet-description"></a>コマンドレットの説明を追加する方法

このセクションでは、コマンドレットのヘルプの [説明] セクションに表示されるコンテンツを追加する方法について説明します。 ヘルプ ファイルでこのコンテンツは、各コマンドレットのコマンドのノードに追加されます。

> [!NOTE]
> ヘルプ ファイル、開いている Windows PowerShell のインストール ディレクトリにある dll Help.xml ファイルの 1 つの完全なビュー。 たとえば、Microsoft.PowerShell.Commands.Management.dll Help.xml ファイルには、Windows PowerShell コマンドレットのいくつかのコンテンツが含まれています。

### <a name="to-add-a-description"></a>説明を追加するには

- さらに詳しくコマンドレットの基本的な機能の説明から始めます。 多くの場合は、コマンドレット名で使用される用語について説明し、例を使用して未知の概念を説明します。 たとえば、コマンドレットでデータをファイルに追加すると場合、は、既存のファイルの末尾にデータが追加されることを説明します。

- すべてのコマンドレットの機能を検索するには、パラメーター リストを確認します。 コマンドレットの主な機能について説明し、その他の機能と機能します。 たとえば、コマンドレットの主な機能が 1 つのプロパティを変更するのには、コマンドレットがすべてのプロパティを変更する場合は、そのように言ってについて詳しく説明します。 コマンドレットのパラメーターには、さまざまな方法で情報を要求するユーザーができるように、これについて説明します。

- ユーザーが明らかな使用だけでなく、コマンドレットを使用できる方法に関する情報が含まれます。 たとえば、オブジェクトを使用することができる`Get-Host`コマンドレットは、Windows PowerShell コマンド ウィンドウ内のテキストの色に変更を取得します。

  次に例を示します。"、`Get-Acl`コマンドレットは、ファイルまたはリソースのセキュリティ記述子を表すオブジェクトを取得します。 セキュリティ記述子には、リソースのアクセス制御リスト (ACL) が含まれます。 ACL アクセス許可が指定のユーザーおよびユーザー グループがリソースにアクセスする必要がある。"

- 詳細な説明は、コマンドレットを示す必要がありますが、コマンドレットを使用する概念のについては説明する必要があります。 その他のメモには、概念の定義を配置します。

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)