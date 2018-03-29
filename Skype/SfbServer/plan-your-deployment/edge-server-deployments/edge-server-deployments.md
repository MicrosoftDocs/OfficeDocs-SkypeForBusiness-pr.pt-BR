---
title: Planejar implantações do Servidor de Borda no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: Planejar seu Skype para ambiente de borda de servidor do Business Server 2015. Este tópico apresenta conceitos de borda e permite que você organize-se com nossos tópicos mais aprofundados.'
ms.openlocfilehash: 828bdc52a6c4fe55294768d69c441b9c996fa9a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a>Planejar implantações do Servidor de Borda no Skype for Business Server 2015
 
**Resumo:** planeje o ambiente da Borda do Servidor de seu Skype for Business Server 2015. Este tópico apresenta os conceitos de Borda permite que você se organize com nossos tópicos mais detalhados.
  
Quando você tem um Skype para ambiente de negócios 2015 de servidor que está funcionando bem internamente, a próxima etapa para você pode ser a apresentar um servidor de borda ou um pool de borda para o ambiente. Essa função seria vital se quiser que os serviços fornecidos pelo Skype para negócios 2015 de servidor a ser usado por pessoas que estão fora da rede interna. Isso pode incluir:
  
- Usuários remotos: funcionários remotos, temporariamente ou de modo contínuo.
    
- Os usuários federados: Seu parceiro seus funcionários.
    
- Usuários móveis.
    
- Clientes em potencial, parceiros e até usuários anônimos que você quer convidar para reuniões e apresentações.
    
Acesso de usuário externo, que é o que os servidores de borda fornecem, permitir que tudo isso acontecerá. Os usuários internos será podem aproveitar os seguintes serviços são hospedados por seu Skype para Business Server 2015 implantação:
  
- Mensagens instantâneas e presença para comunicação: usuários externos autorizados podem participar em conversas de mensagens instantâneas e conferências. Eles obter as informações de presença de outros usuários (que também recebem suas informações de presença). Você não poderá fazer conferências com vários participantes, se você estiver usando um provedor público de mensagens Instantâneas, que é estritamente-a-ponto de comunicação. Mas os protocolos SIP e XMPP são aceitos.
    
- Áudio/vídeo (A / V) conferência: os usuários externos autorizados podem participar de sua Skype para conferências de áudio e vídeos Business Server 2015.
    
- Conferência da Web: os usuários externos autorizados podem participar de sua Skype para conferências de negócios. Se você quiser, você também pode habilitar a participação de usuários remotos, usuários federados e usuários anônimos. Os usuários públicos de mensagens Instantâneas não podem participar de conferências. Também existem opções para permitir que esses usuários participem do compartilhamento de área de trabalho e aplicativos, e até mesmo ajam como organizadores ou apresentadores da reunião.
    
Acesso de dispositivo móvel é suportado, como está o Enterprise Voice. Você pode convidar usuários externos para as reuniões das quais eles devem participar, mesmo usuários anônimos, se você quiser dar permissões a eles.
  
Se isso atender às necessidades de sua organização, planejar um ambiente de Borda será de grande ajuda para a implementação. Para ler mais sobre o assunto, temos os tópicos listados abaixo.
  
## <a name="planning-topics"></a>Tópicos de planejamento:

Os artigos de planejamento são:
  
- [Requisitos de sistema do servidor de borda no Skype para Business Server 2015](system-requirements.md)
    
- [Requisitos de ambiente de servidor de borda no Skype para Business Server 2015](edge-environmental-requirements.md)
    
- [Cenários de servidor de borda no Skype para Business Server 2015](scenarios.md)
    

