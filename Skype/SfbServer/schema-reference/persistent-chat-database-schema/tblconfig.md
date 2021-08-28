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
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contém algumas configurações sem suporte do Servidor de Chat Persistente, em uma linha.
ms.openlocfilehash: 8cf1fc53087d3fc786ac47e848a21dbd2a8f5549
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595303"
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
   

