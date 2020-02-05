---
title: Configurar troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumo: saiba como configurar um tronco entre um servidor de mediação e os pares para Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: eb2cf3042fe4e0d1a7c840fb31c583b18289bb7b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768064"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurar troncos no Skype for Business Server
 
**Resumo:** Saiba como configurar um tronco entre um servidor de mediação e os pares para Enterprise Voice no Skype for Business Server.
  
Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes pares para fornecer conectividade PSTN (rede telefônica pública comutada) para clientes e dispositivos do Enterprise Voice em sua organização:
  
- Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)
    
- Gateway PSTN
    
- Central privada de comutação telefônica (PBX)
    
Para obter mais detalhes, consulte [planejar conectividade PSTN no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e servidores de mediação. Essas associações são feitas pela definição de um tronco, que é uma associação lógica entre um pool do servidor de mediação e um gateway de rede telefônica pública comutada (SBC), ou PBX IP. Use o construtor de topologias para associar gateways a servidores de mediação (ou seja, troncos).
  
- Para atribuir ou remover um tronco no Skype for Business Server, primeiro você deve definir um tronco no construtor de topologias. Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do servidor de mediação, a porta de escuta do servidor de mediação, o FQDN do gateway e a porta de escuta do gateway.
    
- Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação. Isso fornece resiliência adicional à infraestrutura Enterprise Voice, que é especialmente útil em cenários de interoperabilidade de PBX (Private Branch Exchange). 
    
Quando um tronco é definido, ele precisa ser associado à rota. Para associar um tronco a uma rota, você define um nome simples para o tronco no construtor de topologias. Esse nome simples é usado como o nome do tronco no painel de controle do Skype for Business Server, em que os troncos podem ser associados às rotas. O nome do tronco simples é usado como o nome do gateway do Shell de gerenciamento do Skype for Business Server. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

O administrador deve selecionar um tronco padrão associado a um servidor de mediação. No construtor de topologias, clique com o botão direito do mouse no servidor de mediação associado e, em seguida, clique em **Propriedades**. Especifique o gateway padrão do servidor de mediação. 
  

