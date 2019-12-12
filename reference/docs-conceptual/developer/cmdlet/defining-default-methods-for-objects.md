---
title: オブジェクトの既定のメソッドの定義 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fe744a-485f-4c21-9623-1cb546372211
caps.latest.revision: 9
ms.openlocfilehash: 346a194c6b4c81aa61a6331cdb62ae380a17bb1e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365691"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="06d4d-102">オブジェクトの既定のメソッドを定義する</span><span class="sxs-lookup"><span data-stu-id="06d4d-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="06d4d-103">.NET Framework オブジェクトを拡張すると、コードメソッドとスクリプトメソッドをオブジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="06d4d-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="06d4d-104">これらのメソッドの定義に使用される XML については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="06d4d-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="06d4d-105">次のセクションの例は、Windows PowerShell インストールディレクトリ (`$PSHOME`) の `Types.ps1xml` の種類のファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="06d4d-105">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="06d4d-106">詳細については、「 [types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06d4d-106">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="06d4d-107">コードメソッド</span><span class="sxs-lookup"><span data-stu-id="06d4d-107">Code methods</span></span>

<span data-ttu-id="06d4d-108">コードメソッドは、.NET Framework オブジェクトの静的メソッドを参照しています。</span><span class="sxs-lookup"><span data-stu-id="06d4d-108">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="06d4d-109">次の例では、 **ToString**メソッドが[system.xml](/dotnet/api/System.Xml.XmlNode)型に追加されます。</span><span class="sxs-lookup"><span data-stu-id="06d4d-109">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="06d4d-110">[Pscodemethod](/dotnet/api/system.management.automation.pscodemethod)要素は、拡張メソッドをコードメソッドとして定義します。</span><span class="sxs-lookup"><span data-stu-id="06d4d-110">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="06d4d-111">[Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name)要素は、拡張メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="06d4d-111">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="06d4d-112">また、 [Codereference 参照](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference)要素は静的メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="06d4d-112">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="06d4d-113">[Pscodemethod](/dotnet/api/system.management.automation.pscodemethod)要素を[psmembers](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0)要素のメンバーに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="06d4d-113">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.</span></span>

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

## <a name="script-methods"></a><span data-ttu-id="06d4d-114">スクリプトメソッド</span><span class="sxs-lookup"><span data-stu-id="06d4d-114">Script methods</span></span>

<span data-ttu-id="06d4d-115">スクリプトメソッドは、値がスクリプトの出力であるメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="06d4d-115">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="06d4d-116">次の例では、 **Converttodatetime**メソッドが[system.management.managementobject](/dotnet/api/System.Management.ManagementObject)型に追加されています。</span><span class="sxs-lookup"><span data-stu-id="06d4d-116">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="06d4d-117">[Psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0)要素は、拡張メソッドをスクリプトメソッドとして定義します。</span><span class="sxs-lookup"><span data-stu-id="06d4d-117">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element defines the extended method as a script method.</span></span> <span data-ttu-id="06d4d-118">[Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name)要素は、拡張メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="06d4d-118">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="06d4d-119">また、 [script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script)要素は、メソッド値を生成するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="06d4d-119">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="06d4d-120">[Psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0)要素は、 [psmembers](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0)要素のメンバーに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="06d4d-120">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="06d4d-121">「</span><span class="sxs-lookup"><span data-stu-id="06d4d-121">See also</span></span>

[<span data-ttu-id="06d4d-122">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="06d4d-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
