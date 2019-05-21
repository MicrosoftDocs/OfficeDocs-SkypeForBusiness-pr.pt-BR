---
title: Tabela ClientVersions no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: A tabela ClientVersions é uma tabela de suporte que armazena uma lista de vários tipos de cliente e versões que participaram de sessões registradas no banco de dados. Cada registro na tabela representa uma versão do cliente.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296508"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabela ClientVersions no Skype for Business Server 2015
 
A tabela ClientVersions é uma tabela de suporte que armazena uma lista de vários tipos de cliente e versões que participaram de sessões registradas no banco de dados. Cada registro na tabela representa uma versão do cliente.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primária  <br/> |Número exclusivo que identifica esse tipo de cliente e a versão.  <br/> |
|**Versão** <br/> |**nvarchar(256)** <br/> ||Nome da versão.  <br/> |
|**ClientType** <br/> |int  <br/> ||Especifica o tipo de cliente usado na sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais informações. <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
   

