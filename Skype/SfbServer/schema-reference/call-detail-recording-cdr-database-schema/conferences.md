---
title: Tabela de conferências no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Cada registro desta tabela contém detalhes da chamada sobre uma conferência.
ms.openlocfilehash: 97d7fcb4dc2217b1b7c52c1aa3424f1cf9f57808
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815349"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabela de conferências no Skype for Business Server 2015
 
Cada registro desta tabela contém detalhes da chamada sobre uma conferência.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primária  <br/> |Hora em que a solicitação de conferência foi capturada pelo agente de CDR. Usado apenas como uma chave primária para identificar uma instância de conferência de forma exclusiva.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a **identificação_da_sessãotime** para identificar exclusivamente uma instância de conferência. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Exterior  <br/> |URL da conferência. Consulte a [tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) para obter mais informações. <br/> |
|**ConfInstance** <br/> |identificador  <br/> | <br/> |Útil para conferências recorrentes; cada instância de uma conferência recorrente tem o mesmo **ConferenceUri**, mas terá um **ConfInstance**diferente. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Hora de início da conferência.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Hora de início da conferência.  <br/> |
|**Poolid** <br/> |int  <br/> |Exterior  <br/> |Número de identificação para identificar o pool no qual a conferência foi capturada. Consulte a [tabela de grupos](pools.md) para obter mais informações. <br/> |
|**OrganizerId** <br/> |Núm  <br/> |Exterior  <br/> |Número de identificação para identificar o URI do organizador dessa conferência. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**Sinalizador** <br/> |smallint  <br/> || Uma máscara de bits que contém atributos de conferência. Os valores possíveis são: <br/>  0X01 <br/>  Sintética <br/>  Transação <br/> |
|**Processe** <br/> |bit  <br/> ||Campo interno usado pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   
\*Para a maioria das sessões, o SessionIdSeq terá o valor de 1. Se duas sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de uma será 1 e, para a outra, será 2 e assim por diante.
  

