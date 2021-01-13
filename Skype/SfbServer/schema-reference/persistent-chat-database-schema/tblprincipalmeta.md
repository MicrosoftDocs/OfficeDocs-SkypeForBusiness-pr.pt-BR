---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas dos Serviços de Domínio Active Directory.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831541"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas dos Serviços de Domínio Active Directory.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|prinAffiliationsDirty  <br/> |bit, não nulo  <br/> |Verdadeiro se as afiliações da entidade precisam ser atualizadas.  <br/> |
|prinAttributesDirty  <br/> |bit, não nulo  <br/> |Verdadeiro se os atributos da entidade precisam ser atualizados.  <br/> |
|prinDeleted  <br/> |bit, não nulo  <br/> |Verdadeiro se a entidade foi excluída.  <br/> |
|tryCount  <br/> |int  <br/> |Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.  <br/> |
|lastTry  <br/> |datetime  <br/> |Carimbo de data/hora da tentativa mais recente para atualizar a entidade. Pode ser nulo se ainda não houve tentativa de atualização.  <br/> |
|nextTry  <br/> |datetime  <br/> |Carimbo de data/hora para a próxima atualização agendada. Pode ser nulo se nenhuma atualização foi agendada.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|prinID  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
   

