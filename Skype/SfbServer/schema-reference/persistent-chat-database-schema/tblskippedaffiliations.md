---
title: tblSkippedAffiliations
ms.reviewer: ''
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
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874784"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
Skippedaffiliations inclui as afiliações que não podiam ser lidas (geralmente devido a erros de acesso do Active Directory Domain Services).
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|affDescription  <br/> |nvarchar (256), não nulo  <br/> |Uma cadeia de caracteres identificando a afiliação.  <br/> O formato é: guid: _{0}_ uri: _{1}_ gt _ id:_{2}_ <br/> |
|updatedBy  <br/> |int, não nulo  <br/> |ID da entidade que atualizou esta linha. Sempre é 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte para essas entradas.  <br/> |
   
**Chaves**

|**Coluna (s)**|**Descrição**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
   

