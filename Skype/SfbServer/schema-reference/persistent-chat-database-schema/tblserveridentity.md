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
description: tblServerIdentity contém os servidores de chat ativos no pool do Servidor de Chat Persistente.
ms.openlocfilehash: 092331f275ef76372ad1bd2d2462acb9eb7848eea263d59c2276d7a4b6a83779
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303654"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contém os servidores de chat ativos no pool do Servidor de Chat Persistente.
  
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
   

