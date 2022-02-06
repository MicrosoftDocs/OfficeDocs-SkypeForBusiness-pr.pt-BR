---
title: tblActivePeers
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
   

