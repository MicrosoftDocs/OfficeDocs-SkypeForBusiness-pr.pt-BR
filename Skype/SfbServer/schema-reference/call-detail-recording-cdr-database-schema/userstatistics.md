---
title: Tabela userstatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela userstatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295689"
---
# <a name="userstatistics-table"></a>Tabela userstatistics
 
A tabela userstatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse usuário.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Última vez em que o usuário se conectou.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Última vez em que o usuário organizou uma conferência.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que o usuário experimentou uma falha na chamada.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Última vez que o usuário experimentou uma falha na chamada como um organizador de conferências.  <br/> |
   

