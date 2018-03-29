---
title: Serviço de usuário para CQD
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumo: Saiba mais sobre o serviço de usuário, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: c4bb2395ea3fa4541140a7966bbfb554ef53c168
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="user-service-for-cqd"></a>Serviço de usuário para CQD
 
**Resumo:** Saiba mais sobre o serviço de usuário, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada.
  
## <a name="user-service"></a>Serviço de usuário

API do repositório fornece um modelo de gerenciamento de usuário simplificada onde o provisionamento (criando novas contas de usuário) do usuário é automático e implícita. Quando um usuário faz uma solicitação em relação a API do repositório pela primeira vez, o repositório cria um novo registro de usuário. 
  
Painel de controle de qualidade também cria automaticamente um usuário de chamada dedicada itens para o novo usuário. Os novos itens de usuário dedicado são clones completas dos itens do usuário do sistema. Dessa forma, os usuários começam com suas próprias cópias de relatórios e consultas que eles podem iniciar imediatamente personalizando. 
  
> [!NOTE]
> Usando o painel de controle de qualidade de chamada, os usuários podem redefinir seus itens dedicados a qualquer momento. 
  
 **IDs de usuário especiais**
  
API do repositório inclui REST API URIs que espera um valor inteiro para especificar um determinado usuário. Exemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`. Aqui, {userId} deverão ser substituído por um valor inteiro, como 0, 1, etc.
  
Além disso, a API do repositório aceitará duas identificações de usuário especiais em {userId} em URIs.
  
-  *padrão* - representa o usuário que está atualmente interagindo com a API. Isso permite aos aplicativos acessar o conteúdo do usuário atual sem manter o controle do valor de ID de usuário real. Exemplo: ` https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *sistema* - representa o usuário do sistema. Isso permite aos aplicativos acessar o conteúdo do usuário do sistema sem saber o valor de ID de usuário real. Exemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
Salvo indicação contrária, as IDs de usuário especiais podem ser usado em {userId} em URIs. 
  
As operações do REST estão incluídas na tabela a seguir.
  
|**Operação**|**Descrição**|
|:-----|:-----|
|[Colocar os usuários](get-users.md) <br/> |Retorna uma lista de usuários no repositório.  <br/> |
|[Obter do usuário](get-user.md) <br/> |Retorna um registro de usuário.  <br/> |
   

