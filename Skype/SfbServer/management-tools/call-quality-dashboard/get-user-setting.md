---
title: Obter as Configuração de Usuário
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumo: saiba mais sobre a operação Obter Configuração do Usuário, que faz parte do Serviço de Configurações do Usuário. O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832481"
---
# <a name="get-user-setting"></a>Obter as Configuração de Usuário
 
**Resumo:** Saiba mais sobre a operação Obter Configuração do Usuário, que faz parte do Serviço de Configurações do Usuário. O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Configuração do Usuário faz parte do Serviço de Configurações do Usuário na API de Repositório para Painel de Qualidade da Chamada.
  
## <a name="get-user-setting"></a>Obter as Configuração de Usuário

Obter Configuração do Usuário retorna uma configuração de usuário único.
  

|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  - ID do usuário.
  
 *chave*  - Chave da configuração.
  
 *valor*  - Valor da configuração.
  

