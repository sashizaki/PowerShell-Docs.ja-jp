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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364431"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a>Windows PowerShell スナップインを作成する方法

Windows PowerShell スナップインは、一連のコマンドレットと別の Windows PowerShell プロバイダーをシェルに登録するためのメカニズムを提供します。これにより、シェルの機能が拡張されます。 Windows PowerShell スナップインでは、すべてのコマンドレットとプロバイダーを1つのアセンブリに登録したり、特定のコマンドレットとプロバイダーの一覧を登録したりできます。

スナップインアセンブリは、他のオペレーティングシステムと同様に、保護されたディレクトリにインストールする必要があります。 そうしないと、悪意のあるユーザーがアセンブリを安全でないコードに置き換えることができます。

## <a name="windows-powershell-snap-in-classes"></a>Windows PowerShell スナップインクラス

すべての Windows PowerShell スナップインクラスは、 [add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)クラスまたは[Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラスから派生しています。

## <a name="examples"></a>例

[Windows PowerShell スナップインの記述](./writing-a-windows-powershell-snap-in.md): この例では、アセンブリ内のすべてのコマンドレットとプロバイダーを登録するために使用されるスナップインを作成する方法を示します。

[カスタム Windows PowerShell スナップ](./writing-a-custom-windows-powershell-snap-in.md)インの作成: この例では、単一のアセンブリに存在する可能性がある特定のコマンドレットとプロバイダーのセットを登録するために使用されるカスタムスナップインを作成する方法を示します。

## <a name="see-also"></a>参照

[Add-pssnapin (システム管理)](/dotnet/api/System.Management.Automation.PSSnapIn)

[Custompssnapin (システム管理)](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[コマンドレットの登録](./registering-cmdlets.md)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
