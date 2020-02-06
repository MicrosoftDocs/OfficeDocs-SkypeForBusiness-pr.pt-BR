---
title: Obter configurações de usuário
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: Saiba mais sobre a operação obter configurações de usuário, que faz parte do serviço de configurações do usuário. O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 5b5ad679387866ba6562e031b6d3a42cc68851a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816740"
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
  
```json
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
