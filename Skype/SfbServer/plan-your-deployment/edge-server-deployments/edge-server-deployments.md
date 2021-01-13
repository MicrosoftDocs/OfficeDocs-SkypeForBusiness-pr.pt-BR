---
title: Planejar implantações do Servidor de Borda no Skype for Business Server
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: planeje seu ambiente de Borda do Skype for Business Server. Este tópico apresenta os conceitos do Edge e permite que você se organize com nossos tópicos mais aprofundados.'
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813801"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planejar implantações do Servidor de Borda no Skype for Business Server
 
**Resumo:** Planeje seu ambiente de Borda do Skype for Business Server. Este tópico apresenta os conceitos do Edge e permite que você se organize com nossos tópicos mais aprofundados.
  
Quando você tem um ambiente do Skype for Business Server que está funcionando bem internamente, a próxima etapa para você pode ser introduzir um Servidor de Borda ou um pool de Borda para o ambiente. Essa função será vital se você quiser que os serviços fornecidos pelo Skype for Business Server sejam usados por pessoas fora da rede interna. Eles podem incluir:
  
- Usuários remotos: funcionários que estão fora do local, temporariamente ou de forma contínua.
    
- Usuários federados: funcionários de suas organizações parceiras.
    
- Usuários móveis.
    
- Clientes em potencial, parceiros e até mesmo usuários anônimos que você deseja convidar para reuniões e apresentações.
    
O Acesso de Usuário Externo, que é o que os Servidores de Borda fornecem, permitem que tudo isso aconteça. Seus usuários internos poderão aproveitar os seguintes serviços hospedados pela implantação do Skype for Business Server:
  
- IM e presença para comunicação: usuários externos autorizados podem participar de conversas e conferências de IM. Eles podem obter informações de presença para outros usuários (que também receberão suas informações de presença). Você não poderá fazer conferências com vários participantes se estiver usando um provedor de IM público, isso é estritamente uma comunicação ponto a ponto. Mas os protocolos SIP e XMPP são suportados.
    
- Conferência de áudio/vídeo (A/V: usuários externos autorizados podem participar de suas conferências de áudio e vídeo do Skype for Business Server.
    
- Webconferência: seus usuários externos autorizados podem participar de suas conferências do Skype for Business. Você também pode habilitar a participação de usuários remotos, federados e anônimos, se quiser. Os usuários públicos de IM não podem participar de conferências. Também há opções para permitir que esses usuários participem do compartilhamento de aplicativos e da área de trabalho e até mesmo atuem como organizadores ou apresentadores da reunião.
    
O acesso a dispositivos móveis é suportado, assim como o Enterprise Voice. Você pode convidar usuários externos para as reuniões que deseja que eles participem, mesmo usuários anônimos, se quiser dar permissões a eles.
  
Se isso parece algo que sua organização precisa, planejar um ambiente de Borda será de grande ajuda para implantá-lo. Para leitura posterior, temos os tópicos listados abaixo.

> [!NOTE]
> Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. 
  
## <a name="planning-topics"></a>Tópicos de planejamento:

Os artigos de planejamento são:
  
- [Requisitos de sistema do Servidor de Borda no Skype for Business Server 2015](system-requirements.md)
    
- [Requisitos ambientais do Servidor de Borda no Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Cenários do Servidor de Borda no Skype for Business Server 2015](scenarios.md)
    

