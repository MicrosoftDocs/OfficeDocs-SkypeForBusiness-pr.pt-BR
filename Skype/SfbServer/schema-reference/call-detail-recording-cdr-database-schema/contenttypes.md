---
title: Tabela ContentTypes no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e em sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296368"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tabela ContentTypes no Skype for Business Server 2015
 
A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e em sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ContentTypeid** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o tipo de conteúdo.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nome do tipo de conteúdo.  <br/> |
   

