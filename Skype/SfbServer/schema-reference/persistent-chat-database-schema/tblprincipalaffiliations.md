---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos Serviços de Domínio active Directory, em contêineres do Active Directory, em domínios.
ms.openlocfilehash: 5eb67681e5823b8549deb01b44e0bcb771e26882a2cd713d9cf598ae0670335b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341666"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos Serviços de Domínio active Directory, em contêineres do Active Directory, em domínios.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|principalID  <br/> |int, não nulo  <br/> |ID da entidade de segurança afiliada.  <br/> |
|affiliationID  <br/> |int, não nulo  <br/> |ID da entidade de segurança que representa a afiliação. Cada entidade (exceto system-user-types) tem também uma autoafiliação.  <br/> |
|index  <br/> |int, not null  <br/> |Index. O valor para autoafiliações é -1 e, para as outras afiliações, ele aumenta sequencialmente de 1 em cada \<principalID, affiliationId\> bucket.  <br/> |
|updatedBy  <br/> |int, not null  <br/> |Entidade de segurança que fez a atualização mais recente. Isso geralmente é 1, o que significa Sincronização do Active Directory.  <br/> |
   
**Teclas**

|**Columns**|**Descrição**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Chave primária.  <br/> |
|principalID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
   

