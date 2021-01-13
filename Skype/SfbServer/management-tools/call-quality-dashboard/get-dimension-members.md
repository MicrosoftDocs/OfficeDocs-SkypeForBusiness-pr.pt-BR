---
title: Obter os Membros da Dimensão
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumo: saiba mais sobre a operação Obter Membros da Dimensão. A operação Obter Membros da Dimensão faz parte da API de Dados do Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832631"
---
# <a name="get-dimension-members"></a>Obter os Membros da Dimensão
 
**Resumo:** Saiba mais sobre a operação Obter Membros da Dimensão. A operação Obter Membros da Dimensão faz parte da API de Dados do Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Membros da Dimensão faz parte da API de Dados do Painel de Qualidade da Chamada.
  
## <a name="get-dimension-members"></a>Obter os Membros da Dimensão

A operação Obter Membros da Dimensão retorna a lista de membros de uma dimensão específica. Ele também dá a capacidade de filtrar a lista de membros e obter um subconjunto, para reduzir o custo de transferência eletrônica.
  

|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|POSTAR  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da** Solicitação - Contém o nome da dimensão para a que queremos os membros. Além disso, o número máximo de membros retornados, ao lado de você pode especificar algumas filtragem para limitar os membros retornados.
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON em resposta a uma solicitação de "[StartDate]. [Month]".
  
> [!NOTE]
> A lista está mostrando apenas uma pequena parte da lista. 
  
```json
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
