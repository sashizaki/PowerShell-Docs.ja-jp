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
ms.openlocfilehash: 9285a2f0e673de8b86084157423512bdeeda109d
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058193"
---
# <a name="writing-an-item-provider"></a>アイテム プロバイダーを記述する

このトピックでは、アクセスし、データ ストア内のアイテムを操作する Windows PowerShell プロバイダーのメソッドを実装する方法について説明します。 項目にアクセスできるようにするには、プロバイダーがから派生する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。

このトピックの例ではプロバイダーでは、そのデータ ストアとして Access データベースを使用します。 いくつかのヘルパー メソッドと、データベースとの対話に使用されるクラスがあります。 ヘルパー メソッドを含む完全なサンプルは、次を参照してください[AccessDBProviderSample03。](./accessdbprovidersample03.md)

Windows PowerShell プロバイダーに関する詳細については、[Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)を参照してください。

## <a name="implementing-item-methods"></a>項目のメソッドを実装します。

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスにアクセスして、データ ストア内の項目を操作するために使用できるいくつかのメソッドを公開します。 これらのメソッドの完全な一覧を参照してください。 [ItemCmdletProvider メソッド](http://msdn.microsoft.com/library/system.management.automation.provider.itemcmdletprovider_methods\(v=vs.85\).aspx)します。 この例では、4 つのこれらのメソッドを実装しますが。 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)指定したパスにある項目を取得します。 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)指定した項目の値を設定します。 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)指定されたパスに項目が存在するかどうかを確認します。 [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)かどうかに、データ ストア内の場所にマップを参照してください。 へのパスを確認します。

> [!NOTE]
> このトピックでは、の情報に基づいて[Windows PowerShell プロバイダーのクイック スタート](./windows-powershell-provider-quickstart.md)します。 このトピックでは、プロバイダーのプロジェクトを設定する方法の基本については説明しませんまたはから継承されたメソッドを実装する方法、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスを作成し、ドライブを削除します。

### <a name="declaring-the-provider-class"></a>プロバイダー クラスを宣言します。

派生するプロバイダーを宣言、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスし、で装飾、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute).

```csharp
[CmdletProvider("AccessDB", ProviderCapabilities.None)]

   public class AccessDBProvider : ItemCmdletProvider
   {

  }

```

### <a name="implementing-getitem"></a>GetItem を実装します。

[System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)ユーザーを呼び出すときに、PowerShell エンジンによって呼び出される、 [Microsoft.PowerShell.Commands.Get 項目](/dotnet/api/Microsoft.PowerShell.Commands.Get-Item)コマンドレット、プロバイダー。 メソッドは、指定されたパスにある項目を返します。 Access データベースの例では、メソッドは、項目が、テーブル、データベースまたはデータベース内の行で、ドライブ自体、かどうかをチェックします。 メソッドを呼び出してにアイテムを PowerShell エンジンに送信する、 [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)メソッド。

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

### <a name="implementing-setitem"></a>SetItem を実装します。

[System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを呼び出す PowerShell エンジンの呼び出しによって呼び出されます、 [Microsoft.PowerShell.Commands.Set 項目](/dotnet/api/Microsoft.PowerShell.Commands.Set-Item)コマンドレット. 指定したパスにある項目の値を設定します。

アクセス データベースの例は、その項目には、行があるため、メソッドをスローする場合にのみ、項目の値を設定する[NotSupportedException](http://msdn.microsoft.com/library/system.notsupportedexception\(v=vs.110\).aspx)項目がない場合、行。

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

### <a name="implementing-itemexists"></a>ItemExists を実装します。

[System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドは、ユーザーを呼び出すと、PowerShell エンジンによって呼び出されます、 [Microsoft.PowerShell.Commands.Test パス](/dotnet/api/Microsoft.PowerShell.Commands.Test-Path)コマンドレット。 メソッドは、指定されたパスに項目があるかどうかを判断します。 項目が存在する場合、メソッドは成功に PowerShell エンジンに呼び出して[System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)します。

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

### <a name="implementing-isvalidpath"></a>IsValidPath を実装します。

[System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッドは、指定されたパスが現在のプロバイダーの構文が有効かどうかを確認します。 パスにある項目が存在するかどうかはチェックしません。

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

## <a name="next-steps"></a>次の手順

ドライブ内の別の 1 つのパスから項目を移動して、他の項目を含む項目をサポートしているは一般的な現実世界のプロバイダー。 コンテナーをサポートするプロバイダーの例は、[コンテナー プロバイダーの書き込み](./writing-a-container-provider.md)を参照してください。 項目の移動をサポートするプロバイダーの例は、[ナビゲーション プロバイダーの記述](./writing-a-navigation-provider.md)を参照してください。

## <a name="see-also"></a>参照

[コンテナーのプロバイダーの作成](./writing-a-container-provider.md)

[ナビゲーション プロバイダーの作成](./writing-a-navigation-provider.md)

[Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)