---
title: Incluir o suporte de segurança no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planejamento de como incluir o suporte de segurança da sua organização em uma implantação do E9-1-1, em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 952d10a4547ec91452e9ea60f43c58c70c04c7c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="include-the-security-desk-in-skype-for-business-server-2015"></a>Incluir o suporte de segurança no Skype for Business Server 2015
 
Planejamento de como incluir o suporte de segurança da sua organização em uma implantação do E9-1-1, em Skype para Business Server Enterprise Voice.
  
Sua empresa pode exigir que a central de segurança se envolva em uma chamada de emergência. Para ajudar a decidir como integrar a Central de Segurança à sua implantação do E9-1-1, você deve responder às perguntas a seguir.
  
**Você deseja que o suporte de segurança seja notificado quando houver uma chamada de emergência?**
  
Você pode configurar a política de local para que Skype para Business Server envia alertas de (IM) de mensagens instantâneas para o Skype para endereços corporativos SIP do pessoal de segurança de um ou mais. Esses alertas contêm o nome, o número e o local da pessoa que está fazendo a chamada de emergência e facilitam a segurança na assistência com a situação de emergência.
    
**Deseja estabelecer conferência com o suporte de segurança em cada chamada de emergência?**
  
Se tiver suporte do provedor de serviços de emergência, você poderá configurar a política de local para incluir um número de retorno de chamada com cada chamada de emergência. Esse número é usado pelo provedor para estabelecer conferência com a equipe de segurança da sua organização em chamadas de emergência. Essa conferência pode ser configurada na política de local para ser unidirecional (somente escuta) ou bidirecional.
    
> [!NOTE]
> Se desejar, você pode configurar uma equipe de segurança diferente para cada política de local. Isso permite personalizar a resposta para áreas diferentes da empresa ou criar um comportamento diferente para chamadas de emergência que originam da parte interna em oposição à parte externa da rede. Você pode usar grupos de distribuição para especificar o pessoal que deseja notificar. 
  

