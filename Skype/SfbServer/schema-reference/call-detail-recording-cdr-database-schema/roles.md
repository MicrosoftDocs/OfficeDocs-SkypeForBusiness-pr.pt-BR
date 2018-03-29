---
title: Tabela Roles
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a>Tabela Roles
 
A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primária  <br/> ||
|**Função** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - desconhecido <br/>  1 - apresentador <br/>  2 - participante <br/> |
   

