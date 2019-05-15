---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: o tblPrincipalAffiliations inclui as principais afiliações que descrevem as associações em locais, incluindo grupos de segurança do Active Directory Domain Services, em contêineres do Active Directory, em domínios.
ms.openlocfilehash: fb1bd8eb7291ba001a5c23240c2de70aaff048b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929816"
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
   

