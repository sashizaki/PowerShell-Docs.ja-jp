---
ms.date: 09/13/2016
ms.topic: reference
title: アイテム プロバイダーを記述する
description: アイテム プロバイダーを記述する
ms.openlocfilehash: f70c6ee50277988c4e3b7c255dc4548bc30319dd
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355206"
---
# <a name="writing-an-item-provider"></a><span data-ttu-id="1fd5d-103">アイテム プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="1fd5d-103">Writing an item provider</span></span>

<span data-ttu-id="1fd5d-104">このトピックでは、データストア内の項目にアクセスして操作する Windows PowerShell プロバイダーのメソッドを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-104">This topic describes how to implement the methods of a Windows PowerShell provider that access and manipulate items in the data store.</span></span> <span data-ttu-id="1fd5d-105">項目にアクセスできるようにするには、プロバイダーを、 [システムの管理](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) プロバイダークラスから派生させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-105">To be able to access items, a provider must derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

<span data-ttu-id="1fd5d-106">このトピックの例のプロバイダーでは、データストアとして Access データベースを使用しています。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-106">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="1fd5d-107">データベースとの対話に使用されるヘルパーメソッドとクラスはいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-107">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="1fd5d-108">ヘルパーメソッドを含む完全なサンプルについては、「 [AccessDBProviderSample03](./accessdbprovidersample03.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-108">For the complete sample that includes the helper methods, see [AccessDBProviderSample03](./accessdbprovidersample03.md)</span></span>

<span data-ttu-id="1fd5d-109">Windows PowerShell プロバイダーの詳細については、「 [Windows Powershell プロバイダーの概要](./windows-powershell-provider-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-109">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-item-methods"></a><span data-ttu-id="1fd5d-110">項目メソッドの実装</span><span class="sxs-lookup"><span data-stu-id="1fd5d-110">Implementing item methods</span></span>

<span data-ttu-id="1fd5d-111">System.string [クラスは](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) 、データストア内の項目にアクセスして操作するために使用できるいくつかのメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-111">The [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class exposes several methods that can be used to access and manipulate the items in a data store.</span></span>
<span data-ttu-id="1fd5d-112">これらのメソッドの完全な一覧については、「 [itemの表示プロバイダーのメソッド](/dotnet/api/system.management.automation.provider.itemcmdletprovider#methods)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-112">For a complete list of these methods, see [ItemCmdletProvider Methods](/dotnet/api/system.management.automation.provider.itemcmdletprovider#methods).</span></span>
<span data-ttu-id="1fd5d-113">この例では、これらの4つのメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-113">In this example, we will implement four of these methods.</span></span>
<span data-ttu-id="1fd5d-114">System.string。指定されたパスの項目[を取得し](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)ます。...</span><span class="sxs-lookup"><span data-stu-id="1fd5d-114">[System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) gets an item at a specified path.</span></span>
<span data-ttu-id="1fd5d-115">[Setitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) は、指定された項目の値を設定しています。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-115">[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) sets the value of the specified item.</span></span>
<span data-ttu-id="1fd5d-116">System.object は、指定されたパスに項目が存在するかどうか[を確認します。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)</span><span class="sxs-lookup"><span data-stu-id="1fd5d-116">[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) checks whether an item exists at the specified path.</span></span>
<span data-ttu-id="1fd5d-117">System.string は、データストア内の場所にマップされているかどうかを確認するためのパス[を確認します。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)</span><span class="sxs-lookup"><span data-stu-id="1fd5d-117">[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) checks a path to see if it maps to a location in the data store.</span></span>

> [!NOTE]
> <span data-ttu-id="1fd5d-118">このトピックは、「 [Windows PowerShell プロバイダーのクイックスタート](./windows-powershell-provider-quickstart.md)」の情報に基づいています。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-118">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="1fd5d-119">このトピックでは、プロバイダープロジェクトを設定する方法の基本については説明しません。また、ドライブを作成または削除する [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) クラスから継承されたメソッドを実装する方法についても説明しません。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-119">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="1fd5d-120">プロバイダークラスの宣言</span><span class="sxs-lookup"><span data-stu-id="1fd5d-120">Declaring the provider class</span></span>

<span data-ttu-id="1fd5d-121">プロバイダーを宣言して、system.servicemodel [プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) クラスから派生させ、そのプロバイダーを system.string [属性](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)で装飾します。このクラスを宣言してください。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-121">Declare the provider to derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a><span data-ttu-id="1fd5d-122">GetItem の実装</span><span class="sxs-lookup"><span data-stu-id="1fd5d-122">Implementing GetItem</span></span>

<span data-ttu-id="1fd5d-123">ユーザーがプロバイダーで[GetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand)コマンドレットを呼び出したときに、PowerShell エンジンによって呼び出された場合は、" [System.](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) ......................................。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-123">The [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.GetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.getitemcommand) cmdlet on your provider.</span></span> <span data-ttu-id="1fd5d-124">メソッドは、指定されたパスにある項目を返します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-124">The method returns the item at the specified path.</span></span> <span data-ttu-id="1fd5d-125">Access データベースの例では、メソッドは、アイテムがドライブ自体であるか、データベース内のテーブルであるか、またはデータベース内の行であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-125">In the Access database example, the method checks whether the item is the drive itself, a table in the database, or a row in the database.</span></span> <span data-ttu-id="1fd5d-126">メソッドは、 [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) ...........................................。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-126">The method sends the item to the PowerShell engine by calling the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method.</span></span>

```csharp
protected override void GetItem(string path)
      {
          // check if the path represented is a drive
          if (PathIsDrive(path))
          {
              WriteItemObject(this.PSDriveInfo, path, true);
              return;
          }// if (PathIsDrive...

           // Get table name and row information from the path and do
           // necessary actions
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               DatabaseTableInfo table = GetTable(tableName);
               WriteItemObject(table, path, true);
           }
           else if (type == PathType.Row)
           {
               DatabaseRowInfo row = GetRow(tableName, rowNumber);
               WriteItemObject(row, path, false);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

       }
```

### <a name="implementing-setitem"></a><span data-ttu-id="1fd5d-127">SetItem の実装</span><span class="sxs-lookup"><span data-stu-id="1fd5d-127">Implementing SetItem</span></span>

<span data-ttu-id="1fd5d-128">[Setitem \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドは、ユーザーが SetItemCommand コマンドレットを呼び出したときに、powershell エンジンによって呼び出されます。このメソッドは、ユーザーが[](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand)コマンドレットを呼び出したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-128">The [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method is called by the PowerShell engine calls when a user calls the [Microsoft.PowerShell.Commands.SetItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.setitemcommand) cmdlet.</span></span> <span data-ttu-id="1fd5d-129">このメソッドは、指定されたパスにある項目の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-129">It sets the value of the item at the specified path.</span></span>

<span data-ttu-id="1fd5d-130">Access データベースの例では、項目が行である場合にのみ項目の値を設定することが理にかなっています。そのため、項目が行でない場合、メソッドは [NotSupportedException](/dotnet/api/system.notsupportedexception) をスローします。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-130">In the Access database example, it makes sense to set the value of an item only if that item is a row, so the method throws [NotSupportedException](/dotnet/api/system.notsupportedexception) when the item is not a row.</span></span>

```csharp
protected override void SetItem(string path, object values)
       {
           // Get type, table name and row number from the path specified
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type != PathType.Row)
           {
               WriteError(new ErrorRecord(new NotSupportedException(
                     "SetNotSupported"), "",
                  ErrorCategory.InvalidOperation, path));

               return;
           }

           // Get in-memory representation of table
           OdbcDataAdapter da = GetAdapterForTable(tableName);

           if (da == null)
           {
               return;
           }
           DataSet ds = GetDataSetForTable(da, tableName);
           DataTable table = GetDataTable(ds, tableName);

           if (rowNumber >= table.Rows.Count)
           {
               // The specified row number has to be available. If not
               // NewItem has to be used to add a new row
               throw new ArgumentException("Row specified is not available");
           } // if (rowNum...

           string[] colValues = (values as string).Split(',');

           // set the specified row
           DataRow row = table.Rows[rowNumber];

           for (int i = 0; i < colValues.Length; i++)
           {
               row[i] = colValues[i];
           }

           // Update the table
           if (ShouldProcess(path, "SetItem"))
           {
               da.Update(ds, tableName);
           }

       }
```

### <a name="implementing-itemexists"></a><span data-ttu-id="1fd5d-131">ItemExists の実装</span><span class="sxs-lookup"><span data-stu-id="1fd5d-131">Implementing ItemExists</span></span>

<span data-ttu-id="1fd5d-132">ユーザーが[Microsoft. PowerShell. TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand)コマンドレットを呼び出したときに、powershell エンジンによって呼び出された場合は、[このメソッドが呼び出されます。](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)</span><span class="sxs-lookup"><span data-stu-id="1fd5d-132">The [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method is called by the PowerShell engine when a user calls the [Microsoft.PowerShell.Commands.TestPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.Testpathcommand) cmdlet.</span></span> <span data-ttu-id="1fd5d-133">メソッドは、指定されたパスに項目があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-133">The method determines whether there is an item at the specified path.</span></span> <span data-ttu-id="1fd5d-134">項目が存在する場合、メソッドは、その項目を PowerShell エンジンに渡します [。これ](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)を行うには、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-134">If the item does exist, the method passes it back to the PowerShell engine by calling [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).</span></span>

```csharp
protected override bool ItemExists(string path)
       {
           // check if the path represented is a drive
           if (PathIsDrive(path))
           {
               return true;
           }

           // Obtain type, table name and row number from path
           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           DatabaseTableInfo table = GetTable(tableName);

           if (type == PathType.Table)
           {
               // if specified path represents a table then DatabaseTableInfo
               // object for the same should exist
               if (table != null)
               {
                   return true;
               }
           }
           else if (type == PathType.Row)
           {
               // if specified path represents a row then DatabaseTableInfo should
               // exist for the table and then specified row number must be within
               // the maximum row count in the table
               if (table != null && rowNumber < table.RowCount)
               {
                   return true;
               }
           }

           return false;

       }
```

### <a name="implementing-isvalidpath"></a><span data-ttu-id="1fd5d-135">IsValidPath の実装</span><span class="sxs-lookup"><span data-stu-id="1fd5d-135">Implementing IsValidPath</span></span>

<span data-ttu-id="1fd5d-136">この [メソッドは](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) 、指定されたパスが現在のプロバイダーに対して構文的に有効かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-136">The [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method checks whether the specified path is syntactically valid for the current provider.</span></span> <span data-ttu-id="1fd5d-137">項目がパスに存在するかどうかは確認されません。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-137">It does not check whether an item exists at the path.</span></span>

```csharp
protected override bool IsValidPath(string path)
       {
           bool result = true;

           // check if the path is null or empty
           if (String.IsNullOrEmpty(path))
           {
               result = false;
           }

           // convert all separators in the path to a uniform one
           path = NormalizePath(path);

           // split the path into individual chunks
           string[] pathChunks = path.Split(pathSeparator.ToCharArray());

           foreach (string pathChunk in pathChunks)
           {
               if (pathChunk.Length == 0)
               {
                   result = false;
               }
           }
           return result;
       }
```

## <a name="next-steps"></a><span data-ttu-id="1fd5d-138">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1fd5d-138">Next steps</span></span>

<span data-ttu-id="1fd5d-139">典型的な現実世界のプロバイダーは、他の項目を含む項目をサポートしたり、ドライブ内のあるパスから別のパスに項目を移動したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-139">A typical real-world provider is capable of supporting items that contain other items, and of moving items from one path to another within the drive.</span></span> <span data-ttu-id="1fd5d-140">コンテナーをサポートするプロバイダーの例については、「 [コンテナープロバイダーの作成](./writing-a-container-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-140">For an example of a provider that supports containers, see [Writing a container provider](./writing-a-container-provider.md).</span></span> <span data-ttu-id="1fd5d-141">項目の移動をサポートするプロバイダーの例については、「 [ナビゲーションプロバイダーの作成](./writing-a-navigation-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fd5d-141">For an example of a provider that supports moving items, see [Writing a navigation provider](./writing-a-navigation-provider.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1fd5d-142">参照</span><span class="sxs-lookup"><span data-stu-id="1fd5d-142">See Also</span></span>

[<span data-ttu-id="1fd5d-143">コンテナー プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="1fd5d-143">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="1fd5d-144">ナビゲーション プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="1fd5d-144">Writing a navigation provider</span></span>](./writing-a-navigation-provider.md)

[<span data-ttu-id="1fd5d-145">Windows PowerShell プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="1fd5d-145">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
