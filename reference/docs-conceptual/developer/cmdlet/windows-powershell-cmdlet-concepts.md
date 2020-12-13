---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell コマンドレットの概念
description: Windows PowerShell コマンドレットの概念
ms.openlocfilehash: da34d3d229f6d57ee22d84fc024b31eb2ee27ba3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652533"
---
# <a name="windows-powershell-cmdlet-concepts"></a><span data-ttu-id="6a838-103">Windows PowerShell コマンドレットの概念</span><span class="sxs-lookup"><span data-stu-id="6a838-103">Windows PowerShell Cmdlet Concepts</span></span>

<span data-ttu-id="6a838-104">ここでは、コマンドレットの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-104">This section describes how cmdlets work.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6a838-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6a838-105">In This Section</span></span>

<span data-ttu-id="6a838-106">このセクションには、次のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="6a838-106">This section includes the following topics.</span></span>

<span data-ttu-id="6a838-107">[コマンドレットの開発ガイドライン](./cmdlet-development-guidelines.md) このトピックでは、整形式のコマンドレットを生成するために使用できる開発ガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-107">[Cmdlet Development Guidelines](./cmdlet-development-guidelines.md) This topic provides development guidelines that can be used to produce well-formed cmdlets.</span></span>

<span data-ttu-id="6a838-108">[コマンドレットクラスの宣言](./cmdlet-class-declaration.md) このトピックでは、コマンドレットクラスの宣言について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-108">[Cmdlet Class Declaration](./cmdlet-class-declaration.md) This topic describes cmdlet class declaration.</span></span>

<span data-ttu-id="6a838-109">[Windows PowerShell コマンドの承認](./approved-verbs-for-windows-powershell-commands.md) された動詞このトピックでは、コマンドレットクラスを宣言するときに使用できる定義済みのコマンドレット動詞の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6a838-109">[Approved Verbs for Windows PowerShell Commands](./approved-verbs-for-windows-powershell-commands.md) This topic lists the predefined cmdlet verbs that you can use when you declare a cmdlet class.</span></span>

<span data-ttu-id="6a838-110">[コマンドレットの入力処理方法](./cmdlet-input-processing-methods.md) このトピックでは、コマンドレットが前処理操作、入力処理操作、および処理後の操作を実行できるようにするメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-110">[Cmdlet Input Processing Methods](./cmdlet-input-processing-methods.md) This topic describes the methods that allow a cmdlet to perform preprocessing operations, input processing operations, and post processing operations.</span></span>

<span data-ttu-id="6a838-111">[コマンドレットのパラメーター](./cmdlet-parameters.md) ここでは、コマンドレットに追加できるさまざまな種類のパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-111">[Cmdlet Parameters](./cmdlet-parameters.md) This section describes the different types of parameters that you can add to cmdlets.</span></span>

<span data-ttu-id="6a838-112">[コマンドレットの属性](./cmdlet-attributes.md) このセクションでは、.NET Framework クラスをコマンドレットとして宣言し、フィールドをコマンドレットパラメーターとして宣言し、パラメーターの入力検証規則を宣言するために使用する属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-112">[Cmdlet Attributes](./cmdlet-attributes.md) This section describes the attributes that are used to declare .NET Framework classes as cmdlets, to declare fields as cmdlet parameters, and to declare input validation rules for parameters.</span></span>

<span data-ttu-id="6a838-113">[コマンドレットのエイリアス](./cmdlet-aliases.md) このトピックでは、コマンドレットのエイリアスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-113">[Cmdlet Aliases](./cmdlet-aliases.md) This topic describes cmdlet aliases.</span></span>

<span data-ttu-id="6a838-114">[コマンドレットの出力](./cmdlet-output.md) このセクションでは、コマンドレットから返される出力の種類と、コマンドレットによって返されるオブジェクトを定義および表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-114">[Cmdlet Output](./cmdlet-output.md) This section describes the type of output that cmdlets can return and how to define and display the objects that are returned by cmdlets.</span></span>

<span data-ttu-id="6a838-115">[コマンドレットの登録](./modules-and-snap-ins.md) ここでは、モジュールとスナップインを使用してコマンドレットを登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-115">[Registering Cmdlets](./modules-and-snap-ins.md) This section describes how to register cmdlets by using modules and snap-ins.</span></span>

<span data-ttu-id="6a838-116">[確認の要求](./requesting-confirmation-from-cmdlets.md) このセクションでは、コマンドレットがシステムに変更を加える前にユーザーに確認を要求する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-116">[Requesting Confirmation](./requesting-confirmation-from-cmdlets.md) This section describes how cmdlets request confirmation from a user before they make a change to the system.</span></span>

<span data-ttu-id="6a838-117">[Windows PowerShell エラー報告](./error-reporting-concepts.md) ここでは、コマンドレットが終了エラーと終了しないエラーを報告する方法と、エラーレコードを解釈する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-117">[Windows PowerShell Error Reporting](./error-reporting-concepts.md) This section describes how cmdlets report terminating errors and non-terminating errors, and it describes how to interpret error records.</span></span>

<span data-ttu-id="6a838-118">[バックグラウンドジョブ](./background-jobs.md) このトピックでは、現在のセッションで実行されているコマンドに干渉しないバックグラウンドジョブ内で、コマンドレットが作業を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-118">[Background Jobs](./background-jobs.md) This topic describes how cmdlets can perform their work within background jobs that do not interfere with the commands that are executing in the current session.</span></span>

<span data-ttu-id="6a838-119">[コマンドレット内](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) のコマンドレットとスクリプトの呼び出しこのトピックでは、コマンドレットが入力処理メソッド内から他のコマンドレットとスクリプトを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-119">[Invoking Cmdlets and Scripts Within a Cmdlet](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) This topic describes how cmdlets can invoke other cmdlets and scripts from within their input processing methods.</span></span>

<span data-ttu-id="6a838-120">[コマンドレットの設定](./cmdlet-sets.md) このトピックでは、基本クラスを使用してコマンドレットのセットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-120">[Cmdlet Sets](./cmdlet-sets.md) This topic describes using base classes to create sets of cmdlets.</span></span>

<span data-ttu-id="6a838-121">[Windows PowerShell セッションの状態](./windows-powershell-session-state.md) このトピックでは、Windows PowerShell セッションの状態について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a838-121">[Windows PowerShell Session State](./windows-powershell-session-state.md) This topic describes Windows PowerShell session state.</span></span>
