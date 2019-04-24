---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Principaltype contém os tipos principais para categorizar o que está na tabela tblPrincipal.
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212436"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
Principaltype contém os tipos principais para categorizar o que está na tabela tblPrincipal.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, não nulo  <br/> |ID do tipo de entidade.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), não nulo  <br/> |Descrição do tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bit, não nulo  <br/> |True se o type corresponde às entidades que são usadas para finalidades internas.  <br/> |
|ptypeIsUser  <br/> |bit, não nulo  <br/> |True se o tipo for um tipo de usuário.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|ptypeID  <br/> |Chave primária.  <br/> |
   
**Valores principais**

|**ID**|**Função**|**Descrição**|**Usuário**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Qualquer um  <br/> |Entidade genérica com nenhum tipo conhecido. Não é usada na tabela tblPrincipal.  <br/> ||
|2  <br/> |Dopode  <br/> |Entidade genérica do tipo de usuário. Não é usada na tabela tblPrincipal.  <br/> |Sim  <br/> |
|3  <br/> |AnyGroup  <br/> |Entidade genérica com semântica de grupo. Não é usada na tabela tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Entidade usada internamente pelo servidor de Chat persistente.  <br/> ||
|5  <br/> |Usuário  <br/> |Usuário regular.  <br/> |Sim  <br/> |
|8  <br/> |CONTROLADOR DE DOMÍNIO  <br/> |Controlador de domínio do Active Directory dos serviços de domínio.  <br/> ||
|9  <br/> |Grupo  <br/> |Grupo de segurança do Active Directory.  <br/> ||
|10  <br/> |Pasta  <br/> |Contêiner do Active Directory ou unidade organizacional.  <br/> ||
   
## <a name="see-also"></a>Confira também

[tblPrincipal](tblprincipal.md)
