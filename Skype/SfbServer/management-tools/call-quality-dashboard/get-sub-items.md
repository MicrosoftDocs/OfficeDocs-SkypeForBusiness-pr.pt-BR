---
title: Obter subitens
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumo: Saiba mais sobre a operação obter subitens, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 523a6050065680550685337dabfec72c87f30bf7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816760"
---
# <a name="get-sub-items"></a>Obter subitens
 
**Resumo:** Saiba mais sobre a operação obter subitens, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação obter subitens é parte do serviço de item na API do repositório para o painel de qualidade da chamada.
  
## <a name="get-sub-items"></a>Obter subitens

Obter subitens retorna os subitens de um item específico.
  

|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<do\>portal de/QoERepositoryService/Repository/item/{itemid}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** -nenhum.
  
 **Solicitar cabeçalhos** -sem cabeçalhos adicionais.
  
 **Corpo da solicitação** -nenhum.
  
 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK). Se um ID de usuário especificado não for encontrado, ele retornará o código de status 404 (não encontrado).
  
 **Cabeçalhos de resposta** -sem cabeçalhos adicionais.
  
 **Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.
  
> [!NOTE]
> Uma matriz de objeto de item é retornada. 
  
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

O objeto de item retornado pela operação de subitens contém somente os três campos a seguir. 
  
 *ItemId* -ID do item.
  
 *userid* -ID do usuário que é proprietário deste item.
  
 *tipo* – o tipo do conteúdo. Este campo é definido pelos aplicativos.
  
> [!NOTE]
>  `Content`os `subItems` campos não são incluídos na resposta para reduzir a quantidade de dados transmitidos pela rede.
  

