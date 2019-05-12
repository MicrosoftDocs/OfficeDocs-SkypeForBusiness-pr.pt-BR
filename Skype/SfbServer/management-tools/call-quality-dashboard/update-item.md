---
title: Atualizar Item
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumo: Saiba sobre a operação de atualização de Item, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 6ccdcd401b8f65193fd7e7f93b94c25b8540d1c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915028"
---
# <a name="update-item"></a>Atualizar Item
 
**Resumo:** Saiba mais sobre a operação de atualização de Item, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
A operação de atualização de Item é parte do serviço do Item na API repositório para o painel de controle de qualidade de chamada.
  
## <a name="update-item"></a>Atualizar Item

Atualizar Item atualiza um item específico no repositório.
  

|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https://\<portal\>/QoERepositoryService/repositório/item / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** -conteúdo-tipo: application/json.
  
 **Corpo da solicitação** - JSON.
  
Carga de solicitação de exemplo:
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *conteúdo*  JSON formatado dados a serem armazenados como o novo conteúdo de um Item de subsites existente. Tecnicamente, um repositório pode armazenar o conteúdo de qualquer esquema, mas quando usado para painel de controle de qualidade de chamada, ele deve ser um relatório ou uma consulta. *tipo*  Sempre especifique "application json" para painel de controle de qualidade de chamada.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 204 (sem conteúdo). Se uma ID de item especificado não for encontrada, será retornado o código de status 404 (não encontrado).
  
> [!IMPORTANT]
> "Nenhum conteúdo" não é um status de erro. Isso significa que uma resposta não retornou nada no corpo (em contraste, conteúdo de 200 retorna Okey no corpo). Indica que o Item foi atualizado com êxito. 
  
 **Cabeçalhos de resposta** - None.
  
 **Corpo de resposta** - None.
  

