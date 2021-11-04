---
title: Configurar troncos em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumo: saiba como configurar um tronco entre um Servidor de Mediação e pares para Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: 128be18c31802787c173c8d180de80f5ae5a64fb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748887"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurar troncos em Skype for Business Server
 
**Resumo:** Saiba como configurar um tronco entre um Servidor de Mediação e pares para Enterprise Voice em Skype for Business Server.
  
Como parte da implantação Enterprise Voice, você pode configurar um tronco entre um Servidor de Mediação e um ou mais dos seguintes pares para fornecer conectividade PSTN (rede telefônica pública comutado) para clientes e dispositivos Enterprise Voice em sua organização:
  
- Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)
    
- Gateway PSTN
    
- Central privada de comutação telefônica (PBX)
    
Para obter mais detalhes, [consulte Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype for Business Server funcionalidade suporta várias associações entre gateways e Servidores de Mediação. Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool do Servidor de Mediação e um gateway PSTN (rede telefônica pública comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX. Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).
  
- Para atribuir ou remover um tronco Skype for Business Server, você deve primeiro definir um tronco no Construtor de Topologias. Um tronco consiste na seguinte associação: FQDN (Nome de domínio totalmente qualificado do Servidor de Mediação), a porta de escuta do Servidor de Mediação, o FQDN do gateway e a porta de escuta do gateway.
    
- Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o Servidor de Mediação. Isso fornece resiliência adicional à infraestrutura de Enterprise Voice, que é especialmente útil em cenários interoperacionais de PBX (private branch exchange). 
    
Quando um tronco é definido, ele deve estar associado a uma rota. Para associar um tronco a uma rota, você define um nome simples para o tronco no Construtor de Topologias. Esse nome simples é usado como o nome do tronco no painel de controle Skype for Business Server, onde os troncos podem ser associados a rotas. O nome do tronco simples é usado como o nome do gateway do Shell de Gerenciamento Skype for Business Server. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

O administrador deve selecionar um tronco padrão associado a um Servidor de Mediação. No Construtor de Topologias, clique com o botão direito do mouse no Servidor de Mediação associado e clique em **Propriedades**. Especifique o gateway padrão para o Servidor de Mediação. 
  

