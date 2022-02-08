---
title: Obter o Log de integração
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumo: saiba mais sobre a operação Obter Log de Integração, que faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: b82ecffd5b39df6e149787ec7b3265f3e8176376
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388069"
---
# <a name="get-integration-log"></a>Obter o Log de integração
 
**Resumo:** Saiba mais sobre a operação Obter Log de Integração, que faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Obter Log de Integração faz parte da API de Dados para Painel de Qualidade de Chamada
  
## <a name="get-integration-log"></a>Obter o Log de integração

Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.
  
Essa operação está desabilitada por padrão por motivos de segurança. Quando desabilitado, ele retorna uma cadeia de caracteres vazia. Para habilitar essa operação, os administradores precisam configurar o web.config para o aplicativo Web host da API de Dados.
  

|Método|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |\<portal\>https:///QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Headers de solicitação** - Sem headers adicionais.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Headers de resposta** - Sem headers adicionais.
  
 **Corpo da Resposta** - Abaixo está uma estrutura de exemplo de entradas de log.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


