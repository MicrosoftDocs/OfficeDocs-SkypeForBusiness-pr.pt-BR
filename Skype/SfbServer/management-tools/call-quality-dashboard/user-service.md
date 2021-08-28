---
title: Serviço de Usuário para CQD
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumo: Saiba mais sobre o Serviço de Usuário, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 4a7655e7f3e9dfb846c3978786e92dbbce078083
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606140"
---
# <a name="user-service-for-cqd"></a>Serviço de Usuário para CQD
 
**Resumo:** Saiba mais sobre o Serviço de Usuário, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="user-service"></a>Serviço do Usuário

A API de repositório fornece um modelo de gerenciamento de usuário simplificado em que o provisionamento do usuário (criação de novas contas de usuário) é automático e implícito. Quando um usuário faz uma solicitação contra a API de Repositório pela primeira vez, o repositório cria um novo registro de usuário. 
  
O Painel de Qualidade de Chamada também cria automaticamente itens dedicados ao usuário para o novo usuário. Os novos itens dedicados ao usuário são clones completos dos itens do usuário do sistema. Dessa forma, os usuários começam com suas próprias cópias de Relatórios e Consultas que podem iniciar imediatamente a personalização. 
  
> [!NOTE]
> Usando o Painel de Qualidade de Chamada, os usuários podem redefinir seus itens dedicados a qualquer momento. 
  
 **IDs de usuário especiais**
  
A API do Repositório inclui URIs da API REST que esperam um valor inteiro para especificar um usuário específico. Exemplo:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . Aqui, {userId} deve ser substituído por um valor inteiro, como 0, 1, etc.
  
Além disso, a API do Repositório aceitará duas IDs de usuário especiais em {userId} em URIs.
  
-  *default*  - representa o usuário que está interagindo com a API no momento. Isso permite que os aplicativos acessem o conteúdo do usuário atual sem acompanhar o valor real da ID do usuário. Exemplo: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *system*  - representa o usuário do sistema. Isso permite que os aplicativos acessem o conteúdo do usuário do sistema sem saber o valor real da ID do usuário. Exemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
A menos que seja notado de outra forma, as IDs de usuário especiais podem ser usadas em {userId} em URIs. 
  
As operações REST estão incluídas na tabela a seguir.
  
|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter usuários](get-users.md) <br/> |Retorna uma lista de usuários no repositório.  <br/> |
|[Obter usuário](get-user.md) <br/> |Retorna um registro de usuário.  <br/> |
   

