---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell ファースト ステップ ガイド"
ms.assetid: b0e2ad92-875f-421d-b612-f624e644aa69
ms.openlocfilehash: 93a4d4a6bc0ebef6b6af7f7f8af59dec865bcfa3
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="getting-started-with-windows-powershell"></a><span data-ttu-id="bfa9b-103">Windows PowerShell ファースト ステップ ガイド</span><span class="sxs-lookup"><span data-stu-id="bfa9b-103">Getting Started with Windows PowerShell</span></span>
<span data-ttu-id="bfa9b-104">Windows PowerShell は、特にシステム管理者向けに設計された Windows コマンド ライン シェルです。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-104">Windows PowerShell is a Windows command-line shell designed especially for system administrators.</span></span> <span data-ttu-id="bfa9b-105">Windows PowerShell には対話型のプロンプトとスクリプト環境が含まれており、それらを単独で、または組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-105">Windows PowerShell includes an interactive prompt and a scripting environment that can be used independently or in combination.</span></span>

<span data-ttu-id="bfa9b-106">テキストを受け入れて返す大部分のシェルとは異なり、Windows PowerShell は .NET Framework の共通言語ランタイム (CLR) と .NET Framework の上に構築されており、.NET Framework オブジェクトを受け入れて返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-106">Unlike most shells, which accept and return text, Windows PowerShell is built on top of the .NET Framework common language runtime (CLR) and the .NET Framework, and accepts and returns .NET Framework objects.</span></span> <span data-ttu-id="bfa9b-107">環境のこの根本的な変更により、まったく新しいツールと方法で Windows の管理と構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-107">This fundamental change in the environment brings entirely new tools and methods to the management and configuration of Windows.</span></span>

<span data-ttu-id="bfa9b-108">Windows PowerShell は、シンプルな単一機能のコマンド ライン ツールをシェルに組み込んだ、コマンドレットという概念を導入しました。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-108">Windows PowerShell introduces the concept of a cmdlet (pronounced "command-let"), a simple, single-function command-line tool built into the shell.</span></span> <span data-ttu-id="bfa9b-109">各コマンドレットは別々に使うことができますが、これらのシンプルなツールを組み合わせて使って複雑なタスクを実行すると、そのパワーが発揮されます。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-109">You can use each cmdlet separately, but their power is realized when you use these simple tools in combination to perform complex tasks.</span></span> <span data-ttu-id="bfa9b-110">Windows PowerShell には 100 を超える基本的なコア コマンドレットが組み込まれているほか、独自のコマンドレットを作成して他のユーザーと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-110">Windows PowerShell includes more than one hundred basic core cmdlets, and you can write your own cmdlets and share them with other users.</span></span>

<span data-ttu-id="bfa9b-111">多くのシェルと同じように、Windows PowerShell はコンピューター上のファイル システムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-111">Like many shells, Windows PowerShell gives you access to the file system on the computer.</span></span> <span data-ttu-id="bfa9b-112">それに加えて、Windows PowerShell で*プロバイダー* を使うと、レジストリやデジタル署名の証明書ストアといった他のデータ ストアへのアクセスが、ファイル システムへのアクセスと同じほど簡単になります。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-112">In addition, Windows PowerShell *providers* enable you to access other data stores, such as the registry and the digital signature certificate stores, as easily as you access the file system.</span></span>

<span data-ttu-id="bfa9b-113">このファースト ステップ ガイドでは、Windows PowerShell の概要情報を提供し、その言語、コマンドレット、プロバイダー、オブジェクトの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfa9b-113">This Getting Started guide provides an introduction to Windows PowerShell: the language, the cmdlets, the providers, and the use of objects.</span></span>

<span data-ttu-id="bfa9b-114">このトピックの内容:</span><span class="sxs-lookup"><span data-stu-id="bfa9b-114">In this topic:</span></span>

- [<span data-ttu-id="bfa9b-115">Windows PowerShell のシステム要件</span><span class="sxs-lookup"><span data-stu-id="bfa9b-115">Windows PowerShell System Requirements</span></span>](../setup/Windows-PowerShell-System-Requirements.md)

- [<span data-ttu-id="bfa9b-116">Windows PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="bfa9b-116">Installing Windows PowerShell</span></span>](../setup/Installing-Windows-PowerShell.md)

- [<span data-ttu-id="bfa9b-117">Windows PowerShell の開始</span><span class="sxs-lookup"><span data-stu-id="bfa9b-117">Starting Windows PowerShell</span></span>](../setup/Starting-Windows-PowerShell.md)

- [<span data-ttu-id="bfa9b-118">Windows PowerShell を使用する準備を行う</span><span class="sxs-lookup"><span data-stu-id="bfa9b-118">Getting Ready to Use Windows PowerShell</span></span>](Getting-Ready-to-Use-Windows-PowerShell.md)

