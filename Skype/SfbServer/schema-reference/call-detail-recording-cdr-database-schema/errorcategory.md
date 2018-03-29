---
title: Tabela ErrorCategory no Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'A tabela ErrorCategory contém o nome amigável para cada Skype para a classificação de diagnóstico Business Server 2015. Por padrão, o Skype para Business Server 2015 usa as seguintes classificações:'
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabela ErrorCategory no Skype para Business Server 2015
 
A tabela ErrorCategory contém o nome amigável para cada Skype para a classificação de diagnóstico Business Server 2015. Por padrão, o Skype para Business Server 2015 usa as seguintes classificações:
  
- 0--êxito
    
- 1-- falha esperada
    
- 2 - Falha inesperada
    
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo para a classificação.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> || Valor e o nome amigável atribuído para a classificação. Os valores permitidos são: <br/>  0--êxito <br/>  1-- falha esperada <br/>  2 - Falha inesperada <br/> |
   

