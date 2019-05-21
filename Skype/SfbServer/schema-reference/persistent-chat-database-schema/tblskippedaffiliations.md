---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos serviços de domínio Active Directory).
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295150"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos serviços de domínio Active Directory).
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|multiimprimir  <br/> |int, não nulo  <br/> |ID da entidade de segurança.  <br/> |
|affDescription  <br/> |nvarchar (256), NOT NULL  <br/> |Uma cadeia de caracteres que identifica a afiliação.  <br/> O formato é: GUID: _{0}_ URI: _{1}_> ID:_{2}_ <br/> |
|updatedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que atualizou esta linha. É sempre 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte dessas entradas.  <br/> |
   
**As**

|**Coluna (s)**|**Descrição**|
|:-----|:-----|
|\<affDescription\>  <br/> |Chave primária.  <br/> |
|multiimprimir  <br/> |Chave estrangeira com Lookup na tabela tblPrincipal. retoid.  <br/> |
   

