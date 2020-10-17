---
title: Combinar cmdlets do Skype for Business online com outros cmdlets do Windows PowerShell no
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb395820f9f90060ac24b737fab08c7d615727c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499608"
---
# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Combinar cmdlets do Skype for Business online com outros cmdlets do Windows PowerShell no

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-05_

Quando você se conecta ao Skype for Business online usando o Windows PowerShell, aproximadamente 40 os cmdlets do Skype for Business online estarão disponíveis para uso. No entanto, você não está limitado a usar apenas os cmdlets 40 ao gerenciar o Skype for Business online. Além dos cmdlets do Skype for Business Online, você também pode usar quaisquer outros cmdlets do Windows PowerShell instalados no computador. (Quando você instala o Windows PowerShell 3,0, centenas de cmdlets principais do Windows PowerShell também estão instalados.) Seus comandos podem misturar e combinar cmdlets do Skype for Business Online e quaisquer outros cmdlets disponíveis no computador.

Embora um curso completo no Windows PowerShell 3,0 ultrapasse o escopo deste artigo, aqui estão alguns exemplos que mostram por que você pode querer misturar e combinar cmdlets. Em primeiro lugar, nenhum dos cmdlets do Skype for Business Online inclui um comando Print e nenhum comando desse tipo pode ser encontrado no console do Windows PowerShell. Então, como você obtém uma cópia impressa das informações recuperadas por um cmdlet? Uma maneira é recuperar as informações e enviá-las para o cmdlet **Out-Printer** :

    Get-CsTenant | Out-Printer

Como nenhum parâmetro adicional é incluído, todas as informações retornadas pelo cmdlet **Out-Printer** serão impressas na impressora padrão.

Da mesma forma, nenhum cmdlet do Skype for Business Online inclui um parâmetro que permite salvar dados em um arquivo. Mas tudo bem: este comando usa o cmdlet **Out-File** para salvar as informações retornadas no arquivo de texto C: \\ logs \\Tenants.txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

E este comando usa o cmdlet **Select-Object** para limitar os dados retornados e exibidos na tela. Neste exemplo, o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) recupera as informações de todos os seus usuários do Skype for Business Online e, em seguida, o cmdlet **Select-Object** é usado para limitar os dados exibidos ao valor de identidade do usuário e sua política de arquivamento:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Como haverá centenas de cmdlets disponíveis para uso no computador, você pode ter dificuldade para determinar quais cmdlets são cmdlets do Skype for Business Online e quais não são. Para retornar uma lista dos cmdlets do Skype for Business online (e somente os cmdlets do Skype for Business online), primeiro você deve determinar o nome do módulo do Windows PowerShell temporário que contém todos os cmdlets do Skype for Business online. Para tanto, execute este comando a partir do prompt do Windows PowerShell:

    Get-Module

As informações semelhantes às seguintes serão exibidas na tela:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

O módulo com o script ModuleType é o módulo que contém os cmdlets do Skype for Business online. Para retornar uma lista desses cmdlets, execute o cmdlet **Get-Command** , usando o nome do módulo de script como o nome do módulo:

    Get-Command -Module tmp_5astd3uh.m5v

É possível que você possa ter vários módulos com um ModuleType igual a script. Nesse caso, você pode executar o seguinte comando para descobrir qual módulo inclui o cmdlet **Get-CsTenant** :

    Get-Command Get-CsTenant

O módulo retornado para o cmdlet **Get-CsTenant** será o módulo que contém todos os cmdlets do Skype for Business Online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Confira também


[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

