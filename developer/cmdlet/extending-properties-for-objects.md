---
title: オブジェクトのプロパティの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f33ff3e9-213c-44aa-92ab-09450e65c676
caps.latest.revision: 11
ms.openlocfilehash: be31d03b02394cb1694909cf7b65bbc2a29f6976
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795438"
---
# <a name="extending-properties-for-objects"></a><span data-ttu-id="34bbe-102">オブジェクトのプロパティを拡張する</span><span class="sxs-lookup"><span data-stu-id="34bbe-102">Extending Properties for Objects</span></span>

<span data-ttu-id="34bbe-103">.NET Framework オブジェクトを拡張するときに追加できますエイリアス プロパティ、コードのプロパティ、ノート プロパティ、スクリプトのプロパティ、およびプロパティ セット オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="34bbe-103">When you extend .NET Framework objects, you can add alias properties, code properties, note properties, script properties, and property sets to the objects.</span></span> <span data-ttu-id="34bbe-104">これらのプロパティを定義するために使用される XML は次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-104">The XML that is used to define these properties is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="34bbe-105">セクションでは、次の例は、Windows PowerShell のインストール ディレクトリで既定 Types.ps1xml 型ファイル (`$pshome`)。</span><span class="sxs-lookup"><span data-stu-id="34bbe-105">The examples in the following sections are from the default Types.ps1xml types file in the Windows PowerShell installation directory (`$pshome`).</span></span>

## <a name="alias-properties"></a><span data-ttu-id="34bbe-106">エイリアスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="34bbe-106">Alias Properties</span></span>

<span data-ttu-id="34bbe-107">エイリアスのプロパティでは、既存のプロパティの新しい名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-107">An alias property defines a new name for an existing property.</span></span>

<span data-ttu-id="34bbe-108">次の例では、`Count`プロパティに追加されます、 [System.Array でしょうか。Displayproperty = Fullname](/dotnet/api/System.Array)型。</span><span class="sxs-lookup"><span data-stu-id="34bbe-108">In the following example, the `Count` property is added to the [System.Array?Displayproperty=Fullname](/dotnet/api/System.Array) type.</span></span> <span data-ttu-id="34bbe-109">[AliasProperty](http://msdn.microsoft.com/en-us/b140038c-807a-4bb9-beca-332491cda1b1)要素は、エイリアス プロパティとして、拡張プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-109">The [AliasProperty](http://msdn.microsoft.com/en-us/b140038c-807a-4bb9-beca-332491cda1b1) element defines the extended property as an alias property.</span></span> <span data-ttu-id="34bbe-110">[名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素を新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-110">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the new name.</span></span> <span data-ttu-id="34bbe-111">また、 [ReferencedMemberName](http://msdn.microsoft.com/en-us/0c5db6cc-9033-4d48-88a7-76b962882f7a)要素は、別名で参照されている既存のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-111">And, the [ReferencedMemberName](http://msdn.microsoft.com/en-us/0c5db6cc-9033-4d48-88a7-76b962882f7a) element specifies the existing property that is referenced by the alias.</span></span> <span data-ttu-id="34bbe-112">(追加することも、 [AliasProperty](http://msdn.microsoft.com/en-us/d6647953-94ad-4b0b-af2e-4dda6952dee1)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。</span><span class="sxs-lookup"><span data-stu-id="34bbe-112">(You can also add the [AliasProperty](http://msdn.microsoft.com/en-us/d6647953-94ad-4b0b-af2e-4dda6952dee1) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="code-properties"></a><span data-ttu-id="34bbe-113">コードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="34bbe-113">Code Properties</span></span>

<span data-ttu-id="34bbe-114">コードのプロパティは、.NET Framework オブジェクトの静的プロパティを参照します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-114">A code property references a static property of a .NET Framework object.</span></span>

<span data-ttu-id="34bbe-115">次の例では、`Node`プロパティに追加されます、 [System.IO.Directoryinfo でしょうか。Displayproperty = Fullname](/dotnet/api/System.IO.DirectoryInfo)型。</span><span class="sxs-lookup"><span data-stu-id="34bbe-115">In the following example, the `Node` property is added to the [System.IO.Directoryinfo?Displayproperty=Fullname](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="34bbe-116">[CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db)要素は、コードのプロパティとして、拡張プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-116">The [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db) element defines the extended property as a code property.</span></span> <span data-ttu-id="34bbe-117">[名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-117">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended property.</span></span> <span data-ttu-id="34bbe-118">また、 [GetCodeReference](http://msdn.microsoft.com/en-us/62af34f5-cc22-42c0-9e0c-3bd0f5c1a4a0)要素は、拡張プロパティによって参照される静的メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-118">And, the [GetCodeReference](http://msdn.microsoft.com/en-us/62af34f5-cc22-42c0-9e0c-3bd0f5c1a4a0) element defines the static method that is referenced by the extended property.</span></span> <span data-ttu-id="34bbe-119">(追加することも、 [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。</span><span class="sxs-lookup"><span data-stu-id="34bbe-119">(You can also add the [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="note-properties"></a><span data-ttu-id="34bbe-120">ノート プロパティ</span><span class="sxs-lookup"><span data-stu-id="34bbe-120">Note Properties</span></span>

<span data-ttu-id="34bbe-121">メモのプロパティでは、静的な値を持つプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-121">A note property defines a property that has a static value.</span></span>

<span data-ttu-id="34bbe-122">次の例では、 `Status` (値は「成功」では常に) プロパティに追加されます、 [System.IO.Directoryinfo でしょうか。Displayproperty = Fullname](/dotnet/api/System.IO.DirectoryInfo)型。</span><span class="sxs-lookup"><span data-stu-id="34bbe-122">In the following example, the `Status` property (whose value is always "Success") is added to the [System.IO.Directoryinfo?Displayproperty=Fullname](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="34bbe-123">[NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb)要素拡張プロパティを定義します注プロパティとして、[名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張プロパティの名前を指定し、[値](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c)要素。拡張プロパティの静的な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-123">The [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb) element defines the extended property as a note property; the [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended property; and the [Value](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c) element specifies the static value of the extended property.</span></span> <span data-ttu-id="34bbe-124">(、 [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb)のメンバーに要素を追加することも、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。</span><span class="sxs-lookup"><span data-stu-id="34bbe-124">(The [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb) element can also be added to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="script-properties"></a><span data-ttu-id="34bbe-125">スクリプトのプロパティ</span><span class="sxs-lookup"><span data-stu-id="34bbe-125">Script Properties</span></span>

<span data-ttu-id="34bbe-126">スクリプト プロパティは、値が、スクリプトの出力のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-126">A script property defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="34bbe-127">次の例では、`VersionInfo`プロパティに追加されます、 [System.IO.Fileinfo でしょうか。Displayproperty = Fullname](/dotnet/api/System.IO.FileInfo)型。</span><span class="sxs-lookup"><span data-stu-id="34bbe-127">In the following example, the `VersionInfo` property is added to the [System.IO.Fileinfo?Displayproperty=Fullname](/dotnet/api/System.IO.FileInfo) type.</span></span> <span data-ttu-id="34bbe-128">[ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350)要素は、スクリプト プロパティとして、拡張プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-128">The [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350) element defines the extended property as a script property.</span></span> <span data-ttu-id="34bbe-129">[名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-129">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended property.</span></span> <span data-ttu-id="34bbe-130">また、 [GetScriptBlock](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c)要素は、プロパティの値を生成するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-130">And, the [GetScriptBlock](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c) element specifies the script that generates the property value.</span></span> <span data-ttu-id="34bbe-131">(追加することも、 [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。</span><span class="sxs-lookup"><span data-stu-id="34bbe-131">(You can also add the [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="property-sets"></a><span data-ttu-id="34bbe-132">プロパティ セット</span><span class="sxs-lookup"><span data-stu-id="34bbe-132">Property Sets</span></span>

<span data-ttu-id="34bbe-133">プロパティ セットは、セットの名前で参照可能な拡張プロパティのグループを定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-133">A property set defines a group of extended properties that can be referenced by the name of the set.</span></span> <span data-ttu-id="34bbe-134">たとえば、`Property`のパラメーター、 [Format-table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)コマンドレットは、特定のプロパティを表示する設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="34bbe-134">For example, the `Property` parameter of the [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table) cmdlet can specify a specific property set to be displayed.</span></span> <span data-ttu-id="34bbe-135">プロパティのセットを指定すると、セットに属しているプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34bbe-135">When a property set is specified, only those properties that belong to the set are displayed.</span></span>

<span data-ttu-id="34bbe-136">オブジェクトに定義できるプロパティのセットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="34bbe-136">There is no restriction on the number of property sets that can be defined for an object.</span></span> <span data-ttu-id="34bbe-137">ただし、PSStandardMembers メンバーのセット内でオブジェクトの既定の表示プロパティを定義するために使用するプロパティ セットを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34bbe-137">However, the property sets used to define the default display properties of an object must be specified within the PSStandardMembers member set.</span></span> <span data-ttu-id="34bbe-138">DefaultDisplayProperty、DefaultDisplayPropertySet、および DefaultKeyPropertySet、Types.ps1xml の種類のファイルの既定のプロパティ セット名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34bbe-138">In the Types.ps1xml types file, the default property set names include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="34bbe-139">PSStandardMembers メンバーのセットに追加するすべての追加のプロパティ セットは無視されます。</span><span class="sxs-lookup"><span data-stu-id="34bbe-139">Any additional property sets that you add to the PSStandardMembers member set are ignored.</span></span>

<span data-ttu-id="34bbe-140">次の例では、DefaultDisplayPropertySet プロパティ セットは、PSStandardMembers メンバーのセットに追加、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)型。</span><span class="sxs-lookup"><span data-stu-id="34bbe-140">In the following example, the DefaultDisplayPropertySet property set is added to the PSStandardMembers member set of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) type.</span></span> <span data-ttu-id="34bbe-141">[PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188)要素は、プロパティのグループを定義します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-141">The [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188) element defines the group of properties.</span></span> <span data-ttu-id="34bbe-142">[名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素がプロパティ セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-142">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the property set.</span></span> <span data-ttu-id="34bbe-143">また、 [ReferencedProperties](http://msdn.microsoft.com/en-us/5e620423-8679-4fbf-b6db-9f79288e4786)要素がセットのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="34bbe-143">And, the [ReferencedProperties](http://msdn.microsoft.com/en-us/5e620423-8679-4fbf-b6db-9f79288e4786) element specifies the properties of the set.</span></span> <span data-ttu-id="34bbe-144">(追加することも、 [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188)要素のメンバーに、[型](http://msdn.microsoft.com/en-us/e5dbd353-d6b2-40a1-92b6-6f1fea744ebe)要素です)。</span><span class="sxs-lookup"><span data-stu-id="34bbe-144">(You can also add the [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188) element to the members of the [Type](http://msdn.microsoft.com/en-us/e5dbd353-d6b2-40a1-92b6-6f1fea744ebe) element.)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="34bbe-145">参照</span><span class="sxs-lookup"><span data-stu-id="34bbe-145">See Also</span></span>

[<span data-ttu-id="34bbe-146">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="34bbe-146">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
