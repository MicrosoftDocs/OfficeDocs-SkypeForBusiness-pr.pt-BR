---
title: Tabela NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede em identificadores de conexão de rede usados em outro lugar no banco de dados de Qualidade da Experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: d6e8bf04c8426a6278528de90f383c9867f92c8b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626443"
---
# <a name="networkconnectiondetail-table"></a>Tabela NetworkConnectionDetail
 
A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede em identificadores de conexão de rede usados em outro lugar no banco de dados de Qualidade da Experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primário  <br/> |Identificador exclusivo do tipo de conexão de rede.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Unique  <br/> |Tipo de conexão de rede que corresponde a NetworkConnectionDetailKey. Os valores permitidos são:  <br/> 0 -- Com fio  <br/> 1 -- Wi-Fi  <br/> 2 -- Ethernet  <br/> 3 - MobileBB  <br/> 4 - Outros  <br/> 5 - Tunnel  <br/> |
   

