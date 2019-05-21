---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas a partir dos serviços de domínio Active Directory.
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295255"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas a partir dos serviços de domínio Active Directory.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|multiimprimir  <br/> |int, não nulo  <br/> |ID da entidade de segurança.  <br/> |
|prinAffiliationsDirty  <br/> |bit, e não nulo  <br/> |Verdadeiro se as afiliações principais precisarem ser atualizadas.  <br/> |
|prinAttributesDirty  <br/> |bit, e não nulo  <br/> |Verdadeiro se os atributos principais precisarem ser atualizados.  <br/> |
|prinDeleted  <br/> |bit, e não nulo  <br/> |Verdadeiro se o capital foi excluído.  <br/> |
|tryCount  <br/> |int  <br/> |Número de tentativas de atualizar a entidade de segurança do AD DS que aconteceram até agora.  <br/> |
|lastTry  <br/> |datetime  <br/> |Carimbo de data/hora da tentativa mais recente de atualizar a entidade de segurança. Pode ser NULL se ainda não houver uma tentativa de atualização.  <br/> |
|nextTry  <br/> |datetime  <br/> |Carimbo de data/hora para a próxima atualização agendada. Pode ser NULL se não houver mais nenhuma atualização agendada.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|multiimprimir  <br/> |Chave primária.  <br/> |
|multiimprimir  <br/> |Chave estrangeira com Lookup na tabela tblPrincipal. retoid.  <br/> |
   

