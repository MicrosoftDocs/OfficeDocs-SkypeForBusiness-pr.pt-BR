---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: a tabela tblADCookie inclui os cookies atuais de sincronização de Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929942"
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
   

