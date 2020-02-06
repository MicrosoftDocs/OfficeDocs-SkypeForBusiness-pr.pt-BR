---
title: Obter item
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumo: Saiba mais sobre a operação de obtenção de itens, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 295276e6f3b0f577dae9a43c4c0f62e23b8582f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816790"
---
# <a name="get-item"></a>Obter item
 
**Resumo:** Saiba mais sobre a operação obter item, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação obter item faz parte do serviço de itens na API do repositório para o painel de qualidade da chamada.
  
## <a name="get-item"></a>Obter item

Obter item retorna um item específico no repositório.
  
|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<do\>portal de/QoERepositoryService/Repository/item/{itemid}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** -nenhum.
  
 **Solicitar cabeçalhos** -sem cabeçalhos adicionais.
  
 **Corpo da solicitação** -nenhum.
  
 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de item especificada não for encontrada, será retornado o código de status 404 (não encontrado).
  
 **Cabeçalhos de resposta** -sem cabeçalhos adicionais.
  
 **Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *ItemId* -ID do item.
  
 *userid* -ID do usuário que é proprietário deste item.
  
 *conteúdo* -o conteúdo específico do aplicativo.
  
 *tipo* – o tipo do conteúdo. Este campo é definido pelos aplicativos.
  
 *Subitemids* – as IDs de subitens, se houver. Trata-se de um curto circuito para obter a operação de subitens para salvar uma chamada. Os aplicativos também podem obter as mesmas informações usando a operação obter subitens.
  

