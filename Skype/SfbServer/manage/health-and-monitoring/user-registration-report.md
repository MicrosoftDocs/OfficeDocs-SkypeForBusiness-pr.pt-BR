---
title: Relatório de Registro de Usuário no Skype for Business Server
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
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Resumo: saiba mais sobre o Relatório de Registro de Usuário no Skype for Business Server.'
ms.openlocfilehash: cb732bdd10c051b35f4f2b69413168fd6515f998
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816641"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Relatório de Registro de Usuário no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Registro de Usuário no Skype for Business Server.
  
O Relatório de Registro de Usuário fornece uma visão geral da atividade de logon do usuário, principalmente informações sobre o número de usuários que fez logon no Skype for Business Server durante um período de tempo especificado (por hora, diariamente, semanalmente, mensalmente). Lembre-se de que o relatório mostra apenas quantas pessoas fizeram logon. Ele não mostra quais pessoas fizeram logon. Os Relatórios de Monitoramento não fornecem informações sobre quais usuários específicos estão usando o Skype for Business Server (e quais não estão). No entanto, você pode obter uma estimativa aproximada de informações de usuário usando o Relatório de Atividades de Usuário.
  
Ao fornecer informações sobre logons de usuários, o Relatório de Registro de Usuário faz duas distinções importantes. Primeiro, ele desdobra os logons  em duas categorias primárias: logons internos e logons externos. Logons internos representam usuários que fizeram logon de dentro da firewall de sua organização (isto é, enquanto contectados à rede corporativa). Logons externos representam os usuários que se conectados de fora do firewall por meio de um Servidor de Borda (por exemplo, um usuário que fez logon em um internet café conta como um logon externo). Caso precise saber quantas de seus usuários estão fazendo logon de fora da firewall, o Relatório de Registro de Usuário pode fornecer essa informação a você.
  
Além disseo, o Relatório de Registro de Usuário indica quantos usuários ativos estavam presentes durante um dado período de tempo. Um usuário ativo é um usuário que participou de uma sessão de mensagens instantâneas (IM), participou de uma reunião do Skype for Business Server, fez ou recebeu uma chamada telefônica ou usou o Skype for Business Server durante esse período de tempo. Isso é diferente de um usuário que fez logon mas nunca realmente usou o sistema.
  
## <a name="accessing-the-user-registration-report"></a>Acessando o Relatório de Registro de Usuário

Você acessa o Relatório de Registro de Usuário apenas a partir da página inicial de Relatórios de Monitoramento. O Relatório de Registro de Usuário não leva a qualquer outro relatório.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Usando o Relatório de Registro de Usuário da melhor maneira possível

Depois de ter implantado o Skype for Business Server, uma pergunta comum é esta: como posso saber se meus usuários estão realmente usando essa nova tecnologia? Embora tenha algumas limitações neste sentido, o Relatório de Registro de Usuário pode ajudar você a responder esta pergunta. Para determinar se os usuários estão ou não usando o Skype for Business Server, você precisa fazer duas coisas. Primeiro, obtenha o valor da métrica de Usuários de logon exclusivos, do Relatório de Registro de Usuário. Esse valor informa quantos indivíduos distintos estão conectados ao Skype for Business Server.
  
Em comparação, a métrica Total de logons mostra quantas vezes no total alguém fez logon no Skype for Business Server. Por exemplo, suponha que Ken Myer tenha se conectado ao Skype for Business Server cinco vezes em um único dia. Nesse caso, Ken Myer contaria como cinco sessões de logon separadas para a métrica de Total de logons, mas como apenas um usuário de logon para a métrica de Usuários de logon exclusivos. Do mesmo modo, não é incomum que um usuário faça logon de vários dispositivos ou locais. Por exemplo, um usuário pode fazer logoff usando seu computador desktop, seu laptop e pode ter um telefone IP que faça logoff automaticamente no Skype for Business Server. Neste exemplo, existe um usuário exclusivo com três logons.
  
Para explicar de modo mais aprofundado a diferença entre total de logons e logons exclusivos, considere os logons para um dado período de tempo na tabela a seguir.
  
|**Usuário**|**Horário de logon**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 8:45  <br/> |
|Ken Myer  <br/> |7/7/2015 8:46  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 09:17  <br/> |
|Ken Myer  <br/> |7/7/2015 09:22  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 09:31  <br/> |
   
Observe que há um total de cinco logons; no entanto, existem apenas dois usuários de logon exclusivos: Ken Myer (que fez logon três vezes) e Pilar Ackerman (que fez logon duas vezes). Essa é a diferença entre logons e usuários de logon exclusivos.
  
Além de saber o número de logons exclusivos, você precisa saber o número total de usuários que foram habilitados para o Skype for Business Server. Esse valor pode ser recuperado abrindo o Shell de Gerenciamento do Skype for Business Server e executando o seguinte comando do Windows PowerShell:
  
```PowerShell
(Get-CsUser).Count
```

Se o comando anterior retornar um valor de 1.236 e a métrica de usuários de logon exclusivos retornar um valor médio de 667, isso sugere que um pouco mais da metade dos usuários habilitados para o Skype for Business estão realmente fazendo logon no sistema todos os dias (ou seja, 667 dividido por 1.236, que é aproximadamente 54%).
  
> [!CAUTION]
> Lembre-se de que as métricas de logon registram usuários que realmente fizeram logons durante o período de tempo especificado. Elas não rastreiam os usuários que já estão logados no sistema. Por exemplo, se a sua métrica de Usuários de logon exclusivos mostra 667 logons e você possui 1.236 usuários, isso sugere que quase a metade de seus usuários estão fazendo logon no sistema. No entanto, suponha que 300 usuários já estavam logados no sistema no momento em que você começou a verificar os dados de logon. Isso significa que você tinha quase 1.000 usuários conectados ao Skype for Business Server, o que significa que cerca de 80% dos usuários estavam conectados. 
  
Você também deve comparar o valor de Usuários de logon exclusivos com o valor da métrica de Usuários ativos exclusivos. A métrica Usuários ativos exclusivos informa quantos usuários exclusivos realmente usaram o Skype for Business Server: eles fizeram uma chamada telefônica, ingressaram em uma Reunião do Skype for Business Server ou participaram de uma sessão de IM. Essas informações são úteis, pois o Skype for Business Server pode ser configurado para ser iniciado automaticamente sempre que um usuário iniciar o Windows. Por isso, você pode ter um grande número de usuários que fazem logoff automaticamente no Skype for Business quando fazem logoff no Windows todos os dias, mas nunca usam o Skype for Business Server durante esse período.
  
A métrica Usuários ativos exclusivos também fornece dados mais significativos em uma organização em que os usuários normalmente não fazem logoff do Windows no final do dia. Em vez disso, eles simplesmente bloquearão seus computadores e deixarão o Windows e o Skype for Business em execução. Em uma situação assim, você pode acabar com poucos logons por dia, pois seus usuários fizeram logon vários dias atrás e nunca fizeram o logoff. No entanto, usuários ativos exclusivos informam se os usuários estão usando ativamente o Skype for Business ou outro cliente do Skype for Business Server.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Registro de Usuário permite exibir dados de todos os seus Pools de Registradores e Servidores de Borda ou exibir dados de um pool individual. Você também pode escolher como os dados devem ser agrupados. Nesse caso, registros agrupados por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode usar com o Relatório de registro do usuário.
  
**Filtros do Relatório de registro do usuário**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Por mês (um máximo de 12 meses pode ser exibido) <br/>  Se as datas de início e término excedem o número máximo de valores permitidos para o intervalo selecionado, apenas o número máximo de valores (começando pela data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/8/2015 12:00 a 7/9/2015 00:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN do pool do Registrador ou Servidor de Borda. Você pode tanto selecionar um pool individual ou escolher **[Todos]** para visualizar os dados de todos os pools. Essa lista suspensa é automaticamente preenchida por você com base nos registros no banco de dados. <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de registro do usuário. 
  
**Métrica do Relatório de registro do usuário**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**A cada hora** <br/> **Diariamente** <br/> **Semanalmente** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado na barra de ferramentas de filtro. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 7/7/2015, verá uma divisão por hora da atividade de registro do usuário para essa data.  <br/> |
|**Total de logons** <br/> |Não  <br/> |Número total de sessões de logon bem-sucedidas.  <br/> |
|**Logons internos** <br/> |Não  <br/> |Número total de logons dentro da rede interna.  <br/> |
|**Logons externos** <br/> |Não  <br/> |Número total logons de fora da rede interna, usando o Servidor de Borda.  <br/> |
|**Usuários de logon exclusivo** <br/> |Não  <br/> |Número total de usuário com ao menos uma sessão de logon. Um usuário com várias sessões de logon conta como um usuário, da mesma forma que uma pessoa que teve uma única sessão de logon.  <br/> |
|**Usuários ativos exclusivos** <br/> |Não  <br/> |Número total de usuários envolvidos em uma sessão ponto a ponto ou de conferência. Um usuário com várias sessões de logon conta como um usuário, da mesma forma que uma pessoa que teve uma única sessão.  <br/> |
   

