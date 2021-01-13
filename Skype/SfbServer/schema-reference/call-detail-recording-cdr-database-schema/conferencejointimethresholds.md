---
title: Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo Relatório de Resumo de Tempo de Participação em Conferência. Este relatório resume o período necessário para que os usuários participem com êxito de uma conferência; esses valores de tempo são reportados como média e em uma das seguintes categorias:'
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813301"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015
 
A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo Relatório de Resumo de Tempo de Participação em Conferência. Este relatório resume o período necessário para que os usuários participem com êxito de uma conferência; esses valores de tempo são reportados como média e em uma das seguintes categorias:
  
- Menos de 2 segundos.
    
- Entre 2 e 5 segundos.
    
- Entre 5 e 10 segundos.
    
- Mais de 10 segundos
    
A tabela ConferenceJoinTimeThresholds contém os valores de classificação de 2 segundos, 5 segundos e 10 segundos.
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primário  <br/> |Identificador exclusivo da classificação.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Limite superior da classificação. Os valores permitidos são: <br/>  2  <br/>  5  <br/>  10  <br/> |
   

