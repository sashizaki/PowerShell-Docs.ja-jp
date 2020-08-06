---
title: パラメーターの書式設定 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8e031f62aa8bcb0e9d5b900b2eace7187b1f3dd
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784284"
---
# <a name="format-parameters"></a><span data-ttu-id="e6d25-102">書式のパラメーター</span><span class="sxs-lookup"><span data-stu-id="e6d25-102">Format Parameters</span></span>

<span data-ttu-id="e6d25-103">次の表に、データの書式設定または生成に使用されるパラメーターの推奨される名前と機能を示します。</span><span class="sxs-lookup"><span data-stu-id="e6d25-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="e6d25-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6d25-104">Parameter</span></span>|<span data-ttu-id="e6d25-105">機能</span><span class="sxs-lookup"><span data-stu-id="e6d25-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="e6d25-106">**As**</span><span class="sxs-lookup"><span data-stu-id="e6d25-106">**As**</span></span><br><span data-ttu-id="e6d25-107">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="e6d25-107">Data type: Keyword</span></span>|<span data-ttu-id="e6d25-108">コマンドレットの出力形式を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6d25-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="e6d25-109">たとえば、テキストやスクリプトなどが考えられます。</span><span class="sxs-lookup"><span data-stu-id="e6d25-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="e6d25-110">**Binary**</span><span class="sxs-lookup"><span data-stu-id="e6d25-110">**Binary**</span></span><br><span data-ttu-id="e6d25-111">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e6d25-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="e6d25-112">コマンドレットがバイナリ値を処理することを示すには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6d25-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="e6d25-113">**エンコード**</span><span class="sxs-lookup"><span data-stu-id="e6d25-113">**Encoding**</span></span><br><span data-ttu-id="e6d25-114">データ型: キーワード</span><span class="sxs-lookup"><span data-stu-id="e6d25-114">Data type: Keyword</span></span>|<span data-ttu-id="e6d25-115">サポートされているエンコードの種類を指定するには、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6d25-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="e6d25-116">たとえば、ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、Byte、String などの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e6d25-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="e6d25-117">**改行**</span><span class="sxs-lookup"><span data-stu-id="e6d25-117">**NewLine**</span></span><br><span data-ttu-id="e6d25-118">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e6d25-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="e6d25-119">パラメーターを指定したときに改行文字がサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6d25-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="e6d25-120">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="e6d25-120">**ShortName**</span></span><br><span data-ttu-id="e6d25-121">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e6d25-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="e6d25-122">パラメーターを指定したときに短い名前がサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6d25-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="e6d25-123">**Width**</span><span class="sxs-lookup"><span data-stu-id="e6d25-123">**Width**</span></span><br><span data-ttu-id="e6d25-124">データ型: Int32</span><span class="sxs-lookup"><span data-stu-id="e6d25-124">Data type: Int32</span></span>|<span data-ttu-id="e6d25-125">ユーザーが出力デバイスの幅を指定できるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6d25-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="e6d25-126">**ラップ**</span><span class="sxs-lookup"><span data-stu-id="e6d25-126">**Wrap**</span></span><br><span data-ttu-id="e6d25-127">データ型: SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e6d25-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="e6d25-128">パラメーターを指定したときにテキストの折り返しがサポートされるように、このパラメーターを実装します。</span><span class="sxs-lookup"><span data-stu-id="e6d25-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="e6d25-129">参照</span><span class="sxs-lookup"><span data-stu-id="e6d25-129">See Also</span></span>

[<span data-ttu-id="e6d25-130">コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="e6d25-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="e6d25-131">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="e6d25-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="e6d25-132">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e6d25-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
