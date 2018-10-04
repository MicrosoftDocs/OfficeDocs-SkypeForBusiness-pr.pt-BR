---
title: Obter configurações de usuário
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: Saiba mais sobre a operação obter configurações de usuário, que é parte do serviço de configurações de usuário. O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 41bc45f63366337000ad8c263ff8e6dbcb36a3b3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375376"
---
# <a name="get-user-settings"></a>Obter configurações de usuário
 
**Resumo:** Saiba mais sobre a operação obter configurações de usuário, que é parte do serviço de configurações de usuário. O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
A operação obter configurações de usuário é parte do serviço de configurações do usuário na API repositório para o painel de controle de qualidade de chamada.
  
## <a name="get-user-settings"></a>Obter configurações de usuário

Configurações de usuário Get retorna uma lista de configurações para um usuário especificado.
  

|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<portal\>/QoERepositoryService/repositório/usuário / {userId} / configuração  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI**
  
- *efetivo* - opcional. Esse parâmetro se aplica apenas quando o padrão de ID de usuário especial é usado. Em outros casos, ele será ignorado. `True`Retorna as configurações de usuário efetivo e `false` retorna apenas as configurações de usuário (padrão).
    
  **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
  O **corpo da solicitação** - None.
  
  **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
  **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).
  
  **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
  **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.
  
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