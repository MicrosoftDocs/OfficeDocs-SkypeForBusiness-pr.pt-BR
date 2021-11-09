---
title: Tabela AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma origem.
ms.openlocfilehash: 10dbe69533fe26ba156c270f003fb11ab56e5179
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856428"
---
# <a name="appliedbandwidthsource-table"></a>Tabela AppliedBandwidthSource
 
A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma origem.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica a origem.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Unique  <br/> |Essa é a origem do cap de largura de banda que está sendo imposto. Ele descreve de onde vem o limite de largura de banda (por exemplo, "Servidor de Política", "SERVIDOR TURN" ou "Modalidade").  <br/> |
   

