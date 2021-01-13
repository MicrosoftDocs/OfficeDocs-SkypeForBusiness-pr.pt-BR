---
title: Obter os Subitens
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumo: saiba mais sobre a operação Sub-Items obter, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832501"
---
# <a name="get-sub-items"></a>Obter os Subitens
 
**Resumo:** Saiba mais sobre a operação Sub-Items obter, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Sub-Items é parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-sub-items"></a>Obter os Subitens

Get Sub-Items retorna sub-itens de um Item específico.
  

|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subtentem  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.
  
> [!NOTE]
> Uma matriz do objeto Item é retornada. 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

O objeto Item retornado pela Sub-Items contém apenas os três campos a seguir. 
  
 *itemId*  - ID do item.
  
 *userId*  - ID do usuário que possui este Item.
  
 *tipo*  - O tipo do conteúdo. Esse campo é definido pelos aplicativos.
  
> [!NOTE]
>  `Content` e `subItems` os campos não são incluídos na resposta para reduzir a quantidade de dados transmitidos pela rede.
  

