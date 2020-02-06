---
title: Relatório de diagnóstico de atividade ponto a ponto no Skype for Business Server
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
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Resumo: Saiba mais sobre o relatório de diagnóstico de atividades ponto a ponto no Skype for Business Server.'
ms.openlocfilehash: 7491fc6752bbf7c08c7433f83ea58fcd1a2ba86c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817810"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Relatório de diagnóstico de atividade ponto a ponto no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de diagnóstico de atividades ponto a ponto no Skype for Business Server.
  
O Relatório de Diagnóstico de Atividades Ponto a Ponto fornece informações sobre o sucesso e falha de suas sessões de comunicação ponto a ponto. Observe que o Skype for Business Server distingue entre os diferentes tipos de falha:
  
- **Falha esperada**. Uma falha esperada é normalmente uma falha somente no sentido mais técnico. Por exemplo, vamos supor que você ligue para alguém, mas ele ou ela esteja fora do escritório e não possa atender ao telefone. Como a chamada não foi atendida, ela é considerada tecnicamente uma falha. Por outro lado, isso era uma falha esperada: o Skype for Business Server não espera que você atenda ao telefone se não estiver disponível para atender ao telefone. Da mesma maneira, uma falha esperada ocorrerá se você tentar enviar uma mensagem instantânea a um usuário que esteja offline, ou conectado apenas a um telefone que não suporta mensagem instantânea.
    
- **Falha inesperada**. Um erro inesperado é exatamente o que o nome sugere: um erro que, baseado nas circunstâncias, você não espera. Por exemplo, suponha que você ligue para alguém e essa pessoa está disponível para atender a chamada; no entanto, quando o Skype for Business Server tenta direcionar sua chamada para a caixa postal, a chamada falha porque a conectividade com a Unificação de mensagens do Exchange foi perdida. Esse é um erro inesperado: você espera que as chamada sempre sejam encaminhadas para a caixa postal. Como regra geral, falhas inesperadas são verdadeiras falhas: elas são problemas que provavelmente não podem ser corrigidos por meio da educação do usuário ou por medidas parecidas.
    
Observe que talvez as métricas Sucesso, Falha esperada e Falha inesperada não acrescentem à métrica Total de sessões. Por exemplo, na ilustração anterior, temos os seguintes valores:
  
|**Êxitos**|**Falhas esperadas**|**Falhas inesperadas**|**Total de sessões**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Se você adicionar 2024 + 469 + 16 terá um total de 2.509 sessões, ainda assim a coluna Total de sessões mostrará um total de 2.521 sessões. As 12 sessões que "faltam" são sessões que o sistema não pode categorizar como bem-sucedida ou sem sucesso. Isso, às vezes, é o caso quando um produto de terceiros introduz um novo código de diagnóstico que não está familiarizado com o Skype for Business Server. Quando isso acontece, as chamadas feitas usando esse produto, e o relatório desse código de diagnóstico, não podem sempre ser categorizados como Sucesso, Falha esperada ou Falha inesperada.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Acessando o Relatório de Diagnóstico de Atividades Ponto a Ponto

O Relatório de Diagnóstico de Atividades Ponto a Ponto é acessado a partir da home page dos Relatórios de monitoramento. Você pode acessar o [relatório de distribuição de falha no Skype for Business Server](failure-distribution-report.md) clicando em uma das seguintes métricas:
  
- Volume de falhas inesperadas
    
- Volume de falhas esperadas
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Fazendo o melhor uso do Relatório de Diagnóstico de Atividades Ponto a Ponto

Há diversas maneiras de usar filtrar o Relatório de Diagnóstico de Atividades Ponto a Ponto, mas, por padrão, essas opções de filtragem ficam ocultas. Para exibir as opções de filtragem disponíveis, clique no botão Mostrar/Ocultar Parâmetros no canto superior direito da janela de relatório. Depois de fazer isso, as opções de filtragem ficarão disponíveis para uso.
  
## <a name="filters"></a>Filtros

Filtros oferecem uma maneira de você retornar um conjunto de dados mais preciso ou visualizar os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Diagnóstico de Atividade Ponto-a-Ponto permite que você filtre tais coisas como a modalidade de sessão (por exemplo, mensagens instantâneas, transferência de arquivos ou compartilhamento de arquivos). Você pode escolher também como os dados devem ser agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode utilizar com o Relatório de Diagnóstico de Atividade Ponto-a-Ponto.
  
**Filtros de Relatório de Diagnóstico de Atividade Ponto-a-Ponto**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para os dias de 7/8/2015 12:00 a 7/9/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Tudo]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Modalidade** <br/> | Indica o tipo de atividade de comunicação que ocorreu. Selecione um dos seguintes: <br/>  [Todos] <br/>  Mensagens instantâneas <br/>  Transferência de arquivos <br/>  Compartilhamento de aplicativos <br/>  Áudio <br/>  Vídeo <br/> |
   
## <a name="metrics-per-modality"></a>Medidas (por modalidade)

A tabela a seguir lista as informações oferecidas no Relatório de Diagnóstico de Atividades Ponto-a-Ponto para cada modalidade.
  
**Medidas (por modalidade)**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Volume de sucesso** <br/> |Não  <br/> |Número total de sessões ponto-a-ponto com êxito.  <br/> |
|**Porcentagem de sucesso** <br/> |Não  <br/> |Porcentagem de sessões ponto-a-ponto completas com problemas significativos. Calculado dividindo o Volume de sucesso pelo Total de sessões.  <br/> |
|**Volume de falhas esperadas** <br/> |Não  <br/> |Número total de sessões nas quais ocorreu uma "falha esperada".  <br/> Uma falha esperada é quando se sabe que a falha ocorrerá. Por exemplo, se um usuário tiver definido seu status como Não perturbe, é esperado que qualquer chamada para esse usuário falhe.  <br/> |
|**Percentual de falhas esperadas** <br/> |Não  <br/> |Porcentagem de sessões ponto-a-ponto que tiveram um erro esperado. Calculado dividindo o Volume de falhas esperadas pelo Total de sessões.  <br/> |
|**Volume de falhas inesperadas** <br/> |Não  <br/> |Número total de sessões nas quais ocorreu uma "falha inesperada".  <br/> Uma falha inesperada é uma falha que ocorre no que aparenta ser um sistema íntegro. Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera. Se isso ocorrer, isso seria sinalizado como uma falha inesperada.  <br/> |
|**Percentual de falhas inesperadas** <br/> |Não  <br/> |Porcentagem de sessões ponto-a-ponto nas quais um erro inesperado ocorreu. Calculado dividindo o Volume de falhas inesperadas pelo Total de sessões.  <br/> |
|**Total de sessões** <br/> |Não  <br/> |Número total de sessões, incluindo sessões bem-sucedidas, com falha (esperada e/ou inesperada) e sessões não categorizadas.  <br/> |
   

