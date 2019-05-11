---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: o tblServerIdentity inclui os servidores de bate-papo ativas no pool Persistent Chat Server.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924805"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
o tblServerIdentity inclui os servidores de bate-papo ativas no pool Persistent Chat Server.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|serverID  <br/> |int, não nulo  <br/> |ID do servidor. Corresponde à ID da instância do repositório de gerenciamento Central.  <br/> |
|serverAddress  <br/> |nvarchar (256), não nulo  <br/> |Endereço do servidor usando o endereço do Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |A última vez em que o servidor de canal atualizou esta linha para fornecer evidências de que ele está sendo executado.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|serverID  <br/> |Chave primária.  <br/> |
   

