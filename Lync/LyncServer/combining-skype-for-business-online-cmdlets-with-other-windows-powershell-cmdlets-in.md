---
title: Combinando cmdlets do Skype for Business online com outros cmdlets do Windows PowerShell no
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcd352521285e619c9ceeb55a0699b4d4ea73e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="9c9e4-102">Combinando cmdlets do Skype for Business online com outros cmdlets do Windows PowerShell no</span><span class="sxs-lookup"><span data-stu-id="9c9e4-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c9e4-103">_**Tópico da última modificação:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="9c9e4-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="9c9e4-104">Quando você se conecta ao Skype for Business online usando o Windows PowerShell, cerca de 40 cmdlets do Skype for Business online estarão disponíveis para uso.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="9c9e4-105">No entanto, você não está limitado a usar apenas os cmdlets do 40 ao gerenciar o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="9c9e4-106">Além dos cmdlets do Skype for Business Online, você também pode usar quaisquer outros cmdlets do Windows PowerShell instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="9c9e4-107">(Quando você instala o Windows PowerShell 3,0, centenas de cmdlets do Windows PowerShell básicos também são instalados.) Seus comandos podem misturar e combinar cmdlets do Skype for Business Online e quaisquer outros cmdlets disponíveis no seu computador.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="9c9e4-108">Embora um curso completo do Windows PowerShell 3,0 ultrapasse o escopo deste artigo, aqui estão alguns exemplos que mostram porque você pode querer combinar e comparar cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="9c9e4-109">Em primeiro lugar, nenhum dos cmdlets do Skype for Business Online inclui um comando de impressão, e esse comando não pode ser encontrado no console do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="9c9e4-110">Então, como você obtém uma cópia impressa das informações recuperadas por um cmdlet?</span><span class="sxs-lookup"><span data-stu-id="9c9e4-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="9c9e4-111">Uma maneira é recuperar as informações e, em seguida, enviar essas informações para o cmdlet **Out-Printer** :</span><span class="sxs-lookup"><span data-stu-id="9c9e4-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="9c9e4-112">Como nenhum parâmetro adicional está incluído, todas as informações retornadas pelo cmdlet **Out-Printer** serão impressas na impressora padrão.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="9c9e4-113">Da mesma forma, nenhum dos cmdlets do Skype for Business Online inclui um parâmetro que permite salvar dados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="9c9e4-114">Mas isso é certo: esse comando usa o cmdlet **Out-File** para salvar as informações retornadas no arquivo de texto C\\:\\registra locatários. txt:</span><span class="sxs-lookup"><span data-stu-id="9c9e4-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="9c9e4-115">E esse comando usa o cmdlet **Select-Object** para limitar os dados que são retornados e exibidos na tela.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="9c9e4-116">Neste exemplo, o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) recupera informações de todos os seus usuários do Skype for Business Online e, em seguida, o cmdlet **Select-Object** é usado para limitar os dados exibidos ao valor de identidade do usuário e às políticas de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="9c9e4-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="9c9e4-117">Como há centenas de cmdlets disponíveis para serem usados em seu computador, você pode ter dificuldade em determinar quais cmdlets são cmdlets do Skype for Business Online e quais não são.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="9c9e4-118">Para retornar uma lista dos cmdlets do Skype for Business online (e somente cmdlets do Skype for Business online), primeiro você deve determinar o nome do módulo do Windows PowerShell temporário que contém todos os cmdlets do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="9c9e4-119">Para fazer isso, execute este comando a partir do prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9c9e4-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="9c9e4-120">As informações semelhantes às seguintes serão exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="9c9e4-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="9c9e4-121">O módulo com o script ModuleType é o módulo que contém os cmdlets do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="9c9e4-122">Para retornar uma lista desses cmdlets, execute o cmdlet **Get-Command** usando o nome do módulo de script como o nome do módulo:</span><span class="sxs-lookup"><span data-stu-id="9c9e4-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="9c9e4-123">É possível que você tenha vários módulos com um ModuleType igual a script.</span><span class="sxs-lookup"><span data-stu-id="9c9e4-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="9c9e4-124">Nesse caso, você pode executar o seguinte comando para descobrir qual módulo inclui o cmdlet **Get-CsTenant** :</span><span class="sxs-lookup"><span data-stu-id="9c9e4-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="9c9e4-125">O módulo retornado para o cmdlet **Get-CsTenant** será o módulo que contém todos os cmdlets do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="9c9e4-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="9c9e4-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="9c9e4-126">See Also</span></span>


<span data-ttu-id="9c9e4-127">[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9c9e4-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

