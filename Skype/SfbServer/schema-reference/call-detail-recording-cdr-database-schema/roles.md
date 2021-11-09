---
title: Tabela Funções
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
ms.openlocfilehash: 67faf16a478a8ca1f4c2f3bc21bd5d4a6f28909f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842643"
---
# <a name="roles-table"></a>Tabela Funções
 
A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**Função** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconhecido <br/>  1 - Apresentador <br/>  2 - Participante <br/> |
   

