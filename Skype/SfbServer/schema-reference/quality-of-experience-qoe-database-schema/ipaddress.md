---
title: Tabela IPAddress
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 52086b456d9011730252c8c104aba46369467350
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390813"
---
# <a name="ipaddress-table"></a>Tabela IPAddress
 
A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primário  <br/> |Identificador exclusivo do endereço IP especificado.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Unique  <br/> |Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para IpAddressKey. Pode ser um endereço IPv4 ou IPv6.  <br/> |
   

