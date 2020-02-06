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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: A tabela gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutada) que têm registros no banco de dados.
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815159"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabela gateways no Skype for Business Server 2015
 
A tabela gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutada) que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Gatewayid** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse gateway.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Nome do gateway.  <br/> |
   

