---
title: Inclua o security desk no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planejando como incluir o escritório de segurança da sua organização em uma implantação do E9-1-1, Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 7d65fb30fe62441e83386dcfaa0b90a13bb3c32f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767539"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Inclua o security desk no Skype for Business Server
 
Planejando como incluir o escritório de segurança da sua organização em uma implantação do E9-1-1, Skype for Business Server Enterprise Voice.
  
Sua empresa pode exigir que a central de segurança se envolva em uma chamada de emergência. Para ajudar a decidir como integrar a Central de Segurança à sua implantação do E9-1-1, você deve responder às perguntas a seguir.
  
**Você deseja que o suporte de segurança seja notificado quando houver uma chamada de emergência?**
  
Você pode configurar a política de local para que Skype for Business Server envie alertas de mensagens instantâneas (IM) para os endereços SIP Skype for Business de uma ou mais equipes de segurança. Esses alertas contêm o nome, o número e o local da pessoa que está fazendo a chamada de emergência e facilitam a segurança na assistência com a situação de emergência.
    
**Deseja estabelecer conferência com o suporte de segurança em cada chamada de emergência?**
  
Se tiver suporte do provedor de serviços de emergência, você poderá configurar a política de local para incluir um número de retorno de chamada com cada chamada de emergência. Esse número é usado pelo provedor para estabelecer conferência com a equipe de segurança da sua organização em chamadas de emergência. Essa conferência pode ser configurada na política de local para ser unidirecional (somente escuta) ou bidirecional.
    
> [!NOTE]
> Se desejar, você pode configurar uma equipe de segurança diferente para cada política de local. Isso permite personalizar a resposta para áreas diferentes da empresa ou criar um comportamento diferente para chamadas de emergência que originam da parte interna em oposição à parte externa da rede. Você pode usar grupos de distribuição para especificar o pessoal que você deseja notificar. 
  

