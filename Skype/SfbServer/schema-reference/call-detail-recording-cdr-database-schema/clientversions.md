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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: A tabela ClientVersions é uma tabela de suporte que armazena uma lista de vários tipos de cliente e versões que participaram de sessões registradas no banco de dados. Cada registro na tabela representa uma versão do cliente.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815399"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabela ClientVersions no Skype for Business Server 2015
 
A tabela ClientVersions é uma tabela de suporte que armazena uma lista de vários tipos de cliente e versões que participaram de sessões registradas no banco de dados. Cada registro na tabela representa uma versão do cliente.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primária  <br/> |Número exclusivo que identifica esse tipo de cliente e a versão.  <br/> |
|**Versão** <br/> |**nvarchar(256)** <br/> ||Nome da versão.  <br/> |
|**ClientType** <br/> |int  <br/> ||Especifica o tipo de cliente usado na sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais informações. <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
   

