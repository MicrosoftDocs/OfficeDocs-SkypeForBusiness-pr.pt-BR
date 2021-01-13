---
title: Relatórios de Diagnóstico de Chamadas (por usuário) no Skype for Business Server
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
ms.assetid: 9da13470-001e-415f-b8c5-29b1f3b531ba
description: 'Resumo: saiba mais sobre os Relatórios de Diagnóstico de Chamadas por usuário usados no Skype for Business Server.'
ms.openlocfilehash: bcf59c63e98bb7c701b52fd6df564da16fd3761d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817091"
---
# <a name="call-diagnostic-reports-per-user-in-skype-for-business-server"></a>Relatórios de Diagnóstico de Chamadas (por usuário) no Skype for Business Server
  
Os Relatórios de Diagnóstico de Chamada oferecem informações por usuário sobre sessões ponta a ponta e de conferência. Neste momento, há apenas um relatório, o Relatório **de Atividades do Usuário.**

O Relatório de Atividades do Usuário fornece uma lista detalhada das sessões ponto a ponto e de conferência realizadas pelos usuários em um determinado período de tempo. Ao contrário de muitos dos Relatórios de Monitoramento, o Relatório de Atividades do Usuário vincula cada chamada a usuários individuais. Por exemplo, sessões ponto a ponto especificam os URIs SIP da pessoa que iniciou a chamada (o usuário De) e a pessoa que está sendo chamada (o usuário Para). Se você expandir as informações de uma conferência, verá uma lista de todos os participantes da conferência e a função que eles realizaram para essa conferência.

Às vezes, o Relatório de Atividades do Usuário é chamado de relatório de "help desk". Isso ocorre porque o relatório é frequentemente usado pela equipe de help desk para recuperar informações de sessão de um usuário específico. Você pode filtrar chamadas feitas ou feitas por um usuário individual simplesmente digitando o URI do SIP do usuário na caixa de prefixo de URI do usuário.

Se você fizer isso, o Relatório de Atividades do Usuário retornará informações para qualquer usuário cujo URI do SIP comece com a cadeia de caracteres especificada. Por exemplo, se você digitar **ken** na caixa URI, o Relatório de Atividades do Usuário localizará **Ken**. Myer@litwareinc.com. No entanto, ele também localizará esses usuários:

- **ken** azi@litwareinc.com

- **ken** burg@litwareinc.com

- **Ken**. Sanchez@litwareinc.com

- **Ken** nedy@litwareinc.com

Para garantir que apenas as informações de Ken Myer são retornadas, digite seu URI completo (Ken.Myer@litwareinc.com) na caixa de pesquisa ou pelo menos o tipo suficiente de URI de Ken para distingui-lo exclusivamente de outros usuários em sua organização. Por exemplo:

Ken.my

## <a name="to-access-the-user-activity-report"></a>Para acessar o relatório de atividades do usuário

O Relatório de Atividades do Usuário é acessado na página inicial dos Relatórios de Monitoramento. Você também pode acessar o Relatório de Atividades do Usuário clicando na métrica URI do Usuário no Relatório de Inventário de Telefones IP no [Skype for Business Server.](ip-phone-inventory-report.md) De dentro do Relatório de Atividades do Usuário, clicar no URI da Conferência (para uma conferência) leva você ao Relatório de Detalhes da Conferência. Da mesma forma, clicar na métrica Detalhe de uma chamada ponto a ponto leva você ao Relatório detalhado de sessão ponto a ponto no [Skype for Business Server.](peer-to-peer-session-detail-report.md)

## <a name="making-the-best-use-of-the-user-activity-report"></a>Fazendo o melhor uso do relatório de atividades do usuário

Embora haja muitas informações boas no Relatório de Atividades do Usuário, essas informações podem, às vezes, ser difíceis de localizar. Por exemplo, todas as atividades do usuário que ocorrem em sua organização durante um período especificado são incluídas no Relatório de Atividades do Usuário; Isso significa que, no relatório, há informações sobre quais usuários realmente usaram o Skype for Business Server de alguma forma.

> [!NOTE]
> Tecnicamente, é possível que algumas atividades do usuário não tenham sido registradas: enquanto o Skype for Business Server se esforça para manter informações sobre todas as chamadas telefônicas, é possível que uma chamada possa ter sido feita sem que as informações sobre essa chamada tenham sido gravadas no banco de dados. O Skype for Business Server foi projetado para dar uma aparência extremamente precisa, mas não necessariamente perfeita, de como o Skype for Business Server está sendo usado. (O fato de que não há garantia de que 100% de todas as chamadas sejam registradas explica por que o monitoramento do Skype for Business Server não deve ser usado como um sistema de cobrança.) Segundo, um Relatório de Monitoramento só pode exibir, no máximo, 1.000 registros. Dependendo da quantidade de atividade do usuário e do período com o que você está trabalhando, isso significa que sua consulta pode não retornar todos os dados realmente armazenados no banco de dados. 

- Quais usuários realmente usaram o sistema durante esse período de tempo?

- Quais dos meus usuários foram os mais ativos durante esse período?

- Os usuários que fazem a maioria das chamadas telefônicas também são os usuários que participam da maioria das sessões de mensagens instantâneas?

Se precisar responder a perguntas como esta, você pode exportar os dados recuperados pelos Relatórios de Monitoramento para uma planilha do Excel. Em seguida, use essa planilha e/ou um arquivo de valores separados por vírgula para analisar os dados de maneiras que o Relatório de Atividades do Usuário. Por exemplo, suponha que você tenha exportado os dados do relatório para o Excel e, em seguida, para um arquivo de valores separados por vírgulas. Nesse ponto, você pode importar os dados do . Arquivo CSV para o Windows PowerShell usando um comando semelhante a este:

```PowerShell
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Depois que os dados foram importados, você pode usar comandos simples do Windows PowerShell para ajudar a responder às suas perguntas. Por exemplo, este comando retorna uma lista de usuários exclusivos que serviram como "De usuário" em pelo menos uma sessão:

```PowerShell
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

Em outras palavras:

<pre>
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
</pre>

Este comando lista os usuários exclusivos (com base no número total de sessões em que participaram:

```PowerShell
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Ele retorna dados semelhantes a isto:

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

Este comando limita as sessões relatadas àqueles que incluíram áudio como modalidade:

```PowerShell
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Se você manter o mouse sobre qualquer ID de diagnóstico mostrada no relatório, uma dica de ferramenta será exibida descrevendo essa ID.

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Atividades do Usuário permite filtrar os dados retornados com base em informações como tipo de atividade (ou seja, sessões ponto a ponto ou sessões de conferência) ou pelo endereço SIP do usuário (permitindo que você ex veja as atividades de um usuário). Também é possível escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que você pode usar com o Relatório de Atividades do Usuário.

**Filtros do relatório de atividades do usuário**


| **Nome**   | **Descrição**  |
|:-----------|:--------|
| **De** <br/>             | Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 17/07/12015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/17/12015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/13/2015  <br/> As semanas são sempre de domingo a sábado.  <br/>                                                      |
| **To** <br/>               | Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 17/07/12015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/17/12015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/13/2015  <br/> As semanas são contadas de domingo até sábado.  <br/>                                                             |
| **Tipo de atividade** <br/>    | Tipo de atividade. Selecione um dos seguintes: <br/>  [Tudo] <br/>  Ponto a ponto <br/>  Conferência <br/>      |
| **Modalidade** <br/>         | A modalidade disponível varia dependendo do Tipo de Atividade selecionado. Se o Tipo de Atividade for Ponto a Ponto, você poderá selecionar IM; Transferência de arquivos; Compartilhamento de aplicativos; Voz; ou Vídeo como a modalidade.  <br/> Se o Tipo de Atividade for Conferência, você poderá selecionar conferência por telefone de IM; Webconferência; Compartilhamento de aplicativos; Conferência de voz/vídeo; ou conferência de telefonia.  <br/>         |
| **Categoria da sessão** <br/> | Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções: <br/>  [Tudo] <br/>  Sucesso <br/>  Falha esperada <br/>  Falha inesperada <br/>  Uma "falha esperada" é uma falha esperada; por exemplo, se um usuário definiu seu status como Não Incomodar, é esperado que qualquer chamada para esse usuário falhe. Uma "falha inesperada" ocorre em um sistema que parecia saudável. Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera. Se isso ocorrer, será sinalizado como uma falha inesperada. <br/> |
| **Prefixo URI do usuário** <br/>  | Endereço SIP do usuário. Para exibir registros somente para o usuário Ken Myer, você precisa inserir o endereço SIP de Ken Myer. Por exemplo:  <br/> sip:kenmyer@litwareinc.com  <br/>

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para sessões ponto a ponto (ou seja, sessões envolvendo apenas dois participantes).

**Métricas para sessões ponto a ponto**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Ver os detalhes** <br/> |Não  <br/> |Quando você clica nesse item, o relatório mostra o Relatório Detalhado de Sessão Ponto a Ponto para a sessão selecionada.  <br/> |
|**Do usuário** <br/> |Sim  <br/> |Endereço SIP do usuário que iniciou a sessão ponto a ponto.  <br/> |
|**Para usuário** <br/> |Sim  <br/> |Endereço SIP do usuário que ingressou na sessão ponto a ponto.  <br/> |
|**Modalidades** <br/> |Sim  <br/> |Tipo de comunicação usada na sessão. Por exemplo, IM, áudio ou transferência de arquivo.  <br/> |
|**Hora do convite** <br/> |Sim  <br/> |Data e hora em que o convite inicial para ingressar na sessão ponto a ponto foi enviado.  <br/> |
|**Hora da resposta** <br/> |Sim  <br/> |Data e hora em que o usuário "Para" aceitou o convite da sessão.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e hora em que a sessão ponto a ponto terminou.  <br/> |
|**ID do Diagnóstico** <br/> |Sim  <br/> |Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).

**Métricas para sessões de conferência**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**URI de conferência** <br/> |Sim  <br/> |Identificador exclusivo da conferência. Quando você clica nesse item, o relatório mostra o Relatório de Detalhes da Conferência para a sessão selecionada. Quando você expande esse item, o relatório mostra informações sobre os participantes da conferência. Para obter detalhes, consulte a seção "Métricas para participantes da conferência" posteriormente neste tópico.  <br/> |
|**Organizador** <br/> |Sim  <br/> |Endereço SIP do usuário que organizou a conferência.  <br/> |
|**Pool** <br/> |Sim  <br/> |Nome do Servidor de Borda (se for o caso) usado na conferência.  <br/> |
|**Hora de início** <br/> |Sim  <br/> |Data e hora de início da conferência.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e hora de encerramento da conferência.  <br/> |

## <a name="metrics-for-conference-participants"></a>Métricas para participantes da conferência

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para cada participante em uma conferência.

**Métricas para participantes da conferência**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Função** <br/> |Não  <br/> |Função de conferência (por exemplo, Apresentador) para o usuário.  <br/> |
|**Participante** <br/> |Não  <br/> |Endereço SIP do usuário.  <br/> |
|**Conectividade** <br/> |Não  <br/> |Tipo de conexão de rede. Por exemplo, "De Interno" para conexão interna ou "De PSTN" para usuários de discagem.  <br/> |
|**Hora de ingresso** <br/> |Não  <br/> |Data e hora em que o usuário ingressou na conferência.  <br/> |
|**Hora de saída** <br/> |Não  <br/> |Data e hora em que o usuário saiu da conferência.  <br/> |
|**ID de diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.  <br/> |

