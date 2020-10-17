---
title: Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business Online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ad45c9deecf364c273ff64e939c4379d169f3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499958"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="9d7a3-102">Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9d7a3-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d7a3-103">_**Última modificação do tópico:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="9d7a3-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="9d7a3-104">Se você estiver familiarizado com a janela de comando encontrada em todas as versões do Windows (ou se estiver familiarizado com o MS-DOS), terá uma partida de início quando se trata de aprender a usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="9d7a3-105">Na janela de comando, digite um comando e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="9d7a3-106">Em resposta, o computador executa um comando ou um arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="9d7a3-107">Por exemplo, para retornar informações sobre todos os arquivos e pastas no diretório atual, digite este comando no prompt de comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="9d7a3-108">Por sua vez, você obtém informações sobre todos os arquivos e pastas no diretório atual:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

<span data-ttu-id="9d7a3-109">Este é um exemplo de um resultado quando você digita apenas o nome de um comando ou um arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="9d7a3-110">No entanto, muitos dos comandos executados dentro da janela de comando também aceitam *argumentos*.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="9d7a3-111">Argumentos são partes adicionais de informações que são passadas para o comando, que modificam o comportamento do comando.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="9d7a3-112">Por exemplo, se você quisesse ver os nomes dos arquivos e pastas no diretório atual — não há outras informações, como o tamanho do arquivo ou pasta, ou a data e hora em que a pasta ou pasta foi criada.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="9d7a3-113">Nesse caso, você deve acrescentar o argumento **/b** ao executar o comando dir:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="9d7a3-114">Quando você inclui o argumento **/b** , o comando **dir** retorna apenas os nomes das pastas e dos arquivos encontrados no diretório atual:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

```console
Deploy
Intel
PerfLogs
Program Files
Program Files (x86)
Users
Windows
pldok.log
RHDSetup.exe
setup.doc
```

<span data-ttu-id="9d7a3-115">No comando anterior, o argumento **/b** é a única informação necessária para limitar os dados retornados aos nomes de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="9d7a3-116">Isso geralmente é o caso com comandos de linha de comando: a mera presença de um argumento é tudo o que é necessário para alterar o comportamento do comando.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="9d7a3-117">(Ou seja, você inclui o argumento **/b** para ocultar informações adicionais ou exclui o argumento **/b** para mostrar as informações extras.) Em outras ocasiões, no entanto, você deve especificar um *valor de argumento*.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="9d7a3-118">Um valor de argumento é uma informação adicional passada para o próprio argumento.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="9d7a3-119">Por exemplo, o argumento **/o** permite que você especifique como deseja que o comando dir Classifique os dados retornados.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="9d7a3-120">Entre outras opções, você pode usar o valor de argumento **e** para classificar por extensão de arquivo ou o valor de argumento **s** para classificar por tamanho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="9d7a3-121">Por exemplo, esse comando classifica os dados retornados por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="9d7a3-122">Observe como o valor de argumento **e** é incluído imediatamente após o argumento **/o** :</span><span class="sxs-lookup"><span data-stu-id="9d7a3-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="9d7a3-123">Usando nossa pasta de exemplo, os dados retornados terão a seguinte aparência, com os arquivos classificados alfabeticamente por extensão de arquivo:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

<span data-ttu-id="9d7a3-124">Ou, para ajudá-lo a identificar exatamente o que estamos falando:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="9d7a3-125">Embora o Windows PowerShell use uma terminologia diferente, a abordagem básica para trabalhar com o Windows PowerShell é o mesmo que trabalhar com a janela de comando: você digita comandos, inclui argumentos e valores de argumentos conforme necessário e, em seguida, pressiona ENTER para executar esses comandos.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="9d7a3-126">Como observado, no entanto, o Windows PowerShell usa uma terminologia diferente da usada pelo shell de comando.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="9d7a3-127">No Windows PowerShell, os comandos executados são conhecidos como *cmdlets*.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="9d7a3-128">Por sua vez, os argumentos passados para um cmdlet são conhecidos como *parâmetros*, e os valores passados para um parâmetro são conhecidos como *valores de parâmetro*.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="9d7a3-129">As definições anteriores são um pouco simplificadas.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="9d7a3-130">Os cmdlets são, basicamente, aplicativos que podem ser executados apenas de dentro do ambiente do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="9d7a3-131">No entanto, você também pode executar outros comandos e aplicativos de dentro do Windows PowerShell, incluindo a maioria dos comandos e aplicativos que podem ser executados a partir de uma janela de comando.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="9d7a3-132">Por exemplo, se você deseja iniciar o bloco de notas no Windows PowerShell, tudo o que precisa fazer é digitar o seguinte e pressionar ENTER:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="9d7a3-133">No entanto, quando se trata de gerenciar o Skype for Business Online, a maioria dos administradores confiará nos cmdlets do Windows PowerShell para executar tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="9d7a3-134">No momento, há poucos outros tipos de comandos ou aplicativos que podem ser usados para gerenciar o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="9d7a3-135">Às vezes, os cmdlets do Skype for Business Online podem ser usados sem nenhum argumento adicional (, conforme observado, os argumentos são conhecidos como parâmetros no Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="9d7a3-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="9d7a3-136">Por exemplo, o comando a seguir chama o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) sem parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="9d7a3-137">Em si, o comando retorna informações sobre todos os seus usuários do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="9d7a3-138">No entanto, a maioria dos cmdlets do Skype for Business online também aceita parâmetros (e valores de parâmetro).</span><span class="sxs-lookup"><span data-stu-id="9d7a3-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="9d7a3-139">Considere o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="9d7a3-140">Este comando consiste em três partes:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="9d7a3-141">O cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="9d7a3-142">O parâmetro Identity.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-142">The Identity parameter.</span></span> <span data-ttu-id="9d7a3-143">Observe que, no Windows PowerShell, os parâmetros são sempre precedidas por um traço (-).</span><span class="sxs-lookup"><span data-stu-id="9d7a3-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="9d7a3-144">Isso significa que, para esse mesmo cmdlet, o parâmetro UnassignedUser seria indicado usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9d7a3-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="9d7a3-145">Isso é útil para saber, não apenas porque os parâmetros devem ser precedidas por um traço, mas também porque isso difere da janela de comando, onde os argumentos são precedidas usando uma barra (/):</span><span class="sxs-lookup"><span data-stu-id="9d7a3-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="9d7a3-146">O valor do parâmetro **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="9d7a3-147">Esse comando, incidentalmente, retorna informações sobre um usuário específico: o usuário com a identidade kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9d7a3-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9d7a3-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="9d7a3-148">See Also</span></span>


<span data-ttu-id="9d7a3-149">[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9d7a3-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

