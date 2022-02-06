---
title: Sub-relatório de resumo de conferência no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 'Resumo: Saiba mais sobre o Sub-relatório resumo da conferência Skype for Business Server.'
---

# <a name="conference-summary-subreport-in-skype-for-business-server"></a>Sub-relatório de resumo de conferência no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Sub-relatório resumo da conferência Skype for Business Server.
  
O Subrelatório de Resumo da Conferência oferece uma visão geral das sessões de conferência em falha. Estas sessões em falha são detalhadas pelo tipo de sessão: Sessão de foco e sessões MCU.
  
## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou para exibir os dados retornados de formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Subrelatório de Resumo da Conferência.
  
**Filtros do Subrelatório de Resumo da Conferência**

|**Name**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas sempre correm do domingo até sábado.  <br/> |
|**Pool** <br/> |FQDN do pool do Registrador ou Servidor de Borda. É possível selecionar um pool individual ou clicar em **[Todos]** para exibir os dados de todos os pools. Esta lista suspensa é preenchida automaticamente para você com base nos registros do banco de dados.<br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Subrelatório de Resumo de Conferência.
  
**Métricas do Subrelatório de Resumo da Conferência**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Total de conferências** <br/> |Não  <br/> |Número total de conferências realizadas.  <br/> |
|**Total de sessões de conferência** <br/> |Não  <br/> |Número total de sessões de conferência. Uma única conferência pode ter várias sessões; por exemplo, uma conferência pode incluir uma sessão Foco e uma sessão MCU.  <br/> |
|**Taxa de falha de sessão geral** <br/> |Não  <br/> |Porcentagem de todas as conferências que falharam.  <br/> |
|**Sessões de foco** <br/> |Não  <br/> |Número total de sessões de Foco.  <br/> |
|**Taxa de falha do foco** <br/> |Não  <br/> |Porcentagem das sessões de Foco que falharam.  <br/> |
|Sessões MCU  <br/> |Não  <br/> |Número total de sessões MCU.  <br/> |
|**Taxa de falha MCU** <br/> |Não  <br/> |Porcentagem de sessões MCU que falharam.  <br/> |
|**Sessões MCU por modalidade** <br/> |Não  <br/> |Número total de sessões MCU, agrupado por modalidade (por exemplo, conferência IM).  <br/> |
|**Taxa de falha por modalidade** <br/> |Não  <br/> |Porcentagem de sessões MCU que falharam, agrupadas por modalidade (por exemplo, conferência de IM).  <br/> |
   

