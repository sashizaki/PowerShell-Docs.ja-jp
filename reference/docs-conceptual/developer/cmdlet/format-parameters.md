---
title: パラメーターの書式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10e025c5-9aa6-45a5-b851-23d14db1f4cc
caps.latest.revision: 7
ms.openlocfilehash: 0bd3888d81aa6d1dde26c0066f7bca9dac8a8bca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369751"
---
# <a name="format-parameters"></a><span data-ttu-id="0c32d-102">書式のパラメーター</span><span class="sxs-lookup"><span data-stu-id="0c32d-102">Format Parameters</span></span>

<span data-ttu-id="0c32d-103">次の表に、データの書式設定または生成に使用されるパラメーターの推奨される名前と機能を示します。</span><span class="sxs-lookup"><span data-stu-id="0c32d-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="0c32d-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c32d-104">Parameter</span></span>|<span data-ttu-id="0c32d-105">機能</span><span class="sxs-lookup"><span data-stu-id="0c32d-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="0c32d-106">**と**</span><span class="sxs-lookup"><span data-stu-id="0c32d-106">**As**</span></span><br><span data-ttu-id="0c32d-107">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="0c32d-107">Data type: Keyword</span></span>|<span data-ttu-id="0c32d-108">コマンドレットの出力形式を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="0c32d-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="0c32d-109">たとえば、テキストやスクリプトなどが考えられます。</span><span class="sxs-lookup"><span data-stu-id="0c32d-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="0c32d-110">**バイナリ**</span><span class="sxs-lookup"><span data-stu-id="0c32d-110">**Binary**</span></span><br><span data-ttu-id="0c32d-111">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0c32d-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="0c32d-112">コマンドレットがバイナリ値を処理することを示すには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="0c32d-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="0c32d-113">**暗号化**</span><span class="sxs-lookup"><span data-stu-id="0c32d-113">**Encoding**</span></span><br><span data-ttu-id="0c32d-114">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="0c32d-114">Data type: Keyword</span></span>|<span data-ttu-id="0c32d-115">サポートされているエンコードの種類を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="0c32d-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="0c32d-116">たとえば、ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、Byte、String などの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c32d-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="0c32d-117">**改行**</span><span class="sxs-lookup"><span data-stu-id="0c32d-117">**NewLine**</span></span><br><span data-ttu-id="0c32d-118">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0c32d-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="0c32d-119">パラメーターを指定したときに改行文字がサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="0c32d-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="0c32d-120">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="0c32d-120">**ShortName**</span></span><br><span data-ttu-id="0c32d-121">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0c32d-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="0c32d-122">パラメーターを指定したときに短い名前がサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="0c32d-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="0c32d-123">**幅**</span><span class="sxs-lookup"><span data-stu-id="0c32d-123">**Width**</span></span><br><span data-ttu-id="0c32d-124">データ型: Int32</span><span class="sxs-lookup"><span data-stu-id="0c32d-124">Data type: Int32</span></span>|<span data-ttu-id="0c32d-125">ユーザーが出力デバイスの幅を指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="0c32d-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="0c32d-126">**アラウンド**</span><span class="sxs-lookup"><span data-stu-id="0c32d-126">**Wrap**</span></span><br><span data-ttu-id="0c32d-127">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0c32d-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="0c32d-128">パラメーターを指定したときにテキストの折り返しがサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="0c32d-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="0c32d-129">参照</span><span class="sxs-lookup"><span data-stu-id="0c32d-129">See Also</span></span>

[<span data-ttu-id="0c32d-130">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="0c32d-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="0c32d-131">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="0c32d-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="0c32d-132">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="0c32d-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)