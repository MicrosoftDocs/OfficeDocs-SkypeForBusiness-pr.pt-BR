---
title: Relatório de IM ponto a ponto no Skype for Business Server
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
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 'Resumo: Saiba mais sobre o relatório de IM ponto a ponto no Skype for Business Server.'
ms.openlocfilehash: 7775e7dc4a6fc3cd36283decd12971ac0e0f780a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817911"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Relatório de IM ponto a ponto no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de IM ponto a ponto no Skype for Business Server.
  
O Relatório de Mensagens Instantâneas Ponto a Ponto fornece informações de tendência sobre sessões de IM (mensagens instantâneas) ponto a ponto, detalhadas por pool e tipo de autenticação. O relatório pode mostrar o número total de sessões que aconteceram durante o período de tempo especificado (por exemplo, dia por dia ou hora por hora), ou pode mostrar o número total de mensagens instantâneas enviadas durante esse período de tempo.
  
## <a name="accessing-the-peer-to-peer-im-report"></a>Acessando o Relatório de Mensagens Instantâneas Ponto a Ponto

Você pode acessar o relatório de mensagens instantâneas ponto a ponto apenas abrindo o [relatório de Resumo de atividades ponto a ponto no Skype for Business Server](peer-to-peer-activity-summary-report.md) e clicando em uma das seguintes métricas:
  
- Total de sessões de mensagens instantâneas ponto a ponto
    
- Total de mensagens instantâneas ponto a ponto
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Usando o Relatório de Mensagens Instantâneas Ponto a Ponto da melhor maneira possível

Por padrão, o Relatório de Mensagens Instantâneas Ponto a Ponto mostra a você a contagem de mensagens por hora (ou dia, dependendo de suas configurações). No entanto, você também pode escolher visualizar o dia por sessões por hora. Para fazer isso, clique em **Ocultar/Exibir Parâmetros** no canto superior direito da janela Relatórios, e então clique em **Contagem de Sessão** a partir da lista **Relatar por**.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de obter um resultado mais refinado de conjunto de dados ou visualizar os dados resultantes de maneiras diferentes. A tabela a seguir lista os filtros que você pode utilizar com o Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto.
  
**Filtros do Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para visualizar por semana ou por mês, digite uma data qualquer da semana ou mês (não é necessário digitar o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 03/07/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Caso as datas de início e término excedam o número máximo de valores permitidos para o intervalo selecionado, será exibido somente o número máximo de valores (começando a partir da data de inicio). Por exemplo, se você selecionar o intervalo Diariamente com uma data de início em 7/7/2015 e a data de término em 28/2/2012, os dados serão exibidos para dos dias 7/8/2012 00:00 a 7/9/2012 00:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Relatar por** <br/> | Indica os valores a serem usados no relatório. Selecione uma das seguintes opções: <br/>  Contagem de sessão <br/>  Contagem de mensagem <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por Pool

A tabela a seguir lista as informações fornecidas pelo Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto.
  
**Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por Pool**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Pool** <br/> |Não  <br/> |Nome do pool de registradores ou servidor de borda.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora em que a sessões ocorreram.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou contagem total de mensagens.  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por tipo de autenticação

A tabela a seguir lista as informações fornecidas pelo Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto para cada tipo de autenticação usada pelos participantes em uma sessão ponto a ponto.
  
**Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por tipo de autenticação**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de autenticação** <br/> |Não  <br/> | Tipo de autenticação usada pelos participantes da sessão. Normalmente, os valores são um dos seguintes: <br/>  Enterprise <br/>  Federated <br/>  PIC <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora em que a sessões ocorreram.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou contagem total de mensagens.  <br/> |
   

