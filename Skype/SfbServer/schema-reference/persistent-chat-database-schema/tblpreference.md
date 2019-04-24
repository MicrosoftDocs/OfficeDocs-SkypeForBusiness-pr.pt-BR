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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212534"
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


