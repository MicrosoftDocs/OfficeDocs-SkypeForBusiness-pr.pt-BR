---
title: Tabela ClientVersions no Skype for Business Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e as versões que participaram de sessões gravadas no banco de dados. Cada registro da tabela representa uma versão de cliente.
ms.openlocfilehash: 230310d414c9dc34a92317e6369e18643b86f8d5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842693"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabela ClientVersions no Skype for Business Server 2015
 
ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e as versões que participaram de sessões gravadas no banco de dados. Cada registro da tabela representa uma versão de cliente.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primário  <br/> |Número exclusivo que identifica esse tipo de cliente e a versão.  <br/> |
|**Versão** <br/> |**nvarchar(256)** <br/> ||Nome da versão.  <br/> |
|**ClientType** <br/> |int  <br/> ||Especifique o tipo de cliente utilizado na sessão. Consulte a [tabela UserAgentDef para](useragentdef.md) obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

