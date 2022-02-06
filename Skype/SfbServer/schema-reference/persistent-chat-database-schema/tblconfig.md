---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: 'tblConfig contém algumas configurações sem suporte do Servidor de Chat Persistente, em uma linha.'
---

# <a name="tblconfig"></a>tblConfig
 
tblConfig contém algumas configurações sem suporte do Servidor de Chat Persistente, em uma linha.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), não nulo  <br/> |Contém "pool."  <br/> |
|configContent  <br/> |nvarchar (máx.)  <br/> |Conteúdo de configuração.  <br/> |
|configPoolID  <br/> |GUID, não nulo  <br/> |ID exclusivo da instância de banco de dados.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|configLabel  <br/> |Chave primária.  <br/> |
   

