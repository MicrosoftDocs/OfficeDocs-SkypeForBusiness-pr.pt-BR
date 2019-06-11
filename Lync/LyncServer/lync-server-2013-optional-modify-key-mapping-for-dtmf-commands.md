---
title: 'Lync Server 2013: (Opcional) Modificar mapeamento principal de comandos DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a9fbe17a07403fbf0195026d44b490680973e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>(Opcional) Modificar mapeamento principal de comandos DTMF no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-30_

Os usuários de conferência discada podem pressionar teclas no teclado do telefone para executar comandos DTMF (multifrequência de tom dual). Comandos DTMF permitem que os usuários que discam para uma conferência controlem as configurações da conferência (como ativar ou desativar o próprio microfone, ou bloquear e desbloquear a conferência) pelo teclado do telefone. Você pode usar cmdlets para modificar as chaves usadas para os comandos DTMF. Esta etapa é opcional.

<div>


> [!NOTE]  
> Para obter detalhes sobre esses cmdlets e as possíveis opções de DTMF, consulte documentação do Shell de gerenciamento do Lync Server ou ajuda da linha de comando do Shell de gerenciamento do Lync Server.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>Para modificar o mapeamento de teclas dos comandos DTMF

1.  Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função **cs-ServerAdministrator** ou **CsAdministrator** .

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute o seguinte no prompt de comando:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Este cmdlet retorna as configurações de DTMF usadas para a conferência discada.

4.  Execute o cmdlet a seguir e especifique a tecla a ser pressionada para cada opção que você deseja alterar:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Esse cmdlet modifica as configurações de DTMF usadas para a conferência discada.
    
    Por exemplo:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    Este exemplo troca a tecla pressionada para habilitar ou desabilitar anúncios e a tecla que é pressionada para ativar e desativar o mudo para todos os participantes. Como nenhuma identidade é especificada, essas alterações se aplicam às configurações de DTMF globais.

5.  (Opcional) Para criar conjuntos adicionais de comandos DTMF para sites específicos, use o cmdlet **New-CsDialinConferencingDtmfConfiguration** com uma identidade de site. Ao criar novas configurações DTMF para sites, as configurações do site têm precedência sobre as configurações globais. Para obter detalhes, consulte documentação do Shell de gerenciamento do Lync Server ou ajuda da linha de comando do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

