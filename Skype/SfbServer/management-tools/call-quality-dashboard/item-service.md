---
title: Serviço de Item para Painel de Qualidade de Chamada (CQD)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: saiba mais sobre o Serviço de Item, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827701"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Serviço de Item para Painel de Qualidade de Chamada (CQD)
 
**Resumo:** Saiba mais sobre o Serviço de Item, que faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada.
  
## <a name="item-service"></a>Serviço de Itens

A API de repositório oferece um serviço de gerenciamento de conteúdo simples, conhecido como serviço de item, que pode ser usado para armazenar qualquer conteúdo definido pelo aplicativo para os usuários. 
  
O conteúdo do sistema é de propriedade do usuário do sistema e compartilhado por todos os usuários com acesso somente leitura. O conteúdo dedicado do usuário pertence a usuários regulares e somente os proprietários podem modificá-los ou excluí-los, mas todos os usuários ainda têm acesso somente leitura a eles.
  
> [!NOTE]
> Esta documentação da API abrange operações somente leitura da API de Repositório. 
  
O Painel de Qualidade da Chamada salva Relatórios e Consultas como Itens no banco de dados de repositório. Um Item pode ter sub-itens opcionais, e o Painel de Qualidade de Chamada organiza relatórios e consultas em uma estrutura hierárquica usando o recurso sub-itens.
  
O serviço de item inclui os seguintes conceitos:
  
- **Item** - o elemento básico do repositório. Cada item pertence a exatamente um usuário.
    
- **Sub-Item** - a mecânica organizacional básica do repositório. O item pode ter zero, um ou mais itens subordinados.
    
- **Item Ancestrales** - a lista de itens, começando do item mais alto, que é o item padrão do usuário, levando a um determinado Item.
    
- **Conteúdo do Item** - o conteúdo específico do aplicativo armazenado em Itens. O Painel de Qualidade da Chamada salva representações JSON de Relatórios e Consultas no Conteúdo.
    
As operações REST estão incluídas na tabela a seguir.
  

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter itens](get-items.md) <br/> |Obter itens retorna todos os itens no repositório.  <br/> |
|[Obter item](get-item.md) <br/> |Get Item retorna um Item específico.  <br/> |
|[Obter subitens](get-sub-items.md) <br/> |Get Sub-Items retorna sub-itens de um item específico.  <br/> |
|[Obter o Item Predecessor](get-item-ancestors.md) <br/> |Get Item Ancestors retorna ancestrais de um item específico.  <br/> |
|[Atualizar Item](update-item.md) <br/> |Atualize um item específico no repositório.  <br/> |
   

