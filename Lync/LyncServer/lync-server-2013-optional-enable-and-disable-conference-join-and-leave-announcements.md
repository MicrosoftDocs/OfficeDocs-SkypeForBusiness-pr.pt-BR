---
title: (Opcional) Habilitar e desabilitar comunicados de ingresso e saída de conferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 778969dfa5ed6b84fdbcd2b204e497f8d649f1a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>(Opcional) Habilitar e desabilitar comunicados de ingresso e saída de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-30_

Quando os usuários de discagem entram ou deixam uma conferência, o aplicativo de anúncio de conferência pode anunciar a entrada ou a saída tocando um tom ou dizendo seus nomes. Você pode alterar como os comunicados funcionam Executando cmdlets. Esta etapa é opcional.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar o comportamento de anúncio de ingresso e saída de conferência

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **cs-ServerAdministrator** ou **CsAdministrator** .

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute o seguinte no prompt de comando:
    
        Get-CsDialinConferencingConfiguration
    
    Esse cmdlet recupera informações sobre a necessidade de os participantes gravarem o nome ao ingressar em uma conferência e como o Lync Server responde quando os participantes ingressam ou deixam uma conferência discada.

4.  Execute o seguinte no prompt de comando:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **O EnableNameRecording**   determina se os participantes anônimos devem gravar o nome antes de entrar na conferência. O valor padrão é "$true", que significa que os participantes receberão essa solicitação. (Os participantes autenticados não registram seus nomes porque seu nome de exibição é utilizado.)
    
    **EntryExitAnnouncementsEnabledByDefault**   indica se os comunicados estão ativados ou desativados por padrão. O valor padrão é "$false", o que significa que, por padrão, não há anúncios quando os participantes participam ou saem de uma conferência. O organizador da reunião pode substituir essa configuração ao agendar uma reunião.
    
    **EntryExitAnnouncementsType**   indica a ação tomada sempre que um participante entra ou sai de uma conferência para a qual os comunicados são habilitados. O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer está participando da conferência" quando os anúncios são ativados.
    
    É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.
    
    Por exemplo:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    Neste exemplo, as configurações são configuradas no escopo do site de Redmond. Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência. Um tom é tocado quando os participantes entram ou deixam uma conferência.

</div>

</div>

<span> </span>

</div>

</div>

</div>

