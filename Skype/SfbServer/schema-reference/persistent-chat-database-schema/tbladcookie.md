---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol).
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295528"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol).
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, não nulo  <br/> |GUID principal do domínio que está sendo monitorado.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |FQDN (nome de domínio totalmente qualificado) do controlador de domínio atual usado para a sincronização dos serviços de domínio Active Directory. Tem valor informativo.  <br/> |
|adcContent  <br/> |imagem (binário)  <br/> |Cookie de sincronização do Active Directory.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Carimbo de data/hora com o tempo de atualização de linha.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Tempo até que a linha esteja bloqueada para alterações. Isso faz parte de um mecanismo de travamento do software que garante que apenas um dos serviços de chat faça a sincronização do Active Directory de cada vez.  <br/> |
   
**As**

|**Coluna (s)**|**Descrição**|
|:-----|:-----|
|prinGuid  <br/> |Chave primária.  <br/> |
|prinGuid  <br/> |Chave estrangeira com pesquisa na tabela principal. prinGuid.  <br/> |
   

