---
title: 'Lync Server 2013: opções de bypass de mídia global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Opções de bypass de mídia global no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

<div>


> [!NOTE]  
> Este tópico pressupõe que você já configurou a bypass de mídia para qualquer tronco para um par (um gateway PSTN (rede telefônica pública comutada), um PBX IP ou um controlador de borda de sessão (SBC) em um provedor de serviços de telefonia pela Internet para um site ou serviço específico para Qual você deseja que a mídia ignore o servidor de mediação.



</div>

Além de habilitar o bypass de mídia para conexões individuais de tronco associadas a um par, você deve também habilitá-lo globalmente. As configurações globais de bypass de mídia podem tanto especificar que o bypass de mídia sempre recebe tentativas de chamadas para o PSTN ou que o bypass de mídia é implantado usando o mapeamento de subredes para sites de rede e regiões de rede - similar ao que é feito pelo controle de admissão de chamada, outro recurso de voz avançado. Quando o bypass de mídia e o controle de admissão de chamadas estão ativados a região de rede, o site de rede e as informações da subrede especificadas pelo controle de admissão de chamada são usados automaticamente ao determinar se usam ou não o bypass de mídia. Isso significa que você não pode especificar se o bypass de mídia sempre recebe tentativas de chamada para o PSTN quando o controle de admissão de chamada está ativado.

Este tópico descreve como usar o painel de controle do Lync Server e o Shell de gerenciamento do Lync Server juntos para definir configurações de bypass de mídia global.

<div>


> [!NOTE]  
> Ao usar estas etapas para configurar o bypass de mídia, pressupõe-se que você possui uma boa conectividade entre os clientes e o par do Servidor de Mediação (por exemplo, um gateway PSTN, um IP-PBX ou um SBC em um provedor de tronco SIP). Se houver qualquer limitação de largura de banda no link, o bypass de mídia não poderá ser aplicado na chamada. O bypass de mídia não interopera com todos os gateways PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no programa de interoperabilidade aberta da comunicação <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>unificada – Lync Server em.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Próximas etapas: escolher configurações de bypass de mídia global

Depois de habilitar a opção ignorar mídia em qualquer conexão de tronco a um par de sites ou serviços específicos, use o seguinte conteúdo para:

  - Habilite o bypass de mídia sempre, conforme descrito em [Configurar o bypass de mídia no Lync Server 2013 para sempre ignorar o servidor de mediação](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - Ou configure o bypass de mídia para usar as informações do site e da região, conforme descrito em [configurar as configurações globais do bypass de mídia no Lync Server 2013 para usar as informações do site e da região](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Associar uma subrede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Configurar bypass de mídia no Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Bypass de mídia e Servidor de Mediação no Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

