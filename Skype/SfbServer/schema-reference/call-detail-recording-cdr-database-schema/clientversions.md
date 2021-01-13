---
title: Tabela ClientVersions no Skype for Business Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e as versões que participaram de sessões gravadas no banco de dados. Cada registro da tabela representa uma versão de cliente.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813311"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabela ClientVersions no Skype for Business Server 2015
 
ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e as versões que participaram de sessões gravadas no banco de dados. Cada registro da tabela representa uma versão de cliente.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primário  <br/> |Número exclusivo que identifica esse tipo de cliente e a versão.  <br/> |
|**Versão** <br/> |**nvarchar(256)** <br/> ||Nome da versão.  <br/> |
|**ClientType** <br/> |int  <br/> ||Especifique o tipo de cliente utilizado na sessão. Consulte a [tabela UserAgentDef para](useragentdef.md) obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

