---
title: Relatório de Detalhes de Chamada no Skype for Business Server
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
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 'Resumo: saiba mais sobre o Relatório de Detalhes de Chamada usado Skype for Business Server.'
ms.openlocfilehash: 8f5d9e99a9141e1954aef2636ed5d671003e6ad3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834209"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Relatório de Detalhes de Chamada no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Detalhes de Chamada usado Skype for Business Server.
  
O Relatório de Detalhes de Chamada fornece uma análise detalhada de uma chamada individual; o relatório inclui quase todas as métricas e estatísticas de Qualidade da Experiência coletadas pelo Skype for Business Server, divididas em seções de relatório, como:
  
- Informações da chamada 
    
- Medição do dispositivo e do sinal do chamador
    
- Medição do dispositivo e do sinal de quem é chamado
    
- Evento do cliente do chamador
    
- Evento do cliente de quem é chamado
    
- Fluxo de áudio (do chamador para que é chamado)
    
- Fluxo de vídeo (do chamador para que é chamado)
    
- Fluxo de áudio (de quem é chamado para o chamador)
    
- Fluxo de vídeo (de quem é chamado para o chamador)
    
Lembre-se de que as categorias e medidas de um determinado relatório dependem de duas coisas: o tipo de sessão e o tipo de ponto de extremidade usados na sessão. Por exemplo, uma chamada com apenas áudio não reportará medidas de fluxo de vídeo; isso se deve ao fato de a chamada não ter um fluxo de vídeo. Da mesma forma, é possível ter um relatório que liste estatísticas do chamador, mas não de quem é chamado. Normalmente, isso ocorre quando quem foi chamado não usa um dispositivo compatível com SIP. Os pontos de extremidade são responsáveis por reportar estatísticas no final de uma chamada; no entanto, um telefone celular (que desconhece SIP ou as estatísticas de SIP) não pode reportar esse tipo de informação. Se você ligar para alguém e essa pessoa atender em um telefone celular, você não obterá um relatório desse telefone celular quando a chamada terminar.
  
O Relatório Detalhado de Chamadas é especialmente útil quando você está tentando determinar exatamente porque determinada chamada enfrentou problemas de qualidade de mídia.
  
## <a name="accessing-the-call-detail-report"></a>Acessando o Relatório Detalhado de Chamadas

O Relatório Detalhado de Chamadas pode ser acessado a partir de qualquer um dos seguintes relatórios:
  
- O [Relatório de Localização Skype for Business Server (location-report.md) (clicando no volume de chamada ou na métrica porcentagem de chamada ruim)
    
- O [Relatório de Resumo de Qualidade de Mídia no Skype for Business Server (summary.md) (clicando na métrica volume de chamada ou em Porcentagem de Chamada Ruim)
    
- O [Relatório de Comparação de](comparison.md) Qualidade de Mídia [](call-list-report-0.md) Skype for Business Server (clicando no Relatório de Lista de Chamada no Skype for Business Server e clicando na métrica Detalhes).
    
- O [Relatório de Desempenho do Servidor Skype for Business Server](server-performance.md) (clicando na métrica volume de chamada ou porcentagem de chamada ruim)
    
- O [Relatório de Lista](call-list-report-0.md) de Skype for Business Server (clicando na métrica Detalhes)
    
No Relatório de Detalhes de Chamada, você pode acessar o [Relatório](device-report.md) de Dispositivos em Skype for Business Server clicando em uma das seguintes métricas:
  
- Dispositivo de captura
    
- Dispositivo de renderização
    
Também é possível acessar o Relatório de Tendências de Qualidade de Mídia clicando na medida Servidor de borda de áudio/vídeo.
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>Fazendo o melhor uso do Relatório Detalhado de Chamadas

O Relatório Detalhado de Chamadas normalmente contém 250 medidas diferentes, inclusive itens como Descompasso do carimbo de data/hora do microfone, Tempo de SNR baixo e Extremidade próxima ao tempo de eco. Se não conseguir se lembrar o que exatamente todas essas medidas avaliam, tente pousar o mouse sobre o nome da medida; na maioria das vezes, uma dica de ferramenta será exibida descrevendo a medida.
  
Se você tiver problemas para localizar uma métrica, digite parte do rótulo métrico na caixa de pesquisa e clique em **Localizar**. Por exemplo, se você não conseguir encontrar a métrica de hora SNR baixa, digite SNR na caixa de pesquisa e clique em **Encontrar**.
  
Observe que o relatório apenas rastreia informações sobre uma chamada. A chamada em si não é gravada.
  
## <a name="filters"></a>Filtros

Nenhum. Você não pode filtrar o Relatório Detalhado de Chamadas.
  
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório Detalhado de Chamadas para cada chamada.
  
**Métricas do Relatório Detalhado de Chamadas**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**PAI do chamador** <br/> |Não  <br/> |O P-Asserted-Identity do usuário que iniciou a chamada. Essa identidade é usada para transportar a identidade comprovada de um usuário dentro de uma rede confiável.  <br/> |
|**URI do chamador** <br/> |Não  <br/> |Endereço SIP do usuário que iniciou a chamada.  <br/> |
|**Ponto de extremidade do chamador** <br/> |Não  <br/> |Dispositivo usado para efetuar a chamada.  <br/> |
|**Agente do usuário do chamador** <br/> |Não  <br/> |Software usado no dispositivo que fez a chamada.  <br/> |
|**Início da chamada** <br/> |Não  <br/> |Data e hora em que a chamada foi iniciada.  <br/> |
|**Chamada de desvio do Servidor de Mediação** <br/> |Não  <br/> |Indica se a chamada conectou a um gateway de voz PSTN ou IP-PBX qualificado sem passar pelo Servidor de Mediação.  <br/> |
|**OS do chamador** <br/> |Não  <br/> |Sistema operacional do computador do chamador.  <br/> |
|**CPU do chamador** <br/> |Não  <br/> |CPU instalado no computador do usuário que iniciou a chamada.  <br/> |
|**Número de core do CPU do chamador** <br/> |Não  <br/> |Número do processador no computador usado pela pessoa que iniciou a chamada.  <br/> |
|**Velocidade de CPU do chamador** <br/> |Não  <br/> |Velocidade de relógio do CPU do computador usado pela pessoa que iniciou a chamada.  <br/> |
|**Virtualização de CPU do chamador** <br/> |Não  <br/> |Virtualização (se houver) no computador usado pela pessoa que iniciou a chamada.  <br/> |
|**PAI do receptor da chamada** <br/> |Não  <br/> |O P-Asserted-Identity do usuário convidado a entrar na chamada. Essa identidade é usada para transportar a identidade comprovada de um usuário dentro de uma rede confiável.  <br/> |
|**URI do receptor da chamada** <br/> |Não  <br/> |Endereço SIP do usuário que foi chamado.  <br/> |
|**Ponto de extremidade do receptor da chamada** <br/> |Não  <br/> |Dispositivo usado para receber a chamada.  <br/> |
|**Agente do usuário do receptor da chamada** <br/> |Não  <br/> |Software usado no dispositivo que recebeu a chamada.  <br/> |
|**Duration** <br/> |Não  <br/> |Tempo da chamada.  <br/> |
|**Sinalizador de aviso do desvio de mídia** <br/> |Não  <br/> |Aviso emitido quando o Servidor de Mediação foi desviado.  <br/> |
|**OS do receptor da chamada** <br/> |Não  <br/> |Sistema operacional do computador do usuário que foi chamado.  <br/> |
|**CPU do receptor da chamada** <br/> |Não  <br/> |CPU instalado no computador do usuário que foi chamado.  <br/> |
|**Número de core do receptor da chamada** <br/> |Não  <br/> |Número do processador no computador usado pela pessoa que foi chamada.  <br/> |
|**Velocidade de CPU do receptor da chamada** <br/> |Não  <br/> |Velocidade de relógio do CPU do computador usado pela pessoa que foi chamada.  <br/> |
|**Virtualização de CPU do receptor da chamada** <br/> |Não  <br/> |Virtualização (se houver) no computador usado pela pessoa que foi chamada.  <br/> |
   

