---
title: tblServerIdentity
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: o tblServerIdentity inclui os servidores de bate-papo ativas no pool Persistent Chat Server.
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
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
   

