---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: a tblActivePeers contém as conexões ponto a ponto atuais entre os serviços de bate-papo.
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212674"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
a tblActivePeers contém as conexões ponto a ponto atuais entre os serviços de bate-papo.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, não nulo  <br/> |ID do servidor que postou a entrada.  <br/> |
|aplPeerID  <br/> |int, não nulo  <br/> |ID do ponto ao qual o servidor de postagem está conectado.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Chave primária.  <br/> |
|aplServerID  <br/> |Chave estrangeira com pesquisa na tabela Tblserveridentity.  <br/> |
|aplPeerID  <br/> |Chave estrangeira com pesquisa na tabela Tblserveridentity.  <br/> |
   

