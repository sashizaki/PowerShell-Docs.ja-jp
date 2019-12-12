---
title: Windows PowerShell コマンドレットの概念 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b3ef3f4-c626-4679-884f-406a37412b3e
caps.latest.revision: 16
ms.openlocfilehash: 2f84c57da7429462c69b2a020d9f8ac04f8d0f35
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369121"
---
# <a name="windows-powershell-cmdlet-concepts"></a><span data-ttu-id="aabe8-102">Windows PowerShell コマンドレットの概念</span><span class="sxs-lookup"><span data-stu-id="aabe8-102">Windows PowerShell Cmdlet Concepts</span></span>

<span data-ttu-id="aabe8-103">ここでは、コマンドレットの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-103">This section describes how cmdlets work.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="aabe8-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aabe8-104">In This Section</span></span>

<span data-ttu-id="aabe8-105">このセクションには、次のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="aabe8-105">This section includes the following topics.</span></span>

<span data-ttu-id="aabe8-106">[コマンドレットの開発ガイドライン](./cmdlet-development-guidelines.md)このトピックでは、整形式のコマンドレットを生成するために使用できる開発ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-106">[Cmdlet Development Guidelines](./cmdlet-development-guidelines.md) This topic provides development guidelines that can be used to produce well-formed cmdlets.</span></span>

<span data-ttu-id="aabe8-107">[コマンドレットクラスの宣言](./cmdlet-class-declaration.md)このトピックでは、コマンドレットクラスの宣言について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-107">[Cmdlet Class Declaration](./cmdlet-class-declaration.md) This topic describes cmdlet class declaration.</span></span>

<span data-ttu-id="aabe8-108">[Windows PowerShell コマンドの承認](./approved-verbs-for-windows-powershell-commands.md)された動詞このトピックでは、コマンドレットクラスを宣言するときに使用できる定義済みのコマンドレット動詞の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-108">[Approved Verbs for Windows PowerShell Commands](./approved-verbs-for-windows-powershell-commands.md) This topic lists the predefined cmdlet verbs that you can use when you declare a cmdlet class.</span></span>

<span data-ttu-id="aabe8-109">[コマンドレットの入力処理方法](./cmdlet-input-processing-methods.md)このトピックでは、コマンドレットが前処理操作、入力処理操作、および処理後の操作を実行できるようにするメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-109">[Cmdlet Input Processing Methods](./cmdlet-input-processing-methods.md) This topic describes the methods that allow a cmdlet to perform preprocessing operations, input processing operations, and post processing operations.</span></span>

<span data-ttu-id="aabe8-110">[コマンドレットのパラメーター](./cmdlet-parameters.md)ここでは、コマンドレットに追加できるさまざまな種類のパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-110">[Cmdlet Parameters](./cmdlet-parameters.md) This section describes the different types of parameters that you can add to cmdlets.</span></span>

<span data-ttu-id="aabe8-111">[コマンドレットの属性](./cmdlet-attributes.md)このセクションでは、.NET Framework クラスをコマンドレットとして宣言し、フィールドをコマンドレットパラメーターとして宣言し、パラメーターの入力検証規則を宣言するために使用する属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-111">[Cmdlet Attributes](./cmdlet-attributes.md) This section describes the attributes that are used to declare .NET Framework classes as cmdlets, to declare fields as cmdlet parameters, and to declare input validation rules for parameters.</span></span>

<span data-ttu-id="aabe8-112">[コマンドレットのエイリアス](./cmdlet-aliases.md)このトピックでは、コマンドレットのエイリアスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-112">[Cmdlet Aliases](./cmdlet-aliases.md) This topic describes cmdlet aliases.</span></span>

<span data-ttu-id="aabe8-113">[コマンドレットの出力](./cmdlet-output.md)このセクションでは、コマンドレットから返される出力の種類と、コマンドレットによって返されるオブジェクトを定義および表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-113">[Cmdlet Output](./cmdlet-output.md) This section describes the type of output that cmdlets can return and how to define and display the objects that are returned by cmdlets.</span></span>

<span data-ttu-id="aabe8-114">[コマンドレットの登録](./modules-and-snap-ins.md)ここでは、モジュールとスナップインを使用してコマンドレットを登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-114">[Registering Cmdlets](./modules-and-snap-ins.md) This section describes how to register cmdlets by using modules and snap-ins.</span></span>

<span data-ttu-id="aabe8-115">[確認の要求](./requesting-confirmation-from-cmdlets.md)このセクションでは、コマンドレットがシステムに変更を加える前にユーザーに確認を要求する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-115">[Requesting Confirmation](./requesting-confirmation-from-cmdlets.md) This section describes how cmdlets request confirmation from a user before they make a change to the system.</span></span>

<span data-ttu-id="aabe8-116">[Windows PowerShell エラー報告](./error-reporting-concepts.md)ここでは、コマンドレットが終了エラーと終了しないエラーを報告する方法と、エラーレコードを解釈する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-116">[Windows PowerShell Error Reporting](./error-reporting-concepts.md) This section describes how cmdlets report terminating errors and non-terminating errors, and it describes how to interpret error records.</span></span>

<span data-ttu-id="aabe8-117">[バックグラウンドジョブ](./background-jobs.md)このトピックでは、現在のセッションで実行されているコマンドに干渉しないバックグラウンドジョブ内で、コマンドレットが作業を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-117">[Background Jobs](./background-jobs.md) This topic describes how cmdlets can perform their work within background jobs that do not interfere with the commands that are executing in the current session.</span></span>

<span data-ttu-id="aabe8-118">[コマンドレット内](./invoking-cmdlets-and-scripts-within-a-cmdlet.md)のコマンドレットとスクリプトの呼び出しこのトピックでは、コマンドレットが入力処理メソッド内から他のコマンドレットとスクリプトを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-118">[Invoking Cmdlets and Scripts Within a Cmdlet](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) This topic describes how cmdlets can invoke other cmdlets and scripts from within their input processing methods.</span></span>

<span data-ttu-id="aabe8-119">[コマンドレットの設定](./cmdlet-sets.md)このトピックでは、基本クラスを使用してコマンドレットのセットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-119">[Cmdlet Sets](./cmdlet-sets.md) This topic describes using base classes to create sets of cmdlets.</span></span>

<span data-ttu-id="aabe8-120">[Windows PowerShell セッションの状態](./windows-powershell-session-state.md)このトピックでは、Windows PowerShell セッションの状態について説明します。</span><span class="sxs-lookup"><span data-stu-id="aabe8-120">[Windows PowerShell Session State](./windows-powershell-session-state.md) This topic describes Windows PowerShell session state.</span></span>
