---
title: 項目プロバイダーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 606c880c-6cf1-4ea6-8730-dbf137bfabff
caps.latest.revision: 5
ms.openlocfilehash: e3289e9336b863b5e0998a2beb29353c82a31f79
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856708"
---
# <a name="writing-an-item-provider"></a><span data-ttu-id="d7763-102">アイテム プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="d7763-102">Writing an item provider</span></span>

<span data-ttu-id="d7763-103">このトピックでは、アクセスし、データ ストア内のアイテムを操作する Windows PowerShell プロバイダーのメソッドを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7763-103">This topic describes how to implement the methods of a Windows PowerShell provider that access and manipulate items in the data store.</span></span> <span data-ttu-id="d7763-104">項目にアクセスできるようにするには、プロバイダーがから派生する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。</span><span class="sxs-lookup"><span data-stu-id="d7763-104">To be able to access items, a provider must derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span>

<span data-ttu-id="d7763-105">このトピックの例ではプロバイダーでは、そのデータ ストアとして Access データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7763-105">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="d7763-106">いくつかのヘルパー メソッドと、データベースとの対話に使用されるクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="d7763-106">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="d7763-107">ヘルパー メソッドを含む完全なサンプルは、次を参照してください[AccessDBProviderSample03。](./accessdbprovidersample03.md)</span><span class="sxs-lookup"><span data-stu-id="d7763-107">For the complete sample that includes the helper methods, see [AccessDBProviderSample03](./accessdbprovidersample03.md)</span></span>

<span data-ttu-id="d7763-108">Windows PowerShell プロバイダーに関する詳細については、次を参照してください。 [Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="d7763-108">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-item-methods"></a><span data-ttu-id="d7763-109">項目のメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="d7763-109">Implementing item methods</span></span>

<span data-ttu-id="d7763-110">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスにアクセスして、データ ストア内の項目を操作するために使用できるいくつかのメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="d7763-110">The [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class exposes several methods that can be used to access and manipulate the items in a data store.</span></span> <span data-ttu-id="d7763-111">これらのメソッドの完全な一覧を参照してください。 [ItemCmdletProvider メソッド](http://msdn.microsoft.com/library/system.management.automation.provider.itemcmdletprovider_methods\(v=vs.85\).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="d7763-111">For a complete list of these methods, see [ItemCmdletProvider Methods](http://msdn.microsoft.com/library/system.management.automation.provider.itemcmdletprovider_methods\(v=vs.85\).aspx).</span></span> <span data-ttu-id="d7763-112">この例では、4 つのこれらのメソッドを実装しますが。</span><span class="sxs-lookup"><span data-stu-id="d7763-112">In this example, we will implement four of these methods.</span></span> <span data-ttu-id="d7763-113">[System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)指定したパスにある項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7763-113">[System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) gets an item at a specified path.</span></span> <span data-ttu-id="d7763-114">[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)指定した項目の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d7763-114">[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) sets the value of the specified item.</span></span> <span data-ttu-id="d7763-115">[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)指定されたパスに項目が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d7763-115">[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) checks whether an item exists at the specified path.</span></span> <span data-ttu-id="d7763-116">[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)かどうかに、データ ストア内の場所にマップを参照してください。 へのパスを確認します。</span><span class="sxs-lookup"><span data-stu-id="d7763-116">[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) checks a path to see if it maps to a location in the data store.</span></span>

> [!NOTE]
> <span data-ttu-id="d7763-117">このトピックでは、の情報に基づいて[Windows PowerShell プロバイダーのクイック スタート](./windows-powershell-provider-quickstart.md)します。</span><span class="sxs-lookup"><span data-stu-id="d7763-117">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="d7763-118">このトピックでは、プロバイダーのプロジェクトを設定する方法の基本については説明しませんまたはから継承されたメソッドを実装する方法、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスを作成し、ドライブを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7763-118">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="d7763-119">プロバイダー クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="d7763-119">Declaring the provider class</span></span>

<span data-ttu-id="d7763-120">派生するプロバイダーを宣言、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスし、で装飾、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span><span class="sxs-lookup"><span data-stu-id="d7763-120">Declare the provider to derive from the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a><span data-ttu-id="d7763-121">GetItem を実装します。</span><span class="sxs-lookup"><span data-stu-id="d7763-121">Implementing GetItem</span></span>

<span data-ttu-id="d7763-122">[System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)ユーザーを呼び出すときに、PowerShell エンジンによって呼び出される、 [Microsoft.Powershell.Commands.Get 項目](/dotnet/api/Microsoft.PowerShell.Commands.Get-Item)コマンドレット、プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="d7763-122">The [System.Management.Automation.Provider.Itemcmdletprovider.Getitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) is called by the PowerShell engine when a user calls the [Microsoft.Powershell.Commands.Get-Item](/dotnet/api/Microsoft.PowerShell.Commands.Get-Item) cmdlet on your provider.</span></span> <span data-ttu-id="d7763-123">メソッドは、指定されたパスにある項目を返します。</span><span class="sxs-lookup"><span data-stu-id="d7763-123">The method returns the item at the specified path.</span></span> <span data-ttu-id="d7763-124">Access データベースの例では、メソッドは、項目が、テーブル、データベースまたはデータベース内の行で、ドライブ自体、かどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="d7763-124">In the Access database example, the method checks whether the item is the drive itself, a table in the database, or a row in the database.</span></span> <span data-ttu-id="d7763-125">メソッドを呼び出してにアイテムを PowerShell エンジンに送信する、 [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d7763-125">The method sends the item to the PowerShell engine by calling the [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject) method.</span></span>

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

### <a name="implementing-setitem"></a><span data-ttu-id="d7763-126">SetItem を実装します。</span><span class="sxs-lookup"><span data-stu-id="d7763-126">Implementing SetItem</span></span>

<span data-ttu-id="d7763-127">[System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを呼び出す PowerShell エンジンの呼び出しによって呼び出されます、 [Microsoft.Powershell.Commands.Set 項目](/dotnet/api/Microsoft.PowerShell.Commands.Set-Item)コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="d7763-127">The [System.Management.Automation.Provider.Itemcmdletprovider.Setitem\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) method is called by the PowerShell engine calls when a user calls the [Microsoft.Powershell.Commands.Set-Item](/dotnet/api/Microsoft.PowerShell.Commands.Set-Item) cmdlet.</span></span> <span data-ttu-id="d7763-128">指定したパスにある項目の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d7763-128">It sets the value of the item at the specified path.</span></span>

<span data-ttu-id="d7763-129">アクセス データベースの例は、その項目には、行があるため、メソッドをスローする場合にのみ、項目の値を設定する[NotSupportedException](http://msdn.microsoft.com/library/system.notsupportedexception\(v=vs.110\).aspx)項目がない場合、行。</span><span class="sxs-lookup"><span data-stu-id="d7763-129">In the Access database example, it makes sense to set the value of an item only if that item is a row, so the method throws [NotSupportedException](http://msdn.microsoft.com/library/system.notsupportedexception\(v=vs.110\).aspx) when the item is not a row.</span></span>

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

### <a name="implementing-itemexists"></a><span data-ttu-id="d7763-130">ItemExists を実装します。</span><span class="sxs-lookup"><span data-stu-id="d7763-130">Implementing ItemExists</span></span>

<span data-ttu-id="d7763-131">[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドは、ユーザーを呼び出すと、PowerShell エンジンによって呼び出されます、 [Microsoft.Powershell.Commands.Test パス](/dotnet/api/Microsoft.PowerShell.Commands.Test-Path)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="d7763-131">The [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) method is called by the PowerShell engine when a user calls the [Microsoft.Powershell.Commands.Test-Path](/dotnet/api/Microsoft.PowerShell.Commands.Test-Path) cmdlet.</span></span> <span data-ttu-id="d7763-132">メソッドは、指定されたパスに項目があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d7763-132">The method determines whether there is an item at the specified path.</span></span> <span data-ttu-id="d7763-133">項目が存在する場合、メソッドは成功に PowerShell エンジンに呼び出して[System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)します。</span><span class="sxs-lookup"><span data-stu-id="d7763-133">If the item does exist, the method passes it back to the PowerShell engine by calling [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject\*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject).</span></span>

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

### <a name="implementing-isvalidpath"></a><span data-ttu-id="d7763-134">IsValidPath を実装します。</span><span class="sxs-lookup"><span data-stu-id="d7763-134">Implementing IsValidPath</span></span>

<span data-ttu-id="d7763-135">[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッドは、指定されたパスが現在のプロバイダーの構文が有効かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d7763-135">The [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) method checks whether the specified path is syntactically valid for the current provider.</span></span> <span data-ttu-id="d7763-136">パスにある項目が存在するかどうかはチェックしません。</span><span class="sxs-lookup"><span data-stu-id="d7763-136">It does not check whether an item exists at the path.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="d7763-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="d7763-137">Next steps</span></span>

<span data-ttu-id="d7763-138">ドライブ内の別の 1 つのパスから項目を移動して、他の項目を含む項目をサポートしているは一般的な現実世界のプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="d7763-138">A typical real-world provider is capable of supporting items that contain other items, and of moving items from one path to another within the drive.</span></span> <span data-ttu-id="d7763-139">コンテナーをサポートするプロバイダーの例は、次を参照してください。[コンテナー プロバイダーの書き込み](./writing-a-container-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="d7763-139">For an example of a provider that supports containers, see [Writing a container provider](./writing-a-container-provider.md).</span></span> <span data-ttu-id="d7763-140">項目の移動をサポートするプロバイダーの例は、次を参照してください。[ナビゲーション プロバイダーの記述](./writing-a-navigation-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="d7763-140">For an example of a provider that supports moving items, see [Writing a navigation provider](./writing-a-navigation-provider.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7763-141">参照</span><span class="sxs-lookup"><span data-stu-id="d7763-141">See Also</span></span>

[<span data-ttu-id="d7763-142">コンテナーのプロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="d7763-142">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="d7763-143">ナビゲーション プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="d7763-143">Writing a navigation provider</span></span>](./writing-a-navigation-provider.md)

[<span data-ttu-id="d7763-144">Windows PowerShell プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="d7763-144">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)