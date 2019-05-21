---
title: Relatório de atividade do usuário no Skype for Business Server 25
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
description: 'Resumo: Saiba mais sobre o relatório de atividades do usuário no Skype for Business Server.'
ms.openlocfilehash: b9dabdec0bf038ff7068e9bba40543cbd02d183e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279673"
---
# <a name="user-activity-report-in-skype-for-business-server"></a>Relatório de atividade do usuário no Skype for Business Server

**Resumo:** Saiba mais sobre o relatório atividade do usuário no Skype for Business Server.

O Relatório de Atividades do Usuário oferece uma lista detalhada das sessões ponto a ponto e de conferência realizadas pelos usuários em um determinado período. Diferente de muitos dos Relatórios de Monitoramento, o Relatório de Atividades do Usuário vincula cada chamada a usuários individuais. Por exemplo, as sessões ponto a ponto especificam URIs do SIP da pessoa que iniciou a chamada (o usuário de origem) e a pessoa que está sendo chamada (o usuário de destino). Se as informações forem ampliadas para uma conferência, será possível ver uma lista de todos os participantes da conferência e a função que desempenham na conferência.

O Relatório de Atividades do Usuário é referenciado algumas vezes como o relatório do "suporte técnico". Isso se deve ao fato de o relatório ser sempre usado pela equipe do suporte técnico para recuperar informações sobre a sessão para um usuário específico. É possível filtrar chamadas feitas para ou por um usuário individual simplesmente digitando o URI do SIP do usuário na caixa URI do usuário.

Se você fizer isso, o relatório de atividade do usuário retornará informações para qualquer usuário cujo URI SIP comece com a cadeia de caracteres especificada. Por exemplo, se você digitar **ken** na caixa URI, o Relatório de Atividades do usuário localizará **Ken**.Myer@litwareinc.com. No entanto, ele localizará também esses usuários:

- **ken** Azi@litwareinc.com

- **ken** Burg@litwareinc.com

- **Ken**.Sanchez@litwareinc.com

- **Ken** Nedy@litwareinc.com

Para garantir que somente as informações de Ken Myer sejam retornadas, digite o URI (Ken.Myer@litwareinc.com) completo na caixa de pesquisa ou pelo menos o tipo de URI de Ken para distingui-lo exclusivamente de outros usuários da sua organização. Por exemplo:

Ken.my

## <a name="to-access-the-user-activity-report"></a>Para acessar o Relatório de Atividades do Usuário

O Relatório de Atividades do Usuário é acessado pela home page dos Relatórios de Monitoramento. Você também pode acessar o relatório de atividade do usuário clicando na métrica de URI de usuário no [relatório de inventário de IP Phone no Skype for Business Server](ip-phone-inventory-report.md). No Relatório de Atividades do Usuário, ao clicar em URI da Conferência (para uma conferência), você será levado para o Relatório Detalhado de Conferências. Da mesma forma, clicar na métrica de detalhes de uma chamada ponto a ponto leva você ao [relatório de detalhes de sessão ponto a ponto no Skype for Business Server](peer-to-peer-session-detail-report.md).

## <a name="making-the-best-use-of-the-user-activity-report"></a>Fazendo o melhor uso do relatório de atividades do usuário

Embora haja muitas informações relevantes no Relatório de Atividades do Usuário, essas informações podem, por vezes, ser difíceis de localizar. Por exemplo, todas as atividades do usuário que ocorrem em sua organização durante um período especificado são incluídas no relatório de atividades do usuário; Isso significa que, em um relatório, a informação sobre a qual os usuários realmente usaram o Skype for Business Server está a caminho.

> [!NOTE]
> Tecnicamente, é possível que algumas atividades do usuário possam estar desgravadas: enquanto o Skype for Business Server se empenha para manter as informações sobre todas as chamadas telefônicas, é possível que uma chamada tenha sido feita sem as informações sobre essa chamada sendo gravada na base. O Skype for Business Server foi projetado para fornecer uma visão extremamente precisa, mas não necessariamente perfeita sobre como o Skype for Business Server está sendo usado. (O fato não há nenhuma garantia de que 100% de todas as chamadas sejam registradas explica porque o monitoramento do Skype for Business Server não deve ser usado como um sistema de cobrança.) Segundo, um relatório de monitoramento só pode exibir, no máximo, 1.000 registros. Dependendo da quantidade de usuários que você tem e também de período com o qual está trabalhado, isso significa que sua consulta pode não retornar todos os dados realmente armazenados no banco de dados. 

- Quais usuários usaram realmente o sistema durante este período?

- Quais dentre meus usuários foram os mais ativos durante este período?

- Os usuários que fazem a maioria das chamadas são também aqueles que participam da maioria das sessões de mensagens instantâneas?

Se precisar responder a essas perguntas, será possível exportar os dados recuperados pelos Relatórios de Monitoramento para uma planilha do Excel. Utilize essa planilha e/ou um arquivo de valores separados por vírgulas para analisar os dados como faz o Relatório de Atividades do Usuário. Por exemplo, suponha que os dados do relatório tenham sido exportados para o Excel e depois para um arquivo de valores separados por vírgulas. Nesse ponto, você pode importar os dados do. CSV para o Windows PowerShell usando um comando semelhante a este:

```
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Depois que os dados forem importados, você poderá usar comandos simples do Windows PowerShell para ajudar a responder suas perguntas. Por exemplo, este comando retorna uma lista de usuários exclusivos que atuaram como "usuário de origem" em pelo menos uma sessão:

```
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

Este comando lista os usuários exclusivos (com base no número total de sessões das quais participaram:

```
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Este retorna dados semelhantes a estes:

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

Este comando limita as sessões reportadas àquelas que incluíram áudio como modalidade:

```
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Se você pousar o mouse sobre qualquer ID do diagnóstico mostrado no relatório, uma dica de ferramenta será exibida descrevendo o ID.

## <a name="filters"></a>Filtros

O filtro é uma maneira de retornar um conjunto de dados mais refinado e direcionado, ou ver os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Atividades do Usuário permite filtrar os dados retornados com base em itens como tipo de atividade (isto é, sessão ponto a ponto ou de conferência) ou pelo endereço SIP do usuário (permitindo exibir as atividades para um usuário). Você também pode escolher como os dados serão agrupados; neste caso, os usos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que você pode usar com o Relatório de Atividades do Usuário.

**Filtros do relatório de atividades do usuário**


| **Nome**                   | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:---------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **De** <br/>             | Data/hora de início do intervalo de tempo. Para ver os dados por horas, insira a data e hora de início desta forma:  <br/> 17/7/12015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 17/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 13/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/>                                                      |
| **Até** <br/>               | Data/hora de término do intervalo de tempo. Para ver os dados por horas, insira a data e hora de término desta forma:  <br/> 17/7/12015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 17/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 13/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/>                                                             |
| **Tipo de atividade** <br/>    | Tipo de atividade. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Ponto a ponto <br/>  Conferência <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Modalidade** <br/>         | A Modalidade disponível para você varia de acordo com o Tipo de Atividade selecionado. Se o tipo de atividade for ponto a ponto, você poderá selecionar mensagens instantâneas; Transferência de arquivos; Compartilhamento de aplicativos; Voz ou vídeo como a modalidade.  <br/> Se o Tipo de Atividade for Conferência, você poderá selecionar conferência Telefônica de Mensagem Instantânea; conferência da Web; Compartilhamento de Aplicativos; conferência de Voz/Vídeo; ou conferência Telefônica.  <br/>                                                                                                                                                                                                                                            |
| **Categoria da sessão** <br/> | Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Sucesso <br/>  Falha esperada <br/>  Falha inesperada <br/>  Uma "falha esperada" é uma falha prevista; por exemplo, se um usuário configurou seu status para Não Perturbe, é previsto que qualquer chamada para ele irá falhar. Uma "falha inesperada" ocorre em um sistema que parecia saudável. Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera. Se isso ocorrer, será sinalizado como uma falha inesperada. <br/> |
| **Prefixo de URI do usuário** <br/>  | Endereço SIP para o usuário. Para exibir registros somente para o usuário Ken Myer, digite o endereço SIP de Ken Myer. Por exemplo:  <br/> sip:kenmyer@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para a sessões ponto a ponto (isto é, as que envolvem apenas dois participantes).

**Métricas para sessões ponto a ponto**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Detalhe** <br/> |Não  <br/> |Quando você clica neste item, é mostrado o Relatório de Detalhes de Sessão Ponto a Ponto para a sessão selecionada.  <br/> |
|**Usuário "De"** <br/> |Sim  <br/> |Endereço SIP do usuário que iniciou a sessão ponto a ponto.  <br/> |
|**Usuário "Para"** <br/> |Sim  <br/> |Endereço SIP do usuário que entrou na sessão ponto a ponto.  <br/> |
|**Modalidades** <br/> |Sim  <br/> |Tipo de comunicação usado na sessão. Por exemplo, IM, áudio ou transferência de arquivo.  <br/> |
|**Hora do convite** <br/> |Sim  <br/> |Data e hora em que o convite inicial para entrar na sessão ponto a ponto foi enviado.  <br/> |
|**Hora da resposta** <br/> |Sim  <br/> |Data e hora em que o usuário "Para" aceitou o convite para a sessão.  <br/> |
|**Hora final** <br/> |Sim  <br/> |Data e hora em que a sessão ponto a ponto terminou.  <br/> |
|**ID do Diagnóstico** <br/> |Sim  <br/> |Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para resolução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não os incluem), e as IDs de diagnóstico são relatadas somente em sessões com algum tipo de problema.  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para a sessões de conferência (isto é, as que envolvem três ou mais participantes).

**Métricas para sessões de conferência**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**URI de conferência** <br/> |Sim  <br/> |Identificador exclusivo da conferência. Quando você clica neste item, é mostrado o Relatório de Detalhes da Conferência para a sessão selecionada. Quando você expande esse item, o relatório mostra as informações sobre os participantes. Para obter os detalhes, consulte "Métricas para participantes da conferência", mais adiante neste tópico.  <br/> |
|**Organizador** <br/> |Sim  <br/> |Endereço SIP do usuário que organizou a conferência.  <br/> |
|**Pool** <br/> |Sim  <br/> |Nome do Servidor de Borda (se houver) usado na conferência.  <br/> |
|**Hora inicial** <br/> |Sim  <br/> |Data e hora em que a conferência começou.  <br/> |
|**Hora final** <br/> |Sim  <br/> |Data e hora em que a conferência terminou.  <br/> |

## <a name="metrics-for-conference-participants"></a>Métricas para participantes da conferência

A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para cada participante de uma conferência.

**Métricas para participantes da conferência**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Função** <br/> |Não  <br/> |Função do usuário na conferência (por exemplo, Apresentador).  <br/> |
|**Participante** <br/> |Não  <br/> |Endereço SIP do usuário.  <br/> |
|**Conectividade** <br/> |Não  <br/> |Tipo de conexão da rede. Por exemplo, "De Interno" para conexão interna ou "De PSTN" os usuários discados.  <br/> |
|**Hora da ingresso** <br/> |Não  <br/> |Data e hora em que o usuário entrou na conferência.  <br/> |
|**Hora da saída** <br/> |Não  <br/> |Data e hora em que o usuário saiu da conferência.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.  <br/> |


