---
title: Relatório de lista de falhas no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumo: saiba mais sobre o Relatório de Lista de Falhas no Skype for Business Server.'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816841"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Relatório de lista de falhas no Skype for Business Server 
 
**Resumo:** Saiba mais sobre o Relatório de Lista de Falhas no Skype for Business Server.
  
The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.
  
## <a name="accessing-the-failure-list-report"></a>Accessing the Failure List Report

O Relatório de Lista de Falhas é acessado clicando em qualquer uma das seguintes métricas no Relatório de Distribuição de [Falhas no Skype for Business Server:](failure-distribution-report.md)
  
- Principais motivos diagnósticos (sessões)
    
- Principais modalidades (sessões)
    
- Principais pools (sessões)
    
- Principais fontes (sessões)
    
- Principais componentes (sessões)
    
- Principais usuários de origem (sessões)
    
- Principais usuários de destino (sessões)
    
- Principais agentes de usuários de origem (sessões)
    
No Relatório de Lista de Falhas, você pode acessar o Relatório Detalhado de Sessão Ponto a Ponto no [Skype for Business Server](peer-to-peer-session-detail-report.md) clicando na métrica De detalhe da sessão para uma sessão ponto a ponto. You can also access the Conference Detail Report by clicking the Conference metric for a conference.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Making the Best Use of the Failure List Report

In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:
  
Internal server error creating media for user.
  
It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session. (For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those. For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv. Based on the data saved in that file, this command lists all the users who were involved in at least one failed session: 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

That command will return a list similar to this:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

These two commands report back the total number of failed sessions that each user was involved in:
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

That will return data similar to this:
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Lista de Falhas.
  
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Lista de Falhas para cada chamada mal-sucedida.
  
**Métricas do Relatório de Lista de Falhas**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Hora de relatório** <br/> |Não  <br/> |Data e hora em que o relatório foi gravado.  <br/> |
|**Solicitação** <br/> |Não  <br/> |Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR ou ATÉ LOGO.  <br/> |
|**Código da resposta** <br/> |Não  <br/> |Código da resposta SIP enviado quando a conferência falhou.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros.  <br/> |
|**Join cost time (ms)** <br/> |Não  <br/> |Amount of time (in milliseconds) required for the user to join the conference.  <br/> |
|**Do usuário** <br/> |Não  <br/> |Endereço SIP do usuário que iniciou a chamada.  <br/> |
|**Representante do usuário de origem** <br/> |Não  <br/> |Software usado pelo ponto de extremidade do usuário que iniciou a chamada.  <br/> |
|**Para usuário** <br/> |Não  <br/> |Endereço SIP do usuário que estava recebendo a chamada.  <br/> |
   

