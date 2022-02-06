---
title: Tabela de conferências no Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Cada registro nesta tabela contém detalhes de chamada sobre uma conferência.
---

# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabela de conferências no Skype for Business Server 2015
 
Cada registro nesta tabela contém detalhes de chamada sobre uma conferência.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário  <br/> |Hora em que a solicitação de conferência foi capturada pelo agente CDR. Usada apenas como uma chave primária para identificar exclusivamente uma instância de conferência.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI da conferência. Consulte a [tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) para obter mais informações. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Útil para conferências recorrentes; cada instância de uma conferência recorrente tem o mesmo **ConferenceUri**, mas terá uma **ConfInstance diferente**. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Hora de início da conferência.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Hora de início da conferência.  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |Número da ID para identificar o pool no qual a conferência foi capturada. Consulte a [tabela Pools para](pools.md) obter mais informações. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Foreign  <br/> |Número da ID para identificar o URI do organizador desta conferência. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**Flag** <br/> |smallint  <br/> || Uma máscara de bits que contém atributos de conferência. Os valores possíveis são: <br/>  0X01 <br/>  Sintético <br/>  Transação <br/> |
|**Processado** <br/> |bit  <br/> ||Campo interno usado pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   
\* Para a maioria das sessões, SessionIdSeq terá o valor de 1. Se duas sessões começarem exatamente ao mesmo tempo, SessionIdSeq para uma será 1 e para a outra será 2 e assim por diante.
  

