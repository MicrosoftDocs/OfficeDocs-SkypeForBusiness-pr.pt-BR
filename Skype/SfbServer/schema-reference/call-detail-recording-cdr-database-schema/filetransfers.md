---
title: Modo de exibição de transferência de fileviews
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: O modo de transferência de arquivo armazena informações sobre sessões de transferência de arquivos ponto a ponto. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815199"
---
# <a name="filetransfers-view"></a>Modo de exibição de transferência de fileviews
 
O modo de transferência de arquivo armazena informações sobre sessões de transferência de arquivos ponto a ponto. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
> [!NOTE]
> O modo de exibição filetransfers contém todas as colunas na [exibição SessionDetails](sessiondetails-0.md) , além das colunas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nome do arquivo transferido.  <br/> |
|**Cookie** <br/> |nvarchar(128  <br/> |Usado para identificar todas as mensagens de acompanhamento como associadas a esta.  <br/> |
|**Fileidentity** <br/> |identificador  <br/> |Identificador exclusivo para distinguir entre as transferências de arquivo que envolvem o mesmo nome de arquivo.  <br/> |
|**Aceite** <br/> |bit  <br/> |Pode ser TRUE ou NULL. Se verdadeiro, rejeitar e cancelar será nulo.  <br/> |
|**Rejeitar** <br/> |bit  <br/> |Pode ser TRUE ou NULL. Se verdadeiro, aceitar e cancelar será nulo.  <br/> |
|**Cancelar** <br/> |bit  <br/> |Pode ser TRUE ou NULL. Se verdadeiro, aceitar e rejeitar será nulo.  <br/> |
   

