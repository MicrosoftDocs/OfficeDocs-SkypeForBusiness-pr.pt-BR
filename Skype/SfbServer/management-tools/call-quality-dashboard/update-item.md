---
title: Atualizar Item
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumo: Saiba mais sobre a operação atualizar item, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816670"
---
# <a name="update-item"></a>Atualizar Item
 
**Resumo:** Saiba mais sobre a operação atualizar item, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação atualizar item faz parte do serviço de itens na API do repositório para o painel de qualidade da chamada.
  
## <a name="update-item"></a>Atualizar Item

Atualizar item atualiza um item específico no repositório.
  

|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|SUSPENDE  <br/> |https://\<do\>portal de/QoERepositoryService/Repository/item/{itemid}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** -nenhum.
  
 **Cabeçalhos de solicitação** -Content-Type: Application/JSON.
  
 **Corpo da solicitação** -JSON.
  
Exemplo de carga de solicitação:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *conteúdo* do  Dados formatados como JSON a serem armazenados como o novo conteúdo de um subitem existente. Tecnicamente, um repositório pode armazenar qualquer conteúdo de qualquer esquema, mas quando usado para o painel de qualidade da chamada, deve ser um relatório ou uma consulta. *digite*  Sempre especifique "Application/JSON" para o painel de qualidade da chamada.
  
 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** -uma operação bem-sucedida retorna o código de status 204 (sem conteúdo). Se uma ID de item especificada não for encontrada, será retornado o código de status 404 (não encontrado).
  
> [!IMPORTANT]
> "Sem conteúdo" não é um status de erro. Significa que uma resposta não retornou nada no corpo (em contraste, 200 OK retorna o conteúdo do corpo). Isso indica que o item foi atualizado com êxito. 
  
 **Cabeçalhos de resposta** -nenhum.
  
 **Corpo da resposta** -nenhum.
  

