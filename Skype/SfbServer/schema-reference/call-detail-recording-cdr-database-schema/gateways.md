---
title: Tabela Gateways no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: A tabela Gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway que está envolvido em chamadas PSTN (rede telefônica pública comutado) que têm registros no banco de dados.
ms.openlocfilehash: 62bbe3ab802736a50d1fb049a3585cba286ee7ec16907335aa831ab49259b0fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349663"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabela Gateways no Skype for Business Server 2015
 
A tabela Gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway que está envolvido em chamadas PSTN (rede telefônica pública comutado) que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse gateway.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Nome do gateway.  <br/> |
   

