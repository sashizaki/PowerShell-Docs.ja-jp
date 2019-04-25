---
title: Windows PowerShell スナップインを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], examples
ms.assetid: 71bd9b2c-5f2e-4aa8-b5fe-08c956540d37
caps.latest.revision: 10
ms.openlocfilehash: 43199544dc02ccae4b61053c30d6ed36576adfcf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067996"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a>Windows PowerShell スナップインを作成する方法

Windows PowerShell スナップインをシェルの機能を拡張するため、シェルを使用して一連のコマンドレットと別の Windows PowerShell プロバイダーを登録するためのメカニズムを提供します。 Windows PowerShell スナップインを登録できますコマンドレットとプロバイダーがすべて 1 つのアセンブリにまたは特定のコマンドレットとプロバイダーの一覧を登録できます。

他のオペレーティング システムになると同様、保護されたディレクトリでスナップイン アセンブリをインストールする必要があります。 それ以外の場合、悪意のあるユーザーは、アンセーフ コードとアセンブリを置き換えることができます。

## <a name="windows-powershell-snap-in-classes"></a>Windows PowerShell スナップイン クラス

すべての Windows PowerShell スナップイン クラスから派生、 [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn)または[System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラス。

## <a name="examples"></a>例

[Windows PowerShell スナップインの書き込み](./writing-a-windows-powershell-snap-in.md):この例では、アセンブリ内のすべてのコマンドレットとプロバイダーの登録に使用するスナップインを作成する方法を示します。

[カスタム Windows PowerShell スナップインの書き込み](./writing-a-custom-windows-powershell-snap-in.md):この例では、1 つのアセンブリでのコマンドレットとプロバイダー可能性があるが存在しない一連の特定の登録に使用されるカスタム スナップインを作成する方法を示します。

## <a name="see-also"></a>参照

[System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn)

[System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[コマンドレットを登録します。](./registering-cmdlets.md)

[Windows PowerShell シェル SDK](../windows-powershell-reference.md)
