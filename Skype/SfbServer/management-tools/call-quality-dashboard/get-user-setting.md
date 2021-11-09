---
title: Obter as Configuração de Usuário
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
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumo: saiba mais sobre a operação Obter Configuração do Usuário, que faz parte do Serviço de Configurações Usuário. O Serviço Configurações usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 8091172cd28bc737ff9a2899672ca5643c12de7c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851895"
---
# <a name="get-user-setting"></a>Obter as Configuração de Usuário
 
**Resumo:** Saiba mais sobre a operação Obter Configuração do Usuário, que faz parte do Serviço de Configurações Usuário. O Serviço Configurações usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Obter Configuração do Usuário faz parte do Serviço Configurações usuário na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-user-setting"></a>Obter as Configuração de Usuário

Obter Configuração do Usuário retorna uma única configuração de usuário.
  

|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Headers de solicitação** - Sem headers adicionais.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Headers de resposta** - Sem headers adicionais.
  
 **Corpo da Resposta** - Abaixo está uma carga de resposta de exemplo no JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  - ID do usuário.
  
 *key*  - Chave da configuração.
  
 *value*  - Valor da configuração.
  

