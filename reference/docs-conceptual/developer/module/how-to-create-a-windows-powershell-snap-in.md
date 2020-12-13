---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell スナップインを作成する方法
description: Windows PowerShell スナップインを作成する方法
ms.openlocfilehash: 29394ebcd2f7c4a547aabcb88685ff494b2c381d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657270"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="79a78-103">Windows PowerShell スナップインを作成する方法</span><span class="sxs-lookup"><span data-stu-id="79a78-103">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="79a78-104">Windows PowerShell スナップインは、一連のコマンドレットと別の Windows PowerShell プロバイダーをシェルに登録するためのメカニズムを提供します。これにより、シェルの機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="79a78-104">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="79a78-105">Windows PowerShell スナップインでは、すべてのコマンドレットとプロバイダーを1つのアセンブリに登録したり、特定のコマンドレットとプロバイダーの一覧を登録したりできます。</span><span class="sxs-lookup"><span data-stu-id="79a78-105">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="79a78-106">スナップインアセンブリは、他のオペレーティングシステムと同様に、保護されたディレクトリにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79a78-106">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="79a78-107">そうしないと、悪意のあるユーザーがアセンブリを安全でないコードに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="79a78-107">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="79a78-108">Windows PowerShell スナップインクラス</span><span class="sxs-lookup"><span data-stu-id="79a78-108">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="79a78-109">すべての Windows PowerShell スナップインクラスは、 [add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn) クラスまたは [Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="79a78-109">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="79a78-110">例</span><span class="sxs-lookup"><span data-stu-id="79a78-110">Examples</span></span>

<span data-ttu-id="79a78-111">[Windows PowerShell スナップインの記述](./writing-a-windows-powershell-snap-in.md): この例では、アセンブリ内のすべてのコマンドレットとプロバイダーを登録するために使用されるスナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79a78-111">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="79a78-112">[カスタム Windows PowerShell スナップ](./writing-a-custom-windows-powershell-snap-in.md)インの作成: この例では、単一のアセンブリに存在する可能性がある特定のコマンドレットとプロバイダーのセットを登録するために使用されるカスタムスナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79a78-112">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="79a78-113">参照</span><span class="sxs-lookup"><span data-stu-id="79a78-113">See Also</span></span>

[<span data-ttu-id="79a78-114">Add-pssnapin (システム管理)</span><span class="sxs-lookup"><span data-stu-id="79a78-114">System.Management.Automation.PSSnapIn</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="79a78-115">Custompssnapin (システム管理)</span><span class="sxs-lookup"><span data-stu-id="79a78-115">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="79a78-116">コマンドレットを登録する</span><span class="sxs-lookup"><span data-stu-id="79a78-116">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="79a78-117">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="79a78-117">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
