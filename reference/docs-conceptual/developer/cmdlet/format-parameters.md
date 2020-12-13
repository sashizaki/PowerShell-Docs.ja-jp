---
ms.date: 09/13/2016
ms.topic: reference
title: 書式のパラメーター
description: 書式のパラメーター
ms.openlocfilehash: 5f970683fedc71b208ff6becad761d94611a91a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652821"
---
# <a name="format-parameters"></a><span data-ttu-id="1446e-103">書式のパラメーター</span><span class="sxs-lookup"><span data-stu-id="1446e-103">Format Parameters</span></span>

<span data-ttu-id="1446e-104">次の表に、データの書式設定または生成に使用されるパラメーターの推奨される名前と機能を示します。</span><span class="sxs-lookup"><span data-stu-id="1446e-104">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="1446e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1446e-105">Parameter</span></span>|<span data-ttu-id="1446e-106">機能</span><span class="sxs-lookup"><span data-stu-id="1446e-106">Functionality</span></span>|
|---|---|
|<span data-ttu-id="1446e-107">**As**</span><span class="sxs-lookup"><span data-stu-id="1446e-107">**As**</span></span><br><span data-ttu-id="1446e-108">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="1446e-108">Data type: Keyword</span></span>|<span data-ttu-id="1446e-109">コマンドレットの出力形式を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="1446e-109">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="1446e-110">たとえば、テキストやスクリプトなどが考えられます。</span><span class="sxs-lookup"><span data-stu-id="1446e-110">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="1446e-111">**Binary**</span><span class="sxs-lookup"><span data-stu-id="1446e-111">**Binary**</span></span><br><span data-ttu-id="1446e-112">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1446e-112">Data type: SwitchParameter</span></span>|<span data-ttu-id="1446e-113">コマンドレットがバイナリ値を処理することを示すには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="1446e-113">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="1446e-114">**[エンコード]**</span><span class="sxs-lookup"><span data-stu-id="1446e-114">**Encoding**</span></span><br><span data-ttu-id="1446e-115">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="1446e-115">Data type: Keyword</span></span>|<span data-ttu-id="1446e-116">サポートされているエンコードの種類を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="1446e-116">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="1446e-117">たとえば、ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、Byte、String などの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1446e-117">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="1446e-118">**改行**</span><span class="sxs-lookup"><span data-stu-id="1446e-118">**NewLine**</span></span><br><span data-ttu-id="1446e-119">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1446e-119">Data type: SwitchParameter</span></span>|<span data-ttu-id="1446e-120">パラメーターを指定したときに改行文字がサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="1446e-120">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="1446e-121">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="1446e-121">**ShortName**</span></span><br><span data-ttu-id="1446e-122">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1446e-122">Data type: SwitchParameter</span></span>|<span data-ttu-id="1446e-123">パラメーターを指定したときに短い名前がサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="1446e-123">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="1446e-124">**Width**</span><span class="sxs-lookup"><span data-stu-id="1446e-124">**Width**</span></span><br><span data-ttu-id="1446e-125">データ型: Int32</span><span class="sxs-lookup"><span data-stu-id="1446e-125">Data type: Int32</span></span>|<span data-ttu-id="1446e-126">ユーザーが出力デバイスの幅を指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="1446e-126">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="1446e-127">**ラップ**</span><span class="sxs-lookup"><span data-stu-id="1446e-127">**Wrap**</span></span><br><span data-ttu-id="1446e-128">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1446e-128">Data type: SwitchParameter</span></span>|<span data-ttu-id="1446e-129">パラメーターを指定したときにテキストの折り返しがサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="1446e-129">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="1446e-130">参照</span><span class="sxs-lookup"><span data-stu-id="1446e-130">See Also</span></span>

[<span data-ttu-id="1446e-131">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="1446e-131">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="1446e-132">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="1446e-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="1446e-133">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="1446e-133">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
