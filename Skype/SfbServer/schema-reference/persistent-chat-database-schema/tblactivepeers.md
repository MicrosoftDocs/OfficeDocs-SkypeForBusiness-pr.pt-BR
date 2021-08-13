---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: A tblActivePeers contém as conexões ponto a ponto atuais entre Servidores de Canal.
ms.openlocfilehash: 7ba8bb5730dc1c08a3d0f8aa13d1173192b7cc65134d90c75061ede0db5aa98d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336391"
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
   

