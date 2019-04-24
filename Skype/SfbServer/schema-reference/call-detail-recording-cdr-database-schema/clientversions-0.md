---
title: Exibir ClientVersions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: O modo de exibição ClientVersions armazena informações sobre os diversos tipos de cliente e versões que tenham participado em sessões gravadas no banco de dados. Cada registro no modo de exibição representa uma versão de cliente. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213393"
---
# <a name="clientversions-view"></a>Exibir ClientVersions
 
O modo de exibição ClientVersions armazena informações sobre os diversos tipos de cliente e versões que tenham participado em sessões gravadas no banco de dados. Cada registro no modo de exibição representa uma versão de cliente. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
> [!NOTE]
> Podem haver vários registros para determinadas colunas. 
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Número exclusivo identificando este tipo de cliente e versão.  <br/> |
|**Versão** <br/> |nvarchar(256)  <br/> |Representa o agente de usuário.  <br/> |
|**ClientType** <br/> |int  <br/> |Tipo de cliente.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoria à qual o cliente pertencer a. Por exemplo, o cliente Conferencing_Attendant_1.0 pertence o CAA ClientCategory.  <br/> |
   

