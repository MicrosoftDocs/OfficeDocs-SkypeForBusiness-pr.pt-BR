---
title: Obter o Log de integração
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumo: Saiba mais sobre a operação obter o Log de integração, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 450122266caa21359b424e3abb76a13476f386c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926097"
---
# <a name="get-integration-log"></a>Obter o Log de integração
 
**Resumo:** Saiba mais sobre a operação obter o Log de integração, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
A operação obter integração Log é parte da API de dados para o painel de qualidade de chamada
  
## <a name="get-integration-log"></a>Obter o Log de integração

Obtenha a operação retorna uma lista de entradas de log descrevendo as atividades no cubo de QoE de processamento de Log de integração.
  
Essa operação está desabilitada por padrão, por motivos de segurança. Quando desabilitada, ela retornará uma sequência vazia. Para habilitar essa operação, os administradores precisam configurar o Web. config para o aplicativo de web de host do API de dados.
  

|Método|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 O **corpo da solicitação** - None.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - a seguir é uma estrutura de amostra de entradas de log.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


