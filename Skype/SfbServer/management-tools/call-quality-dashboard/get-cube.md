---
title: Obter o cubo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumo: Saiba mais sobre a operação obter cubo, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 970187ce9f95700185ab09bd7aadf9045575b393
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274769"
---
# <a name="get-cube"></a>Obter o cubo
 
**Resumo:** Saiba mais sobre a operação obter cubo, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação obter cubo faz parte da API de dados para o painel de qualidade da chamada.
  
## <a name="get-cube"></a>Obter o cubo

Obter operação de cubo retorna a lista de dimensões e medidas disponíveis.
  

|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<do\>portal de/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** -nenhum.
  
 **Solicitar cabeçalhos** -sem cabeçalhos adicionais.
  
 **Corpo da solicitação** -nenhum.
  
 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Cabeçalhos de resposta** -sem cabeçalhos adicionais.
  
 **Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.
  
> [!NOTE]
> Este exemplo está mostrando apenas dois primeiros elementos de cada grupo de elementos de cubo. 
  
```
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

 *KPIs* -reservado. A seção KPIs de uma carga de solicitação permite que a operação de execução de consulta retorne valores para os KPIs definidos no cubo. Ainda não existem KPIs no cubo QoE.
  
 *Dimensions* -a lista de dimensões que podem ser usadas em seções de filtros e dimensões de uma carga de solicitação para executar a operação de consulta. Para usar uma dimensão em uma expressão de filtro, você precisa especificar um membro de dimensão, que pode ser obtido usando a operação obter membros da dimensão.
  
 *Medições* – a lista de medições que podem ser usadas na seção medidas de uma carga de solicitação para executar a operação de consulta.
  

