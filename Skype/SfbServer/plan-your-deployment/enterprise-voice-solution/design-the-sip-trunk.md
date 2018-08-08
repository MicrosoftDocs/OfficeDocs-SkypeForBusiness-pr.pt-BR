---
title: Projetar o tronco SIP para E9-1-1 em Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planejando as topologias de tronco SIP para uma implantação do E9-1-1 que usa os provedores de tronco SIP, no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 8a0264bc66be97a80b9ef1d14a020f438a8a89f5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974662"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Projetar o tronco SIP para E9-1-1 em Skype para Business Server
 
Planejando as topologias de tronco SIP para uma implantação do E9-1-1 que usa os provedores de tronco SIP, no Skype para Business Server Enterprise Voice.
  
Skype para Business Server usa troncos SIP para conectar a uma chamada de emergência para o provedor de serviço E9-1-1. Você pode configurar os troncos SIP do serviço de emergência para E9-1-1 em um local central, em vários locais centrais ou em cada filial. No entanto, se o link da WAN entre sites do chamador e o site que hospeda o tronco SIP de serviço de emergência não estiver disponível, uma chamada feita por um usuário no site desconectado será necessário um registro de uso do telefone especial na política de voz do usuário que roteará a chamada para o ECRC através do gateway PSTN (rede) local telefônica comutada pública. O mesmo é verdadeiro se os limites de chamadas simultâneas do serviço de controle de admissão chamada estão em vigor.
  
Há duas maneiras de implementar um tronco SIP em um Skype para ambiente de servidor de negócios:
  
- Use servidores de mediação multihomed que usam suas interfaces roteadas publicamente direcionadas do exterior para se comunicar com o provedor de tronco SIP.
    
- Use um controlador de borda de sessão (SBC) no local para fornecer serviços do provedor de um ponto de demarcação seguro entre os servidores de mediação e o tronco SIP.
    
Se você escolher o último método, certifique-se de que a marca e o modelo do SBC escolhidos foram certificados e oferecem suporte à transmissão de dados de localização PIDF-LO (objeto Local de formato de dados de informação de presença) como parte de seu SIP INVITE. Caso contrário, as chamadas chegarão ao provedor de serviços de emergência retirado das suas informações de localização. Para obter detalhes sobre certificados SBCs, consulte ["infra-estrutura para Microsoft Lync qualificados"](https://go.microsoft.com/fwlink/p/?LinkId=248425) e ["telefonia infraestrutura para Skype para negócios"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
Os provedores de serviços E9-1-1 fornecem acesso a um par de SBCs para redundância. Você precisa tomar várias decisões sobre a topologia de servidor de mediação e a configuração de roteamento de chamadas. Você tratará os SBCs como pares iguais e utilizará o roteamento em rodízio para chamadas entre eles ou designará um SBC como primário e outro secundário?
  
Para obter detalhes sobre como implantar um tronco SIP no Skype para Business Server, consulte o [tronco SIP no Skype para Business Server](sip-trunking.md). As seguintes perguntas ajudaram você a implantar troncos SIP para E9-1-1.
  
 **Você deve implantar o tronco SIP em uma conexão de concessão dedicada ou uma conexão compartilhada com a Internet?**
  
> É importante que as chamadas de emergência sejam sempre conectadas. Uma linha dedicada fornece uma conexão que não será garantida por outro tráfego na rede e permite que você implemente a QoS (Qualidade de Serviço). Lembre-se de que, se você estiver se conectando a provedores de serviços de emergência por meio da Internet pública, será preciso garantir a confidencialidade das chamadas de emergência e a criptografia IPSec será necessária. 
    
 **Sua implantação do E9-1-1 foi projetada para tolerante a desastres?**
  
> Como esta é uma solução de emergência, a resiliência é importante. Implante seus principais e secundários troncos SIP e servidores de mediação em locais de tolerante a desastres. É uma boa ideia para implantar o seu servidor de mediação principal mais próximos aos usuários que ele oferece suporte ao e rota de failover chama através do servidor de mediação secundário (localizado em um local geográfico diferente). 
    
 **Você deve implantar um tronco SIP separado para cada filial?**
  
> Skype para Business Server fornece várias estratégias para manipular a resiliência de voz em filiais, incluindo: tendo redes de dados resiliente, implantando um tronco SIP em cada ramificação da árvore ou enviando chamadas para o gateway local durante interrupções. Para obter detalhes, consulte o [tronco SIP no Skype para Business Server](sip-trunking.md).
    
 **O CAC (serviço de controle de admissão de chamada) está habilitado?**
  
> Skype para Business Server não não chamadas de emergência alça de qualquer maneira diferente de uma chamada comum. Por essa razão, o gerenciamento de largura de banda ou o CAC (serviço de controle de admissão de chamada) pode ter um impacto negativo em uma configuração de E9-1-1. As chamadas de emergência serão bloqueadas ou roteadas para o gateway PSTN local se um CAC estiver habilitado e for excedido o limite configurado em um link no qual as chamadas de emergência estão sendo roteadas. Como acima, tais chamadas não terão dados de localização e devem ser direcionadas manualmente para o ECRC.
    

