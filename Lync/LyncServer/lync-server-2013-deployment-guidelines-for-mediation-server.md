---
title: 'Lync Server 2013: diretrizes de implantação para o servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f55ec3444348b2717721dcad890a4712cd8b9a3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Diretrizes de implantação para o servidor de mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-12_

Este tópico descreve diretrizes de planejamento para a implantação do servidor de mediação. Depois de analisar essas diretrizes, recomendamos que você use a ferramenta de planejamento para criar e exibir possíveis topologias alternativas, que podem servir como modelos para o que a topologia personalizada final que você decidir implantar seria semelhante.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediação autônomo ou posicionado?

O Servidor de mediação é colocado por padrão no servidor Standard Edition ou no servidor Front-End em um pool de Front-End em locais centrais. O número de chamadas de rede telefônica pública comutada (PSTN) que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:

  - O número de pares de gateway que o pool do servidor de mediação controla

  - Os períodos de tráfego de alto volume por meio desses gateways

  - A porcentagem de chamadas que são chamadas cuja mídia ignora o servidor de mediação

Ao planejar, certifique-se de considerar os requisitos de processamento de mídia para chamadas PSTN e conferências A/V que não estão configuradas para bypass de mídia, bem como o processamento necessário para lidar com as interações de sinalização para o número de chamadas em tempo de ocupação que precisam ser suportadas. Se não houver CPU suficiente, você deverá implantar um pool autônomo de servidores de mediação; e os gateways PSTN, IP-PBXs e SBCs precisarão ser divididos em subconjuntos controlados pelos servidores de mediação colocados em um pool e os servidores de mediação autônomos em um ou mais pools autônomos.

Se você implantou gateways PSTN, IP-PBXs ou controladores de borda de sessão (SBCs) que não dão suporte aos recursos corretos para interagir com um pool de servidores de mediação, incluindo o seguinte, eles precisarão ser associados a um pool autônomo que consiste em de um único servidor de mediação:

  - Executar o balanceamento de carga do DNS (sistema de nomes de domínio) da camada de rede nos servidores de mediação em um pool (ou, caso contrário, rotear o tráfego uniformemente para todos os servidores de mediação

  - Aceitar tráfego de qualquer servidor de mediação em um pool

Você pode usar a ferramenta de planejamento do Microsoft Lync Server 2013 para avaliar se a colocação do servidor de mediação com seu pool de front-ends pode lidar com a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o site central e site de filial

Os servidores de mediação no site central podem ser usados para rotear chamadas para gateways IP PBXs ou PSTN em sites de flial. Se você implantar os troncos SIP, no entanto, é necessário implantar um servidor de mediação no site onde termina cada tronco. Com um servidor de mediação no site central para rotear chamadas a um gateway PBX IP ou PSTN de uma filial não requer o uso de bypass de mídia. No entanto, se você pode ativar o bypass de mídia, isso irá reduzir a latência do caminho de mídia e, conseqüentemente, resultar em uma melhor qualidade mídia, porque o caminho de mídia não é mais necessário para seguir o caminho de sinalização. O bypass de mídia também irá diminuir a carga de processamento no pool.

<div>


> [!NOTE]  
> O desvio de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>unificativas – Lync Server em.



</div>

Se a flexibilidade do site de filial for necessária, um Aparelho de Filial Persistente ou uma combinação de um servidor Front-End, um servidor de mediação e um gateway devem ser implantados na filial. (A pressuposição da resiliência do site de filial é que a presença e a conferência não são resistentes no site.) Para obter orientação sobre o planejamento do site de filial para voz, consulte [Planning for Branch-site Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Para interações com um IP-PBX, se o IP-PBX não suportar corretamente interações de mídias antigas com várias caixas de diálogo anteriores e interações RFC 3960, pode haver recorte das primeiras palavras da saudação para chamadas de entrada dos pontos de extremidade IP-PBX para Lync. Esse comportamento pode ser mais grave se um servidor de mediação em um site central estiver roteando chamadas a um PBX IP onde a rota termina em um site de filial, porque é necessário mais tempo para concluir a sinalização. Se você enfrentar esse comportamento, a implantação de um servidor de mediação no site de filial é a única maneira de reduzir o recorte das primeiras palavras.

Finalmente, se o site central tiver um PBX TDM ou se o IP-PBX não elimina a necessidade de um gateway PSTN, você deve implantar um gateway na rota de chamada que conecta o servidor de mediação e o PBX.

<div>


> [!NOTE]  
> Para melhorar o desempenho de mídia do servidor de mediação autônomo, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede nesses servidores. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do recebimento <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>no Windows Server" em. Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

