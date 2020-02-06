---
title: Painel de serviço de item para o painel de qualidade da chamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumo: Saiba mais sobre o serviço de item, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 5fdf2aedcb1a5e8d7d1929d7af70c5911cae46f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816710"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Painel de serviço de item para o painel de qualidade da chamada (CQD)
 
**Resumo:** Saiba mais sobre o serviço de item, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
O serviço de item faz parte da API do repositório para o painel de qualidade da chamada.
  
## <a name="item-service"></a>Serviço de itens

A API do repositório oferece um serviço de gerenciamento de conteúdo simples, conhecido como serviço de item, que pode ser usado para armazenar qualquer conteúdo definido pelo aplicativo para os usuários. 
  
O conteúdo do sistema é de Propriedade do usuário do sistema e compartilhado por todos os usuários com acesso somente leitura. O conteúdo do usuário exclusivo pertence a usuários regulares, e somente os proprietários podem modificá-los ou excluí-los, mas todos os usuários ainda têm acesso somente leitura a eles.
  
> [!NOTE]
> Esta documentação de API aborda operações somente leitura da API do repositório. 
  
O painel de qualidade de chamada salva relatórios e consultas como itens no banco de dados do repositório. Um item pode ter subitens opcionais, e o painel de qualidade da chamada organiza relatórios e consultas em uma estrutura hierárquica usando o recurso de subitens.
  
O serviço de item inclui os seguintes conceitos:
  
- **Item** -o elemento básico do repositório. Cada item pertence a exatamente um usuário.
    
- **Subitem** -a mecânica organizacional básica do repositório. O item pode ter zero, um ou mais itens subordinados.
    
- **Item ancestrais** -a lista de itens, a partir do item mais superior, que é o item padrão do usuário, que leva a um determinado item.
    
- **Conteúdo do item** – o conteúdo específico do aplicativo armazenado em itens. Painel de qualidade de chamada salva representações JSON de relatórios e consultas no conteúdo.
    
As operações REST estão incluídas na tabela a seguir.
  

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter itens](get-items.md) <br/> |Obter itens retorna todos os itens no repositório.  <br/> |
|[Obter item](get-item.md) <br/> |Obter item retorna um item específico.  <br/> |
|[Obter subitens](get-sub-items.md) <br/> |Obter subitens retorna os subitens de um item específico.  <br/> |
|[Obter o Item Predecessor](get-item-ancestors.md) <br/> |Obter item ancestrais retorna os ancestrais de um item específico.  <br/> |
|[Atualizar Item](update-item.md) <br/> |Atualize um item específico no repositório.  <br/> |
   

