---
title: Exibição ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: A exibição ClientVersions armazena informações sobre os vários tipos de cliente e versões que participaram de sessões registradas no banco de dados. Cada registro na exibição representa uma versão do cliente. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815409"
---
# <a name="clientversions-view"></a>Exibição ClientVersions
 
A exibição ClientVersions armazena informações sobre os vários tipos de cliente e versões que participaram de sessões registradas no banco de dados. Cada registro na exibição representa uma versão do cliente. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
> [!NOTE]
> Pode haver vários registros para determinadas colunas. 
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Número exclusivo que identifica esse tipo de cliente e a versão.  <br/> |
|**Versão** <br/> |nvarchar(256)  <br/> |Representa o agente do usuário.  <br/> |
|**ClientType** <br/> |int  <br/> |Tipo de cliente.  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Categoria à qual o cliente pertence. Por exemplo, o cliente Conferencing_Attendant_1 0 pertence à CAA ClientCategory.  <br/> |
   

