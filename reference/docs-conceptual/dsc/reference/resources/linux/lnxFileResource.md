---
ms.date: 07/17/2020
ms.topic: reference
title: Linux 用 DSC の nxFile リソース
description: Linux 用 DSC の nxFile リソース
ms.openlocfilehash: 14a8174a92f1bbde9b1f16cf814ef7c83309c737
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389030"
---
# <a name="dsc-for-linux-nxfile-resource"></a><span data-ttu-id="bbcf9-103">Linux 用 DSC の nxFile リソース</span><span class="sxs-lookup"><span data-stu-id="bbcf9-103">DSC for Linux nxFile Resource</span></span>

<span data-ttu-id="bbcf9-104">PowerShell Desired State Configuration (DSC) の **nxFile** リソースは、Linux ノード上でファイルとディレクトリを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-104">The **nxFile** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and directories on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="bbcf9-105">構文</span><span class="sxs-lookup"><span data-stu-id="bbcf9-105">Syntax</span></span>

```Syntax
nxFile <string> #ResourceName
{
    DestinationPath = <string>
    [ SourcePath = <string> ]
    [ Type = <string> { directory | file | link } ]
    [ Contents = <string> ]
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Recurse = <bool> ]
    [ Force = <bool> ]
    [ Links = <string> { follow | manage | ignore } ]
    [ Group = <string> ]
    [ Mode = <string> ]
    [ Owner = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="bbcf9-106">Properties</span><span class="sxs-lookup"><span data-stu-id="bbcf9-106">Properties</span></span>

|<span data-ttu-id="bbcf9-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bbcf9-107">Property</span></span> |<span data-ttu-id="bbcf9-108">説明</span><span class="sxs-lookup"><span data-stu-id="bbcf9-108">Description</span></span> |
|---|---|
|<span data-ttu-id="bbcf9-109">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="bbcf9-109">DestinationPath</span></span> |<span data-ttu-id="bbcf9-110">ファイルまたはディレクトリの状態を保証する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-110">Specifies the location where you want to ensure the state for a file or directory.</span></span> |
|<span data-ttu-id="bbcf9-111">SourcePath</span><span class="sxs-lookup"><span data-stu-id="bbcf9-111">SourcePath</span></span> |<span data-ttu-id="bbcf9-112">ファイルまたはフォルダー リソースのコピー元のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-112">Specifies the path from which to copy the file or folder resource.</span></span> <span data-ttu-id="bbcf9-113">このパスはローカル パスまたは `http/https/ftp` URL です。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-113">This path may be a local path, or an `http/https/ftp` URL.</span></span> <span data-ttu-id="bbcf9-114">リモート `http/https/ftp` URL は、**Type** プロパティの値が **file** の場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-114">Remote `http/https/ftp` URLs are only supported when the value of the **Type** property is **file**.</span></span> |
|<span data-ttu-id="bbcf9-115">種類</span><span class="sxs-lookup"><span data-stu-id="bbcf9-115">Type</span></span> |<span data-ttu-id="bbcf9-116">構成されるリソースがディレクトリまたはファイルのいずれであるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-116">Specifies whether the resource being configured is a directory or a file.</span></span> <span data-ttu-id="bbcf9-117">リソースがディレクトリであることを示すには、このプロパティを **directory** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-117">Set this property to **directory** to indicate that the resource is a directory.</span></span> <span data-ttu-id="bbcf9-118">リソースがファイルであることを示すには、**file** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-118">Set it to **file** to indicate that the resource is a file.</span></span> <span data-ttu-id="bbcf9-119">既定値は **file** です。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-119">The default value is **file**.</span></span> |
|<span data-ttu-id="bbcf9-120">内容</span><span class="sxs-lookup"><span data-stu-id="bbcf9-120">Contents</span></span> |<span data-ttu-id="bbcf9-121">特定の文字列など、ファイルの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-121">Specifies the contents of a file, such as a particular string.</span></span> |
|<span data-ttu-id="bbcf9-122">Checksum</span><span class="sxs-lookup"><span data-stu-id="bbcf9-122">Checksum</span></span> |<span data-ttu-id="bbcf9-123">2 つのファイルが同じであるかどうかを決定するときに使用するタイプを定義します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-123">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="bbcf9-124">**Checksum** が指定されていない場合、ファイルまたはディレクトリ名のみが比較に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-124">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="bbcf9-125">値は、**ctime**、**mtime**、または **md5** です。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-125">Values are: **ctime**, **mtime**, or **md5**.</span></span> |
|<span data-ttu-id="bbcf9-126">Recurse</span><span class="sxs-lookup"><span data-stu-id="bbcf9-126">Recurse</span></span> |<span data-ttu-id="bbcf9-127">サブディレクトリが含まれるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-127">Indicates if subdirectories are included.</span></span> <span data-ttu-id="bbcf9-128">サブディレクトリを含めるようにするには、このプロパティを `$true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-128">Set this property to `$true` to indicate that you want subdirectories to be included.</span></span> <span data-ttu-id="bbcf9-129">既定では、 `$false`です。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-129">The default is `$false`.</span></span> <span data-ttu-id="bbcf9-130">このプロパティは、**Type** プロパティが **directory** に設定されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-130">This property is only valid when the **Type** property is set to **directory**.</span></span> |
|<span data-ttu-id="bbcf9-131">Force</span><span class="sxs-lookup"><span data-stu-id="bbcf9-131">Force</span></span> |<span data-ttu-id="bbcf9-132">特定のファイル操作 (ファイルの上書き、空でないディレクトリの削除など) によって、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-132">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="bbcf9-133">**Force** プロパティを使用すると、このようなエラーがオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-133">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="bbcf9-134">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-134">The default value is `$false`.</span></span> |
|<span data-ttu-id="bbcf9-135">リンク</span><span class="sxs-lookup"><span data-stu-id="bbcf9-135">Links</span></span> |<span data-ttu-id="bbcf9-136">シンボリック リンクの目的の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-136">Specifies the desired behavior for symbolic links.</span></span> <span data-ttu-id="bbcf9-137">シンボリック リンクに従い、処理の対象をリンクのターゲットにするには、このプロパティを **follow** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-137">Set this property to **follow** to follow symbolic links and act on the links target.</span></span> <span data-ttu-id="bbcf9-138">たとえば、リンクではなくファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-138">For example, copy the file instead of the link.</span></span> <span data-ttu-id="bbcf9-139">処理の対象をリンクにするには、このプロパティを **manage** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-139">Set this property to **manage** to act on the link.</span></span> <span data-ttu-id="bbcf9-140">たとえば、リンク自体をコピーします。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-140">For example, copy the link itself.</span></span> <span data-ttu-id="bbcf9-141">シンボリック リンクを無視するには、このプロパティを **ignore** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-141">Set this property to **ignore** to ignore symbolic links.</span></span> |
|<span data-ttu-id="bbcf9-142">Group</span><span class="sxs-lookup"><span data-stu-id="bbcf9-142">Group</span></span> |<span data-ttu-id="bbcf9-143">ファイルまたはディレクトリのアクセス許可を与える **グループ** の名前。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-143">The name of the **Group** to have permissions to the file or directory.</span></span> |
|<span data-ttu-id="bbcf9-144">モード</span><span class="sxs-lookup"><span data-stu-id="bbcf9-144">Mode</span></span> |<span data-ttu-id="bbcf9-145">8 進数またはシンボリック表記で、リソースに必要なアクセス許可を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-145">Specifies the desired permissions for the resource, in octal or symbolic notation.</span></span> <span data-ttu-id="bbcf9-146">たとえば、**777** または **rwxrwxrwx** です。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-146">For example, **777** or **rwxrwxrwx**.</span></span> <span data-ttu-id="bbcf9-147">シンボリック表記を使用する場合は、ディレクトリまたはファイルを示す最初の文字を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-147">If using symbolic notation, do not provide the first character which indicates directory or file.</span></span> |
|<span data-ttu-id="bbcf9-148">所有者</span><span class="sxs-lookup"><span data-stu-id="bbcf9-148">Owner</span></span> |<span data-ttu-id="bbcf9-149">ファイルまたはディレクトリを所有するグループの名前。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-149">The name of the group to own the file or directory.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="bbcf9-150">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="bbcf9-150">Common properties</span></span>

|<span data-ttu-id="bbcf9-151">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bbcf9-151">Property</span></span> |<span data-ttu-id="bbcf9-152">説明</span><span class="sxs-lookup"><span data-stu-id="bbcf9-152">Description</span></span> |
|---|---|
|<span data-ttu-id="bbcf9-153">DependsOn</span><span class="sxs-lookup"><span data-stu-id="bbcf9-153">DependsOn</span></span> |<span data-ttu-id="bbcf9-154">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-154">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="bbcf9-155">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-155">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="bbcf9-156">Ensure</span><span class="sxs-lookup"><span data-stu-id="bbcf9-156">Ensure</span></span> |<span data-ttu-id="bbcf9-157">ファイルが存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-157">Determines whether to check if the file exists.</span></span> <span data-ttu-id="bbcf9-158">ファイルが存在することを保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-158">Set this property to **Present** to ensure the file exists.</span></span> <span data-ttu-id="bbcf9-159">ファイルが存在しないことを保証するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-159">Set it to **Absent** to ensure the file does not exist.</span></span> <span data-ttu-id="bbcf9-160">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-160">The default value is **Present**.</span></span> |

## <a name="additional-information"></a><span data-ttu-id="bbcf9-161">追加情報</span><span class="sxs-lookup"><span data-stu-id="bbcf9-161">Additional Information</span></span>

<span data-ttu-id="bbcf9-162">Linux と Windows の既定では、テキスト ファイルで異なる改行文字を使用して、これにより、**nxFile** を使用して Linux コンピューターで一部のファイルを構成すると、予期しない結果が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-162">Linux and Windows use different line break characters in text files by default, and this can cause unexpected results when configuring some files on a Linux computer with **nxFile**.</span></span> <span data-ttu-id="bbcf9-163">予期しない改行文字によって引き起こされる問題を回避しながら Linux ファイルのコンテンツを管理する複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-163">There are multiple ways to manage the content of a Linux file while avoiding issues caused by unexpected line break characters:</span></span>

1. <span data-ttu-id="bbcf9-164">リモート ソース (http、https、または ftp) からファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-164">Copy the file from a remote source (http, https, or ftp)</span></span>

   <span data-ttu-id="bbcf9-165">目的のコンテンツを含むファイルを Linux 上で作成し、構成するノードにアクセスできる Web サーバーまたは FTP サーバーでステージングします。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-165">Create a file on Linux with the desired contents, and stage it on a web or ftp server accessible the node(s) you will configure.</span></span> <span data-ttu-id="bbcf9-166">ファイルへの Web または FTP の URL で、**nxFile** リソースの **SourcePath** プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-166">Define the **SourcePath** property in the **nxFile** resource with the web or ftp URL to the file.</span></span>

   ```powershell
   Import-DSCResource -Module nx

   Node $Node
   {
      nxFile resolvConf
      {
         SourcePath = "http://10.185.85.11/conf/resolv.conf"
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
      }
   }
   ```

1. <span data-ttu-id="bbcf9-167">Linux 改行文字を使用する **$OFS** プロパティの設定後に、[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) を使用して PowerShell スクリプトのファイル コンテンツを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-167">Read the file contents in the PowerShell script with [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) after setting the **$OFS** property to use the Linux line-break character.</span></span>

   ```powershell
   Import-DSCResource -Module nx

   Node $Node
   {
      $OFS = "`n"
      $Contents = Get-Content C:\temp\resolv.conf

      nxFile resolvConf
      {
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
         Contents = "$Contents"
      }
   }
   ```

1. <span data-ttu-id="bbcf9-168">PowerShell 関数を使用して、Linux 改行文字で Windows の改行を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-168">Use a PowerShell function to replace Windows line breaks with Linux line-break characters.</span></span>

   ```powershell
   Function LinuxString($inputStr){
      $outputStr = $inputStr.Replace("`r`n","`n")
      $outputStr += "`n"
      Return $outputStr
   }

   Import-DSCResource -Module nx

   Node $Node
   {
      $Contents = @'
   search contoso.com
   domain contoso.com
   nameserver 10.185.85.11
   '@
       $Contents = LinuxString $Contents

      nxFile resolvConf
      {
         DestinationPath = "/etc/resolv.conf"
         Mode = "644"
         Type = "file"
         Contents = $Contents
      }
   }
   ```

## <a name="example"></a><span data-ttu-id="bbcf9-169">例</span><span class="sxs-lookup"><span data-stu-id="bbcf9-169">Example</span></span>

<span data-ttu-id="bbcf9-170">次の例では、ディレクトリ `/opt/mydir` が存在し、指定されたコンテンツを持つファイルがこのディレクトリが存在するようにしています。</span><span class="sxs-lookup"><span data-stu-id="bbcf9-170">The following example ensures that the directory `/opt/mydir` exists, and that a file with specified contents exists this directory.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node {
    nxFile DirectoryExample
    {
        Ensure = "Present"
        DestinationPath = "/opt/mydir"
        Type = "Directory"
    }

    nxFile FileExample
    {
        Ensure = "Present"
        Destinationpath = "/opt/mydir/myfile"
        Contents=@"
#!/bin/bash`necho "hello world"`n
"@
        Mode = "755"
        DependsOn = "[nxFile]DirectoryExample"
    }
}
```
