---
title: Obter o Cubo
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumo: saiba mais sobre a operação Obter Cubo, que faz parte da API de Dados do Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832621"
---
# <a name="get-cube"></a>Obter o Cubo
 
**Resumo:** Saiba mais sobre a operação Obter Cubo, que faz parte da API de Dados do Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Cubo faz parte da API de Dados do Painel de Qualidade da Chamada.
  
## <a name="get-cube"></a>Obter o Cubo

A operação Obter Cubo retorna a lista de dimensões e medidas disponíveis.
  

|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.
  
> [!NOTE]
> Este exemplo mostra apenas os dois primeiros elementos de cada grupo de elementos Cube. 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 *KPIs*  - Reservado. A seção KPIs de uma carga de solicitação permite que a operação Executar Consulta retorne valores para os KPIs definidos no cubo. Ainda não há KPIs no Cubo QoE.
  
 *Dimensões*  - A lista de dimensões que podem ser usadas nas seções Filtros e Dimensões de uma carga de solicitação para a operação Executar Consulta. Para usar uma dimensão em uma expressão de filtro, você precisa especificar um membro de dimensão, que pode ser obtido usando a operação Obter Membros da Dimensão.
  
 *Medidas*  - A lista de medidas que podem ser usadas na seção Medidas de uma carga de solicitação para a operação Executar Consulta.
  

