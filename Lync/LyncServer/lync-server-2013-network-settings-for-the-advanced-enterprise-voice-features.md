---
title: 'Lync Server 2013: configurações de rede para os recursos avançados de voz empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce4983f7744158c9c9ff56cdfdde818fdc8e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Network settings for the advanced Enterprise Voice features in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-10_

O Lync Server tem três recursos avançados do Enterprise Voice: controle de admissão de chamadas (CAC), serviços de emergência (E9-1-1) e bypass de mídia. Esses recursos compartilham determinados requisitos de configuração para regiões de rede, sites de rede e Associação de cada sub-rede na topologia do Lync Server com um site de rede. Para obter detalhes sobre como planejar a implantação desses recursos, consulte:

  - [Planejamento para controle de admissão de chamada no Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Planejamento para serviços de emergência (E9-1-1) no Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Para obter detalhes sobre como implantar cada um desses recursos, consulte [implantando recursos avançados do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) na documentação de implantação.

Este tópico fornece uma visão geral dos requisitos de configuração que são comuns a todos os três recursos avançados do Enterprise Voice.

<div>

## <a name="network-regions"></a>Regiões de Rede

Uma região de rede é um hub de rede ou backbone de rede usada somente na configuração do serviço de controle de admissão de chamadas (CAC),  E9-1-1 e bypass de mídia.

<div>


> [!NOTE]  
> As regiões de rede não são iguais às regiões de conferência discada do Lync Server, que são necessárias para associar números de acesso de conferência discada com um ou mais planos de discagem do Lync Server. Para obter detalhes sobre regiões de conferência discada, consulte <A href="lync-server-2013-dial-in-conferencing-requirements.md">requisitos de conferência discada no Lync Server 2013</A> na documentação de planejamento.



</div>

O CAC requer que todas as regiões de rede tenham um site central do Lync Server associado, que gerencia o tráfego de mídia dentro da região (isto é, toma decisões com base em políticas que você configurou, em relação a se ou não uma sessão de áudio ou de vídeo em tempo real pode ser estabelecida). Os sites centrais do Lync Server não representam locais geográficos, mas em vez de grupos lógicos de servidores que são configurados como um pool ou um conjunto de pools. Para obter detalhes sobre sites centrais, consulte [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md) na documentação de planejamento. Consulte também [topologias compatíveis no Lync Server 2013](lync-server-2013-supported-topologies.md) na documentação de suporte.

Para configurar uma região de rede, você pode usar a guia **regiões** na seção **configuração de rede** do painel de controle do Lync Server ou executar os cmdlets do Shell de gerenciamento do Lync Server **New-CsNetworkRegion** ou **set-CsNetworkRegion** . Para obter instruções, consulte [criar ou modificar uma região de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Lync Server.

As mesmas definições de região de rede são compartilhadas por todos os três recursos avançados do Enterprise Voice. Se você já criou áreas de rede para um recurso, não será necessário criar novas regiões de rede para outros recursos. No entanto, pode ser necessário modificar uma definição de região de rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você criou áreas de rede para E9-1-1 (que não requer um site central associado) e posteriormente implantou o serviço de controle de admissão de chamadas, é necessário modificar cada uma das definições de região de rede para especificar um site central.

Para associar um site central do Lync Server a uma região de rede, especifique o nome do site central, seja usando a seção **configuração de rede** do painel de controle do Lync Server ou executando os cmdlets shell do Shell de gerenciamento do Lync Server **New-CsNetworkRegion** ou **set-CsNetworkRegion** . Para obter instruções, consulte [criar ou modificar uma região de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="network-sites"></a>Sites de rede

Um site de rede representa uma localização geográfica, como um escritório principal, filiais ou regionais. Cada site de rede deve ser associado a uma região específica de rede.

<div>


> [!NOTE]  
> Os sites de rede são usados somente pelos recursos avançados de voz da empresa. Eles não são iguais aos dos sites de ramificação que você configurou na sua topologia do Lync Server. Para obter detalhes sobre sites de filiais, consulte <A href="lync-server-2013-reference-topologies.md">topologias de referência no Lync Server 2013</A> na documentação de planejamento. Consulte também <A href="lync-server-2013-supported-topologies.md">topologias compatíveis no Lync Server 2013</A> na documentação de suporte.



</div>

Para configurar um site de rede e associá-lo a uma região de rede, você pode usar a seção **configuração de rede** do painel de controle do Lync Server ou executar cmdlets **New-CsNetworkSite** ou **set-CsNetworkSite** do Shell de gerenciamento do Lync Server. Para obter detalhes, consulte [criar ou modificar um site de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="identify-ip-subnets"></a>Identifique as subredes IP

Para cada site de rede, você precisará trabalhar com seu administrador de rede para determinar quais subredes IP são atribuídas a cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho fica muito mais simples.

No exemplo, o site de Nova York na região da América do Norte pode ser atribuído às seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suponha que Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento. Quando ele liga o computador e se conecta à rede, seu computador terá um endereço IP em um dos quatro intervalos alocados para Nova York, por exemplo 172.29.80.103.

<div>


> [!WARNING]  
> As subredes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato oferecido por computadores clientes para poder ser usado adequadamente pelo bypass de mídia. Um cliente do Lync assume seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar o ID de bypass associado com cada cliente, o Registrador irá comparar a lista de subredes IP associadas com cada local de rede na subrede oferecida pelo cliente para uma correspondência exata. Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais. (Se você implantar o controle de admissão de chamada, mas não o bypass de mídia, o controle de admissão de chamada funcionará mesmo se você configurar as subredes virtuais.)<BR>Por exemplo, se um cliente do Lync entrar em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede IP de 255.255.255.0, ele solicitará o ID de bypass associado à sub-rede 172.29.81.0. Se a subrede for definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0. Portanto, é importante que o administrador insira as sub-redes exatamente como são fornecidas pelos clientes do Lync (que são provisionados com as sub-redes durante a configuração de rede, seja estaticamente ou pelo protocolo DHCP (protocolo de configuração de host dinâmico).)



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>Associando Subredes aos Locais de Rede

Cada subrede na rede corporativa deve ser associado um site de rede (ou seja, cada sub-rede deve ser associada a uma localização geográfica). Essa associação de sub-redes habilita os recursos avançados de voz empresarial para localizar os pontos de extremidade geograficamente. Por exemplo, localizar os pontos de extremidade permite que o CAC regule o fluxo de áudio e dados de vídeo em tempo real indo e voltando do local de rede.

Para associar sub-redes a sites de rede, você pode usar a seção **configuração de rede** do painel de controle do Lync Server ou pode usar o Shell de gerenciamento do Lync Server. Para obter instruções, confira [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento para controle de admissão de chamada no Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Planejamento para serviços de emergência (E9-1-1) no Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

