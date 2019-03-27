---
title: tblPreference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contém preferências do cliente dos usuários. Isso é geralmente usado pelos clientes anterior para o Lync 2013.
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879788"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contém preferências do cliente dos usuários. Isso é geralmente usado pelos clientes anterior para o Lync 2013.

**Colunas**


| **Coluna**            | **Tipo**                        | **Descrição**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), não nulo  <br/> | Etiqueta com um formato como: \<uri de sip do usuário\>                   |
| prefSeqID  <br/>      | int, não nulo  <br/>            | Um número sequencial (por etiqueta) para fins de controle de versão.  <br/> |
| prefContent  <br/>    | nvarchar (máx.)  <br/>           | Conteúdo codificado.  <br/>                                         |
| lastModifiedBy  <br/> | int, não nulo  <br/>            | ID da entidade que atualizou a preferência.  <br/>         |

**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Chave primária.  <br/> |


