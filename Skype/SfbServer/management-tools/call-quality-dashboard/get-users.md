---
title: Colocar os usuários
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumo: Saiba mais sobre a operação obter usuários, que é parte do serviço do usuário. O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 4d4de424776514479ed2204eeb0a5315a7323662
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569695"
---
# <a name="get-users"></a>Colocar os usuários
 
**Resumo:** Saiba mais sobre a operação obter usuários, que é parte do serviço do usuário. O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
A operação obter usuários é parte do serviço do usuário na API repositório para o painel de controle de qualidade de chamada.
  
## <a name="get-users"></a>Colocar os usuários

Obtenha uma lista de usuários de retorna os usuários no repositório.
  
|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<portal\>/QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 O **corpo da solicitação** - None.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.
  
> [!NOTE]
> Uma matriz de objetos de usuário é retornada. Para obter detalhes sobre o objeto de usuário, consulte obter um usuário. 
  
```
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


