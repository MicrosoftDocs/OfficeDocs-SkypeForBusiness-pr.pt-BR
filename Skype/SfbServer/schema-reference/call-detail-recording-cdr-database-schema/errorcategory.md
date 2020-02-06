---
title: Tabela ErrorCategory no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Skype for Business Server 2015. Por padrão, o Skype for Business Server 2015 usa as seguintes classificações:'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815249"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabela ErrorCategory no Skype for Business Server 2015
 
A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Skype for Business Server 2015. Por padrão, o Skype for Business Server 2015 usa as seguintes classificações:
  
- 0--sucesso
    
- 1--falha prevista
    
- 2-falha inesperada
    
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CódigoDaCategoria** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo da classificação.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> || Valor e nome amigável atribuídos à classificação. Os valores permitidos são: <br/>  0--sucesso <br/>  1--falha prevista <br/>  2-falha inesperada <br/> |
   

