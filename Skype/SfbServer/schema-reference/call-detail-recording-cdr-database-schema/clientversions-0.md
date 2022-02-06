---
title: Exibição ClientVersions
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: A exibição ClientVersions armazena informações sobre os vários tipos de cliente e versões que participaram de sessões gravadas no banco de dados. Cada registro na exibição representa uma versão do cliente. Essa exibição foi introduzida no Microsoft Lync Server 2013.
---

# <a name="clientversions-view"></a>Exibição ClientVersions
 
A exibição ClientVersions armazena informações sobre os vários tipos de cliente e versões que participaram de sessões gravadas no banco de dados. Cada registro na exibição representa uma versão do cliente. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> Pode haver vários registros para determinadas colunas. 
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Número exclusivo que identifica esse tipo de cliente e a versão.  <br/> |
|**Versão** <br/> |nvarchar(256)  <br/> |Representa o agente do usuário.  <br/> |
|**ClientType** <br/> |int  <br/> |Tipo de cliente.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoria na qual o cliente pertence. Por exemplo, o cliente Conferencing_Attendant_1.pertence ao CAA ClientCategory.  <br/> |
   

