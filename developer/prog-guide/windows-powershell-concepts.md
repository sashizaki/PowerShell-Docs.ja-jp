---
title: Windows PowerShell の概念 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3dd5608e-50b6-4c6a-aee3-dde0e86032bc
caps.latest.revision: 7
ms.openlocfilehash: c4b13518ad6452a39ca49e897e1d3e353818d332
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081038"
---
# <a name="windows-powershell-concepts"></a><span data-ttu-id="be82c-102">Windows PowerShell の概念</span><span class="sxs-lookup"><span data-stu-id="be82c-102">Windows PowerShell Concepts</span></span>

<span data-ttu-id="be82c-103">このセクションには、開発者の視点から Windows PowerShell を理解するのに役立つ概念情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be82c-103">This section contains conceptual information that will help you understand Windows PowerShell from the viewpoint of a developer.</span></span>

|<span data-ttu-id="be82c-104">トピック名</span><span class="sxs-lookup"><span data-stu-id="be82c-104">Topic Name</span></span>|<span data-ttu-id="be82c-105">説明</span><span class="sxs-lookup"><span data-stu-id="be82c-105">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="be82c-106">Windows PowerShell プロバイダー</span><span class="sxs-lookup"><span data-stu-id="be82c-106">Windows PowerShell Providers</span></span>](http://msdn.microsoft.com/en-us/a65c5c75-1131-4ade-90d3-a613dbe620e9)|<span data-ttu-id="be82c-107">データへのアクセスに使用される Windows PowerShell プロバイダーに関するディスカッションを格納します。</span><span class="sxs-lookup"><span data-stu-id="be82c-107">A discussion about Windows PowerShell providers that are used to access data stores.</span></span>|
|[<span data-ttu-id="be82c-108">Windows PowerShell スナップイン</span><span class="sxs-lookup"><span data-stu-id="be82c-108">Windows PowerShell Snap-ins</span></span>](http://msdn.microsoft.com/en-us/20e081a9-522c-48bf-9f21-faaf8cca2e82)|<span data-ttu-id="be82c-109">コマンドレットとプロバイダーを登録するためのメカニズム。</span><span class="sxs-lookup"><span data-stu-id="be82c-109">A mechanism for registering cmdlets and providers.</span></span> <span data-ttu-id="be82c-110">(またを参照してください[Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md))。</span><span class="sxs-lookup"><span data-stu-id="be82c-110">(See also, [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).)</span></span>|
|[<span data-ttu-id="be82c-111">Windows PowerShell ランタイム</span><span class="sxs-lookup"><span data-stu-id="be82c-111">Windows PowerShell Runtime</span></span>](http://msdn.microsoft.com/en-us/949f06e8-0224-4cd3-bbad-a0cebbb5dec8)|<span data-ttu-id="be82c-112">Windows PowerShell 実行空間の現在のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="be82c-112">The current instance of the Windows PowerShell runspace.</span></span>|
|[<span data-ttu-id="be82c-113">Windows PowerShell 実行空間</span><span class="sxs-lookup"><span data-stu-id="be82c-113">Windows PowerShell Runspaces</span></span>](http://msdn.microsoft.com/en-us/a1582cfe-f06d-4aff-adc6-71f49a860ce9)|<span data-ttu-id="be82c-114">運用環境をコマンドが処理されます。</span><span class="sxs-lookup"><span data-stu-id="be82c-114">The operating environments where commands are processed.</span></span>|
|[<span data-ttu-id="be82c-115">Windows PowerShell の名前空間</span><span class="sxs-lookup"><span data-stu-id="be82c-115">Windows PowerShell Namespaces</span></span>](http://msdn.microsoft.com/en-us/04bd2841-e90c-47d2-8a1f-3aeb3df35176)|<span data-ttu-id="be82c-116">Windows PowerShell API 名前空間の概要です。</span><span class="sxs-lookup"><span data-stu-id="be82c-116">Overview of Windows PowerShell API namespaces.</span></span>|
|[<span data-ttu-id="be82c-117">Windows PowerShell のヘルプ</span><span class="sxs-lookup"><span data-stu-id="be82c-117">Windows PowerShell Help</span></span>](http://msdn.microsoft.com/en-us/097b7c1c-a056-4b36-9c86-65b2ee702fc7)|<span data-ttu-id="be82c-118">コマンドレットのヘルプの記述方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be82c-118">A discussion about writing cmdlet Help.</span></span>|
|[<span data-ttu-id="be82c-119">確認を求める</span><span class="sxs-lookup"><span data-stu-id="be82c-119">Requesting Confirmation</span></span>](../cmdlet/requesting-confirmation-from-cmdlets.md)|<span data-ttu-id="be82c-120">どのコマンドレットとプロバイダー、このフィードバックをアクションの前に、ユーザーから要求についてのディスカッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="be82c-120">A discussion about how cmdlets and providers request feedback from the user before an action is taken.</span></span>|
|[<span data-ttu-id="be82c-121">Windows PowerShell オブジェクトの概念</span><span class="sxs-lookup"><span data-stu-id="be82c-121">Windows PowerShell Object Concepts</span></span>](http://msdn.microsoft.com/en-us/a1449178-b6fd-4ca8-a5e1-d747c2c54181)|<span data-ttu-id="be82c-122">どの Windows PowerShell は、オブジェクトを処理します。</span><span class="sxs-lookup"><span data-stu-id="be82c-122">How Windows PowerShell handles objects.</span></span>|
|[<span data-ttu-id="be82c-123">Windows PowerShell の拡張型システム (ETS)</span><span class="sxs-lookup"><span data-stu-id="be82c-123">Windows PowerShell Extended Type System (ETS)</span></span>](http://msdn.microsoft.com/en-us/12700631-be23-4e6b-9bf0-81ea0d166353)|<span data-ttu-id="be82c-124">オブジェクトをプログラムで拡張します。</span><span class="sxs-lookup"><span data-stu-id="be82c-124">Programmatically extending objects.</span></span>|

## <a name="see-also"></a><span data-ttu-id="be82c-125">参照</span><span class="sxs-lookup"><span data-stu-id="be82c-125">See Also</span></span>

[<span data-ttu-id="be82c-126">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="be82c-126">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)