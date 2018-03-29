---
title: Relatório de lista de falhas no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumo: Saiba mais sobre o Failure List Report no Skype para Business Server 2015.'
ms.openlocfilehash: ef5b11f92997e6919de0fd9056acdeebddc898d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="failure-list-report-in-skype-for-business-server-2015"></a>Relatório de lista de falhas no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o Failure List Report no Skype para Business Server 2015.
  
O Relatório da lista de falhas fornece informações sobre os participantes individuais de uma sessão de conferência ou ponto a ponto com falha. Essas informações incluem o URI do usuário que teve o problema, bem como o código de resposta SIP e o ID de diagnóstico associado à falha.
  
## <a name="accessing-the-failure-list-report"></a>Acessando o Relatório da lista de falhas

O Failure List Report é acessado clicando em qualquer uma das seguintes métricas do [Relatório de falha de distribuição no Skype para Business Server 2015](failure-distribution-report.md):
  
- Principais motivos diagnósticos (sessões)
    
- Principais modalidades (sessões)
    
- Principais pools (sessões)
    
- Principais fontes (sessões)
    
- Principais componentes (sessões)
    
- Principais usuários "De" (sessões)
    
- Principais usuários "Para" (sessões)
    
- Principais agentes do usuários "De" (sessões)
    
Do Failure List Report, você pode acessar o [relatório de detalhes de sessão ponto a ponto no Skype para Business Server 2015](peer-to-peer-session-detail-report.md) clicando na métrica detalhe de sessão para uma sessão ponto a ponto. Você também pode acessar o Relatório de detalhes da conferência clicando na métrica Conferência de uma conferência.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Aprimorando o uso do Relatório da lista de falhas

No Relatório da lista de falhas, é possível visualizar uma descrição para cada código de resposta ou cada ID de diagnóstico simplesmente passando o mouse sobre o valor em questão. Por exemplo, se você passar o mouse sobre o ID de diagnóstico 7025, verá a seguinte mensagem em uma dica de ferramenta:
  
Internal server error creating media for user.
  
É importante notar que o Relatório da lista de falhas não fornece uma maneira simples de recuperar diretamente uma lista de todos os usuários que participaram de pelo menos uma sessão com falha, nem fornece uma maneira de determinar quais usuários geralmente estavam envolvidos em uma sessão com falha. (Primeiro, o Failure List Report não terá nenhuma recursos de filtragem.) No entanto, se você exporta os dados e então o converta para um arquivo de valores separados por vírgulas, você pode usar o Windows PowerShell para encontrar as respostas a perguntas como essas. Por exemplo, suponha que você salve os dados em um arquivo .CSV chamado C:\Data\Failure_List.csv. Com base nos dados salvos nesse arquivo, esse comando lista os usuários que estavam envolvidos em pelo menos uma sessão com falha: 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Esse comando retornará uma lista semelhante a esta:
  
```
From user
----
Pilar.Ackerman@litwareinc.com
Henrik.Jensen@litwareinc.com
Gilead.Amosnino@litwareinc.com
David.Ahs@litwareinc.com
Ken.Myer@litwareinc.com
```

Esses dois comandos relatam o número total de sessões com falha em que cada usuário estava envolvido:
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Serão retornados dados semelhantes a estes:
  
```
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
```

## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Lista de Falhas.
  
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Lista de Falhas para cada chamada mal-sucedida.
  
**Métricas do relatório de lista de falha**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Hora de relatório** <br/> |Não  <br/> |Data e hora do registro do relatório.  <br/> |
|**Solicitação** <br/> |Não  <br/> |Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR ou ATÉ LOGO.  <br/> |
|**Código da resposta** <br/> |Não  <br/> |Código da resposta SIP enviado quando a conferência falhou.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.  <br/> |
|**Join cost time (ms)** <br/> |Não  <br/> |Tempo (em milissegundos) necessário para o usuário participar da conferência.  <br/> |
|**Usuário "De"** <br/> |Não  <br/> |Endereço SIP do usuário que iniciou a chamada.  <br/> |
|**Agente do usuário de origem** <br/> |Não  <br/> |Software usado pelo ponto de extremidade do usuário que iniciou a chamada.  <br/> |
|**Usuário "Para"** <br/> |Não  <br/> |Endereço SIP do usuário que estava recebendo a chamada.  <br/> |
   

