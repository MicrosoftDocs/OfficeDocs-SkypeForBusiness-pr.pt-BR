---
title: Tabela ContentTypes no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: ca6497cad38c6e4e59f4da725ab03b8d027f2d93
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827394"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tabela ContentTypes no Skype for Business Server 2015
 
A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o tipo de conteúdo.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nome do tipo de conteúdo.  <br/> |
   

