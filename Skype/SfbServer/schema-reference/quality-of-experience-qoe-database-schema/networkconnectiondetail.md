---
title: Tabela NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: d629c3107aa52b06376974b385b874f6956d0156
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741787"
---
# <a name="networkconnectiondetail-table"></a>Tabela NetworkConnectionDetail
 
A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede em identificadores de conexão de rede usados em outro lugar no banco de dados de Qualidade da Experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primário  <br/> |Identificador exclusivo do tipo de conexão de rede.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Unique  <br/> |Tipo de conexão de rede que corresponde a NetworkConnectionDetailKey. Os valores permitidos são:  <br/> 0 -- Com fio  <br/> 1 -- Wi-Fi  <br/> 2 -- Ethernet  <br/> 3 - MobileBB  <br/> 4 - Outros  <br/> 5 - Tunnel  <br/> |
   

