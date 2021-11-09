---
title: Relatório de tendência de qualidade de mídia do servidor no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Resumo: saiba mais sobre o Relatório de Tendências de Qualidade de Mídia do Servidor Skype for Business Server.'
ms.openlocfilehash: 03091deedf502c4a6d9d65dc5e9f14532a9147ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851014"
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server"></a>Relatório de tendência de qualidade de mídia do servidor no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Tendência de Qualidade de Mídia do Servidor Skype for Business Server.
  
O Relatório de Tendência de Qualidade de Mídia do Servidor oferece uma maneira de comparar graficamente até cinco servidores em métricas de Qualidade da Experiência, como volume de chamada, porcentagem de chamada ruim, perda de pacotes e tremeamento. Ele facilita determinadas tarefas como identificar servidores com desempenho ruim, subutilizados e superutilizados.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Acessando o relatório de tendências de qualidade de mídia do servidor

O relatório de tendências de qualidade de mídia do servidor pode ser acessado por um destes relatórios:
  
- [Relatório de Desempenho do Servidor Skype for Business Server](server-performance.md) (clicando na métrica Tendência)
    
- [Relatório de Detalhes](call-detail-report.md) de Chamada Skype for Business Server (clicando na métrica do servidor de borda A/V. Se o chamador ou chamador for um servidor, você também poderá acessar o Relatório de Tendência de Mídia de Qualidade do Servidor clicando no nome do ponto de extremidade.)
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Aproveitando ao máximo o relatório de tendências de qualidade de mídia do servidor

Quando você clica na métrica Tendência no Relatório de [Desempenho](server-performance.md) do Servidor Skype for Business Server um servidor específico, o Relatório de Tendência de Qualidade de Mídia do Servidor será aberto. No entanto, você verá uma instância em branco do relatório; o servidor selecionado no Relatório de desempenho do servidor não será exibido na tela. Será necessário selecionar o servidor em questão no menu suspenso "Servidores". O menu suspenso "Servidores" apresenta também a opção "Seleciontar tudo". Essa opção não funcionará caso haja mais de cinco servidores; o relatório de tendências de qualidade de mídia do servidor só pode exibir dados para, no máximo, cinco servidores por vez.
  
Nos gráficos exibidos pelo Relatório de Tendência de Qualidade de Mídia do Servidor, os pontos rotulados volume de chamada e porcentagem de chamada ruim são hotlinks; clicar em um ponto no gráfico abrirá uma instância do Relatório de Lista de Chamadas em Skype for Business Server mostrando o total de chamadas (ou chamadas ruins) para o período de tempo especificado. [](call-list-report-0.md)
  
## <a name="filters"></a>Filtros

Os filtros são uma forma de obter dados mais direcionados ou visualizar os dados obtidos de diferentes maneiras. A tabela a seguir relaciona os filtros que podem ser usados no relatório de tendências de qualidade de mídia do servidor.
  
**Filtros do relatório de tendências de qualidade de mídia do servidor**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/08/2015 e uma data de término de 28/09/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/9/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Tipo de servidor** <br/> | Tipo de servidor envolvido na chamada. Os valores permitidos são <br/>  Servidor de mediação <br/>  Servidor de Conferência A/V <br/>  Servidor de Borda A/V <br/>  Gateway (servidor de mediação) <br/>  Gateway (Bypass do servidor de mediação) <br/>  Servidor de conferência AS <br/> |
|**Servidores** <br/> |Nome do servidor envolvidona sessão; essa lista suspensa é preenchida automaticamente com base no valor do filtro de tipo de arquivo. É possível selecionar até cinco servidores diferentes ao compilar o relatório.  <br/> |
|**Tipo de acesso** <br/> | Indica se o participante fez logon a partir da rede interna ou de uma rede externa. Os valores permitidos são: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de rede** <br/> | Indicao tipo de rede ao qual o participante estava conectado. Osvalores permitidos são: <br/>  [Todos] <br/>  Com fio <br/>  Sem fio <br/> |
|**VPN** <br/> | Indica se o participante externos estava usando conexão VPN durante a sessão. Os valores permitidos são: <br/>  [Todos] <br/>  VPN <br/>  Não VPN <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no relatório de tendências de qualidade de mídia do servidor.
  
**Métricas do relatório de tendências de qualidade de mídia do servidor**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas.  <br/> |
|**Degradação (MOS)** <br/> |Não  <br/> |Quantidade média de degradação de MOS (pontuação de opção média) experimentado durante uma chamada. Os valores de degradação podem variar de um baixo de 0,0 a uma alta de 5,0; um valor de 0,5 ou menos representa degradação aceitável. Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5. Skype for Business Server usa um conjunto de algoritmos para prever como os usuários classificariam uma chamada.  <br/> Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Percentual de chamadas ruins** <br/> |Não  <br/> |O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Viagem de ida e volta (ms)** <br/> |Não  <br/> |Quantidade média de tempo (em milésimos de seguntos) exigida para que um pacote (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 200 milésimos de segundo ou menos são considerados de qualidade aceitável.  <br/> Viagens de ida e volta com altos valores podem ser resultado do roteamento de chamadas internacionais, configurações incorretas de roteamento ou servidor de mídia sobrecarregado. Viagens de ida e volta com altos valores resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**Perda de pacote** <br/> |Não  <br/> |Taxa média de perda de pacotes de Protocolo de Transporte em Tempo Real (RTP). (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Não  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Não  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Não  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
   

