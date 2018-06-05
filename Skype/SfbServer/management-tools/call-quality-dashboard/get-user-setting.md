---
title: Obter a configuração do usuário
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumo: Saiba mais sobre a operação de obter a configuração do usuário, que faz parte do serviço de configurações de usuário. O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: e3646b1c6d5a7f959ee76565bb7b92ac84cbe8a4
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569247"
---
# <a name="get-user-setting"></a>Obter a configuração do usuário
 
**Resumo:** Saiba mais sobre a operação de obter a configuração do usuário, que faz parte do serviço de configurações de usuário. O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
A operação de obter a configuração do usuário é parte do serviço de configurações do usuário na API repositório para o painel de controle de qualidade de chamada.
  
## <a name="get-user-setting"></a>Obter a configuração do usuário

Obtenha a configuração do usuário retorna a configuração de um único usuário.
  

|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<portal\>/QoERepositoryService/repositório/usuário / {userId} /setting/ {chave}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 O **corpo da solicitação** - None.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId* - ID do usuário.
  
 *chave* - chave da configuração.
  
 *valor* - valor da configuração.
  

