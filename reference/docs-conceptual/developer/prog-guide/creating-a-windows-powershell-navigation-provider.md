---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell ナビゲーション プロバイダーを作成する
description: Windows PowerShell ナビゲーション プロバイダーを作成する
ms.openlocfilehash: 73d4971fb91acaef9e1f20226e7b9b883730e394
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658667"
---
# <a name="creating-a-windows-powershell-navigation-provider"></a><span data-ttu-id="64f58-103">Windows PowerShell ナビゲーション プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="64f58-103">Creating a Windows PowerShell Navigation Provider</span></span>

<span data-ttu-id="64f58-104">このトピックでは、データストア内を移動できる Windows PowerShell ナビゲーションプロバイダーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64f58-104">This topic describes how to create a Windows PowerShell navigation provider that can navigate the data store.</span></span> <span data-ttu-id="64f58-105">この種類のプロバイダーは、再帰コマンド、入れ子になったコンテナー、および相対パスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="64f58-105">This type of provider supports recursive commands, nested containers, and relative paths.</span></span>

> [!NOTE]
> <span data-ttu-id="64f58-106">このプロバイダーの C# ソースファイル (AccessDBSampleProvider05.cs) は、Windows Vista および .NET Framework 3.0 ランタイムコンポーネントの Microsoft Windows Software Development Kit を使用してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="64f58-106">You can download the C# source file (AccessDBSampleProvider05.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="64f58-107">ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="64f58-108">ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。</span><span class="sxs-lookup"><span data-stu-id="64f58-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="64f58-109">その他の Windows PowerShell プロバイダーの実装の詳細については、「 [Windows Powershell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-109">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

<span data-ttu-id="64f58-110">ここで説明するプロバイダーは、ユーザーがデータベース内のデータテーブルに移動できるように、Access データベースをドライブとして処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="64f58-110">The provider described here enables the user handle an Access database as a drive so that the user can navigate to the data tables in the database.</span></span> <span data-ttu-id="64f58-111">独自のナビゲーションプロバイダーを作成するときに、ナビゲーションに必要なドライブ修飾パスを作成したり、相対パスを正規化したり、データストアの項目を移動したり、子名を取得して項目の親パスを取得したり、項目がコンテナーであるかどうかを確認したりするメソッドを実装できます。</span><span class="sxs-lookup"><span data-stu-id="64f58-111">When creating your own navigation provider, you can implement methods that can make drive-qualified paths required for navigation, normalize relative paths, move items of the data store, as well as methods that get child names, get the parent path of an item, and test to identify if an item is a container.</span></span>

> [!CAUTION]
> <span data-ttu-id="64f58-112">この設計では、名前が ID のフィールドを持つデータベースと、フィールドの型が LongInteger であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-112">Be aware that this design assumes a database that has a field with the name ID, and that the type of the field is LongInteger.</span></span>

## <a name="define-the-windows-powershell-provider"></a><span data-ttu-id="64f58-113">Windows PowerShell プロバイダーを定義する</span><span class="sxs-lookup"><span data-stu-id="64f58-113">Define the Windows PowerShell provider</span></span>

<span data-ttu-id="64f58-114">Windows PowerShell ナビゲーションプロバイダー [は、system.servicemodel クラスの基底クラス](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) から派生した .net クラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-114">A Windows PowerShell navigation provider must create a .NET class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) base class.</span></span> <span data-ttu-id="64f58-115">ここでは、このセクションで説明するナビゲーションプロバイダーのクラス定義を示します。</span><span class="sxs-lookup"><span data-stu-id="64f58-115">Here is the class definition for the navigation provider described in this section.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="31-32":::

<span data-ttu-id="64f58-116">このプロバイダーには、2つ [のパラメーター](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-116">Note that in this provider, the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) attribute includes two parameters.</span></span> <span data-ttu-id="64f58-117">最初のパラメーターは、Windows PowerShell によって使用されるプロバイダーのわかりやすい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="64f58-117">The first parameter specifies a user-friendly name for the provider that is used by Windows PowerShell.</span></span> <span data-ttu-id="64f58-118">2番目のパラメーターは、コマンドの処理中にプロバイダーが Windows PowerShell ランタイムに公開する Windows PowerShell 固有の機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="64f58-118">The second parameter specifies the Windows PowerShell specific capabilities that the provider exposes to the Windows PowerShell runtime during command processing.</span></span> <span data-ttu-id="64f58-119">このプロバイダーには、Windows PowerShell 固有の機能は追加されていません。</span><span class="sxs-lookup"><span data-stu-id="64f58-119">For this provider, there are no Windows PowerShell specific capabilities that are added.</span></span>

## <a name="defining-base-functionality"></a><span data-ttu-id="64f58-120">基本機能の定義</span><span class="sxs-lookup"><span data-stu-id="64f58-120">Defining Base Functionality</span></span>

<span data-ttu-id="64f58-121">「 [PS プロバイダーの設計](./designing-your-windows-powershell-provider.md)」で説明さ [れて](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) いるように、さまざまなプロバイダーの機能を提供する他のいくつかのクラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="64f58-121">As described in [Design Your PS Provider](./designing-your-windows-powershell-provider.md), the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) base class derives from several other classes that provided different provider functionality.</span></span> <span data-ttu-id="64f58-122">そのため、Windows PowerShell ナビゲーションプロバイダーは、これらのクラスによって提供されるすべての機能を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-122">A Windows PowerShell navigation provider, therefore, must define all of the functionality provided by those classes.</span></span>

<span data-ttu-id="64f58-123">セッション固有の初期化情報を追加し、プロバイダーによって使用されるリソースを解放するための機能を実装するには、「 [基本的な PS プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-123">To implement functionality for adding session-specific initialization information and for releasing resources that are used by the provider, see [Creating a Basic PS Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="64f58-124">ただし、ほとんどのプロバイダー (ここで説明するプロバイダーを含む) は、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。</span><span class="sxs-lookup"><span data-stu-id="64f58-124">However, most providers (including the provider described here) can use the default implementation of this functionality provided by Windows PowerShell.</span></span>

<span data-ttu-id="64f58-125">Windows PowerShell ドライブを介してデータストアにアクセスするには、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) 基底クラスのメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-125">To get access to the data store through a Windows PowerShell drive, you must implement the methods of the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) base class.</span></span> <span data-ttu-id="64f58-126">これらのメソッドの実装の詳細については、「 [Windows PowerShell ドライブプロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-126">For more information about implementing these methods, see [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>

<span data-ttu-id="64f58-127">項目の取得、設定、クリアなど、データストアの項目を操作するには、プロバイダー [が、system.object クラスの基本クラス](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) によって提供されるメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-127">To manipulate the items of a data store, such as getting, setting, and clearing items, the provider must implement the methods provided by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) base class.</span></span> <span data-ttu-id="64f58-128">これらのメソッドの実装の詳細については、「 [Windows PowerShell 項目プロバイダーの作成](./creating-a-windows-powershell-item-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-128">For more information about implementing these methods, see [Creating an Windows PowerShell Item Provider](./creating-a-windows-powershell-item-provider.md).</span></span>

<span data-ttu-id="64f58-129">項目を作成、コピー、名前変更、および削除するメソッドだけでなく、データストアの子項目、またはその名前を取得するには、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) 基底クラスによって提供されるメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-129">To get to the child items, or their names, of the data store, as well as methods that create, copy, rename, and remove items, you must implement the methods provided by the [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) base class.</span></span> <span data-ttu-id="64f58-130">これらのメソッドの実装の詳細については、「 [Windows PowerShell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-130">For more information about implementing these methods, see [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>

## <a name="creating-a-windows-powershell-path"></a><span data-ttu-id="64f58-131">Windows PowerShell のパスを作成する</span><span class="sxs-lookup"><span data-stu-id="64f58-131">Creating a Windows PowerShell Path</span></span>

<span data-ttu-id="64f58-132">Windows PowerShell ナビゲーションプロバイダーは、プロバイダー内部の Windows PowerShell パスを使用して、データストアの項目を移動します。</span><span class="sxs-lookup"><span data-stu-id="64f58-132">Windows PowerShell navigation provider use a provider-internal Windows PowerShell path to navigate the items of the data store.</span></span> <span data-ttu-id="64f58-133">プロバイダーの内部パスを作成するには、プロバイダーが、Combine-Path コマンドレットからの呼び出しをサポートするように、system.servicemodel [path \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-133">To create a provider-internal path the provider must implement the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to supports calls from the Combine-Path cmdlet.</span></span> <span data-ttu-id="64f58-134">このメソッドは、親パスと子パスの間にプロバイダー固有のパス区切り記号を使用して、親と子のパスをプロバイダーの内部パスに結合します。</span><span class="sxs-lookup"><span data-stu-id="64f58-134">This method combines a parent and child path into a provider-internal path, using a provider-specific path separator between the parent and child paths.</span></span>

<span data-ttu-id="64f58-135">既定の実装では、パスの区切り文字として "/" または "" を含むパスを使用し \\ 、パスの区切り記号を "" に正規化します。次に、親と子のパスの部分を結合して、パスを \\ 結合した文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-135">The default implementation takes paths with "/" or "\\" as the path separator, normalizes the path separator to "\\", combines the parent and child path parts with the separator between them, and then returns a string that contains the combined paths.</span></span>

<span data-ttu-id="64f58-136">このナビゲーションプロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="64f58-136">This navigation provider does not implement this method.</span></span> <span data-ttu-id="64f58-137">ただし、次のコードは、 [システム](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) の既定の実装であり、このメソッドを実装しています。</span><span class="sxs-lookup"><span data-stu-id="64f58-137">However, the following code is the default implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermakepath](Msh_samplestestcmdlets#testprovidermakepath)]  -->

#### <a name="things-to-remember-about-implementing-makepath"></a><span data-ttu-id="64f58-138">MakePath の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="64f58-138">Things to Remember About Implementing MakePath</span></span>

<span data-ttu-id="64f58-139">次の条件は、使用している [システム](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)の実装に適用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-139">The following conditions may apply to your implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath):</span></span>

- <span data-ttu-id="64f58-140">[システム](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)の実装では、このパスをプロバイダーの名前空間内の有効な完全修飾パスとして検証しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="64f58-140">Your implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method should not validate the path as a legal fully-qualified path in the provider namespace.</span></span> <span data-ttu-id="64f58-141">各パラメーターはパスの一部のみを表すことができ、結合された部分は完全修飾パスを生成しない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-141">Be aware that each parameter can only represent a part of a path, and the combined parts might not generate a fully-qualified path.</span></span> <span data-ttu-id="64f58-142">たとえば、filesystem プロバイダーの windows\system32 [\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッドは、パラメーターに "" を受け取り、 `parent` パラメーターに "abc.dll" を受け取ることがあります。これは、ファイルシステムプロバイダーの場合です。 `child`</span><span class="sxs-lookup"><span data-stu-id="64f58-142">For example, the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method for the filesystem provider might receive "windows\system32" in the `parent` parameter and "abc.dll" in the `child` parameter.</span></span> <span data-ttu-id="64f58-143">メソッドは、これらの値を " \\ " 区切り記号と結合し、完全修飾ファイルシステムパスではない "windows\system32\abc.dll" を返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-143">The method joins these values with the "\\" separator and returns "windows\system32\abc.dll", which is not a fully-qualified file system path.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="64f58-144">[システム](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)の呼び出しで指定されたパス部分には、プロバイダーの名前空間で使用できない文字が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-144">The path parts provided in the call to [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) might contain characters not allowed in the provider namespace.</span></span> <span data-ttu-id="64f58-145">これらの文字は、ワイルドカードの展開に使用されることが多いため、このメソッドの実装では削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="64f58-145">These characters are most likely used for wildcard expansion and the implementation of this method should not remove them.</span></span>

## <a name="retrieving-the-parent-path"></a><span data-ttu-id="64f58-146">親パスの取得</span><span class="sxs-lookup"><span data-stu-id="64f58-146">Retrieving the Parent Path</span></span>

<span data-ttu-id="64f58-147">Windows PowerShell ナビゲーションプロバイダーは、 [Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) メソッドを実装して、指定された完全または部分プロバイダー固有のパスの親部分を取得します。</span><span class="sxs-lookup"><span data-stu-id="64f58-147">Windows PowerShell navigation providers implement the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method to retrieve the parent part of the indicated full or partial provider-specific path.</span></span> <span data-ttu-id="64f58-148">メソッドは、パスの子部分を削除し、親パス部分を返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-148">The method removes the child part of the path and returns the parent path part.</span></span> <span data-ttu-id="64f58-149">パラメーターは、 `root` ドライブのルートへの完全修飾パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="64f58-149">The `root` parameter specifies the fully-qualified path to the root of a drive.</span></span> <span data-ttu-id="64f58-150">マウントされたドライブが取得操作に使用されていない場合、このパラメーターは null または空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="64f58-150">This parameter can be null or empty if a mounted drive is not in use for the retrieval operation.</span></span> <span data-ttu-id="64f58-151">ルートが指定されている場合、メソッドはルートと同じツリー内のコンテナーへのパスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-151">If a root is specified, the method must return a path to a container in the same tree as the root.</span></span>

<span data-ttu-id="64f58-152">サンプルナビゲーションプロバイダーは、このメソッドをオーバーライドしませんが、既定の実装を使用します。</span><span class="sxs-lookup"><span data-stu-id="64f58-152">The sample navigation provider does not override this method, but uses the default implementation.</span></span>
<span data-ttu-id="64f58-153">パス区切り記号として "/" と "" の両方を使用するパスを受け入れ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="64f58-153">It accepts paths that use both "/" and "\\" as path separators.</span></span> <span data-ttu-id="64f58-154">まず、"" 区切り記号のみを含むようにパスを正規化 \\ し、次に親パスを最後の "" に分割 \\ し、親パスを返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-154">It first normalizes the path to have only "\\" separators, then splits the parent path off at the last "\\" and returns the parent path.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetparentpath](Msh_samplestestcmdlets#testprovidergetparentpath)]  -->

#### <a name="to-remember-about-implementing-getparentpath"></a><span data-ttu-id="64f58-155">GetParentPath の実装について覚えておくには</span><span class="sxs-lookup"><span data-stu-id="64f58-155">To Remember About Implementing GetParentPath</span></span>

<span data-ttu-id="64f58-156">[Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドの実装では、プロバイダーの名前空間のパス区切りでパスを構文的に分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-156">Your implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method should split the path lexically on the path separator for the provider namespace.</span></span> <span data-ttu-id="64f58-157">たとえば、filesystem プロバイダーは、このメソッドを使用して最後の " \\ " を検索し、区切り記号の左側にあるすべての要素を返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-157">For example, the filesystem provider uses this method to look for the last "\\" and returns everything to the left of the separator.</span></span>

## <a name="retrieve-the-child-path-name"></a><span data-ttu-id="64f58-158">子パス名を取得する</span><span class="sxs-lookup"><span data-stu-id="64f58-158">Retrieve the Child Path Name</span></span>

<span data-ttu-id="64f58-159">ナビゲーションプロバイダーは、指定された完全または部分的なプロバイダー固有のパスにある項目の子の名前 (リーフ要素) を取得するために、system.string. [Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="64f58-159">Your navigation provider implements the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method to retrieve the name (leaf element) of the child of the item located at the indicated full or partial provider-specific path.</span></span>

<span data-ttu-id="64f58-160">サンプルナビゲーションプロバイダーでは、このメソッドはオーバーライドされません。</span><span class="sxs-lookup"><span data-stu-id="64f58-160">The sample navigation provider does not override this method.</span></span> <span data-ttu-id="64f58-161">既定の実装は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64f58-161">The default implementation is shown below.</span></span> <span data-ttu-id="64f58-162">パス区切り記号として "/" と "" の両方を使用するパスを受け入れ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="64f58-162">It accepts paths that use both "/" and "\\" as path separators.</span></span> <span data-ttu-id="64f58-163">まず、"" 区切り記号のみを含むようにパスを正規化 \\ し、次に親パスを最後の "" に分割し、 \\ 子パス部分の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-163">It first normalizes the path to have only "\\" separators, then splits the parent path off at the last "\\" and returns the name of the child path part.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildname](Msh_samplestestcmdlets#testprovidergetchildname)]  -->

#### <a name="things-to-remember-about-implementing-getchildname"></a><span data-ttu-id="64f58-164">GetChildName の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="64f58-164">Things to Remember About Implementing GetChildName</span></span>

<span data-ttu-id="64f58-165">の実装では、パスの区切り記号でパスを構文的に分割する必要があります。 [Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="64f58-165">Your implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method should split the path lexically on the path separator.</span></span> <span data-ttu-id="64f58-166">指定されたパスにパスの区切り文字が含まれていない場合、メソッドはパスを変更せずに返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-166">If the supplied path contains no path separators, the method should return the path unmodified.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64f58-167">このメソッドの呼び出しで指定されたパスに、プロバイダーの名前空間では無効な文字が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-167">The path provided in the call to this method might contain characters that are illegal in the provider namespace.</span></span> <span data-ttu-id="64f58-168">これらの文字は、ワイルドカードの展開や正規表現の照合に使用されることが多いため、このメソッドの実装では削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="64f58-168">These characters are most likely used for wildcard expansion or regular expression matching, and the implementation of this method should not remove them.</span></span>

## <a name="determining-if-an-item-is-a-container"></a><span data-ttu-id="64f58-169">項目がコンテナーであるかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="64f58-169">Determining if an Item is a Container</span></span>

<span data-ttu-id="64f58-170">ナビゲーションプロバイダーは、 [Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) メソッドを実装して、指定したパスがコンテナーを示すかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="64f58-170">The navigation provider can implement the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method to determine if the specified path indicates a container.</span></span> <span data-ttu-id="64f58-171">パスがコンテナーを表している場合は true、それ以外の場合は false を返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-171">It returns true if the path represents a container, and false otherwise.</span></span> <span data-ttu-id="64f58-172">ユーザーは、指定され `Test-Path` たパスに対してコマンドレットを使用できるようにするために、このメソッドを必要とします。</span><span class="sxs-lookup"><span data-stu-id="64f58-172">The user needs this method to be able to use the `Test-Path` cmdlet for the supplied path.</span></span>

<span data-ttu-id="64f58-173">次のコードは、サンプルナビゲーションプロバイダーでの [Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) の実装を示していますが、</span><span class="sxs-lookup"><span data-stu-id="64f58-173">The following code shows the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) implementation in our sample navigation provider.</span></span> <span data-ttu-id="64f58-174">メソッドは、指定されたパスが正しいことと、テーブルが存在するかどうかを検証し、パスがコンテナーを示す場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-174">The method verifies that the specified path is correct and if the table exists, and returns true if the path indicates a container.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="847-872":::

#### <a name="things-to-remember-about-implementing-isitemcontainer"></a><span data-ttu-id="64f58-175">IsItemContainer の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="64f58-175">Things to Remember About Implementing IsItemContainer</span></span>

<span data-ttu-id="64f58-176">ナビゲーションプロバイダー .NET クラスは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、 [システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) の列挙体から宣言する場合があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-176">Your navigation provider .NET class might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="64f58-177">この場合、 [Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) の実装では、渡されたパスが要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-177">In this case, the implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) needs to ensure that the path passed meets requirements.</span></span> <span data-ttu-id="64f58-178">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、例 [では、](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) .</span><span class="sxs-lookup"><span data-stu-id="64f58-178">To do this, the method should access the appropriate property, for example, the [System.Management.Automation.Provider.Cmdletprovider.Exclude\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) property.</span></span>

## <a name="moving-an-item"></a><span data-ttu-id="64f58-179">項目の移動</span><span class="sxs-lookup"><span data-stu-id="64f58-179">Moving an Item</span></span>

<span data-ttu-id="64f58-180">コマンドレットのサポートでは `Move-Item` 、ナビゲーションプロバイダーによって、 [システムの管理](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) を実装しています。</span><span class="sxs-lookup"><span data-stu-id="64f58-180">In support of the `Move-Item` cmdlet, your navigation provider implements the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method.</span></span> <span data-ttu-id="64f58-181">このメソッドは、パラメーターによって指定された項目を、パラメーターに指定された `path` パスのコンテナーに移動し `destination` ます。</span><span class="sxs-lookup"><span data-stu-id="64f58-181">This method moves the item specified by the `path` parameter to the container at the path supplied in the `destination` parameter.</span></span>

<span data-ttu-id="64f58-182">サンプルのナビゲーションプロバイダーでは、system.string [\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) メソッドはオーバーライドされていませんが、</span><span class="sxs-lookup"><span data-stu-id="64f58-182">The sample navigation provider does not override the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method.</span></span> <span data-ttu-id="64f58-183">既定の実装は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64f58-183">The following is the default implementation.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitem](Msh_samplestestcmdlets#testprovidermoveitem)]  -->

#### <a name="things-to-remember-about-implementing-moveitem"></a><span data-ttu-id="64f58-184">MoveItem の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="64f58-184">Things to Remember About Implementing MoveItem</span></span>

<span data-ttu-id="64f58-185">ナビゲーションプロバイダー .NET クラスは、ExpandWildcards カード、フィルター、包含、または除外のプロバイダー機能を、 [システム](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) の列挙体から宣言する場合があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-185">Your navigation provider .NET class might declare provider capabilities of ExpandWildcards, Filter, Include, or Exclude, from the [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) enumeration.</span></span> <span data-ttu-id="64f58-186">この場合、渡されたパスが要件を満たしていることを確認するために、 [システムの管理](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-186">In this case, the implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) must ensure that the path passed meets requirements.</span></span> <span data-ttu-id="64f58-187">これを行うには、メソッドが適切なプロパティにアクセスする必要があります。たとえば、プロパティを指定し **ます。**</span><span class="sxs-lookup"><span data-stu-id="64f58-187">To do this, the method should access the appropriate property, for example, the **CmdletProvider.Exclude** property.</span></span>

<span data-ttu-id="64f58-188">既定では、このメソッドのオーバーライドでは、system.object [\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) プロパティがに設定されていない限り、既存のオブジェクトにオブジェクトを移動することはできません `true` 。</span><span class="sxs-lookup"><span data-stu-id="64f58-188">By default, overrides of this method should not move objects over existing objects unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="64f58-189">たとえば、filesystem プロバイダーは、既存の c:\bar.txt ファイルの c:\temp\abc.txt をコピーしません。ただし、この場合、 [Force \*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) プロパティをに設定することはできません `true` 。</span><span class="sxs-lookup"><span data-stu-id="64f58-189">For example, the filesystem provider will not copy c:\temp\abc.txt over an existing c:\bar.txt file unless the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is set to `true`.</span></span> <span data-ttu-id="64f58-190">パラメーターで指定されたパスが存在し、コンテナーである場合は、 `destination` " [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) ......................................</span><span class="sxs-lookup"><span data-stu-id="64f58-190">If the path specified in the `destination` parameter exists and is a container, the [System.Management.Automation.Provider.Cmdletprovider.Force\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) property is not required.</span></span> <span data-ttu-id="64f58-191">この場合は、パラメーターで示されている項目 [を、](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) パラメーターによって `path` `destination` 子として指定されたコンテナーに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-191">In this case, [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) should move the item indicated by the `path` parameter to the container indicated by the `destination` parameter as a child.</span></span>

<span data-ttu-id="64f58-192">[システム](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)の実装では、このメソッドの実装によって、 [system](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) ...................... を呼び出し、戻り値を確認してから、データストアに変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-192">Your implementation of the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method should call [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) and check its return value before making any changes to the data store.</span></span> <span data-ttu-id="64f58-193">このメソッドは、ファイルを削除するなど、システム状態が変更されたときの操作の実行を確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="64f58-193">This method is used to confirm execution of an operation when a change is made to system state, for example, deleting files.</span></span>
<span data-ttu-id="64f58-194">このコマンドは、変更するリソースの名前をユーザーに送信[し](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)ます。 Windows PowerShell ランタイムは、ユーザーに表示される内容を決定する際に、コマンドライン設定またはユーザー設定変数を考慮します。</span><span class="sxs-lookup"><span data-stu-id="64f58-194">[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="64f58-195">System.object を呼び出す[と、が返され](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)た後 `true` 、システムの[管理](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)......................................................... [..。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)</span><span class="sxs-lookup"><span data-stu-id="64f58-195">After the call to [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) returns `true`, the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method should call the [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) method.</span></span> <span data-ttu-id="64f58-196">このメソッドは、ユーザーにメッセージを送信して、操作を続行する必要があるかどうかをフィードバックできるようにします。</span><span class="sxs-lookup"><span data-stu-id="64f58-196">This method sends a message to the user to allow feedback to say if the operation should be continued.</span></span> <span data-ttu-id="64f58-197">プロバイダーは、system.servicemodel プロバイダーを呼び出す必要があり [ます。](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) 危険性の高いシステム変更については、追加のチェックとして続行してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-197">Your provider should call [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) as an additional check for potentially dangerous system modifications.</span></span>

## <a name="attaching-dynamic-parameters-to-the-move-item-cmdlet"></a><span data-ttu-id="64f58-198">Move-Item コマンドレットへの動的パラメーターのアタッチ</span><span class="sxs-lookup"><span data-stu-id="64f58-198">Attaching Dynamic Parameters to the Move-Item Cmdlet</span></span>

<span data-ttu-id="64f58-199">`Move-Item`コマンドレットには、実行時に動的に提供される追加のパラメーターが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-199">Sometimes the `Move-Item` cmdlet requires additional parameters that are provided dynamically at runtime.</span></span> <span data-ttu-id="64f58-200">これらの動的パラメーターを指定するには、ナビゲーションプロバイダーが、指定されたパスにある項目から必要なパラメーター値を取得し、コマンドレットクラス[や system.object に](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)類似した解析属性を持つプロパティとフィールドを持つオブジェクトを返すために、システムの[管理](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64f58-200">To provide these dynamic parameters, the navigation provider must implement the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) method to get the required parameter values from the item at the indicated path, and return an object that has properties and fields with parsing attributes similar to a cmdlet class or a [System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) object.</span></span>

<span data-ttu-id="64f58-201">このナビゲーションプロバイダーは、このメソッドを実装していません。</span><span class="sxs-lookup"><span data-stu-id="64f58-201">This navigation provider does not implement this method.</span></span> <span data-ttu-id="64f58-202">ただし、次のコードは、既定の実装である、system.object の既定の実装です。 [Moveitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)です。</span><span class="sxs-lookup"><span data-stu-id="64f58-202">However, the following code is the default implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters).</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters](Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters)]  -->

## <a name="normalizing-a-relative-path"></a><span data-ttu-id="64f58-203">相対パスの正規化</span><span class="sxs-lookup"><span data-stu-id="64f58-203">Normalizing a Relative Path</span></span>

<span data-ttu-id="64f58-204">ナビゲーションプロバイダーは、 [Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)メソッドを実装して、パラメーターで指定された完全修飾パスを、 `path` パラメーターで指定されたパスに対して相対的なものとして正規化します。 `basePath`</span><span class="sxs-lookup"><span data-stu-id="64f58-204">Your navigation provider implements the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method to normalize the fully-qualified path indicated in the `path` parameter as being relative to the path specified by the `basePath` parameter.</span></span> <span data-ttu-id="64f58-205">メソッドは、正規化されたパスの文字列形式を返します。</span><span class="sxs-lookup"><span data-stu-id="64f58-205">The method returns a string representation of the normalized path.</span></span> <span data-ttu-id="64f58-206">パラメーターに存在しないパスが指定されている場合、エラーが書き込ま `path` れます。</span><span class="sxs-lookup"><span data-stu-id="64f58-206">It writes an error if the `path` parameter specifies a nonexistent path.</span></span>

<span data-ttu-id="64f58-207">サンプルナビゲーションプロバイダーでは、このメソッドはオーバーライドされません。</span><span class="sxs-lookup"><span data-stu-id="64f58-207">The sample navigation provider does not override this method.</span></span> <span data-ttu-id="64f58-208">既定の実装は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64f58-208">The following is the default implementation.</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernormalizepath](Msh_samplestestcmdlets#testprovidernormalizepath)]  -->

#### <a name="things-to-remember-about-implementing-normalizerelativepath"></a><span data-ttu-id="64f58-209">NormalizeRelativePath の実装に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="64f58-209">Things to Remember About Implementing NormalizeRelativePath</span></span>

<span data-ttu-id="64f58-210">[Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)の実装では、パラメーターを解析する必要があります `path` が、純粋な構文解析を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64f58-210">Your implementation of [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) should parse the `path` parameter, but it does not have to use purely syntactical parsing.</span></span> <span data-ttu-id="64f58-211">このメソッドは、パスを使用してデータストア内のパス情報を参照し、大文字と小文字の区別と標準化されたパス構文に一致するパスを作成するように設計することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64f58-211">You are encouraged to design this method to use the path to look up the path information in the data store and create a path that matches the casing and standardized path syntax.</span></span>

## <a name="code-sample"></a><span data-ttu-id="64f58-212">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="64f58-212">Code Sample</span></span>

<span data-ttu-id="64f58-213">完全なサンプルコードについては、「 [AccessDbProviderSample05 のコードサンプル](./accessdbprovidersample05-code-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-213">For complete sample code, see [AccessDbProviderSample05 Code Sample](./accessdbprovidersample05-code-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="64f58-214">オブジェクトの種類と書式設定の定義</span><span class="sxs-lookup"><span data-stu-id="64f58-214">Defining Object Types and Formatting</span></span>

<span data-ttu-id="64f58-215">プロバイダーは、既存のオブジェクトにメンバーを追加したり、新しいオブジェクトを定義したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="64f58-215">It is possible for a provider to add members to existing objects or define new objects.</span></span> <span data-ttu-id="64f58-216">詳細については、「[オブジェクトの種類と書式設定の拡張](/previous-versions/ms714665(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-216">For more information, see[Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85)).</span></span>

## <a name="building-the-windows-powershell-provider"></a><span data-ttu-id="64f58-217">Windows PowerShell プロバイダーの構築</span><span class="sxs-lookup"><span data-stu-id="64f58-217">Building the Windows PowerShell provider</span></span>

<span data-ttu-id="64f58-218">詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f58-218">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)).</span></span>

## <a name="testing-the-windows-powershell-provider"></a><span data-ttu-id="64f58-219">Windows PowerShell プロバイダーのテスト</span><span class="sxs-lookup"><span data-stu-id="64f58-219">Testing the Windows PowerShell provider</span></span>

<span data-ttu-id="64f58-220">Windows powershell プロバイダーが Windows PowerShell に登録されている場合は、コマンドラインでサポートされているコマンドレットを実行してテストできます。これには、派生によって使用可能なコマンドレットも含まれます。</span><span class="sxs-lookup"><span data-stu-id="64f58-220">When your Windows PowerShell provider has been registered with Windows PowerShell, you can test it by running the supported cmdlets on the command line, including cmdlets made available by derivation.</span></span> <span data-ttu-id="64f58-221">この例では、サンプルナビゲーションプロバイダーをテストします。</span><span class="sxs-lookup"><span data-stu-id="64f58-221">This example will test the sample navigation provider.</span></span>

1. <span data-ttu-id="64f58-222">新しいシェルを実行し、コマンドレットを使用して、 `Set-Location` アクセスデータベースを示すパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="64f58-222">Run your new shell and use the `Set-Location` cmdlet to set the path to indicate the Access database.</span></span>

   ```powershell
   Set-Location mydb:
   ```

2. <span data-ttu-id="64f58-223">次に、コマンドレットを実行して、 `Get-Childitem` 使用可能なデータベーステーブルであるデータベースアイテムの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="64f58-223">Now run the `Get-Childitem` cmdlet to retrieve a list of the database items, which are the available database tables.</span></span> <span data-ttu-id="64f58-224">このコマンドレットは、テーブルごとにテーブル行の数も取得します。</span><span class="sxs-lookup"><span data-stu-id="64f58-224">For each table, this cmdlet also retrieves the number of table rows.</span></span>

   ```powershell
   Get-ChildItem | Format-Table rowcount,name -AutoSize
   ```

   ```Output
   RowCount   Name
   --------   ----
        180   MSysAccessObjects
          0   MSysACEs
          1   MSysCmdbars
          0   MSysIMEXColumns
          0   MSysIMEXSpecs
          0   MSysObjects
          0   MSysQueries
          7   MSysRelationships
          8   Categories
         91   Customers
          9   Employees
       2155   Order Details
        830   Orders
         77   Products
          3   Shippers
         29   Suppliers
   ```

3. <span data-ttu-id="64f58-225">もう一度コマンドレットを使用して、 `Set-Location` Employees データテーブルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="64f58-225">Use the `Set-Location` cmdlet again to set the location of the Employees data table.</span></span>

   ```powershell
   Set-Location Employees
   ```

4. <span data-ttu-id="64f58-226">ここで、コマンドレットを使用して、 `Get-Location` Employees テーブルへのパスを取得します。</span><span class="sxs-lookup"><span data-stu-id="64f58-226">Let's now use the `Get-Location` cmdlet to retrieve the path to the Employees table.</span></span>

   ```powershell
   Get-Location
   ```

   ```Output
   Path
   ----
   mydb:\Employees
   ```

5. <span data-ttu-id="64f58-227">ここで、コマンドレット `Get-Childitem` にパイプを使用して `Format-Table` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="64f58-227">Now use the `Get-Childitem` cmdlet piped to the `Format-Table` cmdlet.</span></span> <span data-ttu-id="64f58-228">この一連のコマンドレットは、テーブル行である Employees データテーブルの項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="64f58-228">This set of cmdlets retrieves the items for the Employees data table, which are the table rows.</span></span> <span data-ttu-id="64f58-229">これらは、コマンドレットによって指定された形式になってい `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="64f58-229">They are formatted as specified by the `Format-Table` cmdlet.</span></span>

   ```powershell
   Get-ChildItem | Format-Table rownumber,psiscontainer,data -AutoSize
   ```

   ```Output
   RowNumber   PSIsContainer   Data
   ---------   --------------   ----
   0           False            System.Data.DataRow
   1           False            System.Data.DataRow
   2           False            System.Data.DataRow
   3           False            System.Data.DataRow
   4           False            System.Data.DataRow
   5           False            System.Data.DataRow
   6           False            System.Data.DataRow
   7           False            System.Data.DataRow
   8           False            System.Data.DataRow
   ```

6. <span data-ttu-id="64f58-230">これで、コマンドレットを実行して、 `Get-Item` Employees データテーブルの行0の項目を取得できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="64f58-230">You can now run the `Get-Item` cmdlet to retrieve the items for row 0 of the Employees data table.</span></span>

   ```powershell
   Get-Item 0
   ```

   ```Output
   PSPath        : AccessDB::C:\PS\Northwind.mdb\Employees\0
   PSParentPath  : AccessDB::C:\PS\Northwind.mdb\Employees
   PSChildName   : 0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data           : System.Data.DataRow
   RowNumber      : 0
   ```

7. <span data-ttu-id="64f58-231">コマンドレットをもう一度使用して、 `Get-Item` 行0の項目の従業員データを取得します。</span><span class="sxs-lookup"><span data-stu-id="64f58-231">Use the `Get-Item` cmdlet again to retrieve the employee data for the items in row 0.</span></span>

   ```powershell
   (Get-Item 0).data
   ```

   ```Output
   EmployeeID      : 1
   LastName        : Davis
   FirstName       : Sara
   Title           : Sales Representative
   TitleOfCourtesy : Ms.
   BirthDate       : 12/8/1968 12:00:00 AM
   HireDate        : 5/1/1992 12:00:00 AM
   Address         : 4567 Main Street
                     Apt. 2A
   City            : Buffalo
   Region          : NY
   PostalCode      : 98052
   Country         : USA
   HomePhone       : (206) 555-9857
   Extension       : 5467
   Photo           : EmpID1.bmp
   Notes           : Education includes a BA in psychology from
                     Colorado State University. She also completed "The
                     Art of the Cold Call."  Nancy is a member of
                     Toastmasters International.
   ReportsTo       : 2
   ```

## <a name="see-also"></a><span data-ttu-id="64f58-232">参照</span><span class="sxs-lookup"><span data-stu-id="64f58-232">See Also</span></span>

[<span data-ttu-id="64f58-233">Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="64f58-233">Creating Windows PowerShell providers</span></span>](./how-to-create-a-windows-powershell-provider.md)

[<span data-ttu-id="64f58-234">Windows PowerShell プロバイダーを設計する</span><span class="sxs-lookup"><span data-stu-id="64f58-234">Design Your Windows PowerShell provider</span></span>](./designing-your-windows-powershell-provider.md)

<span data-ttu-id="64f58-235">[オブジェクトの種類と書式設定の拡張](/previous-versions/ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="64f58-235">[Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85))</span></span>

[<span data-ttu-id="64f58-236">コンテナーの Windows PowerShell プロバイダーを実装する</span><span class="sxs-lookup"><span data-stu-id="64f58-236">Implement a Container Windows PowerShell provider</span></span>](./creating-a-windows-powershell-container-provider.md)

<span data-ttu-id="64f58-237">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="64f58-237">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="64f58-238">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="64f58-238">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="64f58-239">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="64f58-239">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
