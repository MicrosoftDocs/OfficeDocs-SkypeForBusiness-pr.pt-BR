---
title: Relatório de distribuição de falha no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: 'Resumo: Saiba mais sobre o relatório de distribuição de falha no Skype for Business Server.'
ms.openlocfilehash: d9e7d2ac0ff10743c69bee665be3878ac9009933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305693"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a>Relatório de distribuição de falha no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de distribuição de falha no Skype for Business Server.
  
O Relatório de Distribuição de Falhas classifica sessões com falha nas seguintes categorias:
  
- Principais motivos diagnósticos
    
- Principais modalidades
    
- Principais pools
    
- Principais fontes
    
- Principais componentes
    
- Principais usuários "De"
    
- Principais usuários "Para"
    
- Principais agentes do usuário "De"
    
É possível usar essas categorias para determinar exatamente onde está ocorrendo um problema e, em alguns casos, porque o problema está ocorrendo. Por exemplo, suponha que você tenha registrado 242 sessões de áudio/vídeo com falha durante um determinado dia. Se você observar o Relatório de Distribuição de Falhas, ele poderá mostrar que 237 das sessões com falha ocorreram no pool de Dublin. Isso fornece um ótimo ponto inicial para rastrear e diagnosticar as causas por trás dessas falhas. Se você clicar no pool de Dublin na categoria **Principais pools**, você verá um Relatório de Distribuição de Falhas exclusivo desse pool. Será possível então começar a analisar por que o pool de Dublin enfrentou tantas dificuldades.
  
## <a name="viewing-the-failure-distribution-report"></a>Exibindo o Relatório de Distribuição de Falhas

É possível acessar o Relatório de Distribuição de Falhas a partir de qualquer um dos seguintes relatórios clicando nas medidas **Volume de falhas esperado** ou **Volume de falhas não esperado**:
  
- [Relatório de falhas principais no Skype for Business Server](top-failures-report.md)
    
- [Relatório de diagnóstico de conferência no Skype for Business Server](conference-diagnostic-report.md)
    
- [Relatório de diagnóstico de atividade ponto a ponto no Skype for Business Server](peer-to-peer-activity-diagnostic-report.md)
    
No relatório de distribuição de falha, você pode clicar em qualquer uma das seguintes métricas para exibir o [relatório de lista de falhas no Skype for Business Server](failure-list-report.md):
  
- Principais motivos diagnósticos (sessões)
    
- Principais modalidades (sessões)
    
- Principais pools (sessões)
    
- Principais fontes (sessões)
    
- Principais componentes (sessões)
    
- Principais usuários "De" (sessões)
    
- Principais usuários "Para" (sessões)
    
- Principais agentes do usuários "De" (sessões)
    
## <a name="using-the-failure-distribution-report"></a>Usando o Relatório de Distribuição de Falhas

Dependendo do tamanho de seu monitor e da resolução da tela, é possível que alguns dos dados apresentados no Relatório de Distribuição de Falhas sejam truncados que exibidos na tela. Por exemplo, um agente de usuário com o nome "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" poderá aparecer apenas parcialmente na tela: 
  
UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...
  
Felizmente, é possível ver o nome completo mantendo o mouse sobre o valor truncado.
  
Um medida interessante que pode ser filtrada usando o Relatório de Distribuição de Falhas é o ID do diagnóstico. Se vir o mesmo ID do diagnóstico surgir em outros relatórios, será possível filtrar esse ID no Relatório de Distribuição de Falhas e obter uma visão bastante detalhada de exatamente onde e com que frequência esse ID foi reportado durante uma sessão com falha.
  
## <a name="filters"></a>Filtros

O filtro é uma maneira de retornar um conjunto de dados mais refinado e direcionado, ou ver os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Falha na Distribuição permite filtrar itens como tipo de atividade (sessão ponto a ponto ou de conferência) ou pelo ID diagnóstico que acompanha cada sessão com falha.
  
A tabela a seguir lista os filtros que você pode usar com o Relatório de Falha na Distribuição.
  
**Filtros do Relatório de Falha na Distribuição**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do Pool de registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Todos]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Tipo de atividade** <br/> | Tipo de atividade para filtrar. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Ponto a ponto <br/>  Conferência <br/> |
|**Categoria da sessão** <br/> | Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Sucesso <br/>  Falha esperada <br/>  Falha inesperada <br/>  Uma "falha esperada" é aquela que se espera que ocorra. Por exemplo, se um usuário tiver definido seu status como Não incomodar, é esperado que toda chamada encaminhada para esse usuário falhe. "Falha inesperada" é uma falha que ocorre em um sistema que parece estar em bom estado.Por exemplo, uma chamada não deve ser finalizada se o chamador é colocado em espera. Se isso ocorrer, a situação será sinalizada como falha inesperada. <br/> |
|**ID do Diagnóstico** <br/> |Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a>Métricas para os principais motivos diagnósticos

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no ID diagnóstico relatado com mais frequência.
  
**Métricas para os principais motivos diagnósticos**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Classificação** <br/> |Não  <br/> |Classificação relativa das sessões com falha, com base no ID diagnóstico, que é um identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.  <br/> |
|**Principais motivos diagnósticos** <br/> |Não  <br/> |ID diagnóstico gerado em uma sessão.  <br/> |
|**Sessões** <br/> |Não  <br/> |Número total de sessões com falha em que ID diagnóstico especificado foi gerado.  <br/> |
   
## <a name="metrics-for-top-modalities"></a>Métricas para as principais modalidades

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nas modalidades de sessão que apresentaram mais falhas.
  
**Métricas para as principais modalidades**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Classificação** <br/> |Não  <br/> |Classificação relativa com base na sessão com falha baseada no tipo de sessão (por exemplo, conferência de áudio/vídeo ou sessão de transferência de arquivo ponto a ponto).  <br/> |
|**Principais modalidades** <br/> |Não  <br/> |Tipo de sessão.  <br/> |
|**Sessões** <br/> |Não  <br/> |Número total de sessões com falha envolvendo a modalidade especificada.  <br/> |
   
## <a name="metrics-for-top-pools"></a>Métricas para os principais pools

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos pools que apresentaram mais falhas.
  
**Métricas para os principais pools**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Classificação** <br/> |Não  <br/> |Classificação relativa de sessões com falha com base no pool de registradores ou no servidor de borda em que a sessão foi conduzida.  <br/> |
|**Principais pools** <br/> |Não  <br/> |Nome do pool de registradores ou servidor de borda.  <br/> |
|**Sessões** <br/> |Não  <br/> |Número total de sessões com falha por pool de registradores ou servidor de borda.  <br/> |
   
## <a name="metrics-for-top-sources"></a>Métricas para as principais fontes

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos computadores que apresentaram mais falhas.
  
**Métricas para as principais fontes**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Classificação** <br/> |Não  <br/> |Classificação relativa das sessões com falha por computador.  <br/> |
|**Principais fontes** <br/> |Não  <br/> |Nome do computador envolvido na sessão com falha.  <br/> |
|**Sessões** <br/> |Não  <br/> |Número total de sessões com falha por computador.  <br/> |
   
## <a name="metrics-for-top-components"></a>Métricas para os principais componentes

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos componentes do que apresentaram mais falhas.
  
**Métricas para os principais componentes**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Classificação** <br/> |Não  <br/> |Classificação relativa de sessões com falha com base no componente (por exemplo, ExumRouting, GroupChat ou MediationServer).  <br/> |
|**Principais componentes** <br/> |Não  <br/> |Nome do componente envolvido na sessão com falha.  <br/> |
|**Sessões** <br/> |Não  <br/> |Número total de sessões com falha por componente.  <br/> |
   
## <a name="metrics-for-top-from-users"></a>Métricas para os principais usuários "Para"

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando tentaram chamar alguém (conhecidos como usuários "De").
  
**Métricas para os principais usuários "Para"**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Classificação** <br/> |Não  <br/> |Classificação relativa das sessões com falha, com base no usuário convidado a entrar na sessão.  <br/> |
|**Principais usuários "De"** <br/> |Não  <br/> |Endereço SIP do usuário convidado para entrar na sessão.  <br/> |
|**Sessões** <br/> |Não  <br/> |Número total de sessões com falha por usuário.  <br/> |
   
## <a name="metrics-for-top-to-users"></a>Métricas para os principais usuários

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando o outro usuário tentou chamá-los (conhecidos como usuários "Para").
  
|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Classificação** <br/> |Não  <br/> |Classificação relativa das sessões com falha, com base no usuário que iniciou a sessão.  <br/> |
|**Principais usuários "Para"** <br/> |Não  <br/> |Endereço SIP do usuário que iniciou a sessão.  <br/> |
|**Sessões** <br/> |Não  <br/> |Número total de sessões com falha por usuário.  <br/> |
   
## <a name="metrics-for-top-user-agents"></a>Métricas para os principais agentes do usuário

A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no software de ponto de extremidade que apresentou mais falhas.
  
**Métricas para os principais agentes do usuário**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Classificação** <br/> |Não  <br/> |Classificação relativa de sessões com falha, com base no agente do usuário (software) envolvido na sessão. Por exemplo: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.  <br/> |
|**Principais agentes do usuário** <br/> |Não  <br/> |Nome do agente do usuário envolvido na sessão com falha.  <br/> |
|**Sessões** <br/> |Não  <br/> |Número total de sessões com falha por agente do usuário.  <br/> |
   

