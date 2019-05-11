---
title: Tabela ErrorCategory no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'A tabela ErrorCategory contém o nome amigável para cada Skype para a classificação de diagnóstico Business Server 2015. Por padrão, o Skype para Business Server 2015 usa as seguintes classificações:'
ms.openlocfilehash: b6226396302353b815138b41b7c19f170a0d6b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901084"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabela ErrorCategory no Skype para Business Server 2015
 
A tabela ErrorCategory contém o nome amigável para cada Skype para a classificação de diagnóstico Business Server 2015. Por padrão, o Skype para Business Server 2015 usa as seguintes classificações:
  
- 0--êxito
    
- 1-- falha esperada
    
- 2 - Falha inesperada
    
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo para a classificação.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> || Valor e o nome amigável atribuído para a classificação. Os valores permitidos são: <br/>  0--êxito <br/>  1-- falha esperada <br/>  2 - Falha inesperada <br/> |
   

