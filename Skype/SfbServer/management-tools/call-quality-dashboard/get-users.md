---
title: Obter os Usuários
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumo: saiba mais sobre a operação Obter Usuários, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: ecf549dccf73ec6adae7360efbe516ae3710bf17
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739117"
---
# <a name="get-users"></a>Obter os Usuários
 
**Resumo:** Saiba mais sobre a operação Obter Usuários, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Get Users faz parte do Serviço de Usuário na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-users"></a>Obter os Usuários

Obter Usuários retorna uma lista de usuários no repositório.
  
|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repositório/usuário  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Headers de solicitação** - Sem headers adicionais.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Headers de resposta** - Sem headers adicionais.
  
 **Corpo da Resposta** - Abaixo está uma carga de resposta de exemplo no JSON.
  
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


