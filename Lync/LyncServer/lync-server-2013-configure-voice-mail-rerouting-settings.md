---
title: 'Lync Server 2013: definir configurações de reencaminhamento de caixa postal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f327bfc533b28313e4728b13c7a69d6c16bc034
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Definir configurações de reencaminhamento de caixa postal no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Os aparelhos de filial persistente e servidores de filial persistente podem fornecer sustentabilidade da caixa postal para usuários de filial durante uma interrupção da WAN, se o Unificação de mensagens (UM) do Exchange estiver instalado no site central e um atendedor automático de mensagem de UM do Exchange estiver implantado. Recomendamos que o seu administrador do Exchange configure o AA para aceitar somente mensagens, o que desabilitará outra funcionalidade genérica, como a transferência para um usuário ou a transferência para uma telefonista. Como alternativa, você poderia usar um AA genérico ou um AA personalizado para rotear a chamada.

Para obter detalhes, consulte a seção "preparando para a persistência de caixa postal" de [requisitos de resiliência de site de filial para o Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) na documentação de planejamento.

<div>

## <a name="to-configure-voice-mail-survivability"></a>Para configurar a sustentabilidade da caixa postal

1.  Peça ao administrador do Exchange para configurar o AA para aceitar apenas mensagens (no Shell do Exchange Use o seguinte cmdlet: **set- \<UMAutoAttendant AA\> Name-CallSomeoneEnabled $false**. O parâmetro que especifica que se permita deixar mensagens ( *SendVoiceMsgEnabled*) é verdadeiro por padrão.

2.  No Shell de gerenciamento do Lync Server, use o cmdlet **New-CSVoiceMailReroutingConfiguration** para definir o número de telefone AA como o número de telefone do atendedor automático da um do Exchange na configuração de reencaminhamento de caixa postal no aparelho de filial persistente ou servidor de filial persistente.
    
    <div>
    

    > [!NOTE]  
    > Se você precisar modificar a configuração do roteamento da caixa postal posteriormente, use o cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>. Para obter detalhes, sobre <STRONG>New-</STRONG> e <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, nos tópicos da Ajuda do Shell.

    
    </div>

3.  Defina o número de acesso do assinante da UM do Exchange que corresponde ao plano de discagem de UM do usuário da filial como o número de acesso do assinante do UM do Exchange na configuração de reencaminhamento de caixa postal no aparelho de filial persistente ou servidor de filial persistente.
    
    <div>
    

    > [!NOTE]  
    > Configure o plano de discagem dos usuários de UM do Exchange para que haja apenas um plano de discagem associado a todos os usuários da filial que precisam acessar a funcionalidade obter caixa postal durante uma interrupção da WAN.

    
    </div>

**Próxima etapa** para aparelhos de filial persistente ou servidores de filial persistente: [usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

