---
title: Diretrizes de implantação para o Servidor de Mediação no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Este tópico descreve as diretrizes de planejamento para a implantação do Servidor de Mediação.
ms.openlocfilehash: 245916286fe5f1590581989b8a09daf637c03aa9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800081"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Diretrizes de implantação para o Servidor de Mediação no Skype for Business Server
 
Este tópico descreve as diretrizes de planejamento para a implantação do Servidor de Mediação.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de Mediação Autônomo ou Autônomo?

O Servidor de Mediação é, por padrão, alocado no servidor Standard Edition ou servidor front-end em um pool de front-end nos sites centrais. O número de chamadas PSTN que podem ser tratadas e o número de máquinas necessárias no pool dependerá de:
  
- O número de pares de gateway que o pool do Servidor de Mediação controla.
    
- Os períodos de tráfego de alto volume por meio desses gateways.
    
- A porcentagem de chamadas cuja mídia ignora o Servidor de Mediação.
    
Ao planejar, certifique-se de levar em conta os requisitos de processamento de mídia para chamadas PSTN e conferências A/V que não suportam bypass de mídia, bem como o processamento necessário para lidar com as interações de sinalização para o número de chamadas em horário de pico que precisam de suporte. Se você não tiver CPU suficiente, será necessário implantar um pool autônomo de Servidores de Mediação. Além disso, gateways PSTN, IP-PBXs e SBCs precisarão ser divididos em subconjuntos controlados pelos Servidores de Mediação em um pool e os Servidores de Mediação autônomos em um ou mais pools autônomos.
  
Se você implantou gateways PSTN, IP-PBXs ou Controladores de Borda de Sessão (SBCs) que não têm a capacidade de interagir com um pool de Servidores de Mediação, eles precisarão ser associados a um pool autônomo que consiste em um único Servidor de Mediação. Algumas das coisas que seus gateways PSTN, IP-PBXs ou SBCs precisariam fazer incluem:
  
- Execute o balanceamento de carga DNS (Sistema de Nomes de Domínio) da camada de rede nos Servidores de Mediação em um pool (ou roteia o tráfego uniformemente para todos os Servidores de Mediação em um pool).
    
- Aceitar tráfego de qualquer Servidor de Mediação em um pool.
    
Você pode usar a Ferramenta de Planejamento do Skype for Business para avaliar se colocar o Servidor de Mediação com seu pool de Front-End pode lidar com a carga. Se seu ambiente não conseguir atender a esses requisitos, você precisará implantar um pool de Servidor de Mediação autônomo.
  
## <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o site central e site de filial

 Os servidores de mediação no site central podem ser usados para rotear chamadas para gateways IP PBXs ou PSTN em sites de flial. No entanto, se você implantar troncos SIP, será preciso implantar um Servidor de Mediação no local onde termina cada tronco. Ter um Servidor de Mediação no site central roteia chamadas para um IP-PBX ou gateway PSTN em um site de filial não exige o uso de bypass de mídia, mas um bypass de mídia é recomendado. Isso porque, se você puder habilitar o bypass de mídia, isso reduzirá a latência do caminho de mídia e, consequentemente, resultará em uma qualidade de mídia aprimorada porque o caminho de mídia não é necessário para seguir o caminho de sinalização. O bypass de mídia também irá diminuir a carga de processamento no pool.
  
> [!NOTE]
> O bypass de mídia não interopera com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com o IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no Programa de Interoperabilidade Aberta de Comunicações Unificadas - Lync Server em Explorar dispositivos, infraestrutura e ferramentas testados que suportam e estendem sua experiência do [Skype for Business.](http://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
Se a flexibilidade do site de filial for necessária, um Aparelho de Filial Persistente ou uma combinação de um servidor Front-End, um servidor de mediação e um gateway devem ser implantados na filial. (A suposição com a resiliência do site de filial é que a presença e a conferência não são resilientes no site.) Para obter orientação sobre o planejamento de voz no site de filial, consulte Plano de [resiliência](../enterprise-voice-solution/enterprise-voice-resiliency.md)do Enterprise Voice no Skype for Business Server.
  
Para interações com um IP-PBX, se o IP-PBX não suportar corretamente interações de mídia inicial com várias caixas de diálogo anteriores e interações RFC 3960, poderá haver corte das primeiras palavras da saudação para chamadas de entrada do IP-PBX para pontos de extremidade do Lync. Esse comportamento pode ser mais grave se um servidor de mediação em um site central estiver roteando chamadas a um PBX IP onde a rota termina em um site de filial, porque é necessário mais tempo para concluir a sinalização. Se você experimentar esse comportamento, implantar um Servidor de Mediação no site de filial é a única maneira de reduzir o recorte das primeiras palavras.
  
Finalmente, se o site central tiver um PBX TDM ou se o IP-PBX não elimina a necessidade de um gateway PSTN, você deve implantar um gateway na rota de chamada que conecta o servidor de mediação e o PBX.
  
> [!NOTE]
> Para melhorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede nesses servidores. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "[Receive-Side Scaling Enhancements in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)". Para obter detalhes sobre como habilitar o RSS, consulte a documentação do adaptador de rede. 
  

