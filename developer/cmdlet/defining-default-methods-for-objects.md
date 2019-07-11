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
ms.openlocfilehash: af554cde5e888f2a008028010332caa473151622
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67733984"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="e7255-102">オブジェクトの既定のメソッドを定義する</span><span class="sxs-lookup"><span data-stu-id="e7255-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="e7255-103">.NET Framework オブジェクトを拡張するときに、オブジェクトをコード メソッドおよびスクリプト メソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e7255-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span> <span data-ttu-id="e7255-104">これらのメソッドを定義するために使用される XML は次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="e7255-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="e7255-105">セクションでは、次の例は、Windows PowerShell のインストール ディレクトリに Types.ps1xml 型ファイル (`$pshome`)。</span><span class="sxs-lookup"><span data-stu-id="e7255-105">The examples in the following sections are from the Types.ps1xml types file in the Windows PowerShell installation directory (`$pshome`).</span></span>

## <a name="code-methods"></a><span data-ttu-id="e7255-106">コード メソッド</span><span class="sxs-lookup"><span data-stu-id="e7255-106">Code Methods</span></span>

<span data-ttu-id="e7255-107">コードのメソッドは、.NET Framework オブジェクトの静的メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="e7255-107">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="e7255-108">次の例では、 **ConvertLargeIntegerToInt64**メソッドに追加されます、 [System.Xml.Xmlnode でしょうか。Displayproperty = Fullname](/dotnet/api/System.Xml.XmlNode)型。</span><span class="sxs-lookup"><span data-stu-id="e7255-108">In the following example, the **ConvertLargeIntegerToInt64** method is added to the [System.Xml.Xmlnode?Displayproperty=Fullname](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="e7255-109">[PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)要素は、コードの方法として、拡張メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="e7255-109">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="e7255-110">[名前](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name)要素は、拡張メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7255-110">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="e7255-111">また、 [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference)要素は、静的メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7255-111">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="e7255-112">(追加することも、 [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)要素のメンバーに、 [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0)要素です)。</span><span class="sxs-lookup"><span data-stu-id="e7255-112">(You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.)</span></span>

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodemethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a><span data-ttu-id="e7255-113">スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="e7255-113">Script Methods</span></span>

<span data-ttu-id="e7255-114">スクリプト メソッドでは、値が、スクリプトの出力メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="e7255-114">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="e7255-115">次の例では、 **ConvertToDateTime**メソッドに追加されます、 [System.Management.Managementobject でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.ManagementObject)型。</span><span class="sxs-lookup"><span data-stu-id="e7255-115">In the following example, the **ConvertToDateTime** method is added to the [System.Management.Managementobject?Displayproperty=Fullname](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="e7255-116">[PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0)要素は、スクリプト メソッドとして、拡張メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="e7255-116">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element defines the extended method as a script method.</span></span> <span data-ttu-id="e7255-117">[名前](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name)要素は、拡張メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7255-117">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="e7255-118">また、[スクリプト](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script)要素は、メソッドの値を生成するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7255-118">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="e7255-119">(追加することも、 [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0)要素のメンバーに、 [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0)要素です)。</span><span class="sxs-lookup"><span data-stu-id="e7255-119">(You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e7255-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7255-120">See Also</span></span>

[<span data-ttu-id="e7255-121">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="e7255-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
