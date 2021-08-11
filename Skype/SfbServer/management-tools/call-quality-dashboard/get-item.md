---
title: Obter item
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumo: saiba mais sobre a operação Obter Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: fa82d158b41826a950a852633e6c039e9262543d4aabece5c04397eba40be8ae
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278439"
---
# <a name="get-item"></a>Obter item
 
**Resumo:** Saiba mais sobre a operação Obter Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Get Item faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-item"></a>Obter item

Get Item retorna um item específico no repositório.
  
|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repositório/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Headers de solicitação** - Sem headers adicionais.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de item especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).
  
 **Headers de resposta** - Sem headers adicionais.
  
 **Corpo da Resposta** - Abaixo está uma carga de resposta de exemplo no JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId*  - ID do item.
  
 *userId*  - ID do usuário proprietário desse item.
  
 *content*  - O conteúdo específico do aplicativo.
  
 *type*  - O tipo do conteúdo. Esse campo é definido pelos aplicativos.
  
 *subItemIds*  - As IDs de sub-Items, se algum. Este é um curto-circuito da operação Obter Sub-Items para salvar uma chamada. Os aplicativos podem, alternativamente, obter as mesmas informações usando Obter Sub-Items operação.
  

