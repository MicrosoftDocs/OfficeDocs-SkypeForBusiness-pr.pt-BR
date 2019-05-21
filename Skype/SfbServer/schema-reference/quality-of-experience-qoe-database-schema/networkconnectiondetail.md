---
title: Tabela NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: A tabela NetworkConnectionDetail mapeia tipos de conexão de rede para os identificadores de conexão de rede usados em outro lugar no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294814"
---
# <a name="networkconnectiondetail-table"></a>Tabela NetworkConnectionDetail
 
A tabela NetworkConnectionDetail mapeia tipos de conexão de rede para os identificadores de conexão de rede usados em outro lugar no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primária  <br/> |Identificador exclusivo do tipo de conexão de rede.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Exclusividade  <br/> |Tipo de conexão de rede que corresponde ao NetworkConnectionDetailKey. Os valores permitidos são:  <br/> 0--com fio  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--outros  <br/> 5--Tunnel  <br/> |
   

