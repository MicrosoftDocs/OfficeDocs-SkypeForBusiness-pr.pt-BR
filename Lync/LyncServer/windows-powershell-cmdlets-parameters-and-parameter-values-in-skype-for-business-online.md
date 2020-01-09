---
title: Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9e9582941b05a4151be5baa2ce74acfc79b3db3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="4c849-102">Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4c849-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c849-103">_**Tópico da última modificação:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="4c849-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="4c849-104">Se você estiver familiarizado com a janela de comando encontrada em todas as versões do Windows (ou se estiver familiarizado com o MS-DOS), terá um início para aprender como usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c849-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="4c849-105">Na janela de comando, digite um comando e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="4c849-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="4c849-106">Em resposta, o computador executa um comando ou um arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="4c849-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="4c849-107">Por exemplo, para retornar informações sobre todos os arquivos e pastas do diretório atual, digite este comando no prompt de comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="4c849-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

    dir

<span data-ttu-id="4c849-108">Em seguida, você recebe informações sobre todos os arquivos e pastas no diretório atual:</span><span class="sxs-lookup"><span data-stu-id="4c849-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

``` 
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

<span data-ttu-id="4c849-109">Esse é um exemplo de um resultado quando você digita somente o nome de um comando ou um arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="4c849-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="4c849-110">No entanto, muitos dos comandos executados na janela de comando também aceitam *argumentos*.</span><span class="sxs-lookup"><span data-stu-id="4c849-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="4c849-111">Os argumentos são partes adicionais de informações que são transmitidas ao comando, que modificam o comportamento do comando.</span><span class="sxs-lookup"><span data-stu-id="4c849-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="4c849-112">Por exemplo, se você quisesse ver somente os nomes dos arquivos e da pasta no diretório atual, não há outras informações, como o tamanho do arquivo ou da pasta, ou a data e a hora em que a pasta ou pasta foi criada.</span><span class="sxs-lookup"><span data-stu-id="4c849-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="4c849-113">Nesse caso, você deve acrescentar o argumento **/b** ao executar o comando dir:</span><span class="sxs-lookup"><span data-stu-id="4c849-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

    dir /b

<span data-ttu-id="4c849-114">Quando você inclui o argumento **/b** , o comando **dir** relata somente os nomes das pastas e dos arquivos encontrados no diretório atual:</span><span class="sxs-lookup"><span data-stu-id="4c849-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="4c849-115">No comando anterior, o argumento **/b** é a única informação necessária para limitar os dados retornados a nomes de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="4c849-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="4c849-116">Geralmente, esse é o caso com comandos de linha de comando: a mera presença de um argumento é tudo o que é necessário para alterar o comportamento do comando.</span><span class="sxs-lookup"><span data-stu-id="4c849-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="4c849-117">(Ou seja, você inclui o argumento **/b** para ocultar informações adicionais ou exclui o argumento **/b** para mostrar as informações extras.) Em outras ocasiões, no entanto, você deve especificar um *valor de argumento*.</span><span class="sxs-lookup"><span data-stu-id="4c849-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="4c849-118">Um valor de argumento são informações adicionais passadas para o argumento em si.</span><span class="sxs-lookup"><span data-stu-id="4c849-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="4c849-119">Por exemplo, o argumento **/o** permite que você especifique como deseja que o comando dir Classifique os dados retornados.</span><span class="sxs-lookup"><span data-stu-id="4c849-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="4c849-120">Entre outras opções, você pode usar o valor de argumento **e** para classificar por extensão de arquivo ou o valor de argumento **s** para classificar por tamanho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="4c849-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="4c849-121">Por exemplo, esse comando classifica os dados retornados por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4c849-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="4c849-122">Observe como o valor de argumento **e** é incluído imediatamente após o argumento **/o** :</span><span class="sxs-lookup"><span data-stu-id="4c849-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

    dir /oe

<span data-ttu-id="4c849-123">Usando nossa pasta de exemplo, os dados retornados terão a seguinte aparência, com os arquivos classificados em ordem alfabética pela extensão de arquivo:</span><span class="sxs-lookup"><span data-stu-id="4c849-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

``` 
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

<span data-ttu-id="4c849-124">Ou, para ajudá-lo a identificar exatamente o que estamos falando:</span><span class="sxs-lookup"><span data-stu-id="4c849-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

<span data-ttu-id="4c849-125">configuração.</span><span class="sxs-lookup"><span data-stu-id="4c849-125">setup.</span></span> <span data-ttu-id="4c849-126">**documentação**</span><span class="sxs-lookup"><span data-stu-id="4c849-126">**doc**</span></span>  
<span data-ttu-id="4c849-127">RHDSetup.</span><span class="sxs-lookup"><span data-stu-id="4c849-127">RHDSetup.</span></span> <span data-ttu-id="4c849-128">**exe**</span><span class="sxs-lookup"><span data-stu-id="4c849-128">**exe**</span></span>  
<span data-ttu-id="4c849-129">pldok.</span><span class="sxs-lookup"><span data-stu-id="4c849-129">pldok.</span></span> <span data-ttu-id="4c849-130">**efetua**</span><span class="sxs-lookup"><span data-stu-id="4c849-130">**log**</span></span>

<span data-ttu-id="4c849-131">Embora o Windows PowerShell use uma terminologia diferente, a abordagem básica para trabalhar com o Windows PowerShell é a mesma que trabalhar com a janela de comando: você digita comandos, inclui argumentos e valores de argumento conforme necessário e, em seguida, pressiona ENTER para executar esses comandos.</span><span class="sxs-lookup"><span data-stu-id="4c849-131">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="4c849-132">Como observado, no entanto, o Windows PowerShell usa uma terminologia diferente do que o Shell de comando usa.</span><span class="sxs-lookup"><span data-stu-id="4c849-132">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="4c849-133">No Windows PowerShell, os comandos que você executa são conhecidos como *cmdlets*.</span><span class="sxs-lookup"><span data-stu-id="4c849-133">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="4c849-134">Por sua vez, os argumentos passados para um cmdlet são conhecidos como *parâmetros*, e os valores passados para um parâmetro são conhecidos como *valores de parâmetro*.</span><span class="sxs-lookup"><span data-stu-id="4c849-134">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="4c849-135">As definições anteriores são um pouco simplificadas.</span><span class="sxs-lookup"><span data-stu-id="4c849-135">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="4c849-136">Cmdlets são essencialmente mini-aplicativos que podem ser executados somente de dentro do ambiente do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c849-136">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="4c849-137">No entanto, você também pode executar outros comandos e aplicativos no Windows PowerShell, incluindo a maioria dos comandos e aplicativos que podem ser executados a partir de uma janela de comando.</span><span class="sxs-lookup"><span data-stu-id="4c849-137">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="4c849-138">Por exemplo, se você quiser iniciar o bloco de notas no Windows PowerShell, tudo o que precisa fazer é digitar o seguinte e pressionar ENTER:</span><span class="sxs-lookup"><span data-stu-id="4c849-138">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

    notepad.exe

<span data-ttu-id="4c849-139">No entanto, ao gerenciar o Skype for Business Online, a maioria dos administradores confiará nos cmdlets do Windows PowerShell para executar tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="4c849-139">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="4c849-140">No momento, há poucos outros tipos de comandos ou aplicativos que podem ser usados para gerenciar o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4c849-140">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="4c849-141">Às vezes, os cmdlets do Skype for Business Online podem ser usados sem nenhum argumento adicional (, como observado, os argumentos são conhecidos como parâmetros no Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4c849-141">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="4c849-142">Por exemplo, o comando a seguir chama o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) sem parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="4c849-142">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="4c849-143">Por si só, o comando retorna informações sobre todos os seus usuários do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="4c849-143">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="4c849-144">No entanto, a maioria dos cmdlets do Skype for Business online também aceita parâmetros (e valores de parâmetro).</span><span class="sxs-lookup"><span data-stu-id="4c849-144">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="4c849-145">Considere o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4c849-145">Consider the following command:</span></span>

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

<span data-ttu-id="4c849-146">Este comando consiste em três partes:</span><span class="sxs-lookup"><span data-stu-id="4c849-146">This command consists of three parts:</span></span>

  - <span data-ttu-id="4c849-147">O cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="4c849-147">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="4c849-148">O parâmetro Identity.</span><span class="sxs-lookup"><span data-stu-id="4c849-148">The Identity parameter.</span></span> <span data-ttu-id="4c849-149">Observe que, no Windows PowerShell, os parâmetros são sempre precedidas por um traço (-).</span><span class="sxs-lookup"><span data-stu-id="4c849-149">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="4c849-150">Isso significa que, para esse mesmo cmdlet, o parâmetro UnassignedUser seria indicado usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4c849-150">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
        -UnassignedUser
    
    <span data-ttu-id="4c849-151">Isso é útil, não apenas porque os parâmetros devem ser precedidas com um traço, mas também porque isso é diferente da janela de comando, em que os argumentos são precedidas usando uma barra (/):</span><span class="sxs-lookup"><span data-stu-id="4c849-151">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console 
    /b
    ```

  - <span data-ttu-id="4c849-152">O valor do parâmetro **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="4c849-152">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="4c849-153">Esse comando, incidentalmente, retorna informações sobre um usuário específico: o usuário com a identidade, kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4c849-153">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4c849-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="4c849-154">See Also</span></span>


<span data-ttu-id="4c849-155">[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4c849-155">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

