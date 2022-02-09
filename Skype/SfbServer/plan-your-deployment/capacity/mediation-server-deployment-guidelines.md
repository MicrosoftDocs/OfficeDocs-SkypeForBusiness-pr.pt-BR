---
title: Diretrizes de implantação para o Servidor de Mediação Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Este tópico descreve diretrizes de planejamento para implantação do Servidor de Mediação.
ms.openlocfilehash: 1b5f628f544cafb358b58d325c5d077aef783a89
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397615"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Diretrizes de implantação para o Servidor de Mediação Skype for Business Server
 
Este tópico descreve diretrizes de planejamento para implantação do Servidor de Mediação.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de Mediação Alocado ou Autônomo?

O Servidor de Mediação é, por padrão, alocado no servidor Edição Standard ou servidor front-end em um pool de Front-End em sites centrais. O número de chamadas PSTN (rede telefônica pública comutado) que podem ser manipuladas e o número de máquinas necessárias no pool dependerá de:
  
- O número de pares de gateway que o pool do Servidor de Mediação controla.
    
- Os períodos de tráfego de alto volume através desses gateways.
    
- A porcentagem de chamadas que são chamadas cuja mídia ignora o Servidor de Mediação.
    
Ao planejar, leve em conta os requisitos de processamento de mídia para chamadas PSTN e conferências A/V que não suportam bypass de mídia, bem como o processamento necessário para lidar com interações de sinalização para o número de chamadas de horário de trabalho que precisam ser suportadas. Se você não tiver CPU suficiente, precisará implantar um pool autônomo de Servidores de Mediação. Além disso, gateways PSTN, IP-PBXs e SBCs precisarão ser divididos em subconjuntos controlados pelos Servidores de Mediação alocados em um pool e os Servidores de Mediação autônomos em um ou mais pools autônomos.
  
Se você implantou gateways PSTN, IP-PBXs ou Controladores de Borda de Sessão (SBCs) que não têm a capacidade de interagir com um pool de Servidores de Mediação, eles precisarão ser associados a um pool autônomo que consiste em um único Servidor de Mediação. Algumas das coisas que seus gateways PSTN, IP-PBXs ou SBCs precisariam fazer incluem:
  
- Execute o balanceamento de carga DNS (Sistema de Nomes de Domínio de Camada de Rede) em servidores de mediação em um pool (ou roteia o tráfego uniformemente para todos os Servidores de Mediação em um pool).
    
- Aceite o tráfego de qualquer Servidor de Mediação em um pool.
    
Você pode usar a ferramenta de planejamento Skype for Business para avaliar se a localização do Servidor de Mediação com o pool de Front-End pode manipular a carga. Se seu ambiente não puder atender a esses requisitos, você precisará implantar um pool de Servidor de Mediação autônomo.
  
## <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o site central e site de filial

 Os servidores de mediação no site central podem ser usados para rotear chamadas para gateways IP PBXs ou PSTN em sites de flial. No entanto, se você implantar troncos SIP, será preciso implantar um Servidor de Mediação no site em que cada tronco será encerrado. Ter um Servidor de Mediação no site central roteia chamadas para um gateway IP-PBX ou PSTN em um site de filial não exige o uso de bypass de mídia, mas um bypass de mídia é recomendado. Isso porque, se você puder habilitar o bypass de mídia, ele reduzirá a latência do caminho de mídia e, consequentemente, resultará em melhor qualidade de mídia, pois o caminho de mídia não é necessário para seguir o caminho de sinalização. O bypass de mídia também irá diminuir a carga de processamento no pool.
  
> [!NOTE]
> O bypass de mídia não interopera com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e fez alguns testes com o Cisco IP-PBXs. O bypass de mídia é suportado apenas com produtos e versões listados no Programa de Interoperabilidade Aberta de Comunicações Unificadas - Lync Server no [Explore tested devices, infrastructure, and tools](http://partnersolutions.skypeforbusiness.com/solutionscatalog) that support and extend your Skype for Business experience. 
  
Se a flexibilidade do site de filial for necessária, um Aparelho de Filial Persistente ou uma combinação de um servidor Front-End, um servidor de mediação e um gateway devem ser implantados na filial. (A suposição com a resiliência do site de filial é que a presença e a conferência não são resilientes no site.) Para obter orientações sobre o planejamento de site de filial para voz, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Para interações com um IP-PBX, se o IP-PBX não suportar corretamente interações de mídia interações de mídia inicial com várias caixas de diálogo interações anteriores e RFC 3960, pode haver recorte das primeiras poucas palavras da saudação para chamadas de entrada dos pontos de extremidade IP-PBX para Lync. Esse comportamento pode ser mais grave se um servidor de mediação em um site central estiver roteando chamadas a um PBX IP onde a rota termina em um site de filial, porque é necessário mais tempo para concluir a sinalização. Se você experimentar esse comportamento, implantar um Servidor de Mediação no site de filial é a única maneira de reduzir o recorte das primeiras palavras.
  
Finalmente, se o site central tiver um PBX TDM ou se o IP-PBX não elimina a necessidade de um gateway PSTN, você deve implantar um gateway na rota de chamada que conecta o servidor de mediação e o PBX.
  
> [!NOTE]
> Para melhorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (dimensionamento do lado de recebimento) nos adaptadores de rede nesses servidores. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "[Aprimoramentos de dimensionamento](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) do lado do recebimento no Windows Server". Para obter detalhes sobre como habilitar o RSS, consulte a documentação do adaptador de rede. 
