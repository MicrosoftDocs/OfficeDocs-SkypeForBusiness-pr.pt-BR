---
title: Serviço de usuário para CQD
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumo: Saiba mais sobre o Serviço de Usuário, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803071"
---
# <a name="user-service-for-cqd"></a>Serviço de usuário para CQD
 
**Resumo:** Saiba mais sobre o Serviço de Usuário, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="user-service"></a>Serviço do Usuário

A API de repositório fornece um modelo de gerenciamento de usuário simplificado onde o provisionamento do usuário (criando novas contas de usuário) é automático e implícito. Quando um usuário faz uma solicitação contra a API de Repositório pela primeira vez, o repositório cria um novo registro de usuário. 
  
O Painel de Qualidade da Chamada também cria automaticamente itens dedicados do usuário para o novo usuário. Os novos itens dedicados do usuário são clones completos dos itens do usuário do sistema. Dessa forma, os usuários começam com suas próprias cópias de Relatórios e Consultas que podem iniciar imediatamente a personalização. 
  
> [!NOTE]
> Usando o Painel de Qualidade da Chamada, os usuários podem redefinir seus itens dedicados a qualquer momento. 
  
 **IDs de usuário especiais**
  
A API de repositório inclui URIs da API REST que esperam um valor inteiro para especificar um usuário específico. Exemplo:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . Aqui, {userId} deve ser substituído por um valor inteiro como 0, 1, etc.
  
Além disso, a API de Repositório aceitará duas IDs de usuário especiais em {userId} em URIs.
  
-  *padrão*  - representa o usuário que está interagindo com a API no momento. Isso permite que os aplicativos acessem o conteúdo do usuário atual sem controlar o valor real da ID do usuário. Exemplo: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *system*  - representa o usuário do sistema. Isso permite que os aplicativos acessem o conteúdo do usuário do sistema sem conhecer o valor real da ID do usuário. Exemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
A menos que esteja em contrário, as IDs de usuário especiais podem ser usadas em {userId} em URIs. 
  
As operações REST estão incluídas na tabela a seguir.
  
|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter usuários](get-users.md) <br/> |Retorna uma lista de usuários no repositório.  <br/> |
|[Obter usuário](get-user.md) <br/> |Retorna um registro de usuário.  <br/> |
   

