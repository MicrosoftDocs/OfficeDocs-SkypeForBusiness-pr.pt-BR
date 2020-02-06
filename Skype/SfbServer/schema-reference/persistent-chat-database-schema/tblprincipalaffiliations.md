---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio Active Directory, em contêineres do Active Directory, em domínios.
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814469"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio Active Directory, em contêineres do Active Directory, em domínios.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|entidade de segurança  <br/> |int, não nulo  <br/> |ID do objeto associado.  <br/> |
|afiliaid  <br/> |int, não nulo  <br/> |ID da entidade de segurança que representa a afiliada. Cada entidade de segurança (exceto tipos de usuário do sistema) também tem uma afiliada.  <br/> |
|dedo  <br/> |int, não nulo  <br/> |Dedo. O valor para autoafiliações é-1 e para as outras afiliações que ele aumenta sequencialmente de 1 dentro de cada \<objeto de entidade de segurança\> , o BucketID.  <br/> |
|updatedBy  <br/> |int, não nulo  <br/> |Entidade de segurança que fez a atualização mais recente. Geralmente, isso é 1, o que significa sincronização do Active Directory.  <br/> |
   
**As**

|**Colunas**|**Descrição**|
|:-----|:-----|
|\<entidade de segurança, índice, afiliaid\>  <br/> |Chave primária.  <br/> |
|entidade de segurança  <br/> |Chave estrangeira com Lookup na tabela tblPrincipal. retoid.  <br/> |
|afiliaid  <br/> |Chave estrangeira com Lookup na tabela tblPrincipal. retoid.  <br/> |
   

