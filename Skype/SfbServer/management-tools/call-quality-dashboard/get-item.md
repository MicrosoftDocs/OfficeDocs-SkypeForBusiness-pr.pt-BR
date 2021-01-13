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
description: 'Resumo: saiba mais sobre a operação Obter Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832561"
---
# <a name="get-item"></a>Obter item
 
**Resumo:** Saiba mais sobre a operação Obter Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Item faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-item"></a>Obter item

Get Item retorna um item específico no repositório.
  
|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de item especificada não for encontrada, retornará o código de status 404 (Não Encontrado).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.
  
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
  
 *userId*  - ID do usuário que possui esse item.
  
 *content*  - O conteúdo específico do aplicativo.
  
 *tipo*  - O tipo do conteúdo. Esse campo é definido pelos aplicativos.
  
 *subItemIds*  - as IDs de subsistros, se necessário. Este é um curto circuito da operação Obter Sub-Items para salvar uma chamada. Como alternativa, os aplicativos podem obter as mesmas informações usando a Sub-Items obter.
  

