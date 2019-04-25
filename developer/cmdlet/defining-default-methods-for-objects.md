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
ms.openlocfilehash: fa0f0371856d8723af7ec17a4306de209a481a18
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068217"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="1ed09-102">オブジェクトの既定のメソッドを定義する</span><span class="sxs-lookup"><span data-stu-id="1ed09-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="1ed09-103">.NET Framework オブジェクトを拡張するときに、オブジェクトをコード メソッドおよびスクリプト メソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1ed09-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span> <span data-ttu-id="1ed09-104">これらのメソッドを定義するために使用される XML は次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed09-105">セクションでは、次の例は、Windows PowerShell のインストール ディレクトリに Types.ps1xml 型ファイル (`$pshome`)。</span><span class="sxs-lookup"><span data-stu-id="1ed09-105">The examples in the following sections are from the Types.ps1xml types file in the Windows PowerShell installation directory (`$pshome`).</span></span>

## <a name="code-methods"></a><span data-ttu-id="1ed09-106">コード メソッド</span><span class="sxs-lookup"><span data-stu-id="1ed09-106">Code Methods</span></span>

<span data-ttu-id="1ed09-107">コードのメソッドは、.NET Framework オブジェクトの静的メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-107">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="1ed09-108">次の例では、 **ConvertLargeIntegerToInt64**メソッドに追加されます、 [System.Xml.Xmlnode でしょうか。Displayproperty = Fullname](/dotnet/api/System.Xml.XmlNode)型。</span><span class="sxs-lookup"><span data-stu-id="1ed09-108">In the following example, the **ConvertLargeIntegerToInt64** method is added to the [System.Xml.Xmlnode?Displayproperty=Fullname](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="1ed09-109">[CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05)要素は、コードの方法として、拡張メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-109">The [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) element defines the extended method as a code method.</span></span> <span data-ttu-id="1ed09-110">[名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-110">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended method.</span></span> <span data-ttu-id="1ed09-111">また、 [CodeReference](http://msdn.microsoft.com/en-us/70017b85-18d2-4f55-8357-92f309d5618b)要素は、静的メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-111">And, the [CodeReference](http://msdn.microsoft.com/en-us/70017b85-18d2-4f55-8357-92f309d5618b) element specifies the static method.</span></span> <span data-ttu-id="1ed09-112">(追加することも、 [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。</span><span class="sxs-lookup"><span data-stu-id="1ed09-112">(You can also add the [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="script-methods"></a><span data-ttu-id="1ed09-113">スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="1ed09-113">Script Methods</span></span>

<span data-ttu-id="1ed09-114">スクリプト メソッドでは、値が、スクリプトの出力メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-114">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="1ed09-115">次の例では、 **ConvertToDateTime**メソッドに追加されます、 [System.Management.Managementobject でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.ManagementObject)型。</span><span class="sxs-lookup"><span data-stu-id="1ed09-115">In the following example, the **ConvertToDateTime** method is added to the [System.Management.Managementobject?Displayproperty=Fullname](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="1ed09-116">[ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c)要素は、スクリプト メソッドとして、拡張メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-116">The [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) element defines the extended method as a script method.</span></span> <span data-ttu-id="1ed09-117">[名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張メソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-117">The [Name](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873) element specifies the name of the extended method.</span></span> <span data-ttu-id="1ed09-118">また、[スクリプト](http://msdn.microsoft.com/en-us/1937ad1b-bb2b-4512-9864-01fc0767d46f)要素は、メソッドの値を生成するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ed09-118">And, the [Script](http://msdn.microsoft.com/en-us/1937ad1b-bb2b-4512-9864-01fc0767d46f) element specifies the script that generates the method value.</span></span> <span data-ttu-id="1ed09-119">(追加することも、 [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。</span><span class="sxs-lookup"><span data-stu-id="1ed09-119">(You can also add the [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c) element to the members of the [MemberSets](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3) element.)</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1ed09-120">参照</span><span class="sxs-lookup"><span data-stu-id="1ed09-120">See Also</span></span>

[<span data-ttu-id="1ed09-121">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="1ed09-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)