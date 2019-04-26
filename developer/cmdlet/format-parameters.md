---
title: パラメーターを書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10e025c5-9aa6-45a5-b851-23d14db1f4cc
caps.latest.revision: 7
ms.openlocfilehash: 0bd3888d81aa6d1dde26c0066f7bca9dac8a8bca
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068115"
---
# <a name="format-parameters"></a><span data-ttu-id="97e7e-102">書式のパラメーター</span><span class="sxs-lookup"><span data-stu-id="97e7e-102">Format Parameters</span></span>

<span data-ttu-id="97e7e-103">次の表は、推奨される名前と書式を設定するデータを生成するかに使用されるパラメーターの機能を示します。</span><span class="sxs-lookup"><span data-stu-id="97e7e-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="97e7e-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97e7e-104">Parameter</span></span>|<span data-ttu-id="97e7e-105">機能</span><span class="sxs-lookup"><span data-stu-id="97e7e-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="97e7e-106">**として**</span><span class="sxs-lookup"><span data-stu-id="97e7e-106">**As**</span></span><br><span data-ttu-id="97e7e-107">データの種類:キーワード</span><span class="sxs-lookup"><span data-stu-id="97e7e-107">Data type: Keyword</span></span>|<span data-ttu-id="97e7e-108">コマンドレットの出力形式を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="97e7e-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="97e7e-109">たとえば、テキストまたはスクリプト可能な値になります。</span><span class="sxs-lookup"><span data-stu-id="97e7e-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="97e7e-110">**Binary**</span><span class="sxs-lookup"><span data-stu-id="97e7e-110">**Binary**</span></span><br><span data-ttu-id="97e7e-111">データの種類:SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="97e7e-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="97e7e-112">コマンドレットは、バイナリ値を処理することを示すために、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="97e7e-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="97e7e-113">**エンコード**</span><span class="sxs-lookup"><span data-stu-id="97e7e-113">**Encoding**</span></span><br><span data-ttu-id="97e7e-114">データの種類:キーワード</span><span class="sxs-lookup"><span data-stu-id="97e7e-114">Data type: Keyword</span></span>|<span data-ttu-id="97e7e-115">サポートされているエンコードの種類を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="97e7e-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="97e7e-116">たとえば、使用可能な値は、ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、バイト、および文字列可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97e7e-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="97e7e-117">**NewLine**</span><span class="sxs-lookup"><span data-stu-id="97e7e-117">**NewLine**</span></span><br><span data-ttu-id="97e7e-118">データの種類:SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="97e7e-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="97e7e-119">このパラメーターを実装するは、パラメーターを指定した場合に改行文字がサポートされるようにします。</span><span class="sxs-lookup"><span data-stu-id="97e7e-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="97e7e-120">**短い名前**</span><span class="sxs-lookup"><span data-stu-id="97e7e-120">**ShortName**</span></span><br><span data-ttu-id="97e7e-121">データの種類:SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="97e7e-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="97e7e-122">このパラメーターを実装するは、パラメーターを指定した場合に短い名前がサポートされるようにします。</span><span class="sxs-lookup"><span data-stu-id="97e7e-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="97e7e-123">**Width**</span><span class="sxs-lookup"><span data-stu-id="97e7e-123">**Width**</span></span><br><span data-ttu-id="97e7e-124">データの種類:Int32</span><span class="sxs-lookup"><span data-stu-id="97e7e-124">Data type: Int32</span></span>|<span data-ttu-id="97e7e-125">このパラメーターを実装するは、ユーザーは、出力デバイスの幅を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="97e7e-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="97e7e-126">**ラップ**</span><span class="sxs-lookup"><span data-stu-id="97e7e-126">**Wrap**</span></span><br><span data-ttu-id="97e7e-127">データの種類:SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="97e7e-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="97e7e-128">このパラメーターを実装するは、パラメーターを指定するテキストの折り返しがサポートされるようにします。</span><span class="sxs-lookup"><span data-stu-id="97e7e-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="97e7e-129">参照</span><span class="sxs-lookup"><span data-stu-id="97e7e-129">See Also</span></span>

[<span data-ttu-id="97e7e-130">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="97e7e-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="97e7e-131">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="97e7e-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="97e7e-132">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="97e7e-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
