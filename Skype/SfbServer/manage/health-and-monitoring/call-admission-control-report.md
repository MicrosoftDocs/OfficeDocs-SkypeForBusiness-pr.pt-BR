---
title: Relatório de Controle de Admissão de Chamada Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: 'Resumo: saiba mais sobre os Relatórios de Controle de Admissão de Chamada usados Skype for Business Server.'
ms.openlocfilehash: 83259ed107113d5a013aa3a239ce9ef1eeab833b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754762"
---
# <a name="call-admission-control-report-in-skype-for-business-server"></a>Relatório de Controle de Admissão de Chamada Skype for Business Server
 
**Resumo:** Saiba mais sobre os Relatórios de Controle de Admissão de Chamada usados Skype for Business Server.
  
O Relatório de Controle de Admissão de Chamadas fornece informações sobre sessões de conferência e ponto a ponto que eram conduzidas sob restrições impostas pelo Controle de Admissão de Chamadas. O Controle de Admissão de Chamada fornece uma maneira para os administradores permitirem (ou não permitir) sessões de comunicação com base em restrições de largura de banda. Por exemplo, os administradores podem criar políticas que impõe um limite na quantidade de banda disponível para chamadas de voz e vídeo. Caso o limite de banda tenha sido alcançado, novas chamadas de voz ou vídeo não poderão ser feitas até que uma das chamadas atuais termine e libere os recursos de rede necessários.
  
## <a name="accessing-the-call-admission-control-report"></a>Acessando o Relatório de Controle de Admissão de Chamadas

O Relatório de Controle de Admissão de Chamadas é acessado através da página de Relatórios de Monitoramento. A partir do Relatório de Controle de Admissão de Chamadas você pode buscar mais detalhes em um dos seguintes relatórios:
  
- Relatório de Detalhes da Conferência - Para acessar este relatório, clique na métrica Detalhes de uma sessão de conferência. 
    
- Relatório de Detalhes de Sessão Ponto a Ponto - Para acessar este relatório, clique na métrica Detalhes de uma sessão ponto a ponto.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Usando o Relatório de Controle de Admissão de Chamadas da melhor maneira possível

Para obter uma lista de chamadas que falharam por causa de largura de banda insuficiente, selecione Chamadas rejeitadas por causa do controle de admisssão de chamadas, na lista suspensa de categoria de Chamadas. A maioria das chamadas retornadas provavelmente terão a ID de diagnóstico 5:
  
Largura de banda insuficiente para estabelecer sessão. Tente reencaminhamento PSTN.
  
Isso indica que as limitações do Controle de Admissão de Chamadas estavam impedidndo a chamada de ser feita na rede VoIP.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Controle de Admissão de Chamada permite que você filtre as chamadas de acordo com o usuário que iniciou a chamada ou com o usuário que está sendo chamado. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Controle de Admissão de Chamada.
  
**Filtros do Relatório de Controle de Admissão de Chamadas**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 17/07/12015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/17/12015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/13/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 17/07/12015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/17/12015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/13/2015  <br/> As semanas sempre correm do domingo até sábado.  <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Tudo]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Tipo de atividade** <br/> | Tipo de atividade. Selecione uma das seguintes atividades: <br/>  [Todos] <br/>  Ponto a ponto <br/>  Conferência <br/> |
|**Categoria da chamada** <br/> | Indica o motivo de o CAC ter sido usado para a chamada. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Chamada rejeitada devido ao controle de admissão de chamada <br/>  Chamadas reencaminhadas por PSTN devido ao controle de admissão de chamada <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).
  
**Métricas para sessões ponto a ponto**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Ver os detalhes** <br/> |Não  <br/> |Quando você clica nesse item, o relatório mostra o Relatório de Detalhes da Sessão Ponto a Ponto para a sessão especificada.  <br/> |
|**Do usuário** <br/> |Sim  <br/> |Endereço SIP do usuário que iniciou a sessão.  <br/> |
|**Para usuário** <br/> |Sim  <br/> |Endereço SIP do usuário convidado para ingressar na sessão.  <br/> |
|**Modalidades** <br/> |Sim  <br/> |Modalidades de comunicação (como áudio e vídeo) usadas durante a sessão.  <br/> |
|**Hora do convite** <br/> |Sim  <br/> |Data e hora de envio do convite inicial da sessão para o usuário De.  <br/> |
|**Hora da resposta** <br/> |Sim  <br/> |Data e hora de recebimento da aceitação do convite.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e hora de encerramento da sessão.  <br/> |
|**ID do Diagnóstico** <br/> |Sim  <br/> |Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para sessões de conferência (ou seja, sessões que envolvem três ou mais participantes).
  
**Métricas para sessões de conferência**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**URI de conferência** <br/> |Sim  <br/> |Identificador exclusivo para a conferência. Quando você clica nesse item, o relatório mostra os participantes individuais da conferência.  <br/> |
|**Organizador** <br/> |Sim  <br/> |Endereço SIP do usuário que organizou a conferência.  <br/> |
|**Pool** <br/> |Sim  <br/> |Servidor de Borda usado na conferência.  <br/> |
|**Hora de início** <br/> |Sim  <br/> |Data e hora de início da sessão.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e hora de encerramento da conferência.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Métricas para participantes individuais de conferência

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para participantes individuais da conferência.
  
**Métricas para participantes individuais de conferência**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Função** <br/> |Não  <br/> |Função (por exemplo, Apresentador) desempenhada pelo participante da conferência.  <br/> |
|**Participante** <br/> |Não  <br/> |Endereço SIP do participante de conferência.  <br/> |
|**Conectividade** <br/> |Não  <br/> |Conectividade de rede (normalmente Interna ou Externa) para o participante.  <br/> |
|**Modalidade** <br/> |Não  <br/> |Tipo de conferência (por exemplo, conferência A/V).  <br/> |
|**Hora de ingresso** <br/> |Não  <br/> |Data e hora de ingresso do participante na conferência.  <br/> |
|**Hora de saída** <br/> |Não  <br/> |Data e hora de saída do participante da conferência.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.  <br/> |
   

