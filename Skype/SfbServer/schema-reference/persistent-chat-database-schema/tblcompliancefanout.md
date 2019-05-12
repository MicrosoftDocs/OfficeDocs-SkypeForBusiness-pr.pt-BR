---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: a tabela tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929916"
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
   

