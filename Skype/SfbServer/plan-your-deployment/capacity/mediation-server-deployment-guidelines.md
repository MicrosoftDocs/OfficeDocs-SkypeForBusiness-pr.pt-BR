---
title: Diretrizes de implantação para o servidor de mediação em Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Este tópico descreve as diretrizes de planejamento para implantação de servidor de mediação.
ms.openlocfilehash: 1a35d2f0bb74cfd78cba8924e6cafb6ce601d647
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896110"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Diretrizes de implantação para o servidor de mediação em Skype para Business Server
 
Este tópico descreve as diretrizes de planejamento para implantação de servidor de mediação.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediação autônomos ou colocados?

Servidor de mediação é, por padrão, colocado no servidor Standard Edition ou servidor Front-End em um pool de Front-End em locais centrais. O número de chamadas da rede telefônica pública comutada (PSTN) que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:
  
- O número de pares de gateway que controla o pool do servidor de mediação.
    
- Períodos de tráfego de alto volume nesses gateways.
    
- A porcentagem de chamadas queque ignoram o servidor de mediação.
    
Durante o planejamento, considere os requisitos de processamento de mídia das chamadas PSTN e das conferências A/V que não suportam bypass de mídia, além do processamento necessário para lidar com as interações de sinalização em relação ao número de chamadas em horário de pico que precisam de suporte. Se você não tiver suficiente CPU, você precisará implantar um pool autônomo de servidores de mediação. Além disso, os gateways PSTN, IP-PBXs e SBCs precisará ser dividido em subconjuntos são controlados pelos servidores de mediação colocado em um pool e os servidores de mediação autônomo em um ou mais pools autônomos.
  
Se você implantou os gateways PSTN, IP-PBXs ou controladores de borda de sessão (SBCs) que não têm a capacidade de interagir com um pool de servidores de mediação, precisará ser associado a um pool autônomo, consistindo em um único servidor de mediação. Algumas das coisas que seus gateways PSTN, IP-PBXs ou SBCs precisam fazer incluem:
  
- Executar o sistema de nome de domínio (DNS) balanceamento de carga em servidores de mediação em um pool de camada de rede (ou caso contrário, rotear tráfego uniformemente para todos os servidores de mediação em um pool).
    
- Aceite tráfego de qualquer servidor de mediação em um pool.
    
Você pode usar o Skype para a ferramenta de planejamento de negócios para avaliar se colocando o servidor de mediação com seu pool de Front-End pode manipular a carga. Se seu ambiente não pode atender a esses requisitos, você precisará implantar um pool do servidor de mediação autônomo.
  
## <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o local central e o local da filial

 Servidores de mediação no site central podem ser usado para rotear chamadas para o IP-PBXs ou gateways PSTN em filiais. No entanto, se você implantar troncos SIP, você precisará implantar um servidor de mediação no site onde finaliza a cada tronco. Tendo um servidor de mediação no site central rotear chamadas para um IP-PBX ou gateway PSTN em um site de filial não exige o uso de media bypass, mas o desvio de mídia é recomendado. Isso ocorre porque, se você pode habilitar o bypass de mídia, isso reduzirá a latência do caminho de mídia e, consequentemente, resultará em uma melhor qualidade de mídia, porque o caminho de mídia não precisa seguir o caminho de sinalização. O bypass de mídia também diminuirá a carga de processamento no pool.
  
> [!NOTE]
> O bypass de mídia não interoperará com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com os IP-PBXs da Cisco. Bypass de mídia é suportado somente com produtos e versões listadas em Unified Communications programa de interoperabilidade aberta - Lync Server em [explorar testado dispositivos, infra-estrutura e ferramentas que suportam e estendem seu Skype para experiência de negócios](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Se a resiliência de site de filial for necessária, um aparelho de filial persistente ou a combinação de um servidor Front-End, um servidor de mediação e um gateway deve ser implantada no site da filial. (A pressuposição com resiliência de site de filial é que presença e conferência não são resilientes no site.) Para obter orientação sobre o site de filial Planejando o voice, consulte [Planejar a resiliência do Enterprise Voice em Skype para Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Para interações com um IP-PBX, se o IP-PBX não suporta corretamente interações de mídia inicial com várias caixas de diálogo iniciais e interações do RFC 3960, pode haver corte da primeira primeiras palavras da saudação de chamadas de entrada de IP-PBX nos terminais do Lync. Esse comportamento pode ser mais grave se um servidor de mediação em um site central for onde a rota será encerrada em um site de filial, roteamento de chamadas para um IP-PBX por mais tempo é necessário para a conclusão de sinalização. Se você enfrentar esse comportamento, implantar um servidor de mediação no site da filial é a única maneira de reduzir o corte da primeira algumas palavras.
  
Finalmente, se o site central tiver um PBX TDM, ou se o IP-PBX não elimina a necessidade de um gateway PSTN, você deve implantar um gateway de rota de chamada conectando o servidor de mediação e o PBX.
  
> [!NOTE]
> Para aprimorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede nesses servidores. O RSS permite que pacotes de entrada sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "[Receive-Side aprimoramentos de dimensionamento no Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)". Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede. 
  

