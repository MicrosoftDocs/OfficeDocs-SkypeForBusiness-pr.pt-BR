---
title: Relatório de Falhas Principais no Skype for Business Server
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
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Resumo: saiba mais sobre o Relatório de Falhas Principais Skype for Business Server.'
ms.openlocfilehash: 11a71d2c4a68f15e334f913d7672bf49319f77dc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774781"
---
# <a name="top-failures-report-in-skype-for-business-server"></a>Relatório de Falhas Principais no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Falhas Principais Skype for Business Server.
  
O Relatório de Falhas Principais apresenta uma noção das falhas mais frequentemente relatadas e suas tendências ao longo do tempo. As falhas são baseadas em uma combinação das duas seguintes métricas:
  
- **ID de Diagnóstico**. Identificador único (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP. As IDs de Diagnóstico fornecem informações úteis na solução de problemas relacionados a chamadas.
    
- **Código de resposta**. Os códigos de resposta são utilizados nas sessões de comunicação SIP para responder solicitações SIP. Por exemplo, suponha que Ken envie a solicitação INVITE a Pilar Ackerman (isto é, suponha que Ken Myer ligue para Pilar Ackerman). Se Pilar responder, o telefone enviará o código de resposta 200 (OK), permitindo que o telefone de Ken saiba que Pilar atendeu. O Relatório de Falhas Principais inclui apenas códigos de resposta que foram enviados em resposta a uma falha de chamada; Skype for Business Server não mantém o controle de todos os códigos de resposta emitidos durante o curso de uma chamada.
    
A informação é relatada não apenas para o número total de sessões quando uma falha ocorre, mas também para o número total de usuários que foram impactados pela falha.
  
## <a name="accessing-the-top-failures-report"></a>Acessando o Relatório de Falhas Principais

O Relatório de Falhas Principais é acessado a partir da página Relatórios de Monitoramento. Clicar na métrica sessões relatadas o levará ao Relatório de Distribuição de Falhas [em Skype for Business Server](failure-distribution-report.md).
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Fazendo o melhor uso do Relatório de Falhas Principais

O Relatório de Falhas Principais é incomum quanto a uma coisa: ele permite a filtragem de até 5 IDs de diagnóstico de uma vez. (Normalmente, você só pode filtrar em um item - como um endereço SIP de usuário - de cada vez.) Para filtrar várias IDs de diagnóstico, basta inserir cada ID na caixa IDs de diagnóstico, separando as IDs usando vírgulas. (Se quiser, você pode deixar um espaço em branco após cada vírgula.) Por exemplo:
  
1011, 2412, 1033, 52116, 1008
  
Faça isso e apenas chamadas que falharam e foram reportadas pelo menos em uma dessas cinco IDs de diagnóstico serão exibidas.
  
Se você manter o mouse sob Código de Resposta, você verá uma dica que diz o que um Código de Resposta em questão significa. Por exemplo, se você manter o mouse sobre o Código de Resposta 486, você verá esta mensagem:
  
Ocupado.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou para exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Falhas Principais permite filtrar os dados retornados com base, por exemplo, no tipo de atividade (sessão ponto a ponto ou sessão de conferência), ou no código de resposta SIP que acompanhava a sessão com falha. Você também pode escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode usar com o Relatório de Falhas Principais.
  
**Filtros de Relatório de Falhas Principais**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são contadas de domingo até sábado.  <br/> |
|**Tipo de atividade** <br/> | Tipo de atividade. Selecione um dos seguintes: <br/>  [Todos] <br/>  Ponto a ponto <br/>  Conferência <br/> |
|**Modalidade** <br/> |Neste momento, a única opção disponível é **[Todos]**.  <br/> |
|**Pool** <br/> |FQDN (nome de domínio totalmente qualificado do pool de Registrador ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Todos]** para exibir dados de todos os pools. Esta lista suspensa é preenchida automaticamente com base nos registros contidos no banco de dados.<br/> |
|**Categoria** <br/> | Tipo de falha ocorrido. Selecione um dos seguintes: <br/>  Falha inesperada e esperada <br/>  Falha inesperada <br/>  Uma "falha esperada" é aquela que se espera que ocorra. Por exemplo, se um usuário tiver definido seu status como Não incomodar, é esperado que toda chamada encaminhada para esse usuário falhe. "Falha inesperada" é uma falha que ocorre em um sistema que parecia estar em bom estado.Por exemplo, uma chamada não deve ser finalizada se o chamador é colocado em espera. Se isso ocorrer, a situação será sinalizada como falha inesperada. <br/> |
|**Código de resposta** <br/> |O código de resposta enviado quando a conferência falhou. Digite o código de resposta inteiro. Por exemplo:  <br/> 400  <br/> |
|**ID do Diagnóstico** <br/> |Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que geralmente fornece informações úteis para solucionar problemas de erros. Cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e IDs de diagnóstico serão relatadas somente para as sessões que apresentaram problemas de algum tipo.  <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Falhas Principais.
  
**Medição do Relatório de Falhas Principais**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Rank** <br/> |Sim  <br/> |Classificação relativa com base no número de sessões relatadas.  <br/> |
|**Sessões relatadas** <br/> |Sim  <br/> |Número total de sessões com falha baseadas na ID de diagnóstico e no código de resposta SIP.  <br/> |
|**Usuários afetados** <br/> |Sim  <br/> |Número total de usuários afetados pela sessão com falha.  <br/> |
|**Informações de falha** <br/> |Não  <br/> |Informações detalhadas sobre a falha, incluindo a ID de diagnóstico, o código de resposta SIP e a descrição do motivo da sessão com falha.  <br/> |
|**Tendência no passado** <br/> |Não  <br/> |Representa graficamente as sessões com falha ao longo do tempo.  <br/> |
   

