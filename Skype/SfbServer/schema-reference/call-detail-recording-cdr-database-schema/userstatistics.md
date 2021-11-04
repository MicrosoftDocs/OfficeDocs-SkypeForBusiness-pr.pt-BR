---
title: Tabela UserStatistics
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso do sistema por um usuário individual. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 01f002e1cba20200334f8696f9fb2c20c98e82c1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756444"
---
# <a name="userstatistics-table"></a>Tabela UserStatistics
 
A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso do sistema por um usuário individual. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primário  <br/> |Número único que identifica este usuário.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Última vez que o usuário fez o login.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Última vez que o usuário organizou uma conferência.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que o usuário enfrentou uma falha de ligação.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que o usuário enfrentou uma falha de ligação como um organização da conferência.  <br/> |
   

