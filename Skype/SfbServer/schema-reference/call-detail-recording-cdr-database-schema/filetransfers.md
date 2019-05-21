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
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: O modo de transferência de arquivo armazena informações sobre sessões de transferência de arquivos ponto a ponto. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296235"
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
   

