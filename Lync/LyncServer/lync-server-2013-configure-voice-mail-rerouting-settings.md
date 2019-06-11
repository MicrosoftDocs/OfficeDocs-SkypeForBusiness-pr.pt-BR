---
title: 'Lync Server 2013: Definir configurações de reroteamento de caixa postal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Definir configurações de reroteamento de caixa postal no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Os aparelhos de ramificação sobreviventes e os servidores de filiais sobreviventes podem fornecer impossibilitação da caixa postal para os usuários da filial durante uma interrupção da WAN, se o Exchange Unified Messaging (UM) estiver instalado no site central e um assistente de troca automática de mensagem do Exchange (AA) estiver implantado. Recomendamos que o administrador do Exchange configure o AA para aceitar somente mensagens, o que desabilita outras funcionalidades genéricas, como transferência para um usuário ou transferência para um operador. Você também pode usar um AA genérico ou um AA personalizado para encaminhar a chamada.

Para obter detalhes, consulte a seção "preparando a imsustentabilidade da caixa postal" dos [requisitos de resiliência de site para o Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) na documentação de planejamento.

<div>

## <a name="to-configure-voice-mail-survivability"></a>Para configurar a imsustentabilidade da caixa postal

1.  Peça ao administrador do Exchange para configurar o AA para aceitar somente mensagens (no Shell do Exchange Use o seguinte cmdlet: **set- \<UMAutoAttendant AA\> nome-CallSomeoneEnabled $false**. O parâmetro que especifica a permissão para deixar mensagens (*SendVoiceMsgEnabled*) é verdadeiro por padrão.

2.  No Shell de gerenciamento do Lync Server, use o cmdlet **New-CSVoiceMailReroutingConfiguration** para definir o número de telefone AA como o número de telefone do atendedor automático do Exchange na caixa de entrada de redirecionamento de correio de voz na ramificação da ramificação sobreviventes ou Servidor de ramificação sobreviventes.
    
    <div>
    

    > [!NOTE]  
    > Se você precisar modificar a configuração de redirecionamento de caixa postal mais tarde, use o cmdlet <STRONG>set-CsVoiceMailReRoutingConfiguration</STRONG> para fazer isso. Para obter detalhes, sobre <STRONG>novo-</STRONG> e <STRONG>set-CSVoiceMailReroutingConfiguration</STRONG>, nos tópicos da ajuda do Shell.

    
    </div>

3.  Defina o número de acesso do assinante do Exchange UM que corresponda ao plano de discagem de UM do usuário da filial como o número de acesso do assinante do Exchange na configuração de redirecionamento de caixa postal para o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes.
    
    <div>
    

    > [!NOTE]  
    > Configure o plano de discagem dos usuários do Exchange UM para que haja apenas um plano de discagem associado a todos os usuários da filial que precisam acessar a funcionalidade obter caixa postal durante uma falha de WAN.

    
    </div>

**Próxima etapa** para aparelhos de ramificação sobreviventes ou servidores de filiais sobreviventes: [usuários domésticos em um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

