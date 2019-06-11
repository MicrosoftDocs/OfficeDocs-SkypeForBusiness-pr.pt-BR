---
title: 'Lync Server 2013: diretrizes de implantação para o servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400f8cceeb86d407297b3f564c01266a477ca0ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Diretrizes de implantação para o servidor de mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-12_

Este tópico descreve diretrizes de planejamento para a implantação do servidor de mediação. Depois de revisar essas diretrizes, recomendamos que você use a ferramenta de planejamento para criar e exibir possíveis topologias alternativas, que podem servir como modelos para o que a topologia personalizada final que você decidir implantar seria parecida com a aparência desejada.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediação autônomo ou posicionado?

O servidor de mediação é posicionado por padrão no servidor Standard Edition ou no servidor front-end em um pool de front-ends em sites centrais. O número de chamadas PSTN (Rede Telefônica Pública Comutada) que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:

  - O número de pares de gateway que o pool do servidor de mediação controla

  - Dos períodos de alto volume de tráfego por meio desses gateways

  - A porcentagem de chamadas que são chamadas cuja mídia ignora o servidor de mediação

Durante o planejamento, considere os requisitos de processamento de mídia das chamadas PSTN e das conferências A/V não configuradas para bypass de mídia, além do processamento necessário para lidar com as interações de sinalização em relação ao número de chamadas em horário de pico que precisam de suporte. Se não houver CPU suficiente, você deve implantar um pool autônomo de servidores de mediação; e os gateways PSTN, PBXs IP e SBCs precisarão ser divididos em subconjuntos controlados pelos servidores de mediação posicionados em um pool e os servidores de mediação autônomos em um ou mais pools autônomos.

Se você implantou gateways PSTN, PBXs de IP ou controladores de borda de sessão (SBCs) que não são compatíveis com os recursos corretos para interagir com um pool de servidores de mediação, incluindo o seguinte, eles precisarão estar associados a um pool autônomo que consiste em de um servidor de mediação único:

  - Executar o balanceamento de carga de DNS (sistema de nomes de domínio) de camada de rede em servidores de mediação em um pool (ou de outra forma rotear uniformemente para todos os servidores de mediação em um pool)

  - Aceitar o tráfego de qualquer servidor de mediação em um pool

Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se colocar o servidor de mediação no seu pool de front-end pode manipular a carga. Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o local central e o local da filial

Os servidores de mediação no site central podem ser usados para direcionar chamadas para IP-PBXs ou gateways PSTN em sites de filiais. No entanto, se você implantar troncos SIP, deve implantar um servidor de mediação no site em que cada tronco termina. Ter um servidor de mediação no site central chamadas de rota para um IP-PBX ou um gateway PSTN em um site de filial não requer o uso do bypass de mídia. No entanto, se você puder habilitar o bypass de mídia, isso reduzirá a latência do caminho de mídia e, consequentemente, resultará em uma qualidade de mídia aprimorada porque o caminho da mídia não é mais necessário para acompanhar o caminho de sinalização. O bypass de mídia também diminuirá a carga de processamento no pool.

<div>


> [!NOTE]  
> O bypass de mídia não interoperará com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no programa de interoperabilidade aberta da comunicação <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>unificada – Lync Server em.



</div>

Se a resiliência do site de ramificação for necessária, um aparelho de ramificação sobreviventes ou uma combinação de um servidor front-end, um servidor de mediação e um gateway devem ser implantados no site da filial. (A pressuposição da resiliência do site da ramificação é que a presença e a conferência não são resistentes no site.) Para obter orientação sobre o planejamento de site de filial para voz, consulte [planejando a resiliência de voz no site de filial no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Para interações com um PBX IP, se o IP-PBX não suportar corretamente interações de mídia antigas com várias caixas de diálogo iniciais e interações RFC 3960, pode haver recorte das primeiras palavras da saudação para as chamadas recebidas dos pontos de extremidade IP-PBX para Lync. Esse comportamento pode ser mais sério se um servidor de mediação em um site central estiver encaminhando chamadas para um PBX IP em que a rota termina em um site de filial, pois é necessária mais tempo para a sinalização ser concluída. Se você tiver esse comportamento, a implantação de um servidor de mediação no site da filial é a única maneira de reduzir o recorte das primeiras palavras.

Por fim, se o seu site central tiver um PBX de TDM, ou se o seu PBX IP não eliminar a necessidade de um gateway PSTN, você deve implantar um gateway no servidor de mediação conectando o servidor de mediação da chamada e o PBX.

<div>


> [!NOTE]  
> Para aprimorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede nesses servidores. O RSS permite que pacotes de entrada sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>Server" em. Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

