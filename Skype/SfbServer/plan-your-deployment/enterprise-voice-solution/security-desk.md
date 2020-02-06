---
title: Inclua a central de segurança no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planejando como incluir a segurança da sua organização em uma implantação do E9-1-1, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 19fc8a01fcb51be3ce36435a5a657c3253716b2c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802451"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Inclua a central de segurança no Skype for Business Server
 
Planejando como incluir a segurança da sua organização em uma implantação do E9-1-1, no Skype for Business Server Enterprise Voice.
  
Sua empresa pode exigir que a central de segurança se envolva em uma chamada de emergência. Para ajudar a decidir como integrar a Central de Segurança à sua implantação do E9-1-1, você deve responder às perguntas a seguir.
  
**Você deseja que o suporte de segurança seja notificado quando houver uma chamada de emergência?**
  
Você pode configurar a política de localização para que o Skype for Business Server envie alertas de mensagem instantânea aos endereços SIP do Skype for Business de um ou mais funcionários de segurança. Esses alertas contêm o nome, o número e o local da pessoa que está fazendo a chamada de emergência e facilitam a segurança na assistência com a situação de emergência.
    
**Deseja estabelecer conferência com o suporte de segurança em cada chamada de emergência?**
  
Se tiver suporte do provedor de serviços de emergência, você poderá configurar a política de local para incluir um número de retorno de chamada com cada chamada de emergência. Esse número é usado pelo provedor para estabelecer conferência com a equipe de segurança da sua organização em chamadas de emergência. Essa conferência pode ser configurada na política de local para ser unidirecional (somente escuta) ou bidirecional.
    
> [!NOTE]
> Se desejar, você pode configurar uma equipe de segurança diferente para cada política de local. Isso permite personalizar a resposta para áreas diferentes da empresa ou criar um comportamento diferente para chamadas de emergência que originam da parte interna em oposição à parte externa da rede. Você pode usar grupos de distribuição para especificar o pessoal que deseja notificar. 
  

