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
ms.openlocfilehash: 73834cea1d90943cf954728d6295d8eb33e14f57
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859758"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="efa2f-102">Windows PowerShell スナップインを作成する方法</span><span class="sxs-lookup"><span data-stu-id="efa2f-102">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="efa2f-103">Windows PowerShell スナップインをシェルの機能を拡張するため、シェルを使用して一連のコマンドレットと別の Windows PowerShell プロバイダーを登録するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="efa2f-103">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="efa2f-104">Windows PowerShell スナップインを登録できますコマンドレットとプロバイダーがすべて 1 つのアセンブリにまたは特定のコマンドレットとプロバイダーの一覧を登録できます。</span><span class="sxs-lookup"><span data-stu-id="efa2f-104">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="efa2f-105">他のオペレーティング システムになると同様、保護されたディレクトリでスナップイン アセンブリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="efa2f-105">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="efa2f-106">それ以外の場合、悪意のあるユーザーは、アンセーフ コードとアセンブリを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="efa2f-106">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="efa2f-107">Windows PowerShell スナップイン クラス</span><span class="sxs-lookup"><span data-stu-id="efa2f-107">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="efa2f-108">すべての Windows PowerShell スナップイン クラスから派生、 [System.Management.Automation.Pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)または[System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラス。</span><span class="sxs-lookup"><span data-stu-id="efa2f-108">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.Pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="efa2f-109">例</span><span class="sxs-lookup"><span data-stu-id="efa2f-109">Examples</span></span>

<span data-ttu-id="efa2f-110">[Windows PowerShell スナップインの書き込み](./writing-a-windows-powershell-snap-in.md):この例では、アセンブリ内のすべてのコマンドレットとプロバイダーの登録に使用するスナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="efa2f-110">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="efa2f-111">[カスタム Windows PowerShell スナップインの書き込み](./writing-a-custom-windows-powershell-snap-in.md):この例では、1 つのアセンブリでのコマンドレットとプロバイダー可能性があるが存在しない一連の特定の登録に使用されるカスタム スナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="efa2f-111">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="efa2f-112">参照</span><span class="sxs-lookup"><span data-stu-id="efa2f-112">See Also</span></span>

[<span data-ttu-id="efa2f-113">System.Management.Automation.Pssnapin</span><span class="sxs-lookup"><span data-stu-id="efa2f-113">System.Management.Automation.Pssnapin</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="efa2f-114">System.Management.Automation.Custompssnapin</span><span class="sxs-lookup"><span data-stu-id="efa2f-114">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="efa2f-115">コマンドレットを登録します。</span><span class="sxs-lookup"><span data-stu-id="efa2f-115">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="efa2f-116">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="efa2f-116">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
