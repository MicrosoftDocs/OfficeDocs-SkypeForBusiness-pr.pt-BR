---
title: Configurar troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: saiba como configurar um tronco entre um Servidor de Mediação e pares do Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824951"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurar troncos no Skype for Business Server
 
**Resumo:** Saiba como configurar um tronco entre um Servidor de Mediação e pares do Enterprise Voice no Skype for Business Server.
  
Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um Servidor de Mediação e um ou mais dos seguintes pares para fornecer conectividade PSTN (rede telefônica pública comutado) para clientes e dispositivos Enterprise Voice em sua organização:
  
- Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)
    
- Gateway PSTN
    
- Central privada de comutação telefônica (PBX)
    
Para obter mais detalhes, [consulte Plano para conectividade PSTN no Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)
  
A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e Servidores de Mediação. Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool de Servidor de Mediação e um gateway PSTN (Rede Telefônica Pública Comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX. Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).
  
- Para atribuir ou remover um tronco no Skype for Business Server, você deve primeiro definir um tronco no Construtor de Topologias. Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do Servidor de Mediação, a porta de escuta do Servidor de Mediação, o FQDN do gateway e a porta de escuta do gateway.
    
- Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o Servidor de Mediação. Isso fornece resiliência adicional para a infraestrutura do Enterprise Voice, que é especialmente útil em cenários interoperacionais pbx (central privada de computação). 
    
Quando um tronco é definido, ele deve ser associado a uma rota. Para associar um tronco a uma rota, defina um nome simples para o tronco no Construtor de Topologias. Esse nome simples é usado como o nome do tronco no Painel de Controle do Skype for Business Server, onde os troncos podem ser associados a rotas. O nome do tronco simples é usado como o nome do gateway do Shell de Gerenciamento do Skype for Business Server. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

O administrador deve selecionar um tronco padrão associado a um Servidor de Mediação. No Construtor de Topologias, clique com o botão direito do mouse no Servidor de Mediação associado e clique em **Propriedades.** Especifique o gateway padrão para o Servidor de Mediação. 
  

