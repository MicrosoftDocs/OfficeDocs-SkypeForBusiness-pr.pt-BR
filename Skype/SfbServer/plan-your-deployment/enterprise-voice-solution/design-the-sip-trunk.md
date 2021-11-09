---
title: Projetar o tronco SIP para E9-1-1 em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planejando suas topologias de tronco SIP para uma implantação do E9-1-1 que usa provedores de tronco SIP, Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 36362b9ff516f3f15a990d5d70c42c0bea6119b3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841023"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Projetar o tronco SIP para E9-1-1 em Skype for Business Server
 
Planejando suas topologias de tronco SIP para uma implantação do E9-1-1 que usa provedores de tronco SIP, Skype for Business Server Enterprise Voice.
  
Skype for Business Server usa troncos SIP para conectar uma chamada de emergência ao provedor de serviços E9-1-1. Você pode configurar os troncos SIP do serviço de emergência para E9-1-1 em um local central, em vários locais centrais ou em cada filial. No entanto, se o link WAN entre o site do chamador e o site que hospeda o tronco SIP do serviço de emergência estiver indisponível, uma chamada feita por um usuário no site desconectado precisará de um registro de uso de telefone especial na política de voz do usuário que encaminhará a chamada para o ECRC por meio do gateway PSTN (rede telefônica pública comutado) local. O mesmo é verdadeiro se os limites de chamadas simultâneas do serviço de controle de admissão chamada estão em vigor.
  
Há duas maneiras de implementar um tronco SIP em um ambiente Skype for Business Server:
  
- Use Servidores de Mediação multihomed que usam suas interfaces externas com rotação pública para se comunicar com o provedor de tronco SIP.
    
- Use um SBC (Controlador de Borda de Sessão) local para fornecer um ponto de demarcação seguro entre os Servidores de Mediação e os serviços do provedor de tronco SIP.
    
Se você escolher o último método, certifique-se de que a marca e o modelo do SBC escolhidos foram certificados e oferecem suporte à transmissão de dados de localização PIDF-LO (objeto Local de formato de dados de informação de presença) como parte de seu SIP INVITE. Caso contrário, as chamadas chegarão no provedor de serviços de emergência retirado das suas informações de localização. Para obter detalhes sobre SBCs certificados, consulte ["Infrastructure Qualified for Microsoft Lync"](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) e ["Telephony Infrastructure for Skype for Business"](../../../SfbPartnerCertification/certification/infra-gateways.md). 
  
Os provedores de serviços E9-1-1 fornecem acesso a um par de SBCs para redundância. Você precisa tomar várias decisões sobre a topologia do Servidor de Mediação e a configuração de roteamento de chamadas. Você tratará os SBCs como pares iguais e utilizará o roteamento em rodízio para chamadas entre eles ou designará um SBC como primário e outro secundário?
  
Para obter detalhes sobre como implantar um tronco SIP no Skype for Business Server, consulte [Tronco SIP em Skype for Business Server](sip-trunking.md). As seguintes perguntas ajudaram você a implantar troncos SIP para E9-1-1.
  
 **Você deve implantar o tronco SIP em uma conexão de concessão dedicada ou uma conexão compartilhada com a Internet?**
  
> É importante que as chamadas de emergência sejam sempre conectadas. Uma linha dedicada fornece uma conexão que não será garantida por outro tráfego na rede e permite que você implemente a QoS (Qualidade de Serviço). Lembre-se de que, se você estiver se conectando a provedores de serviços de emergência por meio da Internet pública, será preciso garantir a confidencialidade das chamadas de emergência, a criptografia IPSec será necessária. 
    
 **Sua implantação do E9-1-1 foi projetada para tolerância a desastres?**
  
> Como esta é uma solução de emergência, a resiliência é importante. Implante seus Servidores de Mediação primários e secundários e troncos SIP em locais tolerantes a desastres. É uma boa ideia implantar seu Servidor de Mediação principal mais próximo dos usuários que ele está suportando e rotear chamadas de failover por meio do Servidor de Mediação secundário (localizado em uma localização geográfica diferente). 
    
 **Você deve implantar um tronco SIP separado para cada filial?**
  
> Skype for Business Server fornece várias estratégias para lidar com a resiliência de voz em filiais, incluindo: ter redes de dados resilientes, implantar um tronco SIP em cada filial ou enviar chamadas para o gateway local durante paralisações. Para obter detalhes, consulte [Tronco SIP em Skype for Business Server](sip-trunking.md).
    
 **O CAC (serviço de controle de admissão de chamada) está habilitado?**
  
> Skype for Business Server não lida com chamadas de emergência de forma diferente de uma chamada comum. Por essa razão, o gerenciamento de largura de banda ou o CAC (serviço de controle de admissão de chamada) pode ter um impacto negativo em uma configuração de E9-1-1. As chamadas de emergência serão bloqueadas ou roteadas para o gateway PSTN local se um CAC estiver habilitado e for excedido o limite configurado em um link no qual as chamadas de emergência estão sendo roteadas. Como acima, tais chamadas não terão dados de localização e devem ser direcionadas manualmente para o ECRC.
