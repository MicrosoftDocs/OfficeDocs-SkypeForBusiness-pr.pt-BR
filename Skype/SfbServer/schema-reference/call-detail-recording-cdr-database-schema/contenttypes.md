---
title: Tabela ContentTypes no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
ms.openlocfilehash: 6f15fe8bc5f4da7e12fa3b36de6b613fc1783b3d21e5903e2840f3cd22f5e139
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336402"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tabela ContentTypes no Skype for Business Server 2015
 
A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o tipo de conteúdo.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nome do tipo de conteúdo.  <br/> |
   

