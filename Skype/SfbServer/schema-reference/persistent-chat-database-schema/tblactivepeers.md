---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: o tblActivePeers contém as conexões ponto-a-ponto atuais entre os serviços de chat.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295542"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
o tblActivePeers contém as conexões ponto-a-ponto atuais entre os serviços de chat.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, não nulo  <br/> |ID do servidor que postou a entrada.  <br/> |
|aplPeerID  <br/> |int, não nulo  <br/> |ID do par ao qual o servidor de postagem está conectado.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Chave primária.  <br/> |
|aplServerID  <br/> |Chave estrangeira com Lookup na tabela tblServerIdentity. serverID.  <br/> |
|aplPeerID  <br/> |Chave estrangeira com Lookup na tabela tblServerIdentity. serverID.  <br/> |
   

