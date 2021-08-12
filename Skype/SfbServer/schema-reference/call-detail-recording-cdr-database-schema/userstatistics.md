---
title: Tabela UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso do sistema por um usuário individual. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: d0d3fde20f7c8c94629f75ff00f310111cac16d386fc0b0373ee07b5c2a35fb5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302205"
---
# <a name="userstatistics-table"></a>Tabela UserStatistics
 
A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso do sistema por um usuário individual. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Primário  <br/> |Número único que identifica este usuário.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Última vez que o usuário fez o login.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Última vez que o usuário organizou uma conferência.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que o usuário enfrentou uma falha de ligação.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que o usuário enfrentou uma falha de ligação como um organização da conferência.  <br/> |
   

