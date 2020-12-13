---
ms.date: 09/13/2016
ms.topic: reference
title: RemoteRunspace01 サンプル
description: RemoteRunspace01 サンプル
ms.openlocfilehash: 13c6213089700e779eb185fe48a67c1616fad437
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658020"
---
# <a name="remoterunspace01-sample"></a><span data-ttu-id="d4809-103">RemoteRunspace01 サンプル</span><span class="sxs-lookup"><span data-stu-id="d4809-103">RemoteRunspace01 Sample</span></span>

<span data-ttu-id="d4809-104">このサンプルでは、リモート接続を確立するために使用されるリモート実行空間を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d4809-104">This sample shows how to create a remote runspace that is used to establish a remote connection.</span></span>

## <a name="requirements"></a><span data-ttu-id="d4809-105">要件</span><span class="sxs-lookup"><span data-stu-id="d4809-105">Requirements</span></span>

 <span data-ttu-id="d4809-106">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d4809-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="d4809-107">対象</span><span class="sxs-lookup"><span data-stu-id="d4809-107">Demonstrates</span></span>

- <span data-ttu-id="d4809-108">[Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)オブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="d4809-108">Creating a [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) object.</span></span>

- <span data-ttu-id="d4809-109">Wsmanconnectioninfo オブジェクトの[Runspaceconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConnectionInfo.OperationTimeout) \* プロパティと[Runspaceconnectioninfo. Opentimeout \*](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConnectionInfo.OpenTimeout)プロパティを設定しています。この値を設定すると、 [](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo)オブジェクトのプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d4809-109">Setting the [System.Management.Automation.Runspaces.Runspaceconnectioninfo.Operationtimeout\*](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConnectionInfo.OperationTimeout) and [System.Management.Automation.Runspaces.Runspaceconnectioninfo.Opentimeout\*](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConnectionInfo.OpenTimeout) properties of the [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) object.</span></span>

- <span data-ttu-id="d4809-110">リモート接続を確立するために [Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) オブジェクトを使用するリモート実行空間を作成する。</span><span class="sxs-lookup"><span data-stu-id="d4809-110">Creating a remote runspace that uses the [System.Management.Automation.Runspaces.Wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) object to establish the remote connection.</span></span>

- <span data-ttu-id="d4809-111">リモートの実行空間を閉じてリモート接続を解放しています。</span><span class="sxs-lookup"><span data-stu-id="d4809-111">Closing the remote runspace to release the remote connection.</span></span>

## <a name="example"></a><span data-ttu-id="d4809-112">例</span><span class="sxs-lookup"><span data-stu-id="d4809-112">Example</span></span>

<span data-ttu-id="d4809-113">このサンプルでは、リモート接続を定義し、その接続情報を使用してリモート接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="d4809-113">This sample defines a remote connection and then uses that connection information to establish a remote connection.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;             // Windows PowerShell namespace.
  using System.Management.Automation.Runspaces;   // Windows PowerShell namespace.

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class RemoteRunspace01
  {
    /// <summary>
    /// This sample shows how to use a WSManConnectionInfo object to set
    /// various timeouts and how to establish a remote connection.
    /// </summary>
    /// <param name="args">This parameter is not used.</param>
    public static void Main(string[] args)
    {
      // Create a WSManConnectionInfo object using the default constructor
      // to connect to the "localHost". The WSManConnectionInfo object can
      // also specify connections to remote computers.
      WSManConnectionInfo connectionInfo = new WSManConnectionInfo();

      // Set the OperationTimeout property. The OperationTimeout is used to tell
      // Windows PowerShell how long to wait (in milliseconds) before timing out
      // for any operation. This includes sending input data to the remote computer,
      // receiving output data from the remote computer, and more. The user can
      // change this timeout depending on whether the connection is to a computer
      // in the data center or across a slow WAN.
      connectionInfo.OperationTimeout = 4 * 60 * 1000; // 4 minutes.

      // Set the OpenTimeout property. OpenTimeout is used to tell Windows PowerShell
      // how long to wait (in milliseconds) before timing out while establishing a
      // remote connection. The user can change this timeout depending on whether the
      // connection is to a computer in the data center or across a slow WAN.
      connectionInfo.OpenTimeout = 1 * 60 * 1000; // 1 minute.

      // Create a remote runspace using the connection information.
      using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace(connectionInfo))
      {
        // Establish the connection by calling the Open() method to open the runspace.
        // The OpenTimeout value set previously will be applied while establishing
        // the connection. Establishing a remote connection involves sending and
        // receiving some data, so the OperationTimeout will also play a role in this process.
        remoteRunspace.Open();

        // Add the code to run commands in the remote runspace here. The
        // OperationTimeout value set previously will play a role here because
        // running commands involves sending and receiving data.

        // Close the connection. Call the Close() method to close the remote
        // runspace. The Dispose() method (called by using primitive) will call
        // the Close() method if it is not already called.
        remoteRunspace.Close();
      }
    }
  }
}
```
