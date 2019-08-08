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

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Combinando cmdlets do Skype for Business online com outros cmdlets do Windows PowerShell no

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-05_

Quando você se conecta ao Skype for Business online usando o Windows PowerShell, cerca de 40 cmdlets do Skype for Business online estarão disponíveis para uso. No entanto, você não está limitado a usar apenas os cmdlets do 40 ao gerenciar o Skype for Business online. Além dos cmdlets do Skype for Business Online, você também pode usar quaisquer outros cmdlets do Windows PowerShell instalados no seu computador. (Quando você instala o Windows PowerShell 3,0, centenas de cmdlets do Windows PowerShell básicos também são instalados.) Seus comandos podem misturar e combinar cmdlets do Skype for Business Online e quaisquer outros cmdlets disponíveis no seu computador.

Embora um curso completo do Windows PowerShell 3,0 ultrapasse o escopo deste artigo, aqui estão alguns exemplos que mostram porque você pode querer combinar e comparar cmdlets. Em primeiro lugar, nenhum dos cmdlets do Skype for Business Online inclui um comando de impressão, e esse comando não pode ser encontrado no console do Windows PowerShell. Então, como você obtém uma cópia impressa das informações recuperadas por um cmdlet? Uma maneira é recuperar as informações e, em seguida, enviar essas informações para o cmdlet **Out-Printer** :

    Get-CsTenant | Out-Printer

Como nenhum parâmetro adicional está incluído, todas as informações retornadas pelo cmdlet **Out-Printer** serão impressas na impressora padrão.

Da mesma forma, nenhum dos cmdlets do Skype for Business Online inclui um parâmetro que permite salvar dados em um arquivo. Mas isso é certo: esse comando usa o cmdlet **Out-File** para salvar as informações retornadas no arquivo de texto C\\:\\registra locatários. txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

E esse comando usa o cmdlet **Select-Object** para limitar os dados que são retornados e exibidos na tela. Neste exemplo, o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) recupera informações de todos os seus usuários do Skype for Business Online e, em seguida, o cmdlet **Select-Object** é usado para limitar os dados exibidos ao valor de identidade do usuário e às políticas de arquivamento:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Como há centenas de cmdlets disponíveis para serem usados em seu computador, você pode ter dificuldade em determinar quais cmdlets são cmdlets do Skype for Business Online e quais não são. Para retornar uma lista dos cmdlets do Skype for Business online (e somente cmdlets do Skype for Business online), primeiro você deve determinar o nome do módulo do Windows PowerShell temporário que contém todos os cmdlets do Skype for Business online. Para fazer isso, execute este comando a partir do prompt do Windows PowerShell:

    Get-Module

As informações semelhantes às seguintes serão exibidas na tela:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

O módulo com o script ModuleType é o módulo que contém os cmdlets do Skype for Business online. Para retornar uma lista desses cmdlets, execute o cmdlet **Get-Command** usando o nome do módulo de script como o nome do módulo:

    Get-Command -Module tmp_5astd3uh.m5v

É possível que você tenha vários módulos com um ModuleType igual a script. Nesse caso, você pode executar o seguinte comando para descobrir qual módulo inclui o cmdlet **Get-CsTenant** :

    Get-Command Get-CsTenant

O módulo retornado para o cmdlet **Get-CsTenant** será o módulo que contém todos os cmdlets do Skype for Business Online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Confira também


[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

