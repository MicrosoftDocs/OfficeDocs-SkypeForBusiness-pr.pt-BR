---
title: Obter o Log de integração
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumo: Saiba mais sobre a operação obter log de integração, que faz parte da API de dados para o painel de qualidade de chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 9caa909e80a0bab5257af16fe77e9d154947a56e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816810"
---
# <a name="get-integration-log"></a>Obter o Log de integração
 
**Resumo:** Saiba mais sobre a operação obter log de integração, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação obter log de integração faz parte da API de dados para o painel de qualidade da chamada
  
## <a name="get-integration-log"></a>Obter o Log de integração

A operação obter log de integração retorna uma lista de entradas de log que descrevem as atividades em processamento de cubo QoE.
  
Esta operação é desativada por padrão por motivos de segurança. Quando desabilitado, ele retorna uma cadeia de caracteres vazia. Para habilitar essa operação, os administradores precisam configurar o Web. config do aplicativo Web host da API de dados.
  

|Forma|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<do\>portal de/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** -nenhum.
  
 **Solicitar cabeçalhos** -sem cabeçalhos adicionais.
  
 **Corpo da solicitação** -nenhum.
  
 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Cabeçalhos de resposta** -sem cabeçalhos adicionais.
  
 **Corpo da resposta** -abaixo está uma estrutura de exemplo das entradas do log.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


