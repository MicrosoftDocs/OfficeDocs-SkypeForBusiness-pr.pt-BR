---
title: Tabela de conferências em Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Cada registro desta tabela contém detalhes de chamada sobre uma conferência.
ms.openlocfilehash: f0401c150f3835772ba0df20f8c02c64c9919921
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213260"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabela de conferências em Skype para Business Server 2015
 
Cada registro desta tabela contém detalhes de chamada sobre uma conferência.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária  <br/> |Hora em que a solicitação de conferência foi capturada pelo agente de CDR. Usado apenas como uma chave primária para identificar exclusivamente uma instância de conferência.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |URI da conferência. Consulte a [tabela ConferenceUris do Skype para Business Server 2015](conferenceuris.md) para obter mais informações. <br/> |
|**ConfInstance** <br/> |Identificador exclusivo  <br/> | <br/> |Útil para conferências recorrentes; cada instância de uma conferência recorrente tem o mesmo **ConferenceUri**, mas terá um **ConfInstance**de diferente. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Hora de início da conferência.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Hora de início da conferência.  <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |Número de identificação para identificar o pool no qual a conferência foi capturada. Consulte a [tabela de Pools](pools.md) para obter mais informações. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Externa  <br/> |Número de identificação para identificar o organizador URI desta conferência. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**Sinalizador** <br/> |smallint  <br/> || Uma máscara de bits que contém os atributos de conferência. Valores possíveis são: <br/>  0X01 <br/>  Sintética <br/>  Transação <br/> |
|**Processadas** <br/> |bit  <br/> ||Campo interno usado pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   
\*Para a maioria das sessões, SessionIdSeq terá o valor de 1. Se duas sessões Iniciar em exatamente ao mesmo tempo, o SessionIdSeq para um será 1 e para o outro será 2 e assim por diante.
  

