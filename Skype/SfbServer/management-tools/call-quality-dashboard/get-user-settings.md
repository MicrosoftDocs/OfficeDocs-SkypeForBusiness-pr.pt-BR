---
title: Obter configurações de usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: Saiba mais sobre a operação obter configurações de usuário, que faz parte do serviço de configurações do usuário. O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 8d1bb1da9e9a186cbc10f0c8ba36275348bb7267
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274615"
---
# <a name="get-user-settings"></a>Obter configurações de usuário
 
**Resumo:** Saiba mais sobre a operação obter configurações de usuário, que faz parte do serviço de configurações do usuário. O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação obter configurações do usuário faz parte do serviço configurações do usuário na API do repositório para o painel de qualidade da chamada.
  
## <a name="get-user-settings"></a>Obter configurações de usuário

Obter configurações do usuário retorna uma lista de configurações para um usuário especificado.
  

|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<do\>portal de/QoERepositoryService/Repository/User/{userid}/Setting  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI**
  
- *efetivo* -opcional. Esse parâmetro só se aplica quando o padrão de ID de usuário especial é usado. Em outros casos, ele será ignorado. `True`Retorna as configurações de usuário `false` efetivas e retorna apenas as configurações do usuário (padrão).
    
  **Solicitar cabeçalhos** -sem cabeçalhos adicionais.
  
  **Corpo da solicitação** -nenhum.
  
  **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
  **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).
  
  **Cabeçalhos de resposta** -sem cabeçalhos adicionais.
  
  **Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.
  
```
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
