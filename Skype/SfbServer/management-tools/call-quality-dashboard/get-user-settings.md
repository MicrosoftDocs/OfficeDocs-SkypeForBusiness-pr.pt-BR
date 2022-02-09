---
title: Obter Configurações de Usuário
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: saiba mais sobre a operação Obter Configurações usuário, que faz parte do Serviço de Configurações Usuário. O Serviço Configurações usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: bcde4b170de7b95007c62c5083132504e16ef6c9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401875"
---
# <a name="get-user-settings"></a>Obter Configurações de Usuário
 
**Resumo:** Saiba mais sobre a operação Obter Configurações usuário, que faz parte do Serviço de Configurações Usuário. O Serviço Configurações usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Get User Configurações faz parte do Serviço Configurações usuário na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-user-settings"></a>Obter Configurações de Usuário

Get User Configurações retorna uma lista de configurações para um usuário especificado.
  

|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |\<portal\>https:///QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI**
  
- *effective*  - Opcional. Esse parâmetro só se aplica quando o padrão de ID de usuário especial é usado. Em outros casos, ele será ignorado. `True` retorna configurações efetivas do usuário e `false` retorna apenas as configurações do usuário (padrão).
    
  **Headers de solicitação** - Sem headers adicionais.
  
  **Corpo da Solicitação** - Nenhum.
  
  **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
  **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
  **Headers de resposta** - Sem headers adicionais.
  
  **Corpo da Resposta** - Abaixo está uma carga de resposta de exemplo no JSON.
  
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
