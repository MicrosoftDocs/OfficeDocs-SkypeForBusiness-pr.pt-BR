---
title: Relatório de Lista de Chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Resumo: saiba mais sobre o Relatório de Lista de Chamadas usado no Skype for Business Server.'
ms.openlocfilehash: 8deb14cc8d2b8ff4b47701502de414d7460a81ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817071"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Relatório de Lista de Chamadas no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Lista de Chamadas usado no Skype for Business Server.
  
O Relatório de Lista de Chamadas fornece métricas de QoE (Qualidade da Experiência) para chamadas individuais feitas e recebidas em sua organização. Observe que as métricas reais relatadas dependerão de como você acessa o relatório de Lista de Chamada. Por exemplo, se você abrir o relatório do Relatório de Dispositivos no [Skype for Business Server,](device-report.md)verá métricas como as seguintes, métricas que também são relatadas no Relatório de Dispositivos:
  
- Microfone do chamador
    
- Alto-falante do chamador
    
- Microfone do destinatário da chamada
    
- Alto-falante do destinatário da chamada
    
- Tempo de troca da taxa de voz 
    
No entanto, se você abrir o Relatório de Lista de Chamadas a partir do Relatório de Local no [Skype for Business Server,](location-report.md)não verá nenhuma dessas métricas; em vez disso, você verá métricas como estas:
  
- Viagem de ida e volta (ms)
    
- Degradação (MOS)
    
- Perda de pacote
    
- Tremulação (ms)
    
Essas são as métricas relatadas no Relatório de Locais. No entanto, no Relatório de Lista de Chamada, você sempre pode clicar na métrica Detalhe para fornecer informações completas de QoE para qualquer chamada.
  
## <a name="accessing-the-call-list-report"></a>Acessando o Relatório de Lista de Chamada

O Relatório de Lista de Chamada pode ser acessado em qualquer um dos seguintes relatórios:
  
- O [Relatório de Localização no Skype for Business Server](location-report.md) (clicando na métrica Volume de chamadas ou Percentual de chamadas ruins)
    
- O [Relatório de Dispositivos no Skype for Business Server](device-report.md) (clicando na métrica Volume da chamada ou Percentual de chamadas ruins)
    
- O [Relatório de Resumo de Qualidade de Mídia no Skype for Business Server](summary.md) (clicando na métrica Volume de chamadas ou Percentual de chamadas ruins)
    
- O [Relatório de Desempenho do Servidor no Skype for Business Server](server-performance.md) (clicando na métrica Volume de chamadas ou Percentual de chamadas ruins)
    
No Relatório de Lista de Chamadas, você pode acessar o Relatório Detalhado [de Chamadas no Skype for Business Server](call-detail-report.md) clicando na métrica Detalhes.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Fazendo o melhor uso do Relatório de Lista de Chamada

Se você não conseguir se lembrar o que algumas das métricas do Relatório de Lista de Chamadas (como tempo de troca de voz de taxa) realmente medem, mantenha o mouse sobre o rótulo métrico; uma dica de ferramenta será exibida, dando a você uma breve descrição da métrica.
  
## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Lista de Chamada.
  
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Lista de Chamada para cada chamada.
  
**Métricas do Relatório de Lista de Chamada**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Detalhes** <br/> |Não  <br/> |Quando você clica nesse item, o relatório mostra informações adicionais sobre a chamada.  <br/> |
|**Caller** <br/> |Sim  <br/> |Endereço SIP da pessoa que iniciou a chamada.  <br/> |
|**Destinatário da chamada** <br/> |Sim  <br/> |Endereço SIP da pessoa que foi chamada.  <br/> |
|**Hora de início** <br/> |Sim  <br/> |Data e horário em que a chamada teve início.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e horário em que a chamada terminou.  <br/> |
|**Agente do usuário do chamador** <br/> |Sim  <br/> |Software usado pelo ponto de extremidade da pessoa que iniciou a chamada.  <br/> |
|**Agente do usuário do receptor da chamada** <br/> |Sim  <br/> |Software usado pelo ponto de extremidade da pessoa que foi chamada.  <br/> |
|**Viagem de ida e volta (ms)** <br/> |Sim  <br/> |Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.  <br/> |
|**Degradação (MOS)** <br/> |Sim  <br/> |Quantidade média da degradação MOS enfrentada durante uma chamada. Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0. Um valor de 0,5 ou menos representa degradação aceitável. Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5. No Skype for Business Server, um conjunto de algoritmos prevê como os usuários classificariam uma chamada.  <br/> Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Perda de pacote** <br/> |Sim  <br/> |Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.  <br/> |
|**Trem tremida** <br/> |Sim  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Sim  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Sim  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Sim  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
|**Conectividade** <br/> |Sim  <br/> | Tipo de link de comunicação sem fio. Normalmente, esta é uma das seguintes: <br/>  Retransmissão <br/>  Direct <br/> |
   

