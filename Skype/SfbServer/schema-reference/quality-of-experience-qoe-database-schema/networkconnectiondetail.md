---
title: Tabela NetworkConnectionDetail
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
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a>Tabela NetworkConnectionDetail
 
A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede para os identificadores de conexão de rede usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo para o tipo de conexão de rede.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Exclusivo  <br/> |Tipo de conexão de rede que corresponde ao NetworkConnectionDetailKey. Os valores permitidos são:  <br/> 0--com fio  <br/> 1-- WiFi  <br/> 2-- Ethernet  <br/> 3-- MobileBB  <br/> 4 – outros  <br/> 5 – túnel  <br/> |
   

