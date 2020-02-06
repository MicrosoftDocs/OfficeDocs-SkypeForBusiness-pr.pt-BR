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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas a partir dos serviços de domínio Active Directory.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813569"
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
   

