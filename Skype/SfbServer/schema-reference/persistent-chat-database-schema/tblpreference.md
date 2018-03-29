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
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a>tblPreference
 
tblPreference contém preferências do cliente dos usuários. Isso é geralmente usado pelos clientes anterior para o Lync 2013.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prefLabel  <br/> |nvarchar (255), não nulo  <br/> |Etiqueta com um formato como: \<uri de sip do usuário\>|nome de usuário. \<preferência set\>.  <br/> |
|prefSeqID  <br/> |int, não nulo  <br/> |Um número sequencial (por etiqueta) para fins de controle de versão.  <br/> |
|prefContent  <br/> |nvarchar (máx.)  <br/> |Conteúdo codificado.  <br/> |
|lastModifiedBy  <br/> |int, não nulo  <br/> |ID da entidade que atualizou a preferência.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Chave primária.  <br/> |
   

