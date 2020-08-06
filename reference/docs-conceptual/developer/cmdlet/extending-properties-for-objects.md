---
title: オブジェクトのプロパティの拡張 |Microsoft Docs
ms.date: 08/21/2019
ms.openlocfilehash: acd20c7e2b6ef84a9c932538eb8e167d68c8a660
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784301"
---
# <a name="extending-properties-for-objects"></a><span data-ttu-id="37ca4-102">オブジェクトのプロパティを拡張する</span><span class="sxs-lookup"><span data-stu-id="37ca4-102">Extending Properties for Objects</span></span>

<span data-ttu-id="37ca4-103">.NET Framework オブジェクトを拡張すると、エイリアスプロパティ、コードプロパティ、メモプロパティ、スクリプトプロパティ、およびプロパティセットをオブジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-103">When you extend .NET Framework objects, you can add alias properties, code properties, note properties, script properties, and property sets to the objects.</span></span> <span data-ttu-id="37ca4-104">以下のセクションでは、これらのプロパティを定義する XML について説明します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-104">The XML that defines these properties is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="37ca4-105">次のセクションの例は、 `Types.ps1xml` PowerShell インストールディレクトリ () の既定の種類のファイルに含まれてい `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-105">The examples in the following sections are from the default `Types.ps1xml` types file in the PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="37ca4-106">詳細については、「 [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37ca4-106">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="alias-properties"></a><span data-ttu-id="37ca4-107">別名のプロパティ</span><span class="sxs-lookup"><span data-stu-id="37ca4-107">Alias properties</span></span>

<span data-ttu-id="37ca4-108">エイリアスプロパティは、既存のプロパティの新しい名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-108">An alias property defines a new name for an existing property.</span></span>

<span data-ttu-id="37ca4-109">次の例では、 **Count**プロパティが[system.string 型に](/dotnet/api/System.Array)追加されています。</span><span class="sxs-lookup"><span data-stu-id="37ca4-109">In the following example, the **Count** property is added to the [System.Array](/dotnet/api/System.Array) type.</span></span> <span data-ttu-id="37ca4-110">Alias[プロパティ](/dotnet/api/system.management.automation.psaliasproperty)要素は、拡張プロパティを別名プロパティとして定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-110">The [AliasProperty](/dotnet/api/system.management.automation.psaliasproperty) element defines the extended property as an alias property.</span></span> <span data-ttu-id="37ca4-111">[Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-111">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the new name.</span></span> <span data-ttu-id="37ca4-112">また、 [Referencedmembername](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername)要素は、エイリアスによって参照される既存のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-112">And, the [ReferencedMemberName](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) element specifies the existing property that is referenced by the alias.</span></span> <span data-ttu-id="37ca4-113">また、 `AliasProperty` 要素をメンバーメンバーに追加することも[MemberSets](/dotnet/api/system.management.automation.psmemberset)できます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-113">You can also add the `AliasProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

## <a name="code-properties"></a><span data-ttu-id="37ca4-114">コードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="37ca4-114">Code properties</span></span>

<span data-ttu-id="37ca4-115">コードプロパティは、.NET Framework オブジェクトの静的プロパティを参照します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-115">A code property references a static property of a .NET Framework object.</span></span>

<span data-ttu-id="37ca4-116">次の例では、 **Mode**プロパティが[DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo)型に追加されています。</span><span class="sxs-lookup"><span data-stu-id="37ca4-116">In the following example, the **Mode** property is added to the [System.IO.DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="37ca4-117">[Codeproperty](/dotnet/api/system.management.automation.pscodeproperty)要素は、拡張プロパティをコードプロパティとして定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-117">The [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) element defines the extended property as a code property.</span></span> <span data-ttu-id="37ca4-118">[Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、拡張プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-118">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="37ca4-119">また、 [Getcodereference 参照](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference)要素は、拡張プロパティによって参照される静的メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-119">And, the [GetCodeReference](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) element defines the static method that is referenced by the extended property.</span></span> <span data-ttu-id="37ca4-120">また、 `CodeProperty` 要素をメンバーメンバーに追加することも[MemberSets](/dotnet/api/system.management.automation.psmemberset)できます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-120">You can also add the `CodeProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>Microsoft.PowerShell.Commands.FileSystemProvider</TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

## <a name="note-properties"></a><span data-ttu-id="37ca4-121">プロパティへの注記</span><span class="sxs-lookup"><span data-stu-id="37ca4-121">Note properties</span></span>

<span data-ttu-id="37ca4-122">Note プロパティは、静的な値を持つプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-122">A note property defines a property that has a static value.</span></span>

<span data-ttu-id="37ca4-123">次の例では、 **Status**プロパティの値が常に**Success**であるが、 [DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo)型に追加されています。</span><span class="sxs-lookup"><span data-stu-id="37ca4-123">In the following example, the **Status** property, whose value is always **Success**, is added to the [System.IO.DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="37ca4-124">Note[プロパティ要素は、拡張](/dotnet/api/system.management.automation.psnoteproperty)プロパティを note プロパティとして定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-124">The [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) element defines the extended property as a note property.</span></span> <span data-ttu-id="37ca4-125">[Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、拡張プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-125">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="37ca4-126">[Value](/dotnet/api/system.management.automation.psnoteproperty.value)要素は、拡張プロパティの静的な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-126">The [Value](/dotnet/api/system.management.automation.psnoteproperty.value) element specifies the static value of the extended property.</span></span> <span data-ttu-id="37ca4-127">要素は、 `NoteProperty` メンバーメンバーに追加することもでき[MemberSets](/dotnet/api/system.management.automation.psmemberset)ます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-127">The `NoteProperty` element can also be added to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

## <a name="script-properties"></a><span data-ttu-id="37ca4-128">スクリプトのプロパティ</span><span class="sxs-lookup"><span data-stu-id="37ca4-128">Script properties</span></span>

<span data-ttu-id="37ca4-129">スクリプトプロパティは、スクリプトの出力を値として持つプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-129">A script property defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="37ca4-130">次の例では、 **VersionInfo**プロパティ[が、system.string 型に](/dotnet/api/System.IO.FileInfo)追加されます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-130">In the following example, the **VersionInfo** property is added to the [System.IO.FileInfo](/dotnet/api/System.IO.FileInfo) type.</span></span> <span data-ttu-id="37ca4-131">[Scriptproperty](/dotnet/api/system.management.automation.psscriptproperty)要素は、拡張プロパティをスクリプトプロパティとして定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-131">The [ScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) element defines the extended property as a script property.</span></span> <span data-ttu-id="37ca4-132">[Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、拡張プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-132">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="37ca4-133">また、 [Getscriptblock](/dotnet/api/system.management.automation.psscriptproperty.getterscript)要素は、プロパティ値を生成するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-133">And, the [GetScriptBlock](/dotnet/api/system.management.automation.psscriptproperty.getterscript) element specifies the script that generates the property value.</span></span> <span data-ttu-id="37ca4-134">また、 `ScriptProperty` 要素をメンバーメンバーに追加することも[MemberSets](/dotnet/api/system.management.automation.psmemberset)できます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-134">You can also add the `ScriptProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
        [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

## <a name="property-sets"></a><span data-ttu-id="37ca4-135">プロパティセット</span><span class="sxs-lookup"><span data-stu-id="37ca4-135">Property sets</span></span>

<span data-ttu-id="37ca4-136">プロパティセットは、セットの名前で参照できる拡張プロパティのグループを定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-136">A property set defines a group of extended properties that can be referenced by the name of the set.</span></span>
<span data-ttu-id="37ca4-137">たとえば、 [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table) 
 **プロパティ**パラメーターでは、表示する特定のプロパティセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-137">For example, the [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)
**Property** parameter can specify a specific property set to be displayed.</span></span> <span data-ttu-id="37ca4-138">プロパティセットを指定すると、そのセットに属するプロパティだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-138">When a property set is specified, only those properties that belong to the set are displayed.</span></span>

<span data-ttu-id="37ca4-139">オブジェクトに対して定義できるプロパティセットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="37ca4-139">There's no restriction on the number of property sets that can be defined for an object.</span></span> <span data-ttu-id="37ca4-140">ただし、オブジェクトの既定の表示プロパティを定義するために使用されるプロパティセットは、 **Psstandardmembers**メンバーセット内で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ca4-140">However, the property sets used to define the default display properties of an object must be specified within the **PSStandardMembers** member set.</span></span> <span data-ttu-id="37ca4-141">型ファイルでは、 `Types.ps1xml` 既定のプロパティセット名に**Defaultdisplayproperty**、 **DefaultDisplayPropertySet**、および**DefaultKeyPropertySet**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-141">In the `Types.ps1xml` types file, the default property set names include **DefaultDisplayProperty**, **DefaultDisplayPropertySet**, and **DefaultKeyPropertySet**.</span></span> <span data-ttu-id="37ca4-142">**Psstandardmembers**メンバーセットに追加した追加のプロパティセットはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-142">Any additional property sets that you add to the **PSStandardMembers** member set are ignored.</span></span>

<span data-ttu-id="37ca4-143">次の例では、 **DefaultDisplayPropertySet**プロパティセットが[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)型の**psstandardmembers**メンバーセットに追加されます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-143">In the following example, the **DefaultDisplayPropertySet** property set is added to the **PSStandardMembers** member set of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) type.</span></span> <span data-ttu-id="37ca4-144">[PropertySet](/dotnet/api/system.management.automation.pspropertyset)要素は、プロパティのグループを定義します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-144">The [PropertySet](/dotnet/api/system.management.automation.pspropertyset) element defines the group of properties.</span></span> <span data-ttu-id="37ca4-145">[Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、プロパティセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-145">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the property set.</span></span> <span data-ttu-id="37ca4-146">また、 [Referencedproperties](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames)要素は、セットのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-146">And, the [ReferencedProperties](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) element specifies the properties of the set.</span></span> <span data-ttu-id="37ca4-147">`PropertySet`要素を[Type](/dotnet/api/system.management.automation.pstypename)要素のメンバーに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="37ca4-147">You can also add the `PropertySet` element to the members of the [Type](/dotnet/api/system.management.automation.pstypename) element.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
           <Name>DefaultDisplayPropertySet</Name>
           <ReferencedProperties>
            <Name>Status</Name
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

## <a name="see-also"></a><span data-ttu-id="37ca4-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="37ca4-148">See also</span></span>

[<span data-ttu-id="37ca4-149">Types.ps1xml について</span><span class="sxs-lookup"><span data-stu-id="37ca4-149">About Types.ps1xml</span></span>](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)

[<span data-ttu-id="37ca4-150">システムの管理</span><span class="sxs-lookup"><span data-stu-id="37ca4-150">System.Management.Automation</span></span>](/dotnet/api/System.Management.Automation)

[<span data-ttu-id="37ca4-151">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="37ca4-151">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
