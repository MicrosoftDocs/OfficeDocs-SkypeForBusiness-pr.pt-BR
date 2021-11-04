---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: A tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: 6c0ae5a9b00945494c125511e1206f4177432703
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765069"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
A tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID do evento.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identidade do servidor (correspondente à tabela tblServerIdentity.serverID).  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|fanoutEventID  <br/> |Chave estrangeira com pesquisa na tabela tblComplianceData.cmplEventID.  <br/> |
   

