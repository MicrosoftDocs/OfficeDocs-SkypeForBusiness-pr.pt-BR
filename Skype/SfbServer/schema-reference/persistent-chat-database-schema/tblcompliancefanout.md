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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contém todos os servidores que processaram um evento de conformidade.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814649"
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
   

