---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874045"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID do evento.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identidade do servidor (correspondente à tabela Tblserveridentity).  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|fanoutEventID  <br/> |Chave estrangeira com pesquisa na tabela Tblcompliancedata.  <br/> |
   

