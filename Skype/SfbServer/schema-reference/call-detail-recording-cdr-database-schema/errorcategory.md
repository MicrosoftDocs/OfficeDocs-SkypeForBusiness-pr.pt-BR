---
title: Tabela ErrorCategory no Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico Skype for Business Server 2015. Por padrão, Skype for Business Server 2015 usa as seguintes classificações:'
---

# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabela ErrorCategory no Skype for Business Server 2015
 
A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico Skype for Business Server 2015. Por padrão, Skype for Business Server 2015 usa as seguintes classificações:
  
- 0 -- Sucesso
    
- 1 - Falha esperada
    
- 2 - Falha inesperada
    
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primário  <br/> |Identificador único para a classificação.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> || Valor e nome amigável atribuídos à classificação. Os valores permitidos são: <br/>  0 -- Sucesso <br/>  1 - Falha esperada <br/>  2 - Falha inesperada <br/> |
   

