---
title: Obtenha os Membros da Dimensão
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumo: Saiba mais sobre a operação obter membros da dimensão. A operação obter membros da dimensão faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: ba80e14c011d6cecb9b70f8a8faf32764b5b433d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816820"
---
# <a name="get-dimension-members"></a>Obtenha os Membros da Dimensão
 
**Resumo:** Saiba mais sobre a operação obter membros da dimensão. A operação obter membros da dimensão faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação obter membros da dimensão faz parte da API de dados para o painel de qualidade da chamada.
  
## <a name="get-dimension-members"></a>Obtenha os Membros da Dimensão

A operação obter membros da dimensão retorna a lista de membros de uma dimensão específica. Ele também permite filtrar a lista de membros e obter um subconjunto para reduzir o custo de transferência de fio.
  

|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Postar  <br/> |https://\<do\>portal de/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** -nenhum.
  
 **Solicitar cabeçalhos** -sem cabeçalhos adicionais.
  
 **Corpo da solicitação** -contém o nome da dimensão para a qual queremos os membros. Também número máximo de membros retornados, ao lado de você pode especificar alguns filtros para limitar os membros retornados.
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Cabeçalhos de resposta** -sem cabeçalhos adicionais.
  
 **Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON em resposta a uma solicitação de "[StartDate]. [Mês] "dimensão.
  
> [!NOTE]
> A lista está mostrando apenas uma pequena parte da lista. 
  
```
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
