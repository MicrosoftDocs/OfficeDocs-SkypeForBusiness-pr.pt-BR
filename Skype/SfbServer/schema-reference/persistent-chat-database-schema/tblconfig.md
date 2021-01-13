---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contém algumas configurações não compatíveis com o Servidor de Chat Persistente, em uma linha.
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809731"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contém algumas configurações não compatíveis com o Servidor de Chat Persistente, em uma linha.
  
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
   

