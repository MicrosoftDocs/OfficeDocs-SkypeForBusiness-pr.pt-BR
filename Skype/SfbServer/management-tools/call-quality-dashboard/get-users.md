---
title: Obter os Usuários
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumo: saiba mais sobre a operação Obter Usuários, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832421"
---
# <a name="get-users"></a>Obter os Usuários
 
**Resumo:** Saiba mais sobre a operação Obter Usuários, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Usuários faz parte do Serviço de Usuário na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-users"></a>Obter os Usuários

Obter usuários retorna uma lista de usuários no repositório.
  
|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.
  
> [!NOTE]
> Uma matriz de objetos User é retornada. Para obter detalhes sobre o objeto User, consulte Get User. 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


