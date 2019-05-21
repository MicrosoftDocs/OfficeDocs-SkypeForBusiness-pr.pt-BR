---
title: Tabela gateways no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: A tabela gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutada) que têm registros no banco de dados.
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296179"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabela gateways no Skype for Business Server 2015
 
A tabela gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutada) que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Gatewayid** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse gateway.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Nome do gateway.  <br/> |
   

