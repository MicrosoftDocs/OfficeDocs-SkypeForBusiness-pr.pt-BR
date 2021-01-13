---
title: Obter o Item Predecessor
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumo: Saiba mais sobre a operação Get Item Ancestors, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832571"
---
# <a name="get-item-ancestors"></a>Obter o Item Predecessor
 
**Resumo:** Saiba mais sobre a operação Get Item Ancestors, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Get Item Ancestors faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-item-ancestors"></a>Obter o Item Predecessor

Obter Item Ancestors retorna itens específicos ancestrais do repositório.
  

|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.
  
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
  

