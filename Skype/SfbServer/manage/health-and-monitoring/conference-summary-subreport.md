---
title: Sub-relatório de Resumo de conferências no Skype for Business Server
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
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 'Resumo: Saiba mais sobre o sub-relatório de Resumo de conferências no Skype for Business Server.'
ms.openlocfilehash: 0d0b8fdc3971d60e326e59dd5417458533a10a31
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818061"
---
# <a name="conference-summary-subreport-in-skype-for-business-server"></a>Sub-relatório de Resumo de conferências no Skype for Business Server
 
**Resumo:** Saiba mais sobre o sub-relatório de Resumo de conferências no Skype for Business Server.
  
O Sub-relatório de Resumo de Conferências oferece uma visão geral de sessões de conferências com falha. Estas sessões com falha são detalhadas pelo tipo de sessão: sessões de Foco e sessões MCU.
  
## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou para exibir os dados retornados de formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Sub-relatório de Resumo de Conferências.
  
**Filtros do Sub-relatório de Resumo de Conferências**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Pool** <br/> |O FQDN (nome de domínio totalmente qualificado) do pool Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Todos]** para ver os dados de todos os pools. Essa lista suspensa é preenchida automaticamente com base nos registros no banco de dados.<br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Sub-relatório de Resumo de Conferências.
  
**Métricas do Sub-relatório de Resumo de Conferências**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Conferências totais** <br/> |Não  <br/> |Número total de conferências realizadas.  <br/> |
|**Total de sessões de conferência** <br/> |Não  <br/> |Número total de sessões de conferência. Uma única conferência pode ter várias sessões; por exemplo, uma conferência pode incluir uma sessão Foco e uma sessão MCU.  <br/> |
|**Taxa geral de falha de sessão** <br/> |Não  <br/> |Porcentagem de todas as conferências que falharam.  <br/> |
|**Sessões de Foco** <br/> |Não  <br/> |Número total de sessões de Foco.  <br/> |
|**Taxa de falha de Foco** <br/> |Não  <br/> |Porcentagem das sessões de Foco que falharam.  <br/> |
|Sessões MCU  <br/> |Não  <br/> |Número total de sessões MCU.  <br/> |
|**Taxa de falha de MCU** <br/> |Não  <br/> |Porcentagem de sessões MCU que falharam.  <br/> |
|**Sessões MCU por modalidade** <br/> |Não  <br/> |Número total de sessões MCU, agrupado por modalidade (por exemplo, conferência de IM).  <br/> |
|**Taxa de falha por modalidade** <br/> |Não  <br/> |Porcentagem de sessões MCU que falharam, agrupadas por modalidade (por exemplo, conferência de IM).  <br/> |
   

