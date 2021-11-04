---
title: Relatório de Desempenho do Servidor em Skype for Business Server
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
ms.assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
description: 'Resumo: saiba mais sobre o Relatório de Desempenho do Servidor Skype for Business Server.'
ms.openlocfilehash: 1d276d0dd4deec374ff88ca32d143855dae8919b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746907"
---
# <a name="server-performance-report-in-skype-for-business-server"></a>Relatório de Desempenho do Servidor em Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Desempenho do Servidor Skype for Business Server.
  
O Relatório de Desempenho do Servidor fornece uma lista de servidores Skype for Business Server que sofreram a maior porcentagem de chamadas ruins. O relatório divide os servidores por tipo, relatando estatísticas separadas para os seguintes tipos:
  
- Servidor de Mediação
    
- Servidor de Conferência A/V
    
- Servidor de Borda A/V
    
- Gateway (Servidor de Mediação)
    
- Gateway (desvio de Servidor de Mediação)
    
- Vídeo (incluindo métricas de vídeo para Servidores de Conferência A/V e Servidores de Borda A/V)
    
- Compartilhamento de aplicativos (incluindo métricas de compartilhamento de aplicativos para Servidores de Conferência A/V e Servidores de Borda A/V)
    
É importante observar que a classificação mostrada neste relatório como classificações relativas. Por exemplo, suponha que seu servidor com pior desempenho tenha uma chamada ruim entre suas 1.000 chamadas efetuadas. Isso é uma porcentagem de 0,1% que é mais que aceitável. No entanto, se esse for seu servidor com pior desempenho (isto é, se todos os seus outros servidores tiverem uma porcentagem de chamada ruim mais baixa que 0,1%), então esse servidor aparecerá mesmo assim no Relatório de desempenho do servidor.
  
## <a name="accessing-the-server-performance-report"></a>Como avaliar o Relatório de desempenho do servidor

O Relatório de desempenho do servidor é acessado a partir da página inicial dos Relatórios de Monitoramento. Você pode detalhar o Relatório de [Lista](call-list-report-0.md) de Chamada em Skype for Business Server clicando em uma das seguintes métricas:
  
- Volume da chamada
    
- Percentual de chamadas ruins
    
Além disso, você ver os detalhes do Relatório de Tendência de Qualidade de Mídia do Servidor clicando na seguinte métrica:
  
- Trend
    
## <a name="making-the-best-use-of-the-server-performance-report"></a>Fazendo o melhor uso do Relatório de Desempenho do Servidor

O Relatório de desempenho do servidor fornece várias maneiras de filtrar dados; por exemplo, você pode filtrar por tipo de rede (chamadas feitas de uma chamada cabeada x chamadas de uma conexão sem fio) e tipo de acesso (chamadas feitas de dentro do firewall x chamadas feitas de fora do firewall). Ao exibir o relatório de desempenho do servidor, é uma boa ideia usar esses filtros. Por exemplo, suponha que você tem um Servidor de Mediação que tenha uma porcentagem de chamadas ruins igual a 3,24%. Se você observar apenas as chamadas sem fio, o mesmo servidor teria uma porcentagem de chamadas ruins próxima de 20%. Isso significa que o servidor tem dificuldades com chamadas sem fio, um problema que é obscurecido parcialmente porque o servidor não tem problemas em lidar com chamadas com fio.
  
## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo o Relatório de Desempenho do Servidor permite fazer coisas como filtrar os dados retornados por tipo de servidor ou por tipo de rede (ou seja, com ou sem fio). Você também pode escolher como os dados serão agrupados. Neste caso, os dados são agrupados por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Desempenho do Servidor.
  
**Filtros do Relatório de Desempenho do Servidor**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Tipo de Servidor** <br/> |Indica o tipo de servidor cujo desempenho deve ser reportado. Selecione um dos seguintes:  <br/> [Todos] Servidor de Borda A/V do Servidor de Conferência do Servidor de Conferência do Servidor de Mediação A/V |
|**N Primeiros** <br/> |Indica o número de servidores (com base no percentual de chamadas ruins) a serem exibidos em cada categoria. Por exemplo, se você selecionar **5**, os cinco servidores com pior desempenho são exibidos. Selecione uma das seguintes opções:<br/> [Todos] 5 10 |
|**Tipo de acesso** <br/> |Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:  <br/> [Todos] Externo Interno |
|**Tipo de rede** <br/> |Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:  <br/> [Todos] Sem fio com fio |
|**VPN** <br/> |Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:  <br/> [Todos] VPN não VPN |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Desempenho do Servidor.
  
**Métricas do Relatório de Desempenho do Servidor: Resumo da chamada de áudio**

|**Nome**|**É possível classificar por**|**Descrição**|
|:-----|:-----|:-----|
|**Servidor** <br/> |Não  <br/> |Nome/endereço IP do servidor.  <br/> |
|**Volume de chamadas** <br/> |Não  <br/> |Número total de chamadas realizadas.  <br/> |
|**Percentual de chamadas ruins** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Viagem de ida e volta (ms)** <br/> |Sim  <br/> |Quantidade média (em milissegundos) necessária para um pacote de protocolo de transporte em tempo real (RTP) viajar para outro ponto de extremidade e voltar. Tempos de resposta de 100 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**Degradação (MOS)** <br/> |Sim  <br/> |Quantidade média da degradação MOS enfrentada durante uma chamada. Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0. Um valor de 0,5 ou menos representa degradação aceitável. Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5. Em Skype for Business Server, o Monitoring Server usa um conjunto de algoritmos para prever como os usuários classificariam uma chamada.  <br/> Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Perda de pacote** <br/> |Sim  <br/> |Taxa média de perda de pacotes de protocolo de transporte em tempo real (RTP) (a perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**Tremulação (ms)** <br/> |Sim  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Sim  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Sim  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Sim  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
   
**Métricas do Relatório de Desempenho do Servidor: Resumo da chamada de vídeo**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de Chamada/Tipo de Ponto de Extremidade** <br/> |Não  <br/> | Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem: <br/>  Chamadas Ponto a Ponto de UC <br/>  Sessões de Conferência de UC <br/>  Sessões de Conferência PSTN <br/>  Chamadas PSTN: Desvio de Mídia <br/>  Chamadas PSTN (Não Ignorar): Trecho de UC <br/>  Chamadas PSTN (Não Ignorar): Trecho de Gateway <br/>  Outros Tipos de Chamada <br/> |
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas por tipo de chamada.  <br/> |
|**Percentual de chamadas ruins** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Volume de chamadas (chamadas sem fio)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão sem fio.  <br/> |
|**Volume de chamadas (chamadas VPN)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão VPN.  <br/> |
|**Volume de chamadas (chamadas externas)** <br/> |Não  <br/> |Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).  <br/> |
|**Taxa de bits média (Kbits/s)** <br/> |Não  <br/> |Taxa de bits média (em quilobytes por segundo).  <br/> |
|**% de taxa de bits baixa** <br/> |Não  <br/> |Porcentagem da chamada onde a taxa de bits foi baixa.  <br/> |
|**Perda de pacote de saída** <br/> |Não  <br/> |Perda de pacotes do Protocolo de transporte em tempo real (RTP) para pacotes enviados. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**% de quadros congelados** <br/> |Não  <br/> |Porcentagem de quadros "congelados". Em um quadro congelado, o vídeo não avança enquanto a parte de áudio da chamada prossegue.  <br/> |
|**Taxa de quadros média de saída** <br/> |Não  <br/> |Taxa de quadros média para transmissões de saída durante a chamada.  <br/> |
|**Taxa de quadros média de entrada** <br/> |Não  <br/> |Taxa de quadros média para transmissões de entrada durante a chamada.  <br/> |
|**% de taxa de quadros baixa de entrada** <br/> |Não  <br/> |Porcentagem da chamada onde a taxa de bits foi baixa para vídeo de entrada.  <br/> |
|**% de integridade do cliente** <br/> ||Indica o estado relativo do dispositivo do cliente durante a chamada.  <br/> |
   
**Métricas do Relatório de Desempenho do Servidor: Resumo da chamada de compartilhamento de aplicativo**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de Chamada/Tipo de Ponto de Extremidade** <br/> |Não  <br/> | Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem: <br/>  Chamadas Ponto a Ponto de UC <br/>  Sessões de Conferência de UC <br/>  Sessões de Conferência PSTN <br/>  Chamadas PSTN: Desvio de Mídia <br/>  Chamadas PSTN (Não Ignorar): Trecho de UC <br/>  Chamadas PSTN (Não Ignorar): Trecho de Gateway <br/>  Outros Tipos de Chamada <br/> |
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas por tipo de chamada.  <br/> |
|**Percentual de chamadas ruins** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Volume de chamadas (chamadas sem fio)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão sem fio.  <br/> |
|**Volume de chamadas (chamadas VPN)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão VPN.  <br/> |
|**Volume de chamadas (chamadas externas)** <br/> |Não  <br/> |Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Unidirecional relativo médio** <br/> |Não  <br/> |Atraso unidirecional relativo médio entre dois pontos de extremidade de mídia. Esta é uma medida de latência de salto único.  <br/> |
|**Latência média de processamento lado a lado RDP** <br/> |Não  <br/> |A latência média de processamento lado a lado RDP no Servidor de Conferência AS durante a sessão de visualização. Essa métrica não cobre a latência de rede. Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores.  <br/> |
|**% total de lado a lado estragado** <br/> |Não  <br/> |A porcentagem total de lado a lado estragados.  <br/> |
   

