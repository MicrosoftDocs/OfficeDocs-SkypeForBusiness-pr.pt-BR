---
title: Obtenha os membros de dimensão
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumo: Saiba mais sobre a operação obter membros da dimensão. A operação obter membros da dimensão é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 4c53e809d13b1ceb386c6727805402be9dfaf7f8
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035663"
---
# <a name="get-dimension-members"></a>Obtenha os membros de dimensão
 
**Resumo:** Saiba mais sobre a operação obter membros da dimensão. A operação obter membros da dimensão é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
A operação obter membros da dimensão é parte da API de dados para o painel de qualidade de chamada.
  
## <a name="get-dimension-members"></a>Obtenha os membros de dimensão

Operação de membros da dimensão Get retorna a lista de membros de uma dimensão específica. Ele também dá a capacidade de filtrar a lista de membro e obtenha um subconjunto, para reduzir o custo de transferência de transmissão.
  

|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Postar  <br/> |https://\<portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 **Corpo da solicitação** - contém o nome da dimensão que queremos que os membros de. Também número máximo de membros retornados, ao lado do você pode especificar algumas filtragem para limitar os membros retornados.
  
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

 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON em resposta a uma solicitação para "[StartDate]. [Mês] "dimensão.
  
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