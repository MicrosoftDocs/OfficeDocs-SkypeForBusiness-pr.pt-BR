---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: A tblActivePeers contém as conexões ponto a ponto atuais entre Servidores de Canal.
ms.openlocfilehash: d2d28c70cbb1bc35acdeca4739a667a5e991e52f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756301"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
A tblActivePeers contém as conexões ponto a ponto atuais entre Servidores de Canal.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, não nulo  <br/> |ID do servidor que postou a entrada.  <br/> |
|aplPeerID  <br/> |int, não nulo  <br/> |ID do ponto ao qual o servidor de postagem está conectado.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Chave primária.  <br/> |
|aplServerID  <br/> |Chave estrangeira com pesquisa na tabela tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Chave estrangeira com pesquisa na tabela tblServerIdentity.serverID.  <br/> |
   

