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
description: 'Resumo: saiba mais sobre a operação Obter Membros da Dimensão. A operação Obter Membros da Dimensão faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 3a0c01b310ed60c4b0808d669b553391277f3877bff4c4800bea1b5b765bf5b7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278709"
---
# <a name="get-dimension-members"></a>Obter os Membros da Dimensão
 
**Resumo:** Saiba mais sobre a operação Obter Membros da Dimensão. A operação Obter Membros da Dimensão faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Obter Membros da Dimensão faz parte da API de Dados para Painel de Qualidade de Chamada.
  
## <a name="get-dimension-members"></a>Obter os Membros da Dimensão

Obter a operação Membros da Dimensão retorna a lista de membros de uma dimensão específica. Ele também dá a capacidade de filtrar a lista de membros e obter um subconjunto, para reduzir o custo de transferência de fio.
  

|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|POSTAR  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Headers de solicitação** - Sem headers adicionais.
  
 **Corpo da** Solicitação - Isso contém o nome da dimensão para a que desejamos os membros. Além disso, o número máximo de membros retornados, ao lado de você, pode especificar algumas filtragem para limitar os membros retornados.
  
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
  
 **Headers de resposta** - Sem headers adicionais.
  
 **Corpo da** Resposta - Abaixo está uma carga de resposta de exemplo no JSON em resposta a uma solicitação para "[StartDate]. [Month]" dimension.
  
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
