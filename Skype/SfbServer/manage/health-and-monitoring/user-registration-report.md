---
title: Relatório de registro do usuário no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Resumo: Saiba mais sobre o relatório de registro de usuário no Skype para Business Server.'
ms.openlocfilehash: ba60e691a8f2c7c976fa1c8dbe79ee3668e9c81a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873440"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Relatório de registro do usuário no Skype para Business Server
 
**Resumo:** Saiba mais sobre o relatório de registro de usuário no Skype para Business Server.
  
O relatório de registro do usuário fornece uma visão geral da atividade de logon do usuário, principalmente informações sobre o número de usuários que tiverem feito logon Skype para Business Server durante um período de tempo especificado (por hora, diariamente, semanalmente, mensalmente). Lembre-se de que o relatório mostra apenas quantas pessoas fizeram logon. Ele não mostra quais pessoas fizeram logon. Relatórios de monitoramento não fornecem informações sobre quais usuários específicos estão usando Skype para Business Server (e quais não estão). No entanto, você pode obter uma estimativa aproximada de informações de usuário usando o Relatório de Atividades de Usuário.
  
Ao fornecer informações sobre logons de usuários, o Relatório de Registro de Usuário faz duas distinções importantes. Primeiro, ele desdobra os logons em duas categorias primárias: logons internos e logons externos. Logons internos representam usuários que fizeram logon de dentro do firewall de sua organização (isto é, enquanto estavam conectados à rede corporativa). Logons externos representam os usuários que tiverem feito logon de fora do firewall por meio de um servidor de borda (por exemplo, um usuário que fez logon a partir de um café contará como um logon externo da Internet). Caso precise saber quantos de seus usuários estão fazendo logon de fora do firewall, o Relatório de Registro de Usuário pode fornecer essa informação.
  
Além disso, o Relatório de Registro de Usuário indica quantos usuários ativos estavam presentes durante um dado período de tempo. Um usuário ativo é um usuário que participou de uma sessão (IM), de mensagens instantâneas participou um Skype para reunião de servidor de negócios, feitas recebeu uma chamada telefônica ou caso contrário usado Skype para Business Server durante esse período de tempo. Isso é diferente de um usuário que fez logon mas nunca usou o sistema de fato.
  
## <a name="accessing-the-user-registration-report"></a>Acessando o Relatório de Registro de Usuário

Você acessa o Relatório de Registro de Usuário apenas a partir da home page de Relatórios de Monitoramento. O Relatório de Registro de Usuário não vincula nenhum outro relatório.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Usando o Relatório de Registro de Usuário da melhor maneira possível

Depois que você implantou Skype para Business Server um frequentes pergunta é: como saber se meus usuários realmente estiver usando essa nova tecnologia? Embora tenha algumas limitações neste sentido, o Relatório de Registro de Usuário ajuda você a responder essa pergunta. Para determinar se ou não os usuários estiverem usando Skype para Business Server, você precisará fazer duas coisas. Primeiro, obtenha o valor da métrica de Usuários de logon exclusivos, do Relatório de Registro de Usuário. Este valor informa quantos indivíduos distintos conectados ao Skype para Business Server.
  
Por comparação, a métrica Total de logons mostra a quantidade total de vezes ninguém conectado ao Skype para Business Server. Por exemplo, suponhamos que Ken Myer conectado ao Skype para Business Server cinco vezes diferente em um único dia. Nesse caso, Ken Myer contaria como cinco sessões de logon separadas para a métrica de Total de logons, mas como apenas um usuário de logon para a métrica de Usuários de logon exclusivos. Do mesmo modo, não é incomum que um usuário faça logon de vários dispositivos ou locais. Por exemplo, um usuário pode fazer logon usando seu computador desktop, seu computador laptop, e ela pode ter um telefone IP que faz logon automaticamente para Skype para Business Server. Neste exemplo, temos um usuário exclusivo com três logons.
  
Para explicar de modo mais aprofundado a diferença entre total de logons e logons exclusivos, considere os logons em determinado período de tempo na tabela a seguir.
  
|**Usuário**|**Horário de logon**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 8:45  <br/> |
|Ken Myer  <br/> |7/7/2015 8:46  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 9:17  <br/> |
|Ken Myer  <br/> |7/7/2015 9:22  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 9:31  <br/> |
   
Observe que há um total de cinco logons; no entanto, há apenas dois usuários de logon exclusivo: Ken Myer (que fez logon três vezes) e Pilar Ackerman (que fez logon duas vezes). Essa é a diferença entre logons e usuários de logon exclusivos.
  
Além de saber o número de logons exclusivos, você precisa saber o número total de usuários que tiverem sido habilitados para Skype para Business Server. Esse valor pode ser recuperado abrindo o Skype do Shell de gerenciamento do servidor de negócios e executando o seguinte comando do Windows PowerShell:
  
```
(Get-CsUser).Count
```

Se o comando anterior retorna um valor de 1,236 e métrica de usuários de logon exclusivo retorna um valor médio de 667, que sugere que um pouco acima metade dos seus usuários habilite para Skype para negócios fazem realmente logon para o sistema de cada dia (ou seja 667 dividido por 1,236, que é aproximadamente 54%).
  
> [!CAUTION]
> Lembre-se de que as métricas de logon registram usuários que realmente fizeram logons durante o período de tempo especificado. Elas não rastreiam os usuários que já estão logados no sistema. Por exemplo, se a sua métrica de Usuários de logon exclusivos mostrar 667 logons e você tiver 1.236 usuários, isso sugere que metade de seus usuários estão fazendo logon no sistema. No entanto, suponhamos que 300 usuários já estavam logados no sistema no momento em que você começou a verificar os dados de logon. Que significaria que você realmente tinha quase 1.000 usuários conectados ao Skype para Business Server, o que significaria que quase 80% dos usuários conectados. 
  
Você também deve comparar o valor de Usuários de logon exclusivos com o valor da métrica de Usuários ativos exclusivos. A métrica de usuários ativos exclusivos informa quantos usuários únicos realmente usaram Skype para Business Server: eles feita uma chamada telefônica, eles ingressou um Skype para Business Server reunião ou participaram de uma sessão de mensagens Instantâneas. Isso é informações úteis, pois Skype para Business Server pode ser configurado para ser iniciado automaticamente sempre que um usuário inicia o Windows. Por isso, você pode ter um grande número de usuários que fazem logon automaticamente para Skype para negócios quando fizer logon no Windows por dia, mas nunca realmente usar Skype para Business Server durante esse período de tempo.
  
A métrica de usuários ativos exclusivos também fornece dados mais significativos em uma organização onde os usuários normalmente não fizer logoff do Windows no final do dia. Em vez disso, eles simplesmente bloquear seus computadores e deixe o Windows e Skype para continuidade dos negócios. Em uma situação assim, você pode acabar com poucos logons por dia, pois seus usuários fizeram logon vários dias atrás e nunca fizeram o logoff. No entanto, usuários ativos exclusivos informa se os usuários estão usando ativamente Skype para negócios ou outro Skype para cliente Business Server.
  
## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o relatório de registro do usuário permite exibir dados para todos os servidores de borda e seu pool de registradores ou exibir dados para um pool individual. Você também pode escolher como os dados devem ser agrupados. Nesse caso, registros agrupados por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode usar com o Relatório de registro do usuário.
  
**Filtros do Relatório de registro do usuário**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, apenas o número máximo de valores (começando pela data de início) será exibido. Por exemplo, se você selecionar o intervalo Por dia com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para o intervalo de 7/8/2015 00:00 a 7/9/2015 00:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do pool de Registradores Avançados ou Servidores de Borda. Você pode selecionar um pool individual ou escolher **[Todos]** para visualizar os dados de todos os pools. Essa lista suspensa é automaticamente preenchida com base nos registros no banco de dados. <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Registro de Usuário. 
  
**Métrica do Relatório de Registro de Usuário**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Por hora** <br/> **Diário** <br/> **Semanal** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado na barra de ferramentas de filtro. Quando aplicável, é possível clicar em determinado intervalo de tempo para exibir informações detalhadas sobre ele. Por exemplo, se você estiver usando o intervalo Por dia e clicar em 7/7/2015, verá um detalhamento por hora da atividade de registro do usuário para a data em questão.  <br/> |
|**Total de logons** <br/> |Não  <br/> |Número total de sessões de logon bem-sucedidas.  <br/> |
|**Logons internos** <br/> |Não  <br/> |Número total de logons dentro da rede interna.  <br/> |
|**Logons externos** <br/> |Não  <br/> |Número total logons de fora da rede interna, usando o Servidor de Borda.  <br/> |
|**Usuários de logon exclusivo** <br/> |Não  <br/> |Número total de usuário com ao menos uma sessão de logon. Um usuário com várias sessões de logon conta como um usuário, da mesma forma que uma pessoa que teve uma única sessão de logon.  <br/> |
|**Usuários ativos exclusivos** <br/> |Não  <br/> |Número total de usuários envolvidos em uma sessão ponto a ponto ou de conferência. Um usuário com várias sessões de logon conta como um usuário, da mesma forma que uma pessoa que teve uma única sessão.  <br/> |
   

