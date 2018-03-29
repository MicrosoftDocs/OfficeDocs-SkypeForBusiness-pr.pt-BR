---
title: Configurar troncos no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumo: Saiba como configurar um tronco entre um servidor de mediação e parceiros para o Enterprise Voice no Skype para Business Server 2015.'
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a>Configurar troncos no Skype for Business Server 2015
 
**Resumo:** Saiba como configurar um tronco entre um servidor de mediação e parceiros para o Enterprise Voice no Skype para Business Server 2015.
  
Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes computadores para fornecer conectividade PSTN (rede) telefônica pública comutada clientes Enterprise Voice e dispositivos em sua organização:
  
- Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)
    
- Gateway PSTN
    
- Central privada de comutação telefônica (PBX)
    
Para obter mais detalhes, consulte [Planejar a conectividade PSTN em Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype para a funcionalidade do Business Server suporta vários associações entre gateways e servidores de mediação. Essas associações são feitas por meio da definição de um tronco, que é uma associação de lógica entre um pool do servidor de mediação e um gateway PSTN (rede) telefônica pública comutada, controlador de borda de sessão (SBC) ou IP-PBX. Use o construtor de topologia para associar os gateways com servidores de mediação (ou seja, troncos).
  
- Para atribuir ou remover um tronco no Skype para Business Server, você deve definir um tronco no construtor de topologia. Consiste em um tronco a associação a seguir: servidor de mediação totalmente qualificado (FQDN) do nome de domínio, a porta de escuta do servidor de mediação, o gateway FQDN e a porta de escuta do gateway.
    
- Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação. Isso oferece resiliência adicional a infraestrutura do Enterprise Voice, o que é especialmente útil em cenários interoperational do privada de comutação telefônica (PBX). 
    
Quando um tronco é definido, ele precisa ser associado à rota. Para associar um tronco a uma rota, você pode definir um nome simples para o tronco no construtor de topologia. Esse nome simple é usado como o nome do tronco no Skype para painel de controle do Business Server, onde troncos podem ser associados a rotas. O nome do tronco simples é usado como o nome de gateway a partir do Skype do Shell de gerenciamento do servidor de negócios. 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

O administrador deve selecionar um tronco padrão associado a um servidor de mediação. No Topology Builder, com o botão direito do servidor de mediação associado e clique em **Propriedades**. Especifique o gateway padrão para o servidor de mediação. 
  

