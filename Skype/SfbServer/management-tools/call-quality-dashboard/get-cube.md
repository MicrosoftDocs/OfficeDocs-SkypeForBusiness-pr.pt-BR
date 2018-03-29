---
title: Obtenha o cubo
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumo: Saiba mais sobre a operação obter cubo, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: e39a88e249dc807b201b08d966285d93ae7f82a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="get-cube"></a>Obtenha o cubo
 
**Resumo:** Saiba mais sobre a operação obter cubo, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
A operação obter cubo é parte da API de dados para o painel de qualidade de chamada.
  
## <a name="get-cube"></a>Obtenha o cubo

Operação de cubo Get retorna a lista de medidas e dimensões disponíveis.
  

|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<portal\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 O **corpo da solicitação** - None.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.
  
> [!NOTE]
> Esta amostra apenas está mostrando as duas primeiras elementos de cada grupos de elementos de cubo. 
  
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

 *KPIs* - reservado. A seção de KPIs a carga de solicitação permite que a operação de executar consulta retornar valores para os KPIs definidos no cubo. Nenhum KPIs ainda existem no cubo do QoE.
  
 *Dimensões* - lista de dimensões que podem ser usadas nas seções de filtros e dimensões de uma carga de solicitação para a operação de executar consulta. Para usar uma dimensão em uma expressão de filtro, você precisará especificar um membro de dimensão, que pode ser obtido com a operação obter membros da dimensão.
  
 *Medições* - lista de medidas que podem ser usadas na seção medidas de uma carga de solicitação para a operação de executar consulta.
  

