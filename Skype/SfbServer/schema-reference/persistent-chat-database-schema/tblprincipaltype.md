---
title: tblPrincipalType
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
ms.localizationpriority: medium
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: PrincipalType contém os tipos principais para categorizar o que está na tabela tblPrincipal.
ms.openlocfilehash: 5a4e38c7e29de235c4244e0617575f0732ab4362
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633495"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
PrincipalType contém os tipos principais para categorizar o que está na tabela tblPrincipal.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, não nulo  <br/> |ID do tipo principal.  <br/> |
|ptypeDesc  <br/> |não nulo nvarchar (256)  <br/> |Descrição do tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bit, não nulo  <br/> |True se o tipo corresponder às entidades que são usadas para fins internos.  <br/> |
|ptypeIsUser  <br/> |bit, não nulo  <br/> |True se o tipo for um tipo de usuário.  <br/> |
   
**Chave**

|**Coluna**|**Descrição**|
|:-----|:-----|
|ptypeID  <br/> |Chave primária.  <br/> |
   
**Valores principais**

|**ID**|**Função**|**Descrição**|**Usuário**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Qualquer  <br/> |Entidade genérica sem um tipo conhecido. Não usado na tabela tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Entidade de segurança genérica do tipo de usuário. Não é usada na tabela tblPrincipal.  <br/> |Sim  <br/> |
|3   <br/> |AnyGroup  <br/> |Entidade de segurança genérica com semântica de grupo. Não é usada na tabela tblPrincipal.  <br/> ||
|4   <br/> |SystemUser  <br/> |Principal usado internamente pelo Servidor de Chat Persistente.  <br/> ||
|5   <br/> |Usuário  <br/> |Usuário regular.  <br/> |Sim  <br/> |
|8   <br/> |DC  <br/> |Controlador de domínio dos Serviços de Domínio do Active Directory.  <br/> ||
|9   <br/> |Grupo  <br/> |Grupo de segurança do Active Directory.  <br/> ||
|10   <br/> |Folder  <br/> |Unidade organizacional ou recipiente do Active Directory.  <br/> ||
   
## <a name="see-also"></a>Confira também

[tblPrincipal](tblprincipal.md)
