---
title: Tabela de transferências de fileno Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Cada registro representa uma sessão de transferência de arquivo.
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815209"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabela de transferências de fileno Skype for Business Server 2015
 
Cada registro representa uma sessão de transferência de arquivo.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a **identificação_da_sessãotime** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Nome do arquivo** <br/> |nvarchar(256)  <br/> ||Nome do arquivo.  <br/> |
|**Fileidentity** <br/> |identificador  <br/> ||Identificador exclusivo para distinguir entre as transferências de arquivo que envolvem o mesmo nome de arquivo.  <br/> |
|**Cookie** <br/> |nvarchar(128  <br/> |Primária  <br/> |Usado para identificar todas as mensagens de acompanhamento como associadas a esta.  <br/> |
|**Aceite** <br/> |bit  <br/> ||Pode ser TRUE ou NULL. Se verdadeiro, rejeitar e cancelar será nulo.  <br/> |
|**Rejeitar** <br/> |bit  <br/> ||Pode ser TRUE ou NULL. Se verdadeiro, aceitar e cancelar será nulo.  <br/> |
|**Cancelar** <br/> |bit  <br/> ||Pode ser TRUE ou NULL. Se verdadeiro, aceitar e rejeitar será nulo.  <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   

