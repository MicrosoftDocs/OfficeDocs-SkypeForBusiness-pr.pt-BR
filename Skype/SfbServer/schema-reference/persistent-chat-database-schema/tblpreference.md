---
title: tblPreference
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
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375940"
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


