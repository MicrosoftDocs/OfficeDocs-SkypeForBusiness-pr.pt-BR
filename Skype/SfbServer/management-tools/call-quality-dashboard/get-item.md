---
title: Obtenha Item
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumo: Saiba mais sobre a operação obter Item, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 12b52bdd51e8ba59f1aa90e2a366b3e11fb54805
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532359"
---
# <a name="get-item"></a>Obtenha Item
 
**Resumo:** Saiba mais sobre a operação obter Item, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
A operação obter Item é parte do serviço do Item na API repositório para o painel de controle de qualidade de chamada.
  
## <a name="get-item"></a>Obtenha Item

Obtenha o Item Retorna um item específico no repositório.
  
|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<portal\>/QoERepositoryService/repositório/item / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 O **corpo da solicitação** - None.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey). Se uma ID de item especificado não for encontrada, será retornado o código de status 404 (não encontrado).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId* - ID do item.
  
 *userId* - ID do usuário que possui esse item.
  
 *conteúdo* – o conteúdo de aplicativo específico.
  
 *tipo* - o tipo de conteúdo. Este campo é definido pelos aplicativos.
  
 *subItemIds* - as identificações de subitens, se houver alguma. Este é um short-circuit da operação Get sub-recurso Items para salvar uma chamada. Aplicativos podem se desejar obter as mesmas informações usando a operação obter itens subsites.
  

