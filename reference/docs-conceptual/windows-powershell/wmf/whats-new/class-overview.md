---
ms.date: 07/29/2020
title: PowerShell 5.0 の新しい言語機能
ms.openlocfilehash: dada39c4121a810c7ce87a642f232934152104e5
ms.sourcegitcommit: 339e5fc8a4cc18b4ff6956fe5180343588e40e30
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87410174"
---
# <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="f6bf2-102">PowerShell 5.0 の新しい言語機能</span><span class="sxs-lookup"><span data-stu-id="f6bf2-102">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="f6bf2-103">PowerShell 5.0 では、他のオブジェクト指向プログラミング言語のように、形式的構文とセマンティクスを使って、クラスや他のユーザー定義型を定義する機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-103">PowerShell 5.0 added the ability to define classes and other user-defined types using formal syntax and semantics like other object-oriented programming languages.</span></span> <span data-ttu-id="f6bf2-104">開発者や IT プロフェッショナルがより広範なユース ケースで PowerShell を採用できるようにし、PowerShell アーティファクト (DSC リソースなど) の開発を簡素化し、管理面の対応を促進することがその目標です。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-104">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

<span data-ttu-id="f6bf2-105">PowerShell 5.0 では、PowerShell に次の新しい言語要素が導入されています。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-105">PowerShell 5.0 introduces the following new language elements in PowerShell:</span></span>

### <a name="class-keyword"></a><span data-ttu-id="f6bf2-106">class キーワード</span><span class="sxs-lookup"><span data-stu-id="f6bf2-106">Class keyword</span></span>

<span data-ttu-id="f6bf2-107">`class` キーワードでは新しいクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-107">The `class` keyword defines a new class.</span></span> <span data-ttu-id="f6bf2-108">これは、真の .NET Framework 型です。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-108">This is a true .NET Framework type.</span></span> <span data-ttu-id="f6bf2-109">クラス メンバーはパブリックですが、モジュール スコープ内でのみパブリックです。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-109">Class members are public, but only public within the module scope.</span></span> <span data-ttu-id="f6bf2-110">型名を文字列として参照することはできません (たとえば、`New-Object` は機能しません)。このリリースでは、クラスが定義されているスクリプトまたはモジュール ファイルの外で type リテラル (`[MyClass]` など) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-110">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script or module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="f6bf2-111">enum キーワードおよび列挙</span><span class="sxs-lookup"><span data-stu-id="f6bf2-111">Enum keyword and enumerations</span></span>

<span data-ttu-id="f6bf2-112">区切り文字として改行文字を使用する `enum` キーワードのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-112">Support for the `enum` keyword has been added, which uses newline as the delimiter.</span></span> <span data-ttu-id="f6bf2-113">現時点では、列挙子自体に関して列挙子を定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-113">Currently, you cannot define an enumerator in terms of itself.</span></span> <span data-ttu-id="f6bf2-114">ただし、次の例に示すように、別の列挙型に関して列挙型を初期化することはできます。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-114">However, you can initialize an enum in terms of another enum, as shown in the following example.</span></span> <span data-ttu-id="f6bf2-115">また、基本データ型を指定することはできません。基本データ型は常に `[int]` です。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-115">Also, the base type cannot be specified; it is always `[int]`.</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="f6bf2-116">列挙子の値は、解析時定数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-116">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="f6bf2-117">呼び出されたコマンドの結果に、それを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-117">You cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="f6bf2-118">次の例に示すように、enum では算術演算がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-118">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a><span data-ttu-id="f6bf2-119">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="f6bf2-119">Import-DscResource</span></span>

<span data-ttu-id="f6bf2-120">`Import-DscResource` は真の動的キーワードです。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-120">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="f6bf2-121">PowerShell では、**DscResource** 属性を含むクラスを探して、指定されたモジュールのルート モジュールを解析します。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-121">PowerShell parses the specified module's root module, searching for classes that contain the **DscResource** attribute.</span></span>

### <a name="implementingassembly"></a><span data-ttu-id="f6bf2-122">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="f6bf2-122">ImplementingAssembly</span></span>

<span data-ttu-id="f6bf2-123">新しいフィールド **ImplementingAssembly** が **ModuleInfo** に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-123">A new field, **ImplementingAssembly**, has been added to **ModuleInfo**.</span></span> <span data-ttu-id="f6bf2-124">これは、スクリプトでクラスが定義されている場合はスクリプト モジュールに作成された動的アセンブリに設定されるか、またはバイナリ モジュールの読み込み済みアセンブリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-124">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="f6bf2-125">**ModuleType** が **Manifest** の場合は設定されません。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-125">It is not set when **ModuleType** is **Manifest**.</span></span>

<span data-ttu-id="f6bf2-126">**ImplementingAssembly** フィールドのリフレクションでは、モジュール内のリソースが検出されます。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-126">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="f6bf2-127">これは、PowerShell または他の管理言語で記述されたリソースを検出できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f6bf2-127">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

## <a name="further-reading"></a><span data-ttu-id="f6bf2-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6bf2-128">Further reading</span></span>

- [<span data-ttu-id="f6bf2-129">about_Classes</span><span class="sxs-lookup"><span data-stu-id="f6bf2-129">about_Classes</span></span>](/powershell/module/microsoft.powershell.core/about/about_classes)
- [<span data-ttu-id="f6bf2-130">about_Enum</span><span class="sxs-lookup"><span data-stu-id="f6bf2-130">about_Enum</span></span>](/powershell/module/microsoft.powershell.core/about/about_enum)
- [<span data-ttu-id="f6bf2-131">about_Classes_and_DSC</span><span class="sxs-lookup"><span data-stu-id="f6bf2-131">about_Classes_and_DSC</span></span>](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)
