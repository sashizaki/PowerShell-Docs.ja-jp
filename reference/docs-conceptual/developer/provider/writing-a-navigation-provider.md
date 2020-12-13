---
ms.date: 09/13/2016
ms.topic: reference
title: ナビゲーション プロバイダーを記述する
description: ナビゲーション プロバイダーを記述する
ms.openlocfilehash: 3123672d3365c97714557bd0e72a6e444ac228a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355223"
---
# <a name="writing-a-navigation-provider"></a><span data-ttu-id="b6e3d-103">ナビゲーション プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="b6e3d-103">Writing a navigation provider</span></span>

<span data-ttu-id="b6e3d-104">このトピックでは、入れ子になったコンテナー (複数レベルのデータストア)、項目の移動、および相対パスをサポートする Windows PowerShell プロバイダーのメソッドを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-104">This topic describes how to implement the methods of a Windows PowerShell provider that support nested containers (multi-level data stores), moving items, and relative paths.</span></span> <span data-ttu-id="b6e3d-105">ナビゲーションプロバイダーは、 [system.servicemodel クラスから](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 派生させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-105">A navigation provider must derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

<span data-ttu-id="b6e3d-106">このトピックの例のプロバイダーでは、データストアとして Access データベースを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-106">The provider in the examples in this topic uses an Access database as its data store.</span></span> <span data-ttu-id="b6e3d-107">データベースとの対話に使用されるヘルパーメソッドとクラスはいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-107">There are several helper methods and classes that are used to interact with the database.</span></span> <span data-ttu-id="b6e3d-108">ヘルパーメソッドを含む完全なサンプルについては、「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-108">For the complete sample that includes the helper methods, see [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>

<span data-ttu-id="b6e3d-109">Windows PowerShell プロバイダーの詳細については、「 [Windows Powershell プロバイダーの概要](./windows-powershell-provider-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-109">For more information about Windows PowerShell providers, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span>

## <a name="implementing-navigation-methods"></a><span data-ttu-id="b6e3d-110">ナビゲーションメソッドの実装</span><span class="sxs-lookup"><span data-stu-id="b6e3d-110">Implementing navigation methods</span></span>

<span data-ttu-id="b6e3d-111">System.servicemodel [クラスは、入れ子](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) になったコンテナー、相対パス、および項目の移動をサポートするメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-111">The [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class implements methods that support nested containers, relative paths, and moving items.</span></span> <span data-ttu-id="b6e3d-112">これらのメソッドの完全な一覧については、「 [navigation[プロバイダーメソッド](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods)]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-112">For a complete list of these methods, see [NavigationCmdletProvider Methods](/dotnet/api/system.management.automation.provider.navigationcmdletprovider#methods).</span></span>

> [!NOTE]
> <span data-ttu-id="b6e3d-113">このトピックは、「 [Windows PowerShell プロバイダーのクイックスタート](./windows-powershell-provider-quickstart.md)」の情報に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-113">This topic builds on the information in [Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md).</span></span> <span data-ttu-id="b6e3d-114">このトピックでは、プロバイダープロジェクトを設定する方法の基本については説明しません。また、ドライブを作成または削除する [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) クラスから継承されたメソッドを実装する方法についても説明しません。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-114">This topic does not cover the basics of how to set up a provider project, or how to implement the methods inherited from the [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) class that create and remove drives.</span></span> <span data-ttu-id="b6e3d-115">また、このトピックでは、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスまたはクラスによって公開されるメソッドを実装する方法につい[ては説明](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)しません。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-115">This topic also does not cover how to implement methods exposed by the [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) or [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) classes.</span></span> <span data-ttu-id="b6e3d-116">項目のコマンドレットを実装する方法を示す例については、「 [項目プロバイダーを作成](./writing-an-item-provider.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-116">For an example that shows how to implement item cmdlets, see [Writing an item provider](./writing-an-item-provider.md).</span></span> <span data-ttu-id="b6e3d-117">コンテナーのコマンドレットを実装する方法を示す例については、「 [コンテナープロバイダーの作成](./writing-a-container-provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-117">For an example that shows how to implement container cmdlets, see [Writing a container provider](./writing-a-container-provider.md).</span></span>

### <a name="declaring-the-provider-class"></a><span data-ttu-id="b6e3d-118">プロバイダークラスの宣言</span><span class="sxs-lookup"><span data-stu-id="b6e3d-118">Declaring the provider class</span></span>

<span data-ttu-id="b6e3d-119">プロバイダーを宣言し [て、system.servicemodel クラスから](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 派生させ、それを system.string [属性](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)で装飾します。このクラスは、このクラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-119">Declare the provider to derive from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class, and decorate it with the [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).</span></span>

```
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : NavigationCmdletProvider
   {

   }
```

### <a name="implementing-isitemcontainer"></a><span data-ttu-id="b6e3d-120">IsItemContainer の実装</span><span class="sxs-lookup"><span data-stu-id="b6e3d-120">Implementing IsItemContainer</span></span>

<span data-ttu-id="b6e3d-121">[Isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)メソッドは、指定されたパスの項目がコンテナーであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-121">The [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method checks whether the item at the specified path is a container.</span></span>

```csharp
protected override bool IsItemContainer(string path)
      {
         if (PathIsDrive(path))
         {
             return true;
         }

         string[] pathChunks = ChunkPath(path);
         string tableName;
         int rowNumber;

         PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

         if (type == PathType.Table)
         {
            foreach (DatabaseTableInfo ti in GetTables())
            {
                if (string.Equals(ti.Name, tableName, StringComparison.OrdinalIgnoreCase))
                {
                    return true;
                }
            } // foreach (DatabaseTableInfo...
         } // if (pathChunks...

         return false;
      }
```

### <a name="implementing-getchildname"></a><span data-ttu-id="b6e3d-122">GetChildName の実装</span><span class="sxs-lookup"><span data-stu-id="b6e3d-122">Implementing GetChildName</span></span>

<span data-ttu-id="b6e3d-123">このメソッドは、指定されたパスにある子項目の name プロパティを取得します。 [Getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) メソッド。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-123">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method gets the name property of the child item at the specified path.</span></span> <span data-ttu-id="b6e3d-124">指定したパスにある項目がコンテナーの子でない場合、このメソッドはパスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-124">If the item at the specified path is not a child of a container, then this method should return the path.</span></span>

```csharp
protected override string GetChildName(string path)
       {
           if (PathIsDrive(path))
           {
               return path;
           }

           string tableName;
           int rowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           if (type == PathType.Table)
           {
               return tableName;
           }
           else if (type == PathType.Row)
           {
               return rowNumber.ToString(CultureInfo.CurrentCulture);
           }
           else
           {
               ThrowTerminatingInvalidPathException(path);
           }

           return null;
       }
```

### <a name="implementing-getparentpath"></a><span data-ttu-id="b6e3d-125">GetParentPath の実装</span><span class="sxs-lookup"><span data-stu-id="b6e3d-125">Implementing GetParentPath</span></span>

<span data-ttu-id="b6e3d-126">[Getparentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドは、指定したパスにある項目の親のパスを取得します。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="b6e3d-126">The [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method gets the path of the parent of the item at the specified path.</span></span> <span data-ttu-id="b6e3d-127">指定されたパスにある項目がデータストアのルートである (親がない) 場合、このメソッドはルートパスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-127">If the item at the specified path is the root of the data store (so it has no parent), then this method should return the root path.</span></span>

```csharp
protected override string GetParentPath(string path, string root)
       {
           // If root is specified then the path has to contain
           // the root. If not nothing should be returned
           if (!String.IsNullOrEmpty(root))
           {
               if (!path.Contains(root))
               {
                   return null;
               }
           }

           return path.Substring(0, path.LastIndexOf(pathSeparator, StringComparison.OrdinalIgnoreCase));
       }
```

### <a name="implementing-makepath"></a><span data-ttu-id="b6e3d-128">MakePath の実装</span><span class="sxs-lookup"><span data-stu-id="b6e3d-128">Implementing MakePath</span></span>

<span data-ttu-id="b6e3d-129">指定された親パスと指定された子パスを結合してプロバイダー内部パスを作成 [します (](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) プロバイダーがサポートできるパスの種類の詳細については、「 [Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-129">The [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method joins a specified parent path and a specified child path to create a provider-internal path (for information about path types that providers can support, see [Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md).</span></span> <span data-ttu-id="b6e3d-130">PowerShell エンジンは、ユーザーが次の [コマンドレットを](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) 呼び出すと、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-130">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.JoinPathCommand](/dotnet/api/Microsoft.PowerShell.Commands.joinpathcommand) cmdlet.</span></span>

```csharp
protected override string MakePath(string parent, string child)
       {
           string result;

           string normalParent = NormalizePath(parent);
           normalParent = RemoveDriveFromPath(normalParent);
           string normalChild = NormalizePath(child);
           normalChild = RemoveDriveFromPath(normalChild);

           if (String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               result = String.Empty;
           }
           else if (String.IsNullOrEmpty(normalParent) && !String.IsNullOrEmpty(normalChild))
           {
               result = normalChild;
           }
           else if (!String.IsNullOrEmpty(normalParent) && String.IsNullOrEmpty(normalChild))
           {
               if (normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent;
               }
               else
               {
                   result = normalParent + pathSeparator;
               }
           } // else if (!String...
           else
           {
               if (!normalParent.Equals(String.Empty) &&
                   !normalParent.EndsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result = normalParent + pathSeparator;
               }
               else
               {
                   result = normalParent;
               }

               if (normalChild.StartsWith(pathSeparator, StringComparison.OrdinalIgnoreCase))
               {
                   result += normalChild.Substring(1);
               }
               else
               {
                   result += normalChild;
               }
           } // else

           return result;
       }
```

### <a name="implementing-normalizerelativepath"></a><span data-ttu-id="b6e3d-131">NormalizeRelativePath の実装</span><span class="sxs-lookup"><span data-stu-id="b6e3d-131">Implementing NormalizeRelativePath</span></span>

<span data-ttu-id="b6e3d-132">[Normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)メソッドは、パラメーターとパラメーターを受け取り、パラメーター `path` `basepath` と等価で `path` あり、パラメーターに対して相対的な正規化されたパスを返し `basepath` ます。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-132">The [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method takes `path` and `basepath` parameters, and returns a normalized path that is equivalent to the `path` parameter and relative to the `basepath` parameter.</span></span>

```csharp
protected override string NormalizeRelativePath(string path,
                                                            string basepath)
       {
           // Normalize the paths first
           string normalPath = NormalizePath(path);
           normalPath = RemoveDriveFromPath(normalPath);
           string normalBasePath = NormalizePath(basepath);
           normalBasePath = RemoveDriveFromPath(normalBasePath);

           if (String.IsNullOrEmpty(normalBasePath))
           {
               return normalPath;
           }
           else
           {
               if (!normalPath.Contains(normalBasePath))
               {
                   return null;
               }

               return normalPath.Substring(normalBasePath.Length + pathSeparator.Length);
           }
       }
```

### <a name="implementing-moveitem"></a><span data-ttu-id="b6e3d-133">MoveItem の実装</span><span class="sxs-lookup"><span data-stu-id="b6e3d-133">Implementing MoveItem</span></span>

<span data-ttu-id="b6e3d-134">この [メソッドは](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) 、指定されたパスから指定されたコピー先のパスに項目を移動します。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-134">The [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method moves an item from the specified path to the specified destination path.</span></span> <span data-ttu-id="b6e3d-135">PowerShell エンジンは、ユーザーが [コマンド](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) レットを呼び出したときに、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b6e3d-135">The PowerShell engine calls this method when a user calls the [Microsoft.PowerShell.Commands.MoveItemCommand](/dotnet/api/Microsoft.PowerShell.Commands.moveitemcommand) cmdlet.</span></span>

```csharp
protected override void MoveItem(string path, string destination)
       {
           // Get type, table name and rowNumber from the path
           string tableName, destTableName;
           int rowNumber, destRowNumber;

           PathType type = GetNamesFromPath(path, out tableName, out rowNumber);

           PathType destType = GetNamesFromPath(destination, out destTableName,
                                    out destRowNumber);

           if (type == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(path);
           }

           if (destType == PathType.Invalid)
           {
               ThrowTerminatingInvalidPathException(destination);
           }

           if (type == PathType.Table)
           {
               ArgumentException e = new ArgumentException("Move not supported for tables");

               WriteError(new ErrorRecord(e, "MoveNotSupported",
                   ErrorCategory.InvalidArgument, path));

               throw e;
           }
           else
           {
               OdbcDataAdapter da = GetAdapterForTable(tableName);
               if (da == null)
               {
                   return;
               }

               DataSet ds = GetDataSetForTable(da, tableName);
               DataTable table = GetDataTable(ds, tableName);

               OdbcDataAdapter dda = GetAdapterForTable(destTableName);
               if (dda == null)
               {
                   return;
               }

               DataSet dds = GetDataSetForTable(dda, destTableName);
               DataTable destTable = GetDataTable(dds, destTableName);
               DataRow row = table.Rows[rowNumber];

               if (destType == PathType.Table)
               {
                   DataRow destRow = destTable.NewRow();

                   destRow.ItemArray = row.ItemArray;
               }
               else
               {
                   DataRow destRow = destTable.Rows[destRowNumber];

                   destRow.ItemArray = row.ItemArray;
               }

               // Update the changes
               if (ShouldProcess(path, "MoveItem"))
               {
                   WriteItemObject(row, path, false);
                   dda.Update(dds, destTableName);
               }
           }
       }
```

## <a name="see-also"></a><span data-ttu-id="b6e3d-136">参照</span><span class="sxs-lookup"><span data-stu-id="b6e3d-136">See Also</span></span>

[<span data-ttu-id="b6e3d-137">コンテナー プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="b6e3d-137">Writing a container provider</span></span>](./writing-a-container-provider.md)

[<span data-ttu-id="b6e3d-138">Windows PowerShell プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="b6e3d-138">Windows PowerShell Provider Overview</span></span>](./windows-powershell-provider-overview.md)
