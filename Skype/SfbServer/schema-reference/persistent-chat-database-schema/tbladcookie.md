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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol).
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814699"
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
   

