---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contém as preferências do cliente dos usuários. Isso geralmente é usado por clientes anteriores ao Lync 2013.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815901"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contém as preferências do cliente dos usuários. Isso geralmente é usado por clientes anteriores ao Lync 2013.

**Columns**


| **Coluna**            | **Tipo**                        | **Descrição**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), não nulo  <br/> | Rótulo com um formato como: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, not null  <br/>            | Um número sequencial (por rótulo) para fins de versão.  <br/> |
| prefContent  <br/>    | nvarchar (máx.)  <br/>           | Conteúdo codificado.  <br/>                                         |
| lastModifiedBy  <br/> | int, not null  <br/>            | ID da entidade de entidade que atualizou a preferência.  <br/>         |

**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Chave primária.  <br/> |


