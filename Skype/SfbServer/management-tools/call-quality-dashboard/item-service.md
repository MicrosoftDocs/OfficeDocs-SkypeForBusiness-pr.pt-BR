---
title: Serviço de item para o painel de controle de qualidade de chamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: Saiba mais sobre o serviço de Item, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: cbebdcfcac62eae375c13785b8d9866d055c2b50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897496"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Serviço de item para o painel de controle de qualidade de chamada (CQD)
 
**Resumo:** Saiba mais sobre o serviço de Item, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.
  
## <a name="item-service"></a>Serviço de itens

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
|[Obter item](get-item.md) <br/> |Obtenha o Item Retorna um Item específico.  <br/> |
|[Obter subitens](get-sub-items.md) <br/> |Obter itens sub-recurso retorna subitens de um Item específico.  <br/> |
|[Obter o Item Predecessor](get-item-ancestors.md) <br/> |Get Item ancestrais retorna ancestrais de um Item específico.  <br/> |
|[Atualizar Item](update-item.md) <br/> |Atualize um item específico no repositório.  <br/> |
   

