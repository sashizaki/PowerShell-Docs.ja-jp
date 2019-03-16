---
title: ナビゲーション プロバイダーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98bcfda0-6ee2-46f5-bbc7-5fab8b780d6a
caps.latest.revision: 5
ms.openlocfilehash: f449c17e4c373c42f8a1d96fa9075940111c65bc
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056594"
---
# <a name="writing-a-navigation-provider"></a>ナビゲーション プロバイダーを記述する

このトピックでは、入れ子になったコンテナー (複数レベルのデータ ストア)、項目、および相対パスの移動をサポートする Windows PowerShell プロバイダーのメソッドを実装する方法について説明します。 ナビゲーション プロバイダーがから派生する必要があります、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。

このトピックの例ではプロバイダーでは、そのデータ ストアとして Access データベースを使用します。 いくつかのヘルパー メソッドと、データベースとの対話に使用されるクラスがあります。 ヘルパー メソッドを含む完全なサンプルは、次を参照してください。 [AccessDBProviderSample05](./accessdbprovidersample05.md)します。

Windows PowerShell プロバイダーに関する詳細については、次を参照してください。 [Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)します。

## <a name="implementing-navigation-methods"></a>ナビゲーション メソッドを実装します。

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスが入れ子になったコンテナー、相対パスは、アイテムの移動をサポートするメソッドを実装します。 これらのメソッドの完全な一覧を参照してください。 [NavigationCmdletProvider メソッド](http://msdn.microsoft.com/library/system.management.automation.provider.navigationcmdletprovider_methods\(v=vs.85\).aspx)します。

> [!NOTE]
> このトピックでは、の情報に基づいて[Windows PowerShell プロバイダーのクイック スタート](./windows-powershell-provider-quickstart.md)します。 このトピックでは、プロバイダーのプロジェクトを設定する方法の基本については説明しませんまたはから継承されたメソッドを実装する方法、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスを作成し、ドライブを削除します。 このトピックの「によって公開されるメソッドを実装する方法については説明しませんも、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)または[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。 Item コマンドレットを実装する方法を示しますたとえば、次を参照してください。[項目プロバイダーの作成](./writing-an-item-provider.md)です。 コンテナーのコマンドレットを実装する方法を示しますたとえば、次を参照してください。[コンテナー プロバイダーの書き込み](./writing-a-container-provider.md)します。

### <a name="declaring-the-provider-class"></a>プロバイダー クラスを宣言します。

派生するプロバイダーを宣言、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスし、で装飾、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).

```
[CmdletProvider("AccessDB", ProviderCapabilities.None)]
   public class AccessDBProvider : NavigationCmdletProvider
   {

   }
```

### <a name="implementing-isitemcontainer"></a>IsItemContainer を実装します。

[System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)メソッドは、指定されたパスにある項目がコンテナーでかどうかを確認します。

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

### <a name="implementing-getchildname"></a>GetChildName を実装します。

[System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)メソッドは、指定されたパスに子項目の name プロパティを取得します。 場合は、指定されたパスにある項目は、コンテナーの子ではない、このメソッドは、パスを返します。

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

### <a name="implementing-getparentpath"></a>GetParentPath を実装します。

[System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドは、指定したパスにある項目の親のパスを取得します。 指定されたパスにある項目がデータ ストア (したがって、親を持たない) のルートである場合は、このメソッドは、ルート パスを返す必要があります。

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

### <a name="implementing-makepath"></a>MakePath を実装します。

[System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッドは、指定された親パスと (するパスに関する情報の種類のプロバイダーの内部パスを作成する指定された子パスを結合プロバイダーがサポートを参照してください[Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)します。 PowerShell エンジンは、ユーザーが呼び出すときにこのメソッドを呼び出して、 [Microsoft.PowerShell.Commands.Join パス](/dotnet/api/Microsoft.PowerShell.Commands.Join-Path)コマンドレット。

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

### <a name="implementing-normalizerelativepath"></a>NormalizeRelativePath を実装します。

[System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)メソッドは`path`と`basepath`パラメーター、に相当する正規化されたパスを返します`path`パラメーターとする相対パス、`basepath`パラメーター。

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

### <a name="implementing-moveitem"></a>MoveItem を実装します。

[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッドは、指定された宛先パスに指定されたパスから項目を移動します。 PowerShell エンジンは、ユーザーが呼び出すときにこのメソッドを呼び出して、 [Microsoft.PowerShell.Commands.Move 項目](/dotnet/api/Microsoft.PowerShell.Commands.Move-Item)コマンドレット。

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

## <a name="see-also"></a>参照

[コンテナーのプロバイダーの作成](./writing-a-container-provider.md)

[Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)