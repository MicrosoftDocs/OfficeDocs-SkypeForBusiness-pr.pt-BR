---
title: Obter os Últimos Dados de Integração
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Resumo: saiba mais sobre a operação Obter Últimos Dados de Integração, que faz parte da API de Dados para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832511"
---
# <a name="get-last-integration-data"></a>Obter os Últimos Dados de Integração
 
**Resumo:** Saiba mais sobre a operação Obter Últimos Dados de Integração, que faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Últimos Dados de Integração faz parte da API de Dados do Painel de Qualidade da Chamada.
  
## <a name="get-last-integration-data"></a>Obter os Últimos Dados de Integração

A operação Obter Dados da Última Integração retorna a lista dos últimos 5 êxitos/falhas de arquivamento e processamento de cubos.
  
Esse recurso está desabilitado por padrão e precisa ser habilitado configurando a API de Dados.
  

|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog/Status  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de Resposta** - Abaixo está um exemplo de status do log.
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
