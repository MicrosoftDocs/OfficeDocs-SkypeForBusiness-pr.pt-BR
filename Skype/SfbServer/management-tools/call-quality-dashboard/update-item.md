---
title: Atualizar Item
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumo: saiba mais sobre a operação Atualizar Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803081"
---
# <a name="update-item"></a>Atualizar Item
 
**Resumo:** Saiba mais sobre a operação Atualizar Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Atualizar Item faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="update-item"></a>Atualizar Item

Atualizar Item atualiza um item específico no repositório.
  

|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Request Headers** -Content-Type: application/json.
  
 **Corpo da Solicitação** - JSON.
  
Carga de solicitação de exemplo:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content*  Dados formatados JSON a serem armazenados como o novo conteúdo de um sub-item existente. Tecnicamente, um repositório pode armazenar qualquer conteúdo de qualquer esquema, mas quando usado para o Painel de Qualidade da Chamada, ele deve ser um relatório ou uma consulta. *type*  Sempre especifique "application/json" para o Painel de Qualidade da Chamada.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 204 (Sem Conteúdo). Se uma ID de item especificada não for encontrada, retornará o código de status 404 (Não Encontrado).
  
> [!IMPORTANT]
> "Nenhum Conteúdo" não é um status de erro. Isso significa que uma resposta não retornou nada no corpo (por outro lado, 200 OK retorna conteúdo no corpo). Indica que o Item foi atualizado com êxito. 
  
 **Response Headers** - None.
  
 **Corpo de Resposta** - Nenhum.
  

