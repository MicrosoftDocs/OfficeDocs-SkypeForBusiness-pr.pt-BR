---
title: Tabela NetworkConnectionDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede para os identificadores de conexão de rede usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 6df2511c2dfee0158b4633be5dfa8549639cfc6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889053"
---
# <a name="networkconnectiondetail-table"></a>Tabela NetworkConnectionDetail
 
A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede para os identificadores de conexão de rede usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo para o tipo de conexão de rede.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Exclusivo  <br/> |Tipo de conexão de rede que corresponde ao NetworkConnectionDetailKey. Os valores permitidos são:  <br/> 0--com fio  <br/> 1-- WiFi  <br/> 2-- Ethernet  <br/> 3-- MobileBB  <br/> 4 – outros  <br/> 5 – túnel  <br/> |
   

