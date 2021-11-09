---
title: Planejar implantações do Servidor de Borda no Skype for Business Server
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: Planeje seu ambiente Skype for Business Server Edge. Este tópico apresenta os conceitos de Borda e permite que você se organize com nossos tópicos mais aprofundados.'
ms.openlocfilehash: ae6dd672e3da6568d41898a4bc2ae022b23ad3f3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834109"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planejar implantações do Servidor de Borda no Skype for Business Server
 
**Resumo:** Planeje seu ambiente Skype for Business Server Edge. Este tópico apresenta os conceitos de Borda e permite que você se organize com nossos tópicos mais aprofundados.
  
Quando você tem um ambiente Skype for Business Server que está funcionando bem internamente, a próxima etapa para você pode ser introduzir um Servidor de Borda ou um pool de Borda ao ambiente. Essa função seria vital se você quisesse que os serviços fornecidos pelo Skype for Business Server sejam usados por pessoas que estão fora da sua rede interna. Eles podem incluir:
  
- Usuários remotos: funcionários que estão fora do local, temporariamente ou de forma contínua.
    
- Usuários Federados: funcionários de suas organizações parceiras.
    
- Usuários móveis.
    
- Clientes potenciais, parceiros e até mesmo usuários anônimos que você deseja convidar para reuniões e apresentações.
    
O Acesso de Usuário Externo, que é o que os Servidores de Borda fornecem, permitem que tudo isso aconteça. Seus usuários internos poderão aproveitar os seguintes serviços hospedados pela sua implantação Skype for Business Server:
  
- IM e presença para comunicação: usuários externos autorizados podem participar de conversas e conferências de IM. Eles podem obter informações de presença para outros usuários (que também têm suas informações de presença). Você não poderá fazer conferências multipartidário se estiver usando um provedor de IM público, isso é estritamente comunicação ponto a ponto. Mas os protocolos SIP e XMPP são suportados.
    
- Conferência de áudio/vídeo (A/V): usuários externos autorizados podem participar de suas conferências Skype for Business Server áudio e vídeo.
    
- Webconferência: seus usuários externos autorizados podem participar de suas conferências Skype for Business web. Você também pode habilitar a participação para usuários remotos, usuários federados e usuários anônimos, se quiser. Os usuários de IM pública não podem participar de conferências. Também há opções para permitir que esses usuários participem do compartilhamento de aplicativos e área de trabalho e até mesmo atuar como organizadores de reuniões ou apresentadores.
    
Há suporte para acesso a dispositivos móveis, assim como Enterprise Voice. Você pode convidar usuários externos para as reuniões que deseja que eles participem, mesmo que usuários anônimos, se quiser dar permissões a eles.
  
Se isso parece algo que sua organização precisa, então planejar um ambiente de Borda será uma grande ajuda para implantá-lo. Para mais leitura, temos os tópicos listados abaixo.

> [!NOTE]
> Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não são mais suportados no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. 
  
## <a name="planning-topics"></a>Tópicos de planejamento:

Os artigos de planejamento são:
  
- [Requisitos do sistema do Servidor de Borda Skype for Business Server 2015](system-requirements.md)
    
- [Requisitos ambientais do Servidor de Borda Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Cenários do Servidor de Borda Skype for Business Server 2015](scenarios.md)
    

