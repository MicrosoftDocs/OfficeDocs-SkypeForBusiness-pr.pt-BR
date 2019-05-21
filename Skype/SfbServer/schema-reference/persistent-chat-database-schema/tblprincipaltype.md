---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295241"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, não nulo  <br/> |ID do tipo principal.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), NOT NULL  <br/> |Descrição do tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bit, e não nulo  <br/> |Verdadeiro se o tipo corresponder às entidades de segurança usadas para fins internos.  <br/> |
|ptypeIsUser  <br/> |bit, e não nulo  <br/> |Verdadeiro se o tipo for um tipo de usuário.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|ptypeID  <br/> |Chave primária.  <br/> |
   
**Valores principais**

|**ID**|**Função**|**Descrição**|**Usuário**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Qualquer um  <br/> |Entidade de segurança genérica sem tipo conhecido. Não usado na tabela tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Entidade de usuário genérica do tipo de usuário. Não usado na tabela tblPrincipal.  <br/> |Sim  <br/> |
|3  <br/> |AnyGroup  <br/> |Entidade de segurança genérica com semântica de grupo. Não usado na tabela tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Principal usado internamente pelo servidor de chat persistente.  <br/> ||
|5  <br/> |Usuário  <br/> |Usuário regular.  <br/> |Sim  <br/> |
|08  <br/> |CLONA  <br/> |Controlador de domínio dos serviços de domínio Active Directory.  <br/> ||
|222  <br/> |Grupos  <br/> |Grupo de segurança do Active Directory.  <br/> ||
|254  <br/> |La  <br/> |Contêiner ou unidade organizacional do Active Directory.  <br/> ||
   
## <a name="see-also"></a>Confira também

[tblPrincipal](tblprincipal.md)
