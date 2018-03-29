---
title: Tabela de gateways no Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: A tabela de Gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway que está envolvido em chamadas de (PSTN) da rede telefônica pública comutada que têm registros no banco de dados.
ms.openlocfilehash: e9592b227e8ccff6829748230abd3e8ddb8edb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabela de gateways no Skype para Business Server 2015
 
A tabela de Gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway que está envolvido em chamadas de (PSTN) da rede telefônica pública comutada que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este gateway.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Nome do gateway.  <br/> |
   

