---
title: Tabela Funções
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
ms.localizationpriority: medium
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
ms.openlocfilehash: 037197d12a83c5b79de22c0b7faef435d365da41
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635875"
---
# <a name="roles-table"></a>Tabela Funções
 
A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**Função** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconhecido <br/>  1 - Apresentador <br/>  2 - Participante <br/> |
   

