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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369751"
---
# <a name="format-parameters"></a><span data-ttu-id="c10fd-102">書式のパラメーター</span><span class="sxs-lookup"><span data-stu-id="c10fd-102">Format Parameters</span></span>

<span data-ttu-id="c10fd-103">次の表に、データの書式設定または生成に使用されるパラメーターの推奨される名前と機能を示します。</span><span class="sxs-lookup"><span data-stu-id="c10fd-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="c10fd-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c10fd-104">Parameter</span></span>|<span data-ttu-id="c10fd-105">機能</span><span class="sxs-lookup"><span data-stu-id="c10fd-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="c10fd-106">**As**</span><span class="sxs-lookup"><span data-stu-id="c10fd-106">**As**</span></span><br><span data-ttu-id="c10fd-107">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="c10fd-107">Data type: Keyword</span></span>|<span data-ttu-id="c10fd-108">コマンドレットの出力形式を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="c10fd-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="c10fd-109">たとえば、テキストやスクリプトなどが考えられます。</span><span class="sxs-lookup"><span data-stu-id="c10fd-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="c10fd-110">**Binary**</span><span class="sxs-lookup"><span data-stu-id="c10fd-110">**Binary**</span></span><br><span data-ttu-id="c10fd-111">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c10fd-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="c10fd-112">コマンドレットがバイナリ値を処理することを示すには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="c10fd-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="c10fd-113">**[エンコード]**</span><span class="sxs-lookup"><span data-stu-id="c10fd-113">**Encoding**</span></span><br><span data-ttu-id="c10fd-114">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="c10fd-114">Data type: Keyword</span></span>|<span data-ttu-id="c10fd-115">サポートされているエンコードの種類を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="c10fd-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="c10fd-116">たとえば、ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、Byte、String などの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c10fd-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="c10fd-117">**改行**</span><span class="sxs-lookup"><span data-stu-id="c10fd-117">**NewLine**</span></span><br><span data-ttu-id="c10fd-118">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c10fd-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="c10fd-119">パラメーターを指定したときに改行文字がサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="c10fd-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="c10fd-120">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="c10fd-120">**ShortName**</span></span><br><span data-ttu-id="c10fd-121">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c10fd-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="c10fd-122">パラメーターを指定したときに短い名前がサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="c10fd-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="c10fd-123">**Width**</span><span class="sxs-lookup"><span data-stu-id="c10fd-123">**Width**</span></span><br><span data-ttu-id="c10fd-124">データ型: Int32</span><span class="sxs-lookup"><span data-stu-id="c10fd-124">Data type: Int32</span></span>|<span data-ttu-id="c10fd-125">ユーザーが出力デバイスの幅を指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="c10fd-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="c10fd-126">**アラウンド**</span><span class="sxs-lookup"><span data-stu-id="c10fd-126">**Wrap**</span></span><br><span data-ttu-id="c10fd-127">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c10fd-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="c10fd-128">パラメーターを指定したときにテキストの折り返しがサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="c10fd-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="c10fd-129">参照</span><span class="sxs-lookup"><span data-stu-id="c10fd-129">See Also</span></span>

[<span data-ttu-id="c10fd-130">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="c10fd-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="c10fd-131">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c10fd-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="c10fd-132">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="c10fd-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
