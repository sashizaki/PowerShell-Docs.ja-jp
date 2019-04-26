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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067075"
---
# <a name="windows-powershell-cmdlet-concepts"></a><span data-ttu-id="a5a0c-102">Windows PowerShell コマンドレットの概念</span><span class="sxs-lookup"><span data-stu-id="a5a0c-102">Windows PowerShell Cmdlet Concepts</span></span>

<span data-ttu-id="a5a0c-103">このセクションでは、コマンドレットの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-103">This section describes how cmdlets work.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a5a0c-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a5a0c-104">In This Section</span></span>

<span data-ttu-id="a5a0c-105">このセクションには、次のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-105">This section includes the following topics.</span></span>

<span data-ttu-id="a5a0c-106">[コマンドレットの開発ガイドライン](./cmdlet-development-guidelines.md)このトピックでは、適切な形式でコマンドレットを生成するために使用できる開発ガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-106">[Cmdlet Development Guidelines](./cmdlet-development-guidelines.md) This topic provides development guidelines that can be used to produce well-formed cmdlets.</span></span>

<span data-ttu-id="a5a0c-107">[コマンドレット クラス宣言](./cmdlet-class-declaration.md)このトピックでは、コマンドレット クラス宣言を説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-107">[Cmdlet Class Declaration](./cmdlet-class-declaration.md) This topic describes cmdlet class declaration.</span></span>

<span data-ttu-id="a5a0c-108">[Windows PowerShell コマンドの動詞に承認](./approved-verbs-for-windows-powershell-commands.md)このトピックでは、コマンドレット クラスを宣言するときに使用できる事前定義されたコマンドレット動詞を一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-108">[Approved Verbs for Windows PowerShell Commands](./approved-verbs-for-windows-powershell-commands.md) This topic lists the predefined cmdlet verbs that you can use when you declare a cmdlet class.</span></span>

<span data-ttu-id="a5a0c-109">[コマンドレットの入力の処理方法](./cmdlet-input-processing-methods.md)このトピックでは、前処理の操作を実行、処理の操作を入力し、処理操作の投稿のコマンドレットを許可する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-109">[Cmdlet Input Processing Methods](./cmdlet-input-processing-methods.md) This topic describes the methods that allow a cmdlet to perform preprocessing operations, input processing operations, and post processing operations.</span></span>

<span data-ttu-id="a5a0c-110">[コマンドレットのパラメーターを](./cmdlet-parameters.md)コマンドレットに追加できるパラメーターのさまざまな種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-110">[Cmdlet Parameters](./cmdlet-parameters.md) This section describes the different types of parameters that you can add to cmdlets.</span></span>

<span data-ttu-id="a5a0c-111">[コマンドレット属性](./cmdlet-attributes.md)コマンドレットのパラメーターとしてフィールドを宣言するパラメーターの入力の検証規則を宣言して、コマンドレット、として .NET Framework のクラスを宣言するために使用される属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-111">[Cmdlet Attributes](./cmdlet-attributes.md) This section describes the attributes that are used to declare .NET Framework classes as cmdlets, to declare fields as cmdlet parameters, and to declare input validation rules for parameters.</span></span>

<span data-ttu-id="a5a0c-112">[コマンドレットのエイリアス](./cmdlet-aliases.md)このトピックでは、コマンドレットのエイリアスを説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-112">[Cmdlet Aliases](./cmdlet-aliases.md) This topic describes cmdlet aliases.</span></span>

<span data-ttu-id="a5a0c-113">[コマンドレットの出力](./cmdlet-output.md)の種類のコマンドレットが返すことができる出力と定義し、コマンドレットによって返されるオブジェクトを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-113">[Cmdlet Output](./cmdlet-output.md) This section describes the type of output that cmdlets can return and how to define and display the objects that are returned by cmdlets.</span></span>

<span data-ttu-id="a5a0c-114">[コマンドレットを登録する](./modules-and-snap-ins.md)モジュールおよびスナップインを使用してコマンドレットを登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-114">[Registering Cmdlets](./modules-and-snap-ins.md) This section describes how to register cmdlets by using modules and snap-ins.</span></span>

<span data-ttu-id="a5a0c-115">[確認を求める](./requesting-confirmation-from-cmdlets.md)このセクションでは、システムに変更を加える前に、コマンドレットで確認をユーザーから要求する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-115">[Requesting Confirmation](./requesting-confirmation-from-cmdlets.md) This section describes how cmdlets request confirmation from a user before they make a change to the system.</span></span>

<span data-ttu-id="a5a0c-116">[Windows PowerShell のエラー報告](./error-reporting-concepts.md)このセクションでは、コマンドレットが終了するエラーや未終了エラーを報告する方法について説明し、エラー レコードを解釈する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-116">[Windows PowerShell Error Reporting](./error-reporting-concepts.md) This section describes how cmdlets report terminating errors and non-terminating errors, and it describes how to interpret error records.</span></span>

<span data-ttu-id="a5a0c-117">[バック グラウンド ジョブ](./background-jobs.md)このトピックでは、コマンドレットが、現在のセッションで実行されているコマンドに影響を及ぼさないバック グラウンド ジョブ内の作業を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-117">[Background Jobs](./background-jobs.md) This topic describes how cmdlets can perform their work within background jobs that do not interfere with the commands that are executing in the current session.</span></span>

<span data-ttu-id="a5a0c-118">[コマンドレットと、コマンドレット内でスクリプトを呼び出す](./invoking-cmdlets-and-scripts-within-a-cmdlet.md)このトピックでは、どのコマンドレット呼び出すことができます他のコマンドレットおよびスクリプト内からの入力処理メソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-118">[Invoking Cmdlets and Scripts Within a Cmdlet](./invoking-cmdlets-and-scripts-within-a-cmdlet.md) This topic describes how cmdlets can invoke other cmdlets and scripts from within their input processing methods.</span></span>

<span data-ttu-id="a5a0c-119">[コマンドレット設定](./cmdlet-sets.md)このトピックでは、コマンドレットのセットを作成する基本クラスの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-119">[Cmdlet Sets](./cmdlet-sets.md) This topic describes using base classes to create sets of cmdlets.</span></span>

<span data-ttu-id="a5a0c-120">[Windows PowerShell セッションの状態](./windows-powershell-session-state.md)このトピックでは、Windows PowerShell セッションの状態を説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a0c-120">[Windows PowerShell Session State](./windows-powershell-session-state.md) This topic describes Windows PowerShell session state.</span></span>
