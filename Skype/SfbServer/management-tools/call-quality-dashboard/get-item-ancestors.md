---
title: Obter o Item Predecessor
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumo: saiba mais sobre a operação Obter Ancestrais do Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 0cfc5385af1c0c821d4dc64e9ba0e0bd092fe833
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393733"
---
# <a name="get-item-ancestors"></a>Obter o Item Predecessor
 
**Resumo:** Saiba mais sobre a operação Obter Ancestrais do Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Obter Ancestrais do Item faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-item-ancestors"></a>Obter o Item Predecessor

Get Item Ancestrals retorna um itens específicos ancestrais do repositório.
  

|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |\<portal\>https:///QoERepositoryService/repositório/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Headers de solicitação** - Sem headers adicionais.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).
  
 **Headers de resposta** - Sem headers adicionais.
  
 **Corpo da Resposta** - Abaixo está uma carga de resposta de exemplo no JSON.
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1*  - ID do item.
  
 *Item2*  - Profundidade é a distância do Item. 0 é o pai imediato.
  
 *Item3*  - Título do item.
  

