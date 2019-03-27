---
title: Tabela IPAddress
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: A tabela IPAddress mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876955"
---
# <a name="ipaddress-table"></a>Tabela IPAddress
 
A tabela IPAddress mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo para o endereço IP especificado.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Exclusivo  <br/> |Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para o IpAddressKey. Isso pode ser um IPv4 ou um endereço IPv6.  <br/> |
   

