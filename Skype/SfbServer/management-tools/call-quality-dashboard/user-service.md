---
title: Serviço de usuário para CQD
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumo: Saiba mais sobre o serviço de usuário, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 6e0a6a58be98469458a8c8e7063402ff6477c35f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221307"
---
# <a name="user-service-for-cqd"></a>Serviço de usuário para CQD
 
**Resumo:** Saiba mais sobre o serviço de usuário, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada.
  
## <a name="user-service"></a>Serviço do usuário

A API do repositório fornece um modelo simplificado de gerenciamento de usuários onde o provisionamento do usuário (criação de novas contas de usuário) é automático e implícito. Quando um usuário faz uma solicitação em relação à API do repositório pela primeira vez, o repositório cria um novo registro de usuário. 
  
O painel de qualidade de chamada também cria automaticamente itens dedicados do usuário para o novo usuário. Os novos itens dedicados do usuário são clones completos dos itens do usuário do sistema. Dessa forma, os usuários começam com suas próprias cópias de relatórios e consultas que podem iniciar a personalização imediatamente. 
  
> [!NOTE]
> Usando o painel de qualidade da chamada, os usuários podem redefinir seus itens dedicados a qualquer momento. 
  
 **IDs de usuário especiais**
  
A API do repositório inclui URIs de API REST que esperam um valor inteiro para especificar um usuário específico. Exemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`. Aqui, {userId} deve ser substituído por um valor inteiro, como 0, 1, etc.
  
Além disso, a API do repositório aceitará duas IDs de usuário especiais em {userId} em URIs.
  
-  *padrão* -representa o usuário que está interagindo com a API no momento. Isso permite que os aplicativos acessem o conteúdo do usuário atual sem acompanhar o valor real da ID do usuário. Exemplo: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *System* -representa o usuário do sistema. Isso permite que os aplicativos acessem o conteúdo do usuário do sistema sem conhecer o valor real da ID do usuário. Exemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
A menos que indicado de outra forma, as IDs de usuário especiais podem ser usadas em {userId} em URIs. 
  
As operações REST estão incluídas na tabela a seguir.
  
|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter usuários](get-users.md) <br/> |Retorna uma lista de usuários no repositório.  <br/> |
|[Obter usuário](get-user.md) <br/> |Retorna um registro de usuário.  <br/> |
   

