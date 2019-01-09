---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 DSC の nxFile リソース
ms.openlocfilehash: 80969ba2ea6247fcd616a301d951403a840c851d
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047891"
---
# <a name="dsc-for-linux-nxfile-resource"></a><span data-ttu-id="14fbd-103">Linux 用 DSC の nxFile リソース</span><span class="sxs-lookup"><span data-stu-id="14fbd-103">DSC for Linux nxFile Resource</span></span>

<span data-ttu-id="14fbd-104">PowerShell Desired State Configuration (DSC) の **nxFile** リソースは、Linux ノード上でファイルとディレクトリを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="14fbd-104">The **nxFile** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and directories on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="14fbd-105">構文</span><span class="sxs-lookup"><span data-stu-id="14fbd-105">Syntax</span></span>

```
nxFile <string> #ResourceName
{
    DestinationPath = <string>
    [ SourcePath = <string> ]
    [ Ensure = <string> { Absent | Present }  ]
    [ Type = <string> { directory | file | link } ]
    [ Contents = <string> ]
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Recurse = <bool> ]
    [ Force = <bool> ]
    [ Links = <string> { follow | manage } ]
    [ Group = <string> ]
    [ Mode = <string> ]
    [ Owner = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="14fbd-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="14fbd-106">Properties</span></span>

|  <span data-ttu-id="14fbd-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="14fbd-107">Property</span></span> |  <span data-ttu-id="14fbd-108">説明</span><span class="sxs-lookup"><span data-stu-id="14fbd-108">Description</span></span> |
|---|---|
| <span data-ttu-id="14fbd-109">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="14fbd-109">DestinationPath</span></span>| <span data-ttu-id="14fbd-110">ファイルまたはディレクトリの状態を保証する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-110">Specifies the location where you want to ensure the state for a file or directory.</span></span>|
| <span data-ttu-id="14fbd-111">SourcePath</span><span class="sxs-lookup"><span data-stu-id="14fbd-111">SourcePath</span></span>| <span data-ttu-id="14fbd-112">ファイルまたはフォルダー リソースのコピー元のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-112">Specifies the path from which to copy the file or folder resource.</span></span> <span data-ttu-id="14fbd-113">このパスはローカル パスまたは `http/https/ftp` URL です。</span><span class="sxs-lookup"><span data-stu-id="14fbd-113">This path may be a local path, or an `http/https/ftp` URL.</span></span> <span data-ttu-id="14fbd-114">リモート `http/https/ftp` URL は、**Type** プロパティの値が file の場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="14fbd-114">Remote `http/https/ftp` URLs are only supported when the value of the **Type** property is file.</span></span>|
| <span data-ttu-id="14fbd-115">Ensure</span><span class="sxs-lookup"><span data-stu-id="14fbd-115">Ensure</span></span>| <span data-ttu-id="14fbd-116">ファイルが存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-116">Determines whether to check if the file exists.</span></span> <span data-ttu-id="14fbd-117">ファイルが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-117">Set this property to "Present" to ensure the file exists.</span></span> <span data-ttu-id="14fbd-118">ファイルが存在しないことを保証するには、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-118">Set it to "Absent" to ensure the file does not exist.</span></span> <span data-ttu-id="14fbd-119">既定値は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="14fbd-119">The default value is "Present".</span></span>|
| <span data-ttu-id="14fbd-120">種類</span><span class="sxs-lookup"><span data-stu-id="14fbd-120">Type</span></span>| <span data-ttu-id="14fbd-121">構成されるリソースがディレクトリまたはファイルのいずれであるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-121">Specifies whether the resource being configured is a directory or a file.</span></span> <span data-ttu-id="14fbd-122">リソースがディレクトリであることを示すには、このプロパティを "directory" に設定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-122">Set this property to "directory" to indicate that the resource is a directory.</span></span> <span data-ttu-id="14fbd-123">リソースがファイルであることを示すには、"file" に設定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-123">Set it to "file" to indicate that the resource is a file.</span></span> <span data-ttu-id="14fbd-124">既定値は "file" です。</span><span class="sxs-lookup"><span data-stu-id="14fbd-124">The default value is "file"</span></span>|
| <span data-ttu-id="14fbd-125">内容</span><span class="sxs-lookup"><span data-stu-id="14fbd-125">Contents</span></span>| <span data-ttu-id="14fbd-126">特定の文字列など、ファイルの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-126">Specifies the contents of a file, such as a particular string.</span></span>|
| <span data-ttu-id="14fbd-127">チェックサム</span><span class="sxs-lookup"><span data-stu-id="14fbd-127">Checksum</span></span>| <span data-ttu-id="14fbd-128">2 つのファイルが同じであるかどうかを決定するときに使用するタイプを定義します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-128">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="14fbd-129">**Checksum** が指定されていない場合、ファイルまたはディレクトリ名のみが比較に使用されます。</span><span class="sxs-lookup"><span data-stu-id="14fbd-129">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="14fbd-130">値は、"ctime"、"mtime"、または "md5" です。</span><span class="sxs-lookup"><span data-stu-id="14fbd-130">Values are: "ctime", "mtime", or "md5".</span></span>|
| <span data-ttu-id="14fbd-131">Recurse</span><span class="sxs-lookup"><span data-stu-id="14fbd-131">Recurse</span></span>| <span data-ttu-id="14fbd-132">サブディレクトリが含まれるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-132">Indicates if subdirectories are included.</span></span> <span data-ttu-id="14fbd-133">サブディレクトリを含めるようにするには、このプロパティを **$true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-133">Set this property to **$true** to indicate that you want subdirectories to be included.</span></span> <span data-ttu-id="14fbd-134">既定値は **$false** です。</span><span class="sxs-lookup"><span data-stu-id="14fbd-134">The default is **$false**.</span></span> <span data-ttu-id="14fbd-135">**注:** ときにこのプロパティは有効なのみ、**型**プロパティがディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-135">**Note:** This property is only valid when the **Type** property is set to directory.</span></span>|
| <span data-ttu-id="14fbd-136">Force</span><span class="sxs-lookup"><span data-stu-id="14fbd-136">Force</span></span>| <span data-ttu-id="14fbd-137">特定のファイル操作 (ファイルの上書き、空でないディレクトリの削除など) によって、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-137">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="14fbd-138">**Force** プロパティを使用すると、このようなエラーがオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="14fbd-138">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="14fbd-139">既定値は **$false** です。</span><span class="sxs-lookup"><span data-stu-id="14fbd-139">The default value is **$false**.</span></span>|
| <span data-ttu-id="14fbd-140">リンク</span><span class="sxs-lookup"><span data-stu-id="14fbd-140">Links</span></span>| <span data-ttu-id="14fbd-141">シンボリック リンクの目的の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-141">Specifies the desired behavior for symbolic links.</span></span> <span data-ttu-id="14fbd-142">シンボリック リンクに従い、処理の対象をリンクのターゲットにするには、このプロパティを "follow" に設定します (たとえば、</span><span class="sxs-lookup"><span data-stu-id="14fbd-142">Set this property to "follow" to follow symbolic links and act on the links target (for example.</span></span> <span data-ttu-id="14fbd-143">リンクではなくファイルをコピーします)。</span><span class="sxs-lookup"><span data-stu-id="14fbd-143">copy the file instead of the link).</span></span> <span data-ttu-id="14fbd-144">処理の対象をリンクにするには、このプロパティを "manage" に設定します (たとえば、</span><span class="sxs-lookup"><span data-stu-id="14fbd-144">Set this property to "manage" to act on the link (for example.</span></span> <span data-ttu-id="14fbd-145">リンク自体をコピーします)。</span><span class="sxs-lookup"><span data-stu-id="14fbd-145">copy the link itself).</span></span> <span data-ttu-id="14fbd-146">シンボリック リンクを無視するには、このプロパティを "ignore" に設定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-146">Set this property to "ignore" to ignore symbolic links.</span></span>|
| <span data-ttu-id="14fbd-147">グループ</span><span class="sxs-lookup"><span data-stu-id="14fbd-147">Group</span></span>| <span data-ttu-id="14fbd-148">ファイルまたはディレクトリを所有する**グループ**の名前。</span><span class="sxs-lookup"><span data-stu-id="14fbd-148">The name of the **Group** to own the file or directory.</span></span>|
| <span data-ttu-id="14fbd-149">モード</span><span class="sxs-lookup"><span data-stu-id="14fbd-149">Mode</span></span>| <span data-ttu-id="14fbd-150">8 進数またはシンボリック表記で、リソースに必要なアクセス許可を指定します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-150">Specifies the desired permissions for the resource, in octal or symbolic notation.</span></span> <span data-ttu-id="14fbd-151">(たとえば、777 または rwxrwxrwx)。</span><span class="sxs-lookup"><span data-stu-id="14fbd-151">(for example, 777 or rwxrwxrwx).</span></span> <span data-ttu-id="14fbd-152">シンボリック表記を使用する場合は、ディレクトリまたはファイルを示す最初の文字を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="14fbd-152">If using symbolic notation, do not provide the first character which indicates directory or file.</span></span>|
| <span data-ttu-id="14fbd-153">DependsOn</span><span class="sxs-lookup"><span data-stu-id="14fbd-153">DependsOn</span></span> | <span data-ttu-id="14fbd-154">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-154">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="14fbd-155">たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="14fbd-155">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="additional-information"></a><span data-ttu-id="14fbd-156">追加情報</span><span class="sxs-lookup"><span data-stu-id="14fbd-156">Additional Information</span></span>


<span data-ttu-id="14fbd-157">Linux と Windows の既定では、テキスト ファイルで異なる改行文字を使用して、これにより、__nxFile__ を使用して Linux コンピューターで一部のファイルを構成すると、予期しない結果が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="14fbd-157">Linux and Windows use different line break characters in text files by default, and this can cause unexpected results when configuring some files on a Linux computer with __nxFile__.</span></span> <span data-ttu-id="14fbd-158">予期しない改行文字によって引き起こされる問題を回避しながら Linux ファイルのコンテンツを管理する複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="14fbd-158">There are multiple ways to manage the content of a Linux file while avoiding issues caused by unexpected line break characters:</span></span>

<span data-ttu-id="14fbd-159">手順 1:リモート ソース (http、https、または ftp) からファイルをコピーします。目的のコンテンツを含むファイルを Linux 上で作成し、構成するノードにアクセスできる Web サーバーまたは FTP サーバーでステージングします。</span><span class="sxs-lookup"><span data-stu-id="14fbd-159">Step 1: Copy the file from a remote source (http, https, or ftp): create a file on Linux with the desired contents, and stage it on a web or ftp server accessible the node(s) you will configure.</span></span> <span data-ttu-id="14fbd-160">ファイルへの Web または FTP の URL で、__nxFile__ リソースの __SourcePath__ プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="14fbd-160">Define the __SourcePath__ property in the __nxFile__ resource with the web or ftp URL to the file.</span></span>

```
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


<span data-ttu-id="14fbd-161">手順 2:Linux 改行文字を使用する __$OFS__ プロパティの設定後に、[Get-Content](https://technet.microsoft.com/library/hh849787.aspx) を使用して PowerShell スクリプトのファイル コンテンツを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="14fbd-161">Step 2: Read the file contents in the PowerShell script with [Get-Content](https://technet.microsoft.com/library/hh849787.aspx) after setting the __$OFS__ property to use the Linux line-break character.</span></span>


```
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


<span data-ttu-id="14fbd-162">手順 3:PowerShell 関数を使用して Windows Linux 改行文字と改行を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="14fbd-162">Step 3: Use a PowerShell function to replace Windows line breaks with Linux line-break characters.</span></span>

```
Function LinuxString($inputStr){
    $outputStr = $inputStr.Replace("`r`n","`n")
    $ouputStr += "`n"
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

## <a name="example"></a><span data-ttu-id="14fbd-163">例</span><span class="sxs-lookup"><span data-stu-id="14fbd-163">Example</span></span>

<span data-ttu-id="14fbd-164">次の例では、ディレクトリ `/opt/mydir` が存在し、指定されたコンテンツを持つファイルがこのディレクトリが存在するようにしています。</span><span class="sxs-lookup"><span data-stu-id="14fbd-164">The following example ensures that the directory `/opt/mydir` exists, and that a file with specified contents exists this directory.</span></span>

```
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
    Mode = “755”
    DependsOn = "[nxFile]DirectoryExample"
}
}
```