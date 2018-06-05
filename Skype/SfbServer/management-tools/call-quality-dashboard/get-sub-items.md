---
title: Obter itens sub-recurso
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumo: Saiba mais sobre a operação obter itens sub, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: bc2af38036a40b9181b8ae3ccaa39a803e4e9723
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569586"
---
# <a name="get-sub-items"></a>Obter itens sub-recurso
 
**Resumo:** Saiba mais sobre a operação obter itens sub, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
A operação obter itens sub-recurso é parte do serviço do Item na API repositório para o painel de controle de qualidade de chamada.
  
## <a name="get-sub-items"></a>Obter itens sub-recurso

Obter itens sub-recurso retorna subitens de um Item específico.
  

|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<portal\>/QoERepositoryService/repositório/item / {itemId} / subitem  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 O **corpo da solicitação** - None.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey). Se um usuário especificado que ID não for encontrado, será retornado o código de status 404 (não encontrado).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.
  
> [!NOTE]
> Uma matriz de objeto de Item será retornada. 
  
```
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

O objeto de Item retornado pela operação de subitens contém apenas os seguintes três campos. 
  
 *itemId* - ID do item.
  
 *userId* - ID do usuário que possui esse Item.
  
 *tipo* - o tipo de conteúdo. Este campo é definido pelos aplicativos.
  
> [!NOTE]
>  `Content`e `subItems` campos não estão incluídos na resposta para reduzir a quantidade de dados transmitidos na rede.
  

