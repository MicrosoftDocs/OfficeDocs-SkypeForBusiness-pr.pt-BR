---
title: Serviço de Item para Painel de Qualidade de Chamada (CQD)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: saiba mais sobre o Serviço de Item, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: a0a6ddc923ebf55e5b11ea794398286ca1d19728
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760599"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Serviço de Item para Painel de Qualidade de Chamada (CQD)
 
**Resumo:** Saiba mais sobre o Serviço de Item, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="item-service"></a>Serviço de Itens

A API de repositório oferece um serviço de gerenciamento de conteúdo simples, conhecido como serviço de item, que pode ser usado para armazenar qualquer conteúdo definido pelo aplicativo para usuários. 
  
O conteúdo do sistema pertence ao usuário do sistema e compartilhado por todos os usuários com acesso somente leitura. O conteúdo dedicado do usuário pertence a usuários regulares e somente os proprietários podem modificá-los ou excluí-los, mas todos os usuários ainda têm acesso somente leitura a eles.
  
> [!NOTE]
> Esta documentação da API abrange operações somente leitura da API do Repositório. 
  
O Painel de Qualidade de Chamada salva Relatórios e Consultas como Itens no banco de dados do repositório. Um Item pode ter sub-Itens opcionais e o Painel de Qualidade de Chamada organiza Relatórios e Consultas em uma estrutura hierárquica usando o recurso sub-Items.
  
O serviço item inclui os seguintes conceitos:
  
- **Item** - o elemento básico do repositório. Cada Item pertence a exatamente um Usuário.
    
- **Sub-Item** - a mecânica organizacional básica do repositório. Item pode ter zero, um ou mais Itens subordinados.
    
- **Item Ancestrales** - a lista de Itens, começando a partir do Item mais alto, que é o Item padrão do Usuário, levando a um determinado Item.
    
- **Conteúdo do** Item - o conteúdo específico do aplicativo armazenado em Itens. O Painel de Qualidade de Chamada salva representações JSON de Relatórios e Consultas no Conteúdo.
    
As operações REST estão incluídas na tabela a seguir.
  

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter itens](get-items.md) <br/> |Get Items retorna todos os Itens no repositório.  <br/> |
|[Obter item](get-item.md) <br/> |Get Item retorna um Item específico.  <br/> |
|[Obter subitens](get-sub-items.md) <br/> |Obter Sub-Items retorna sub-Itens de um item específico.  <br/> |
|[Obter o Item Predecessor](get-item-ancestors.md) <br/> |Obter Ancestrais de Item retorna os ancestrais de um item específico.  <br/> |
|[Atualizar Item](update-item.md) <br/> |Atualize um item específico no repositório.  <br/> |
   

