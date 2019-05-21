---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contém as preferências do cliente dos usuários. Isso geralmente é usado por clientes anteriores ao Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295339"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contém as preferências do cliente dos usuários. Isso geralmente é usado por clientes anteriores ao Lync 2013.

**Colunas**


| **Coluna**            | **Tipo**                        | **Descrição**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), NOT NULL  <br/> | Rótulo com um formato como: \<URI de SIP do usuário\>                   |
| prefSeqID  <br/>      | int, não nulo  <br/>            | Um número sequencial (por rótulo) para fins de controle de versão.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Conteúdo codificado.  <br/>                                         |
| lastModifiedBy  <br/> | int, não nulo  <br/>            | ID da entidade de segurança que atualizou a preferência.  <br/>         |

**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Chave primária.  <br/> |


