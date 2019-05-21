---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295500"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID do evento.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identidade do servidor (correspondente à tabela tblServerIdentity. ServerId).  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|fanoutEventID  <br/> |Chave estrangeira com Lookup na tabela tblComplianceData. cmplEventID.  <br/> |
   

