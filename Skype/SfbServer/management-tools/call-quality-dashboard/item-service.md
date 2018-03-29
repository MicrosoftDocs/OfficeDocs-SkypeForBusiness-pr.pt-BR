---
title: Serviço de item para o painel de controle de qualidade de chamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: Saiba mais sobre o serviço de Item, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 218fdb4f2c4b3d73fb4e7f78b5679b66eecf34cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Serviço de item para o painel de controle de qualidade de chamada (CQD)
 
**Resumo:** Saiba mais sobre o serviço de Item, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.
  
## <a name="item-service"></a>Serviço de item

API do repositório oferece um serviço de gerenciamento de conteúdo simples, conhecido como serviço de item, que pode ser usado para armazenar qualquer conteúdo definido pelo aplicativo para usuários. 
  
O conteúdo do sistema é pertencentes ao usuário do sistema e compartilhado por todos os usuários com acesso somente leitura. Conteúdo de usuário dedicada pertencentes a usuários regulares e somente os proprietários podem modificar ou excluí-los, mas todos os usuários ainda têm acesso somente leitura a eles.
  
> [!NOTE]
> Esta documentação de API abrange operações somente leitura da API do repositório. 
  
Painel de controle de qualidade de chamada salva relatórios e consultas como itens do banco de dados do repositório. Um Item pode ter itens sub-recurso opcionais e painel de controle de qualidade de chamada organiza relatórios e consultas em uma estrutura hierárquica usando o recurso de subitens.
  
O serviço de item inclui os seguintes conceitos:
  
- **Item** - o elemento básico de repositório. Cada Item pertence ao usuário exatamente uma.
    
- **Item de suba** mecânica organizacional básica do repositório. O item pode ter zero, um ou mais itens de subordinados.
    
- **Item ancestrais** - a lista de itens, o Item superior, que é o padrão de Item do usuário, levando a um determinado Item tem início.
    
- **Item de conteúdo** - o conteúdo de aplicativo específico armazenado em itens. Painel de controle de qualidade de chamada salva as representações de JSON de relatórios e consultas no conteúdo.
    
As operações do REST estão incluídas na tabela a seguir.
  

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter itens](get-items.md) <br/> |Obter itens retorna todos os itens no repositório.  <br/> |
|[Obtenha Item](get-item.md) <br/> |Obtenha o Item Retorna um Item específico.  <br/> |
|[Obter itens sub-recurso](get-sub-items.md) <br/> |Obter itens sub-recurso retorna subitens de um Item específico.  <br/> |
|[Obter ancestrais do Item](get-item-ancestors.md) <br/> |Get Item ancestrais retorna ancestrais de um Item específico.  <br/> |
|[Atualizar Item](update-item.md) <br/> |Atualize um item específico no repositório.  <br/> |
   

