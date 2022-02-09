---
title: Tabela ContentTypes no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
ms.openlocfilehash: f545355a00c37bf5df5f3b849aa29b6bee572c4f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417454"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tabela ContentTypes no Skype for Business Server 2015
 
A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o tipo de conteúdo.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nome do tipo de conteúdo.  <br/> |
   

