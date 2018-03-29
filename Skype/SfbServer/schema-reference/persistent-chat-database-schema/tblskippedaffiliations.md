---
title: Skippedaffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: Skippedaffiliations inclui as afiliações que não podiam ser lidas (geralmente devido a erros de acesso do Active Directory Domain Services).
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a>Skippedaffiliations
 
Skippedaffiliations inclui as afiliações que não podiam ser lidas (geralmente devido a erros de acesso do Active Directory Domain Services).
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|affDescription  <br/> |nvarchar (256), não nulo  <br/> |Uma cadeia de caracteres identificando a afiliação.  <br/> O formato é: guid: _{0}_ uri: _{1}_> id: _{2}_ <br/> |
|updatedBy  <br/> |int, não nulo  <br/> |ID da entidade que atualizou esta linha. Sempre é 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte para essas entradas.  <br/> |
   
**Chaves**

|**Coluna (s)**|**Descrição**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
   

