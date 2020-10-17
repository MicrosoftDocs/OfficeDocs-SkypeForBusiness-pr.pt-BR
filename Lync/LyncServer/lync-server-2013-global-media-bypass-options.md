---
title: 'Lync Server 2013: opções de bypass de mídia global'
description: 'Lync Server 2013: opções de bypass de mídia global.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554547"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a>Opções de bypass de mídia global no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

<div>


> [!NOTE]  
> Este tópico pressupõe que você já tenha configurado o bypass de mídia para qualquer tronco para um ponto (um gateway PSTN (rede telefônica pública comutada), um IP-PBX ou um SBC (controlador de borda de sessão) em um provedor de serviços de telefonia da Internet) para um site ou serviço específico para o qual você deseja que a mídia ignore o servidor de mediação.



</div>

Além de habilitar o bypass de mídia para conexões individuais de tronco associadas a um par, você deve também habilitá-lo globalmente. As configurações de bypass de mídia global podem especificar que o bypass de mídia sempre é tentado para chamadas para o PSTN, ou que o bypass de mídia seja empregado usando o mapeamento de sub-redes para sites de rede e regiões de rede, semelhante ao que é feito pelo controle de admissão de chamada, outro recurso de voz avançado. Quando o bypass de mídia e o controle de admissão de chamada são habilitados, a região de rede, o local de rede e as informações de sub-rede especificadas para o controle de admissão de chamada são usados automaticamente ao determinar se o bypass de mídia deve ser usado. Isso significa que você não pode especificar que o bypass de mídia sempre seja tentado para chamadas para o PSTN quando o controle de admissão de chamadas estiver habilitado.

Este tópico descreve como usar o painel de controle do Lync Server e o Shell de gerenciamento do Lync Server juntos para definir as configurações de bypass de mídia global.

<div>


> [!NOTE]  
> Ao usar estas etapas para configurar o bypass de mídia, pressupõe-se que você possui uma boa conectividade entre os clientes e o par do Servidor de Mediação (por exemplo, um gateway PSTN, um IP-PBX, ou um SBC em um provedor de tronco SIP). Se houver qualquer limitação de largura de banda no link, o bypass de mídia não poderá ser aplicado na chamada. O bypass de mídia não interopera com todos os gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações unificativas – Lync Server em <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Próximas etapas: definir as configurações globais do bypass de mídia

Depois de habilitar o bypass de mídia em quaisquer conexões tronco para um par de sites específicos ou serviços, use o seguinte conteúdo para:

  - Habilitar o bypass de mídia sempre, conforme descrito em [Configure Media bypass in Lync Server 2013 para sempre ignorar o servidor de mediação](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - Ou configure o bypass de mídia para usar informações de site e de região, conforme descrito em [Configure Media bypass Global Settings in Lync Server 2013 to use site and Region Information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Configurar bypass de mídia no Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Bypass de mídia e servidor de mediação no Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

