---
title: Projetar o tronco SIP para E9-1-1 no Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planejamento de topologias de tronco SIP para uma implantação E9-1-1 que usa provedores de tronco SIP, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: ef30d721b59f29885004ee948055a91ca8af9490
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825791"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Projetar o tronco SIP para E9-1-1 no Skype for Business Server
 
Planejamento de topologias de tronco SIP para uma implantação E9-1-1 que usa provedores de tronco SIP, no Skype for Business Server Enterprise Voice.
  
O Skype for Business Server usa troncos SIP para conectar uma chamada de emergência ao provedor de serviços E9-1-1. Você pode configurar os troncos SIP do serviço de emergência para E9-1-1 em um local central, em vários locais centrais ou em cada filial. No entanto, se o link WAN entre o local do chamador e o local que hospeda o tronco SIP do serviço de emergência não estiver disponível, uma chamada feita por um usuário no site desconectado precisará de um registro de uso de telefone especial na política de voz do usuário que encaminhará a chamada para o ECRC por meio do gateway PSTN (rede telefônica pública comutado) local. O mesmo é verdadeiro se os limites de chamadas simultâneas do serviço de controle de admissão chamada estão em vigor.
  
Há duas maneiras de implementar um tronco SIP em um ambiente do Skype for Business Server:
  
- Use servidores de mediação multihomed que usam suas interfaces roteados publicamente voltados para fora para se comunicar com o provedor de tronco SIP.
    
- Use um SBC (Controlador de Borda de Sessão) local para fornecer um ponto de demarcação seguro entre os Servidores de Mediação e os serviços do provedor de tronco SIP.
    
Se você escolher o último método, certifique-se de que a marca e o modelo do SBC escolhidos foram certificados e oferecem suporte à transmissão de dados de localização PIDF-LO (objeto Local de formato de dados de informação de presença) como parte de seu SIP INVITE. Caso contrário, as chamadas chegarão no provedor de serviços de emergência retirado das suas informações de localização. Para obter detalhes sobre SBCs certificados, consulte "Infraestrutura qualificada para [Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) e "Infraestrutura de [telefonia para o Skype for Business".](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) 
  
Os provedores de serviços E9-1-1 fornecem acesso a um par de SBCs para redundância. Você precisa tomar várias decisões em relação à topologia do Servidor de Mediação e à configuração de roteamento de chamadas. Você tratará os SBCs como pares iguais e utilizará o roteamento em rodízio para chamadas entre eles ou designará um SBC como primário e outro secundário?
  
Para obter detalhes sobre como implantar um tronco SIP no Skype for Business Server, consulte [tronco SIP no Skype for Business Server.](sip-trunking.md) As seguintes perguntas ajudaram você a implantar troncos SIP para E9-1-1.
  
 **Você deve implantar o tronco SIP em uma conexão de concessão dedicada ou uma conexão compartilhada com a Internet?**
  
> É importante que as chamadas de emergência sejam sempre conectadas. Uma linha dedicada fornece uma conexão que não será garantida por outro tráfego na rede e permite que você implemente a QoS (Qualidade de Serviço). Lembre-se de que, se você estiver se conectando a provedores de serviços de emergência por meio da Internet pública, será preciso garantir a confidencialidade das chamadas de emergência, a criptografia IPSec será necessária. 
    
 **Sua implantação de E9-1-1 foi projetada para tolerância a desastres?**
  
> Como esta é uma solução de emergência, a resiliência é importante. Implante seus Servidores de Mediação primários e secundários e troncos SIP em locais tolerantes a desastres. É uma boa ideia implantar seu Servidor de Mediação primário mais próximo dos usuários aos usuários que ele suporta e rotear chamadas de failover por meio do Servidor de Mediação secundário (localizado em uma localização geográfica diferente). 
    
 **Você deve implantar um tronco SIP separado para cada filial?**
  
> O Skype for Business Server oferece várias estratégias para lidar com a resiliência de voz em filiais, incluindo: ter redes de dados resilientes, implantar um tronco SIP em cada filial ou enviar por voz chamadas para o gateway local durante paralisações. Para obter detalhes, [consulte o tronco SIP no Skype for Business Server.](sip-trunking.md)
    
 **O CAC (serviço de controle de admissão de chamada) está habilitado?**
  
> O Skype for Business Server não lida com chamadas de emergência de forma diferente de uma chamada comum. Por essa razão, o gerenciamento de largura de banda ou o CAC (serviço de controle de admissão de chamada) pode ter um impacto negativo em uma configuração de E9-1-1. As chamadas de emergência serão bloqueadas ou roteadas para o gateway PSTN local se um CAC estiver habilitado e for excedido o limite configurado em um link no qual as chamadas de emergência estão sendo roteadas. Como acima, tais chamadas não terão dados de localização e devem ser direcionadas manualmente para o ECRC.
    

