---
title: Atualizar Item
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumo: saiba mais sobre a operação Atualizar Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 4140909786c3144dbc043568a5ca6aa2995a0720
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845394"
---
# <a name="update-item"></a>Atualizar Item
 
**Resumo:** Saiba mais sobre a operação Atualizar Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Atualizar Item faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="update-item"></a>Atualizar Item

Atualizar Item atualiza um item específico no repositório.
  

|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repositório/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Solicitação de Headers** -Content-Type: application/json.
  
 **Corpo da Solicitação** - JSON.
  
Carga de solicitação de exemplo:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content*  Dados formatados JSON a serem armazenados como o novo conteúdo de um sub-Item existente. Tecnicamente, um repositório pode armazenar qualquer conteúdo de qualquer esquema, mas quando usado para o Painel de Qualidade de Chamada, ele deve ser um relatório ou uma consulta. *type*  Sempre especifique "application/json" para Painel de Qualidade de Chamada.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 204 (Sem Conteúdo). Se uma ID de item especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).
  
> [!IMPORTANT]
> "Sem Conteúdo" não é um status de erro. Isso significa que uma resposta não retornou nada no corpo (por outro lado, 200 OK retorna conteúdo em Body). Indica que o Item foi atualizado com êxito. 
  
 **Headers de resposta** - Nenhum.
  
 **Corpo da resposta** - Nenhum.
  

