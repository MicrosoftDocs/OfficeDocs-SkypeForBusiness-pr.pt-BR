---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contém os servidores de chat ativos no pool do servidor de chat persistente.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295185"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contém os servidores de chat ativos no pool do servidor de chat persistente.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|serverID  <br/> |int, não nulo  <br/> |ID do servidor. Corresponde à ID da instância do repositório de gerenciamento central.  <br/> |
|a  <br/> |nvarchar (256), NOT NULL  <br/> |Endereço do servidor usando o endereço do Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |A última vez em que o servidor de canal atualizou essa linha para dar evidências de que esteja em execução.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|serverID  <br/> |Chave primária.  <br/> |
   

