---
title: tblADCookie
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: a tabela tblADCookie inclui os cookies atuais de sincronização de Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: 3e7eeeeae6623bbbb308f4e05c4ab8a4b9a7be50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890977"
---
# <a name="tbladcookie"></a>tblADCookie
 
a tabela tblADCookie inclui os cookies atuais de sincronização de Lightweight Directory Access Protocol (LDAP).
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID principal do domínio sendo monitorado.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nome de domínio totalmente qualificado (FQDN) do controlador de domínio atual usado para sincronização de serviços de domínio do Active Directory. Tem valor informativo.  <br/> |
|adcContent  <br/> |imagem (binário)  <br/> |Cookie da sincronização de diretório ativo.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Carimbo de hora com a hora de atualização da linha.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Tempo até que a linha é bloqueada para alterações. Isso faz parte de um mecanismo de travamento de software que garante que apenas um dos serviços do chat faz a sincronização do Active Directory ao mesmo tempo.  <br/> |
   
**Chaves**

|**Coluna (s)**|**Descrição**|
|:-----|:-----|
|prinGuid  <br/> |Chave primária.  <br/> |
|prinGuid  <br/> |Chave estrangeira com pesquisa na tabela pringuid.  <br/> |
   

