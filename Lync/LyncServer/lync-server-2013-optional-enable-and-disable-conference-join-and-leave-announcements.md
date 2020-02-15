---
title: Opcion Habilitar e desabilitar comunicados de ingresso e saída de conferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b18dadbb4b7dc5a35f8688c46f2836b46cb55a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>Opcion Habilitar e desabilitar comunicados de ingresso e saída de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-30_

Quando usuários de discagem ingressam ou saem de uma conferência, o aplicativo comunicado de conferência pode anunciar sua entrada ou saída tocando um tom ou dizendo seus nomes. Você pode alterar o funcionamento de comunicados executando cmdlets. Esta etapa é opcional.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar o comportamento de anúncio de ingresso e saída de conferência

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-ServerAdministrator** ou **CsAdministrator**.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Execute o seguinte no prompt de comando:
    
        Get-CsDialinConferencingConfiguration
    
    Este cmdlet recupera as informações sobre se os participantes precisam registrar seus nomes ao ingressar em uma conferência e como o Lync Server responde quando os participantes ingressam ou saem de uma conferência discada.

4.  Execute o seguinte no prompt de comando:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   determina se os participantes anônimos são solicitados a gravar seu nome antes de entrar na conferência. O valor padrão é "$true", que significa que os participantes receberão essa solicitação. (Os participantes autenticados não registram seus nomes, pois em vez disso exibem seus nomes de exibição.)
    
    **EntryExitAnnouncementsEnabledByDefault**   indica se os comunicados estão ativados ou desativados por padrão. O valor padrão é "$false", que significa que, por padrão, não anúncios quando os participantes ingressam ou saem de uma conferência. O organizador da reunião pode substituir essa configuração ao agendar uma reunião.
    
    **EntryExitAnnouncementsType**   indica a ação tomada sempre que um participante entra ou sai de uma conferência para a qual comunicados estão habilitados. O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer ingressou na conferência" quando os anúncios estão ativados.
    
    É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.
    
    Por exemplo:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    Neste exemplo, as configurações estão definidas no escopo do site para Redmond. Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência. Um tom é reproduzido quando os participantes entram e saem de uma conferência.

</div>

</div>

<span> </span>

</div>

</div>

</div>

