---
title: Tabela NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 6d39d9e8432a20102d42cea649a51596ce2c1762
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833185"
---
# <a name="networkconnectiondetail-table"></a>Tabela NetworkConnectionDetail
 
A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede em identificadores de conexão de rede usados em outro lugar no banco de dados de Qualidade da Experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primário  <br/> |Identificador exclusivo do tipo de conexão de rede.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Unique  <br/> |Tipo de conexão de rede que corresponde a NetworkConnectionDetailKey. Os valores permitidos são:  <br/> 0 -- Com fio  <br/> 1 -- Wi-Fi  <br/> 2 -- Ethernet  <br/> 3 - MobileBB  <br/> 4 - Outros  <br/> 5 - Tunnel  <br/> |
   

