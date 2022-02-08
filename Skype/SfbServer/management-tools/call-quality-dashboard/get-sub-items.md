---
title: Obter os Subitens
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumo: saiba mais sobre a operação Obter Sub-Items, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 6bfa8e449610317caeeaf512e088f2b56441bd2b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385569"
---
# <a name="get-sub-items"></a>Obter os Subitens
 
**Resumo:** Saiba mais sobre a operação Obter Sub-Items, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Obter Sub-Items faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-sub-items"></a>Obter os Subitens

Obter Sub-Items retorna os sub-itens de um Item específico.
  

|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |\<portal\>https:///QoERepositoryService/repositório/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Headers de solicitação** - Sem headers adicionais.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).
  
 **Headers de resposta** - Sem headers adicionais.
  
 **Corpo da Resposta** - Abaixo está uma carga de resposta de exemplo no JSON.
  
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

O objeto Item retornado pela operação Sub-Items contém apenas os três campos a seguir. 
  
 *itemId*  - ID do item.
  
 *userId*  - ID do Usuário que é o proprietário deste Item.
  
 *type*  - O tipo do conteúdo. Esse campo é definido pelos aplicativos.
  
> [!NOTE]
>  `Content` e `subItems` os campos não são incluídos na resposta para reduzir a quantidade de dados transmitidos pela rede.
  

