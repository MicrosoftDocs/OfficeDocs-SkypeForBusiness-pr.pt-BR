---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: TblServerIdentity contém os servidores de chat ativos no pool do Servidor de Chat Persistente.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831491"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
TblServerIdentity contém os servidores de chat ativos no pool do Servidor de Chat Persistente.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|serverID  <br/> |int, não nulo  <br/> |Identificação do Servidor. Corresponde à ID da instância do armazenamento de Gerenciamento Central.  <br/> |
|serverAddress  <br/> |nvarchar (256), não nulo  <br/> |Endereço do Servidor utilizando o endereço do Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |A última vez em que o Servidor de Canal atualizou esta linha para fornecer evidências de que está sendo executado.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|serverID  <br/> |Chave primária.  <br/> |
   

