---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contém associações de entidades de segurança.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295283"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contém associações de entidades de segurança.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|multiimprimir  <br/> |int, não nulo  <br/> |ID da entidade de segurança.  <br/> |
|memberADPath  <br/> |nvarchar (384), NOT NULL  <br/> |Nome diferenciado de um membro. Um membro não precisa ser um principal (na tabela tblPrincipal).  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<memberADPath\>  <br/> |Chave primária.  <br/> |
|multiimprimir  <br/> |Chave estrangeira com Lookup em tblPrincipal. importaid.  <br/> |
   

