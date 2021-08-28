---
title: Tabela IPAddress
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: bc314566bb29b1be8c14286990608adf250258bf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629393"
---
# <a name="ipaddress-table"></a>Tabela IPAddress
 
A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primário  <br/> |Identificador exclusivo do endereço IP especificado.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Unique  <br/> |Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para IpAddressKey. Pode ser um endereço IPv4 ou IPv6.  <br/> |
   

