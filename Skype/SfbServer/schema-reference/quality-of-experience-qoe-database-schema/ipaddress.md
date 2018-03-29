---
title: Tabela IPAddress
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
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a>Tabela IPAddress
 
A tabela IPAddress mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo para o endereço IP especificado.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Exclusivo  <br/> |Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para o IpAddressKey. Isso pode ser um IPv4 ou um endereço IPv6.  <br/> |
   

