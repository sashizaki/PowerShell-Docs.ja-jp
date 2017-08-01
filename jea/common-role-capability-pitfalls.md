---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "ロール機能のよくある落とし穴"
ms.technology: powershell
ms.openlocfilehash: 8e928ec07ef98b2ec8186a27d3aefa1450a3a424
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
### <a name="common-role-capability-pitfalls"></a><span data-ttu-id="155ec-103">ロール機能のよくある落とし穴</span><span class="sxs-lookup"><span data-stu-id="155ec-103">Common Role Capability Pitfalls</span></span>
<span data-ttu-id="155ec-104">本手順の実行時に陥りやすいいくつかの落とし穴について説明します。</span><span class="sxs-lookup"><span data-stu-id="155ec-104">You may run into a few common pitfalls if you go through this process yourself.</span></span>
<span data-ttu-id="155ec-105">エンドポイントの変更時、また新規作成時にこれらの問題を特定し、対処する方法の概要を以下に紹介します。</span><span class="sxs-lookup"><span data-stu-id="155ec-105">Here is a quick guide explaining how to identify and remediate these issues when modifying or creating a new endpoint:</span></span>

#### <a name="functions-vs-cmdlets"></a><span data-ttu-id="155ec-106">関数とコマンドレット</span><span class="sxs-lookup"><span data-stu-id="155ec-106">Functions vs. Cmdlets</span></span>
<span data-ttu-id="155ec-107">PowerShell で記述された PowerShell コマンドを PowerShell 関数と呼びます。</span><span class="sxs-lookup"><span data-stu-id="155ec-107">PowerShell commands written in PowerShell are PowerShell functions.</span></span>
<span data-ttu-id="155ec-108">特定の .NET クラスとして記述された PowerShell コマンドは、PowerShell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="155ec-108">PowerShell commands written as specialized .NET classes are PowerShell cmdlets.</span></span>
<span data-ttu-id="155ec-109">コマンドの種類を確認するには、`Get-Command` を実行します。</span><span class="sxs-lookup"><span data-stu-id="155ec-109">You can check the command type by running `Get-Command`.</span></span>

#### <a name="visibleproviders"></a><span data-ttu-id="155ec-110">VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="155ec-110">VisibleProviders</span></span>
<span data-ttu-id="155ec-111">コマンドに必要なすべてのプロバイダーを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="155ec-111">You will need to expose any providers your commands need.</span></span>
<span data-ttu-id="155ec-112">最も一般的なプロバイダーとして FileSystem プロバイダーがありますが、他に Registry プロバイダーなどの公開が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="155ec-112">The most common is the FileSystem provider, but you may also need to expose others, like the Registry provider.</span></span>
<span data-ttu-id="155ec-113">プロバイダーの概要については、[Hey, Scripting Guy のブログ投稿](http://blogs.technet.com/b/heyscriptingguy/archive/2015/04/20/find-and-use-windows-powershell-providers.aspx)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="155ec-113">For an introduction to providers, check out this [Hey, Scripting Guy blog post](http://blogs.technet.com/b/heyscriptingguy/archive/2015/04/20/find-and-use-windows-powershell-providers.aspx).</span></span>
<span data-ttu-id="155ec-114">プロバイダーの公開時の注意事項: JEA セッションで直接プロバイダーを公開するより、基盤となるプロバイダーを操作する独自の関数を定義するほうが適している場合もあります。</span><span class="sxs-lookup"><span data-stu-id="155ec-114">Be careful when exposing providers -- often, it is better to define your own function that works with the underlying providers than to directly expose the provider in a JEA session.</span></span>
<span data-ttu-id="155ec-115">この方法でも、ファイル、レジストリ キーなどを操作する権限や、カスタムの検証ロジックを使用して**どの**ファイルやレジストリ キーを管理するか、それらに対するコントロールをユーザーに付与できます。</span><span class="sxs-lookup"><span data-stu-id="155ec-115">This way, you can still allow users to work with files, registry keys, etc. but retain control over **which** files and registry keys they can work with using custom validation logic.</span></span>

