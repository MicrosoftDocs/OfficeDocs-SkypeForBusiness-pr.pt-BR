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
description: tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso dos Serviços de Domínio Active Directory).
ms.openlocfilehash: ddc8ef78f083235ccde122a3f26fd7f37e34b71d9643b1c729f802e3e080c413
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305363"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso dos Serviços de Domínio Active Directory).
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|affDescription  <br/> |nvarchar (256), não nulo  <br/> |Uma cadeia identificando a afiliação.  <br/> O formato é: guid:  _{0}_ uri: _{1}_> id:  _{2}_ <br/> |
|updatedBy  <br/> |int, não nulo  <br/> |ID da principal que atualizou essa linha. É sempre 1 (usuário do sistema) porque a Sincronização do Active Directory é a única origem dessas entradas.  <br/> |
   
**Teclas**

|**Column(s)**|**Descrição**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
   

