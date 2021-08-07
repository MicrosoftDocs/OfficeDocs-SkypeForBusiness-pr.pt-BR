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
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: db9405a05335974456f77d8117f9e3f64e9832750c3d2c23441a5a587ca91d7a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305093"
---
# <a name="ipaddress-table"></a>Tabela IPAddress
 
A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primário  <br/> |Identificador exclusivo do endereço IP especificado.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Unique  <br/> |Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para IpAddressKey. Pode ser um endereço IPv4 ou IPv6.  <br/> |
   

