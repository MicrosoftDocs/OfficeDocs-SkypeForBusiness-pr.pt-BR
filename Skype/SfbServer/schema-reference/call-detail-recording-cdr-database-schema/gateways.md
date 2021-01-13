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
description: A tabela Gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutado) que possuem registros no banco de dados.
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821581"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Tabela Gateways no Skype for Business Server 2015
 
A tabela Gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutado) que possuem registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica este gateway.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Nome do gateway.  <br/> |
   

