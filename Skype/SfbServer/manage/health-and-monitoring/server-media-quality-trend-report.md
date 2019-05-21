---
title: Relatório de tendências de qualidade de mídia do servidor no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Resumo: Saiba mais sobre o relatório de tendências de qualidade de mídia do servidor no Skype for Business Server.'
ms.openlocfilehash: 0ed819c40088c03ca1882ed035b416bf1427e840
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279827"
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server"></a>Relatório de tendências de qualidade de mídia do servidor no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de tendências de qualidade de mídia do servidor no Skype for Business Server.
  
O Relatório de Tendências de Qualidade de Mídia do Servidor é uma forma gráfica de comparar até cinco servidores em relação a métricas de Qualidade da Experiência, como volume da chamada, percentagem de chamadas ruins, perda de pacotes e tremulação. Ele facilita determinadas tarefas como identificar servidores com desempenho ruim, subutilizados e superutilizados.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Acessando o Relatório de Tendências de Qualidade de Mídia do Servidor

O Relatório de Tendências de Qualidade de Mídia do Servidor pode ser acessado por um destes relatórios:
  
- [Relatório de desempenho do servidor no Skype for Business Server](server-performance.md) (clicando na métrica de tendência)
    
- [Relatório de detalhes da chamada no Skype for Business Server](call-detail-report.md) (clicando na métrica de servidor de borda A/V. Se o chamador ou o receptor for um servidor, você também poderá acessar o relatório de tendências de mídia de qualidade do servidor clicando no nome do ponto de extremidade.)
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Aproveitando ao máximo o Relatório de Tendências de Qualidade de Mídia do Servidor

Quando você clica na métrica de tendência no [relatório de desempenho do servidor no Skype for Business Server](server-performance.md) para um servidor específico, o relatório de tendências de qualidade de mídia do servidor será aberto. No entanto, você verá uma instância em branco do relatório; o servidor selecionado no Relatório de Desempenho do Servidor não será exibido na tela. Será necessário selecionar o servidor em questão no menu suspenso "Servidores". O menu suspenso "Servidores" apresenta também a opção "Selecionar tudo". Essa opção não funcionará caso haja mais de cinco servidores; o relatório de tendências de qualidade de mídia do servidor só pode exibir dados para, no máximo, cinco servidores por vez.
  
Nos gráficos exibidos pelo relatório de tendências de qualidade de mídia do servidor, os pontos com o rótulo de chamadas e a porcentagem de chamada baixa são hotlinks; clicar em um ponto no gráfico abrirá uma instância do [relatório de lista de chamadas no Skype for Business Server](call-list-report-0.md) , mostrando o total de chamadas (ou chamadas ruins) pelo período de tempo especificado.
  
## <a name="filters"></a>Filtros

Os filtros são uma forma de obter dados mais direcionados ou visualizar os dados obtidos de diferentes maneiras. A tabela a seguir relaciona os filtros que podem ser usados no relatório de tendências de qualidade de mídia do servidor.
  
**Filtros do Relatório de Tendências de Qualidade de Mídia do Servidor**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Por semana (é possível exibir no máximo 12 semanas) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Por dia com a data de início 7/8/2015 e a data de término 28/9/2015, os dados serão exibidos para os dias de 7/8/2015 00:00 a 7/9/2012 00:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Tipo de Servidor** <br/> | Tipo de servidor envolvido na chamada. Os valores permitidos são <br/>  Servidor de Mediação <br/>  Servidor de Conferência A/V <br/>  Servidor de Borda A/V <br/>  Gateway (Servidor de Mediação) <br/>  Gateway (Bypass do servidor de mediação) <br/>  Servidor de conferência AS <br/> |
|**Servidores** <br/> |Nome do servidor envolvido na sessão; essa lista suspensa é preenchida automaticamente com base no valor do filtro de tipo de arquivo. É possível selecionar até cinco servidores diferentes ao compilar o relatório.  <br/> |
|**Tipo de acesso** <br/> | Indica se o participante fez logon a partir da rede interna ou de uma rede externa. Os valores permitidos são: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de rede** <br/> | Indica o tipo de rede ao qual o participante estava conectado. Os valores permitidos são: <br/>  [Todos] <br/>  Com fio <br/>  Sem fio <br/> |
|**VPN** <br/> | Indica se o participante externos estava usando conexão VPN durante a sessão. Os valores permitidos são: <br/>  [Todos] <br/>  VPN <br/>  Não-VPN <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no relatório de tendências de qualidade de mídia do servidor.
  
**Métricas do relatório de tendências de qualidade de mídia do servidor**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas.  <br/> |
|**Degradação (MOS)** <br/> |Não  <br/> |Valor médio de uma redução da opção MOS (média da opção) durante uma chamada. Os valores de degradação podem variar de um baixo de 0,0 a um alto de 5,0; um valor de 0,5 ou menos representa uma degradação aceitável. As pontuações médias de opinião costumava ser calculadas a partir da classificação da qualidade de uma chamada em uma escala de 1 a 5, feita pelos dos usuários. O Skype for Business Server usa um conjunto de algoritmos para prever como os usuários teriam classificado uma chamada.  <br/> Valores altos de degradação podem ser causados por congestionamento, falta de largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Porcentagem de chamadas ruins** <br/> |Não  <br/> |O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Ida e volta (ms)** <br/> |Não  <br/> |Quantidade média de tempo (em milissegundos) exigida para que um pacote de protocolo RTP vá até um ponto de extremidade e retorne. Tempos de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**Perda de pacote** <br/> |Não  <br/> |Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Não  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Não  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Não  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
   

