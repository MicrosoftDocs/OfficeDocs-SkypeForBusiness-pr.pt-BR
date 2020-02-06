---
title: Diretrizes de implantação para o servidor de mediação no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Este tópico descreve diretrizes de planejamento para a implantação do servidor de mediação.
ms.openlocfilehash: 806886b7c7c5e8ae367a6e104f7fd9127f25c099
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816050"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Diretrizes de implantação para o servidor de mediação no Skype for Business Server
 
Este tópico descreve diretrizes de planejamento para a implantação do servidor de mediação.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediação autônomo ou posicionado?

O servidor de mediação é, por padrão, posicionado no servidor Standard Edition ou no servidor front-end em um pool de front-ends em sites centrais. O número de chamadas da rede telefônica pública comutada (PSTN) que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:
  
- O número de pares de gateway que o pool de servidores de mediação controla.
    
- Períodos de tráfego de alto volume nesses gateways.
    
- A porcentagem de chamadas que são chamadas cuja mídia ignora o servidor de mediação.
    
Durante o planejamento, considere os requisitos de processamento de mídia das chamadas PSTN e das conferências A/V que não suportam bypass de mídia, além do processamento necessário para lidar com as interações de sinalização em relação ao número de chamadas em horário de pico que precisam de suporte. Se você não tiver CPU suficiente, será necessário implantar um pool autônomo de servidores de mediação. Além disso, os gateways PSTN, PBXs IP e SBCs precisarão ser divididos em subconjuntos controlados pelos servidores de mediação posicionados em um pool e os servidores autônomos de mediação em um ou mais pools autônomos.
  
Se você implantou gateways PSTN, PBXs de IP ou controladores de borda de sessão (SBCs) que não têm a capacidade de interagir com um pool de servidores de mediação, eles precisarão ser associados a um pool autônomo, que consiste em um único servidor de mediação. Algumas das coisas que seus gateways PSTN, IP-PBXs ou SBCs precisam fazer incluem:
  
- Executar o balanceamento de carga de DNS (sistema de nomes de domínio) de camada de rede em servidores de mediação em um pool (ou de outra forma rotear uniformemente para todos os servidores de mediação em um pool).
    
- Aceite o tráfego de qualquer servidor de mediação em um pool.
    
Você pode usar a ferramenta de planejamento do Skype for Business para avaliar se posicionar o servidor de mediação com seu pool de front-ends pode manipular a carga. Se o seu ambiente não puder atender a esses requisitos, você precisará implantar um pool autônomo do servidor de mediação.
  
## <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o local central e o local da filial

 Os servidores de mediação no site central podem ser usados para direcionar chamadas para IP-PBXs ou gateways PSTN em sites de filiais. No entanto, se você implantar troncos SIP, será necessário implantar um servidor de mediação no site em que cada tronco termina. Ter um servidor de mediação no site central chamadas de rota para um IP-PBX ou um gateway PSTN em um site de filial não requer o uso do bypass de mídia, mas é recomendável ignorar a mídia. Isso ocorre porque, se você pode habilitar o bypass de mídia, isso reduzirá a latência do caminho de mídia e, consequentemente, resultará em uma melhor qualidade de mídia, porque o caminho de mídia não precisa seguir o caminho de sinalização. O bypass de mídia também diminuirá a carga de processamento no pool.
  
> [!NOTE]
> O bypass de mídia não interoperará com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com os IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no programa de interoperabilidade aberto da comunicação unificada-Lync Server em [explorar dispositivos, infraestrutura e ferramentas testados que dão suporte e ampliam sua experiência com o Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Se a resiliência do site de ramificação for necessária, um aparelho de ramificação sobreviventes ou uma combinação de um servidor front-end, um servidor de mediação e um gateway devem ser implantados no site da filial. (A pressuposição da resiliência do site da ramificação é que a presença e a conferência não são resistentes no site.) Para obter orientação sobre o planejamento de sites de filiais, consulte [planejar a resiliência do Enterprise Voice no Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Para interações com um PBX IP, se o IP-PBX não suportar corretamente interações de mídia antigas com várias caixas de diálogo iniciais e interações RFC 3960, pode haver recorte das primeiras palavras da saudação para as chamadas recebidas dos pontos de extremidade IP-PBX para Lync. Esse comportamento pode ser mais sério se um servidor de mediação em um site central estiver encaminhando chamadas para um PBX IP em que a rota termina em um site de filial, pois é necessária mais tempo para a sinalização ser concluída. Se você tiver esse comportamento, a implantação de um servidor de mediação no site da filial é a única maneira de reduzir o recorte das primeiras palavras.
  
Por fim, se o seu site central tiver um PBX de TDM, ou se o seu PBX IP não eliminar a necessidade de um gateway PSTN, você deve implantar um gateway no servidor de mediação conectando o servidor de mediação da chamada e o PBX.
  
> [!NOTE]
> Para aprimorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede nesses servidores. O RSS permite que pacotes de entrada sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "[aprimoramentos de dimensionamento no lado do Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)". Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede. 
  

