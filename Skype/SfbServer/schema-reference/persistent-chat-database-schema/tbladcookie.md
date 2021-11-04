---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: A tabela tblADCookie inclui os cookies atuais de sincronização do Protocolo LDAP.
ms.openlocfilehash: 770900c7ad5e31173a9e62ea3eb5a8c711afca98
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743167"
---
# <a name="tbladcookie"></a>tblADCookie
 
A tabela tblADCookie inclui os cookies atuais de sincronização do Protocolo LDAP.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID principal do domínio em monitoramento.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nome de domínio totalmente qualificado (FQDN) do controlador de domínio atual usado para a Sincronização de Serviços de Domínio do Active Directory. Tem valor informacional.  <br/> |
|adcContent  <br/> |imagem (binário)  <br/> |Cookie da Sincronização do Active Directory.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Carimbo de data/hora com a data/hora de atualização da linha.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Tempo até que a linha seja bloqueada para alterações. Isso faz parte de um mecanismo de interloque do software que garante que apenas um dos Servidores de Chat faça a sincronização do Active Directory por vez.  <br/> |
   
**Teclas**

|**Column(s)**|**Descrição**|
|:-----|:-----|
|prinGuid  <br/> |Chave primária.  <br/> |
|prinGuid  <br/> |Chave estrangeira com pesquisa na tabela Principal.prinGuid.  <br/> |
   

