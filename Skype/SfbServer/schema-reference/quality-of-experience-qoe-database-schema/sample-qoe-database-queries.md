---
title: Exemplo de consultas ao banco de dados de QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: Esta seção contém exemplos de consultas para o banco de dados de qualidade da experiência (QoE).
ms.openlocfilehash: 42000bfe28acde629165009bbb7b6c33d15f8cdb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294702"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="c146e-103">Exemplo de consultas ao banco de dados de QoE</span><span class="sxs-lookup"><span data-stu-id="c146e-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="c146e-104">Esta seção contém exemplos de consultas para o banco de dados de qualidade da experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="c146e-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="c146e-105">Use o exemplo a seguir para obter a média de tremulação e perda de pacote para todos os fluxos de áudio.</span><span class="sxs-lookup"><span data-stu-id="c146e-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="c146e-106">Use o exemplo a seguir para localizar o número total de conferências que usaram o console de reunião.</span><span class="sxs-lookup"><span data-stu-id="c146e-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync
```

<span data-ttu-id="c146e-107">Use o exemplo a seguir para obter o ConversstionalMOS, o SendingMOS e o ListendingMOS por dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="c146e-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```
select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
from
(
   select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

   union

   select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
   from MediaLineView m
   inner join AudioStream a
   on m.ConferenceDateTime = a.ConferenceDateTime
      and m.SessionSeq = a.SessionSeq
      and m.MediaLineLabel = 0

)as t
group by t.DeviceName
order by SampleNum desc
```
