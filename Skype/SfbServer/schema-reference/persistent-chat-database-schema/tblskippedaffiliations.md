---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: TblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos Serviços de Domínio Active Directory).
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831421"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
TblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos Serviços de Domínio Active Directory).
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|affDescription  <br/> |nvarchar (256), não nulo  <br/> |Uma cadeia identificando a afiliação.  <br/> O formato é: guid:  _{0}_ uri: _{1}_> id:  _{2}_ <br/> |
|updatedBy  <br/> |int, não nulo  <br/> |ID da principal que atualizou essa linha. É sempre 1 (usuário do sistema) porque a Sincronização do Active Directory é a única origem dessas entradas.  <br/> |
   
**Teclas**

|**Colunas**|**Descrição**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
   

