---
ms.date: 09/13/2016
ms.topic: reference
title: オブジェクトの既定のメソッドを定義する
description: オブジェクトの既定のメソッドを定義する
ms.openlocfilehash: c65ca91a7038f32d8c3ef62cfe7881e5ad4dba5a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355529"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="ceab3-103">オブジェクトの既定のメソッドを定義する</span><span class="sxs-lookup"><span data-stu-id="ceab3-103">Defining Default Methods for Objects</span></span>

<span data-ttu-id="ceab3-104">.NET Framework オブジェクトを拡張すると、コードメソッドとスクリプトメソッドをオブジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="ceab3-104">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="ceab3-105">これらのメソッドの定義に使用される XML については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="ceab3-105">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="ceab3-106">次のセクションの例は、 `Types.ps1xml` Windows PowerShell インストールディレクトリ () の種類のファイルに含まれてい `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="ceab3-106">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="ceab3-107">詳細については、「 [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceab3-107">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="ceab3-108">コードメソッド</span><span class="sxs-lookup"><span data-stu-id="ceab3-108">Code methods</span></span>

<span data-ttu-id="ceab3-109">コードメソッドは、.NET Framework オブジェクトの静的メソッドを参照しています。</span><span class="sxs-lookup"><span data-stu-id="ceab3-109">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="ceab3-110">次の例では、 **ToString** メソッドが [System.Xml.Xmlノード](/dotnet/api/System.Xml.XmlNode) 型に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ceab3-110">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="ceab3-111">[Pscodemethod](/dotnet/api/system.management.automation.pscodemethod)要素は、拡張メソッドをコードメソッドとして定義します。</span><span class="sxs-lookup"><span data-stu-id="ceab3-111">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="ceab3-112">[Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name)要素は、拡張メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ceab3-112">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="ceab3-113">また、 [Codereference 参照](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) 要素は静的メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="ceab3-113">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="ceab3-114">[Pscodemethod](/dotnet/api/system.management.automation.pscodemethod)要素を[psmembers](/dotnet/api/system.management.automation.psmemberset)要素のメンバーに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ceab3-114">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodeMethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a><span data-ttu-id="ceab3-115">スクリプトメソッド</span><span class="sxs-lookup"><span data-stu-id="ceab3-115">Script methods</span></span>

<span data-ttu-id="ceab3-116">スクリプトメソッドは、値がスクリプトの出力であるメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="ceab3-116">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="ceab3-117">次の例では、 **Converttodatetime** メソッドが [system.management.managementobject](/dotnet/api/System.Management.ManagementObject) 型に追加されています。</span><span class="sxs-lookup"><span data-stu-id="ceab3-117">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="ceab3-118">[Psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod)要素は、拡張メソッドをスクリプトメソッドとして定義します。</span><span class="sxs-lookup"><span data-stu-id="ceab3-118">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element defines the extended method as a script method.</span></span> <span data-ttu-id="ceab3-119">[Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name)要素は、拡張メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ceab3-119">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="ceab3-120">また、 [script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) 要素は、メソッド値を生成するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ceab3-120">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="ceab3-121">[Psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod)要素は、 [psmembers](/dotnet/api/system.management.automation.psmemberset)要素のメンバーに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ceab3-121">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.Management.ManagementObject</Name>
  <Members>
    <ScriptMethod>
      <Name>ConvertToDateTime</Name>
      <Script>
        [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
      </Script>
    </ScriptMethod>
  </Members>
</Type>
```

## <a name="see-also"></a><span data-ttu-id="ceab3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ceab3-122">See also</span></span>

[<span data-ttu-id="ceab3-123">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="ceab3-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
