---
title: Cenários do Servidor de Borda no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Resumo: Revise esses cenários para ajudá-lo a planejar sua topologia de servidor de borda no Skype Business Server 2015.'
ms.openlocfilehash: 9afe23c626f2a266061c250740e52bc55dd2697d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="edge-server-scenarios-in-skype-for-business-server-2015"></a>Cenários do Servidor de Borda no Skype for Business Server 2015
 
**Resumo:** Examine esses cenários para ajudá-lo a planejar sua topologia de servidor de borda no Skype Business Server 2015.
  
Temos alguns diagramas de cenários para auxiliar com visualizando e decidir sobre qual Skype para topologia de servidor de borda do servidor de negócios que você deseja implementar. Depois de escolher um bom candidato, você pode ler mais informações sobre quais requisitos ambientais serão necessários. Os seguintes são aplicados a qualquer um dos cenários, por isso, vamos mencioná-los primeiro.
  
Estes números, mostrados apenas para fins de exemplo (e, como tal, contêm dados IPv4 e IPv6 de exemplo), não representam o fluxo de comunicação real, mas uma visualização de alto nível de seu tráfego possível. Os detalhes da porta também podem ser observados nos diagramas de porta de cada cenário abaixo.
  
Os diagramas mostram .com para a interface externa e .net para a interna, que também é material de amostra. Suas entradas podem ser bem diferentes na criação de seu próprio plano de Borda final.
  
Não incluímos o Diretor (que é um componente opcional) em qualquer um dos diagramas, mas você pode ler sobre que separadamente (mencionado em outros tópicos de planejamento).
  
Conforme observado acima, há dados IPv6 de amostra nos esquemas. A maioria da documentação no [plano para implantações de servidor de borda no Skype para Business Server 2015](edge-server-deployments.md) fará referência ao IPv4, mas você certamente é suportados, se você quiser usar o IPv6. Observe que você precisará endereços IPv6 em seu espaço de endereços atribuído e lá eles precisarão funcionar com endereços internos e externos, assim como os IPs IPv4. É possível, graças ao Windows, usar  o recurso de pilha dupla, que é uma pilha de rede separada e distinta para IPv4 e IPv6. Se for necessário, isso permitirá que você atribua endereços IPv4 e IPv6 ao mesmo tempo.
  
Existem dispositivos NAT que permitem NAT64 (IPv6 para IPv4) e NAT66 (IPv6 para IPv6)), e isso é válido para uso com Skype para Business Server.
  
> [!IMPORTANT]
> Se você estiver usando o serviço de controle de admissão de chamadas (CAC), é preciso usar IPv4 na interface interna para que ele funcione. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Único consolidado Skype para servidor de borda do servidor de negócios com endereços IP de privados e NAT

Com este cenário, não há opção para alta disponibilidade. Isso significa que você gastará menos no hardware e terá uma implantação mais simples. Se alta disponibilidade for necessária, verifique os cenários consolidados em escala abaixo.
  
![Cenário de borda para borda consolidada única e IP privado usando NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para portas para servidores de borda consolidada única.
  
![Perímetro de rede para borda consolidada única para cenário de borda](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Único consolidado Skype para servidor de borda do servidor de negócios com endereços IP públicos

Com este cenário, não há opção para alta disponibilidade. Isso significa que você gastará menos no hardware e terá uma implantação mais simples. Se alta disponibilidade for necessária, verifique os cenários consolidados em escala abaixo.
  
![Cenário de borda para borda consolidada única e IP público](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para portas para servidores de borda consolidada única.
  
![Perímetro de rede para borda consolidada única para cenário de borda](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Skype consolidada em escala para o pool de borda do servidor de negócios, com o DNS de carga balanceamento e particulares endereços IP e NAT

Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.
  
![Cenário de borda para DNS LB com borda consolidada dimensionada e IP privado usando NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para pools de borda consolidados em escala com balanceamento de carga DNS.
  
![Perímetro de rede para borda consolidada dimensionada para cenário de borda usando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Os endereços IP públicos e balanceamento de carga do Skype consolidada em escala para o pool de borda do servidor de negócios, com DNS

Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.
  
![Cenário de borda para DNS LB com borda consolidada dimensionada com IP público](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para pools de borda consolidados em escala com balanceamento de carga DNS.
  
![Perímetro de rede para borda consolidada dimensionada para cenário de borda usando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Dimensionada consolidada Skype para pool de borda do servidor de negócios, com balanceamento de carga de hardware

Com este cenário, você poderá ter alta disponibilidade em sua implantação de Borda, o que oferece vantagens de escalabilidade e suporte a failover.
  
![Cenário de borda para borda consolidada dimensionada com HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para pools de borda consolidados em escala com balanceamento de carga de hardware
  
![Portas e protocolos de Rede de Perímetro do Servidor de Borda](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

