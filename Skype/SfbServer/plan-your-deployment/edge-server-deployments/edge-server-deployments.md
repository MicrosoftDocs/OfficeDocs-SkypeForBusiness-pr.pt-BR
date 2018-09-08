---
title: Planejar para implantações de servidor de borda no Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: Planejar seu Skype para ambiente de servidor de borda de negócios. Este tópico apresenta conceitos de borda e permite que você organize-se com nossos tópicos mais aprofundados.'
ms.openlocfilehash: f558a4a9623e54a38e134716afe9b95021f237dc
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886119"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planejar para implantações de servidor de borda no Skype para Business Server
 
**Resumo:** Planeje sua Skype para ambiente de servidor de borda de negócios. Este tópico apresenta conceitos de borda e permite que você organize-se com nossos tópicos mais aprofundados.
  
Quando você tem um Skype corporativos para ambiente de servidor que está funcionando bem internamente, a próxima etapa para você pode ser a apresentar um servidor de borda ou um pool de borda para o ambiente. Essa função seria vital se quiser que os serviços fornecidos pelo Skype para Business Server a ser usado por pessoas que estão fora da rede interna. Isso pode incluir:
  
- Usuários remotos: funcionários remotos, temporariamente ou de modo contínuo.
    
- Os usuários federados: Seu parceiro seus funcionários.
    
- Usuários móveis.
    
- Clientes em potencial, parceiros e até usuários anônimos que você quer convidar para reuniões e apresentações.
    
Acesso de usuário externo, que é o que os servidores de borda fornecem, permitir que tudo isso acontecerá. Os usuários internos será podem aproveitar os seguintes serviços são hospedados por seu Skype para implantação de servidor de negócios:
  
- Mensagens instantâneas e presença para comunicação: usuários externos autorizados podem participar em conversas de mensagens instantâneas e conferências. Eles obter as informações de presença de outros usuários (que também recebem suas informações de presença). Você não poderá fazer conferências com vários participantes, se você estiver usando um provedor público de mensagens Instantâneas, que é estritamente-a-ponto de comunicação. Mas os protocolos SIP e XMPP são aceitos.
    
- Áudio/vídeo (A / V) conferência: os usuários externos autorizados podem participar de sua Skype para conferências de áudio e vídeos Business Server.
    
- Conferência da Web: os usuários externos autorizados podem participar de sua Skype para conferências de negócios. Se você quiser, você também pode habilitar a participação de usuários remotos, usuários federados e usuários anônimos. Os usuários públicos de mensagens Instantâneas não podem participar de conferências. Também existem opções para permitir que esses usuários participem do compartilhamento de área de trabalho e aplicativos, e até mesmo ajam como organizadores ou apresentadores da reunião.
    
Acesso de dispositivo móvel é suportado, como está o Enterprise Voice. Você pode convidar usuários externos para as reuniões das quais eles devem participar, mesmo usuários anônimos, se você quiser dar permissões a eles.
  
Se isso atender às necessidades de sua organização, planejar um ambiente de Borda será de grande ajuda para a implementação. Para ler mais sobre o assunto, temos os tópicos listados abaixo.

> [!NOTE]
> Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019. Consulte a [federação XMPP migrando](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. 
  
## <a name="planning-topics"></a>Tópicos de planejamento:

Os artigos de planejamento são:
  
- [Requisitos de sistema do Servidor de Borda no Skype for Business Server 2015](system-requirements.md)
    
- [Requisitos de ambiente do Servidor de Borda no Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Cenários do Servidor de Borda no Skype for Business Server 2015](scenarios.md)
    

