---
title: Obter Configurações de Usuário
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: saiba mais sobre a operação Obter Configurações do Usuário, que faz parte do Serviço de Configurações do Usuário. O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832471"
---
# <a name="get-user-settings"></a>Obter Configurações de Usuário
 
**Resumo:** Saiba mais sobre a operação Obter Configurações do Usuário, que faz parte do Serviço de Configurações do Usuário. O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Configurações do Usuário faz parte do Serviço de Configurações do Usuário na API de Repositório do Painel de Qualidade da Chamada.
  
## <a name="get-user-settings"></a>Obter Configurações de Usuário

Obter configurações do usuário retorna uma lista de configurações para um usuário especificado.
  

|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI**
  
- *efetivo*  - Opcional. Esse parâmetro só se aplica quando o padrão de ID de usuário especial é usado. Em outros casos, ele será ignorado. `True` retorna configurações efetivas do usuário `false` e retorna apenas as configurações do usuário (padrão).
    
  **Solicitação de headers** - nenhum outro.
  
  **Corpo da Solicitação** - Nenhum.
  
  **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
  **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
  **Response Headers** - Sem outros headers.
  
  **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.
  
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
