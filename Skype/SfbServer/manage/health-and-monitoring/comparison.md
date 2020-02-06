---
title: Relatório de comparação de qualidade de mídia no Skype for Business Server
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
ms.assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
description: 'Resumo: Saiba mais sobre o relatório de comparação de qualidade de mídia no Skype for Business Server.'
ms.openlocfilehash: 6ba62abcef7abf9e8702a4b51582a434fdd57df6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818092"
---
# <a name="media-quality-comparison-report-in-skype-for-business-server"></a>Relatório de comparação de qualidade de mídia no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de comparação de qualidade de mídia no Skype for Business Server.
  
O Relatório de Comparação de Qualidade da Mídia permite comparar os valores de qualidade da chamada para diferentes tipos de chamadas de áudio (por exemplo, chamadas realizadas por uma rede sem fio contra chamadas realizadas em uma conexão com fio).
  
## <a name="accessing-the-media-quality-comparison-report"></a>Como acessar o Relatório de Comparação de Qualidade de Mídia

O Relatório de Comparação de Qualidade de Mídia é acessado na página inicial de Relatórios de Monitoramento. 
  
## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou exibir os dados retornados em formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatório de Comparação de Qualidade de Mídia.
  
**Filtros do Relatório de Comparação de Qualidade de Mídia**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Chamadas** <br/> | Tipo de chamada a ser usado como o item de comparação principal. Os valores permitidos são: <br/>  [Todos] <br/>  Externo <br/>  Interno <br/>  VPN <br/>  Não VPN <br/>  Com fio <br/>  Sem fio <br/>  Externo e com fio <br/>  Externo e sem fio <br/>  Externo e VPN <br/>  Externo e não VPN <br/>  Interno e com fio <br/>  Interno e sem fio <br/> |
|**Comparar com chamadas** <br/> | Tipo de chamada a ser usado como o item de comparação secundário. Os valores permitidos são: <br/>  [Todos] <br/>  Externo <br/>  Interno <br/>  VPN <br/>  Não VPN <br/>  Com fio <br/>  Sem fio <br/>  Externo e com fio <br/>  Externo e sem fio <br/>  Externo e VPN <br/>  Externo e não VPN <br/>  Interno e com fio <br/>  Interno e sem fio <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanal (é possível exibir no máximo 12 semanas) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para os dias de 7/8/2015, meia-noite, a 7/9/2015, meia-noite, (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Comparação de Qualidade da Mídia.
  
**Métricas do Relatório de Comparação de Qualidade da Mídia**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas.  <br/> |
|**Degradação (MOS)** <br/> |Não  <br/> |Valor médio da degradação da MOS (Pontuação de opinião média) durante uma chamada. Os valores de degradação podem variar de um baixo de 0,0 a um alto de 5,0; um valor de 0,5 ou menos representa uma degradação aceitável. Historicamente, a média das pontuações de opinião foi calculada pela necessidade de os usuários classificarem a qualidade de uma chamada em uma escala de 1 a 5. O Skype for Business Server usa um conjunto de algoritmos para prever como os usuários teriam classificado uma chamada.  <br/> Valores altos de degradação podem ser causados por congestionamento, falta de largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Porcentagem de chamadas ruins** <br/> |Não  <br/> |O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Ida e volta (ms)** <br/> |Não  <br/> |Quantidade média (em milissegundos) exigida para que um pacote de protocolo RTP viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**Perda de pacote** <br/> |Não  <br/> |Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Não  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Não  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Não  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
   

