---
title: Relatório de atividades do usuário no Skype for Business Server 25
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
description: 'Resumo: Saiba mais sobre o relatório de atividades do usuário no Skype for Business Server.'
ms.openlocfilehash: 0fdb7ab84748e971da7ef50c2b63651511ee38c8
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "41817610"
---
# <a name="user-activity-report-in-skype-for-business-server"></a>Relatório de atividades do usuário no Skype for Business Server

**Resumo:** Saiba mais sobre o relatório de atividades do usuário no Skype for Business Server.

O relatório de atividades do usuário fornece uma lista detalhada das sessões ponto a ponto e de conferência executadas pelos usuários em um determinado período de tempo. Ao contrário de muitos dos relatórios de monitoramento, o relatório de atividades do usuário vincula cada chamada a usuários individuais. Por exemplo, sessões ponto a ponto especificam os URIs SIP da pessoa que iniciou a chamada (o usuário de) e a pessoa que está sendo chamada (o para o usuário). Se você expandir as informações de uma conferência, verá uma lista de todos os participantes da conferência e a função que eles realizaram para a conferência.

O relatório de atividades do usuário às vezes é chamado de relatório "Help Desk". Isso ocorre porque o relatório é geralmente usado pela equipe de assistência técnica para recuperar informações de sessão de um usuário específico. Você pode filtrar por chamadas feitas ou feitas por um usuário individual simplesmente digitando o URI do SIP do usuário na caixa prefixo de URI do usuário.

Se você fizer isso, o relatório de atividades do usuário retornará informações para qualquer usuário cujo URI de SIP comece com a cadeia de caracteres especificada. Por exemplo, se você digitar **Ken** na caixa URI, o relatório de atividades do usuário localizará **Ken**. Myer@litwareinc.com. No entanto, ele também localizará estes usuários:

- **ken** Azi@litwareinc.com

- **ken** Burg@litwareinc.com

- **Ken**. Sanchez@litwareinc.com

- **Ken** Nedy@litwareinc.com

Para garantir que as informações somente para Ken Myer sejam retornadas, digite o URI completo (Ken.Myer@litwareinc.com) na caixa de pesquisa ou pelo menos o tipo de URI de Ken para distingui-lo exclusivamente de outros usuários em sua organização. Por exemplo:

Ken.my

## <a name="to-access-the-user-activity-report"></a>Para acessar o relatório de atividades do usuário

O relatório de atividades do usuário é acessado a partir da Home Page de relatórios de monitoramento. Você também pode acessar o relatório de atividades do usuário clicando na métrica URI do sistema de [telefonia IP no Skype for Business Server](ip-phone-inventory-report.md). No relatório de atividades do usuário, clicar no URI da conferência (para uma conferência) leva você para o relatório de detalhes da conferência. Da mesma forma, clicar na métrica de detalhes de uma chamada ponto a ponto leva você para o [relatório de detalhes de sessão ponto a ponto no Skype for Business Server](peer-to-peer-session-detail-report.md).

## <a name="making-the-best-use-of-the-user-activity-report"></a>Fazendo o melhor uso do relatório de atividades do usuário

Embora haja muitas informações boas no relatório de atividades do usuário, essas informações podem, às vezes, ser difíceis de localizar. Por exemplo, toda a atividade do usuário que ocorre na sua organização durante um período especificado é incluída no relatório de atividades do usuário; Isso significa que, em algum modo, os usuários realmente usaram o Skype for Business Server.

> [!NOTE]
> Tecnicamente, é possível que alguma atividade de usuário seja não gravada: enquanto o Skype for Business Server se esforça para manter as informações sobre todos os telefonemas, é possível que uma chamada tenha sido feita sem que as informações sobre a chamada sejam gravadas no banco de dados. O Skype for Business Server foi projetado para fornecer uma visão extremamente precisa, mas não necessariamente perfeita sobre como o Skype for Business Server está sendo usado. (O fato de não haver garantia de que 100% de todas as chamadas são registradas explica por que o monitoramento do Skype for Business Server não deve ser usado como um sistema de cobrança.) Em segundo lugar, um relatório de monitoramento só pode exibir, no máximo, 1.000 registros. Dependendo da quantidade de atividade do usuário que você tem e, dependendo do período de tempo com o qual você está trabalhando, isso significa que a consulta pode não retornar todos os dados realmente armazenados no banco de dados. 

- Quais usuários usaram realmente o sistema durante esse período de tempo?

- Quais dos meus usuários foram os mais ativos durante esse período de tempo?

- Os usuários que fazem a maioria das chamadas são também aqueles que participam da maioria das sessões de mensagens instantâneas?

Se você precisar responder a perguntas como esta, é possível exportar os dados recuperados pelos relatórios de monitoramento para uma planilha do Excel. Em seguida, você usa essa planilha e/ou um arquivo de valores separados por vírgulas para analisar os dados de forma que o relatório de atividades do usuário. Por exemplo, suponha que você tenha exportado os dados do relatório para o Excel e, em seguida, para um arquivo de valores separados por vírgulas. Nesse ponto, você pode importar os dados do. CSV para o Windows PowerShell usando um comando semelhante a este:

```PowerShell
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Depois que os dados forem importados, você poderá usar comandos simples do Windows PowerShell para ajudar a responder suas perguntas. Por exemplo, este comando retorna uma lista de usuários exclusivos que serviam como "de usuário" em pelo menos uma sessão:

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

Este comando lista os usuários exclusivos (com base no número total de sessões nas quais participaram:

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

Este comando limita as sessões relatadas àquelas que incluíram áudio como modalidade:

```PowerShell
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Se você mantiver o mouse sobre qualquer ID de diagnóstico mostrado no relatório, uma dica de ferramenta será exibida descrevendo essa ID.

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. Por exemplo, o relatório de atividades do usuário permite que você filtre os dados retornados com base em coisas como o tipo de atividade (ou seja, sessões ponto a ponto ou sessões de conferência) ou pelo endereço SIP do usuário (permitindo que você exiba as atividades de um usuário). Também é possível escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o relatório de atividades do usuário.

**Filtros de relatórios de atividades do usuário**


| **Nome**                   | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:---------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **De** <br/>             | Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/17/12015 1:00 PM  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/17/12015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/13/2015  <br/> As semanas são sempre de domingo a sábado.  <br/>                                                      |
| **To** <br/>               | Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/17/12015 1:00 PM  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/17/12015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/13/2015  <br/> As semanas são contadas de domingo até sábado.  <br/>                                                             |
| **Tipo de atividade** <br/>    | Tipo de atividade. Selecione um dos seguintes: <br/>  Todos os <br/>  Ponto a ponto <br/>  Conferência <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Modalidade** <br/>         | A modalidade disponível para você varia de acordo com o tipo de atividade SELECT. Se o tipo de atividade for ponto a ponto, você poderá selecionar IM; Transferência de arquivos; Compartilhamento de aplicativos; Voice ou vídeo como a modalidade.  <br/> Se o tipo de atividade for conferência, você poderá selecionar conferência telefônica de mensagens instantâneas; Conferência da Web; Compartilhamento de aplicativos; Conferência de voz/vídeo; ou conferência telefônica.  <br/>                                                                                                                                                                                                                                            |
| **Categoria da sessão** <br/> | Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções: <br/>  Todos os <br/>  Êxito <br/>  Falha esperada <br/>  Falha inesperada <br/>  Uma "falha esperada" é uma falha que espera acontecer; por exemplo, se um usuário tiver definido seu status como não incomodar, você esperaria que qualquer chamada para esse usuário falhe. Uma "falha inesperada" ocorre em um sistema que parecia saudável. Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera. Se isso ocorrer, será sinalizado como uma falha inesperada. <br/> |
| **Prefixo URI do usuário** <br/>  | Endereço SIP para o usuário. Para exibir registros apenas para o usuário Ken Myer, você precisa inserir o endereço SIP de Ken Myer. Por exemplo:  <br/> sip:kenmyer@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).

**Métricas para sessões ponto a ponto**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Ver os detalhes** <br/> |Não  <br/> |Quando você clica nesse item, o relatório mostra o relatório de detalhes de sessão ponto a ponto da sessão selecionada.  <br/> |
|**Do usuário ** <br/> |Sim  <br/> |Endereço SIP do usuário que iniciou a sessão ponto a ponto.  <br/> |
|**Para usuário** <br/> |Sim  <br/> |Endereço SIP do usuário que ingressou na sessão ponto a ponto.  <br/> |
|**Modalidades** <br/> |Sim  <br/> |Tipo de comunicação usada na sessão. Por exemplo, IM, áudio ou transferência de arquivo.  <br/> |
|**Hora do convite** <br/> |Sim  <br/> |Data e hora em que o convite inicial para entrar na sessão ponto a ponto foi enviado.  <br/> |
|**Hora da resposta** <br/> |Sim  <br/> |Data e hora em que o usuário "para" aceitou o convite da sessão.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e hora em que a sessão ponto a ponto terminou.  <br/> |
|**ID do Diagnóstico** <br/> |Sim  <br/> |Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).

**Métricas para sessões de conferência**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**URI de conferência** <br/> |Sim  <br/> |Identificador de conferência exclusivo. Quando você clica nesse item, o relatório mostra o relatório de detalhes da conferência da sessão selecionada. Quando você expande esse item, o relatório mostra informações sobre os participantes da conferência. Para obter detalhes, consulte a seção "métricas para participantes da conferência" mais adiante neste tópico.  <br/> |
|**Organizador** <br/> |Sim  <br/> |Endereço SIP do usuário que organizou a conferência.  <br/> |
|**Pool** <br/> |Sim  <br/> |Nome do servidor de borda (se houver) usado na conferência.  <br/> |
|**Hora de início** <br/> |Sim  <br/> |Data e hora em que a conferência começou.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e hora de encerramento da conferência.  <br/> |

## <a name="metrics-for-conference-participants"></a>Métricas para participantes da conferência

A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para cada participante de uma conferência.

**Métricas para participantes da conferência**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Função** <br/> |Não  <br/> |Função de conferência (por exemplo, apresentador) para o usuário.  <br/> |
|**Participante** <br/> |Não  <br/> |Endereço SIP do usuário.  <br/> |
|**Conectividade** <br/> |Não  <br/> |Tipo de conexão de rede. Por exemplo, "de interno" para conexão interna ou "de PSTN" para usuários de discagem.  <br/> |
|**Hora de ingresso** <br/> |Não  <br/> |Data e hora em que o usuário entrou na conferência.  <br/> |
|**Hora de saída** <br/> |Não  <br/> |Data e hora em que o usuário saiu da conferência.  <br/> |
|**ID de diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.  <br/> |


