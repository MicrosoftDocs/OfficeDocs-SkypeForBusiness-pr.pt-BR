---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: o tblPrincipalAffiliations inclui as principais afiliações que descrevem as associações em locais, incluindo grupos de segurança do Active Directory Domain Services, em contêineres do Active Directory, em domínios.
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212499"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
o tblPrincipalAffiliations inclui as principais afiliações que descrevem as associações em locais, incluindo grupos de segurança do Active Directory Domain Services, em contêineres do Active Directory, em domínios.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|principalID  <br/> |int, não nulo  <br/> |ID da entidade de segurança afiliada.  <br/> |
|affiliationID  <br/> |int, não nulo  <br/> |ID da entidade de segurança que representa a afiliação. Cada entidade (exceto o usuário digita sistema) tem uma afiliação Self também.  <br/> |
|índice  <br/> |int, não nulo  <br/> |Índice. O valor de afiliações Self é -1 e para as outras afiliações aumenta sequencialmente de 1 dentro de cada \<principalID, affiliationId\> no processo de Balde.  <br/> |
|updatedBy  <br/> |int, não nulo  <br/> |Entidade de segurança que efetuou a atualização mais recente. Isso geralmente é 1, o que significa que a sincronização do Active Directory.  <br/> |
   
**Chaves**

|**Colunas**|**Descrição**|
|:-----|:-----|
|\<principalID, índice, affiliationID\>  <br/> |Chave primária.  <br/> |
|principalID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
|affiliationID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
   

