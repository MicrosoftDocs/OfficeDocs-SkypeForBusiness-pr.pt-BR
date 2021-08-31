---
title: Cenários do Servidor de Borda em Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Resumo: revise esses cenários para ajudá-lo a planejar sua topologia do Servidor de Borda em Skype for Business Server.'
ms.openlocfilehash: 4035418426975b79a35be7ec84c6affac3ab92d5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732072"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Cenários do Servidor de Borda em Skype for Business Server
 
**Resumo:** Revise esses cenários para ajudá-lo a planejar sua topologia do Servidor de Borda em Skype for Business Server.
  
Temos alguns diagramas de cenários para ajudar na visualização e na Skype for Business Server topologia do Servidor de Borda que você deseja implementar. Depois de escolher um bom candidato, você pode ler os requisitos ambientais que você precisará resolver. O seguinte é aplicável a qualquer um dos cenários, portanto, vamos mencioná-lo primeiro.
  
Esses números, que são mostrados apenas para fins de exemplo (e, como tal, contêm dados IPv4 e IPv6 de exemplo), não representam o fluxo de comunicação real, mas sim uma exibição de alto nível do seu tráfego possível. Os detalhes da porta também podem ser vistos nos diagramas de porta para cada cenário abaixo.
  
Os diagramas mostram .com para a interface externa e .net para o interno, que também é um material de exemplo; É claro que suas próprias entradas podem ser bem diferentes quando você estiver montando seu próprio plano final de Borda.
  
Não incluímos o Diretor (que é um componente opcional) em qualquer um dos diagramas, mas você pode ler sobre isso separadamente (ele é mencionado em outros tópicos de Planejamento).
  
Conforme mencionado acima, há dados IPv6 de exemplo nos diagramas. A maioria da documentação em [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) se referirá a IPv4, mas você certamente terá suporte se quiser usar iPv6. Observe que você precisará de endereços IPv6 em seu espaço de endereço atribuído e eles precisarão trabalhar com endereçamento interno e externo, como com IPs IPv4. Você pode, graças a Windows, empregar o recurso de pilha dupla, que é uma pilha de rede separada e distinta para IPv4 e IPv6. Isso permitirá, se necessário, atribuir endereços IPv4 e IPv6 simultaneamente.
  
Há dispositivos NAT que permitem NAT64 (IPv6 a IPv4) e NAT66 (IPv6 a IPv6) e isso é válido para uso com Skype for Business Server.
  
> [!IMPORTANT]
> Se você estiver usando o Cac (Controle de Admissão de Chamada), você precisa usar o IPv4 na interface interna para que ele funcione. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Servidor de Borda Skype for Business Server único com endereços IP privados e NAT

Com esse cenário, não há opção para alta disponibilidade. Isso significa que você gastará menos em hardware e terá uma implantação mais simples. Se a alta disponibilidade for uma idem, confira os cenários consolidados em escala abaixo.
  
![Cenário de borda para borda consolidada única com IP privado usando NAT.](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para portas para Servidores de Borda consolidados único.
  
![Perímetro de rede para borda única consolidada do cenário de borda.](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Servidor de Borda Skype for Business Server único com endereços IP públicos

Com esse cenário, não há opção para alta disponibilidade. Isso significa que você gastará menos em hardware e terá uma implantação mais simples. Se a alta disponibilidade for uma idem, confira os cenários consolidados em escala abaixo.
  
![Cenário de borda para borda consolidada única com IP público.](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para portas para Servidores de Borda consolidados único.
  
![Perímetro de rede para borda única consolidada do cenário de borda.](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Pool de borda consolidado Skype for Business Server dimensionado, com balanceamento de carga DNS e endereços IP privados e NAT

Com esse cenário, você pode ter alta disponibilidade em sua implantação de Borda, o que oferece as vantagens do suporte a escalabilidade e failover.
  
![Cenário de Borda para Borda Consolidada Em Escala, DNS LB com IP particular usando NAT.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para pools de Borda consolidados em escala com balanceamento de carga DNS.
  
![Perímetro de rede para borda consolidada em escala de cenário de borda usando DNS LB.](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Pool de borda consolidado Skype for Business Server dimensionado, com balanceamento de carga DNS e endereços IP públicos

Com esse cenário, você pode ter alta disponibilidade em sua implantação de Borda, o que oferece as vantagens do suporte a escalabilidade e failover.
  
![Cenário de Borda para Borda Consolidada Em Escala, DNS LB com IP público.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagrama de porta

Também temos um diagrama para pools de Borda consolidados em escala com balanceamento de carga DNS.
  
![Perímetro de rede para borda consolidada em escala de cenário de borda usando DNS LB.](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Pool de borda consolidado Skype for Business Server dimensionado, com balanceamento de carga de hardware

Com esse cenário, você pode ter alta disponibilidade em sua implantação de Borda, o que oferece as vantagens do suporte a escalabilidade e failover.
  
![Cenário de Borda para Borda Consolidada Em Escala com HLB.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
