---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: Skippedaffiliations inclui as afiliações que não podiam ser lidas (geralmente devido a erros de acesso do Active Directory Domain Services).
ms.openlocfilehash: 85fe836e75409a0a6aae22583358f9f88dc8d4e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924938"
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
   

