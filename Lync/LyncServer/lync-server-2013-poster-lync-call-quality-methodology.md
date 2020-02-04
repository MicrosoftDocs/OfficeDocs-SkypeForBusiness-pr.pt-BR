---
title: 'Lync Server 2013: pôster: metodologia de qualidade de chamada do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95105501d0403600e88d01ad5fa84363c1e81785
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Metodologia de qualidade de chamada do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-06-24_

Este artigo é um complemento ao pôster da [metodologia de qualidade de chamada do Lync](http://go.microsoft.com/fwlink/?linkid=391841) , que você pode baixar no centro de download.

![Cartaz descrevendo o processo de CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Cartaz descrevendo o processo de CQM")

Você pode usar este pôster para saber mais sobre o CQM, a metodologia de qualidade da chamada do Lync 2013 e do 2010 que ajuda você a encontrar e eliminar problemas que afetam a qualidade da chamada e a experiência do usuário para implementações do Lync que incluem recursos Enterprise Voice. A metodologia de qualidade da chamada é uma nova estrutura de solução de problemas e gerenciamento de serviços que pode focalizar melhor os esforços para melhorar os serviços Enterprise Voice no Lync. Neste artigo, você pode saber mais sobre o CQM, os tipos de servidores e soluções que são monitorados e o que fazer com os dados de telemetria coletados.

Se tiver dúvidas sobre como usar o CQM, você pode enviar suas perguntas para cqmfeedback@microsoft.com.

O pôster explica as seguintes áreas:

  - O que é o Lync CQM?

  - Priorizar: executar consultas de tendências

  - PCD

  - Gerenciado/não gerenciado

  - A estrada da planta do servidor

  - A estrada do último milhar

  - Os pontos de extremidade da estrada

  - Gerenciamento de serviço

  - Regras do jogo de tabuleiro

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>O que é o Lync CQM?

A metodologia de qualidade da chamada é uma nova estrutura de solução de problemas e gerenciamento de serviços que pode focalizar melhor os esforços para melhorar os serviços Enterprise Voice no Lync. Quando você usa o CQM, é preciso ter menos esforço para garantir a qualidade da chamada e a satisfação do usuário para os serviços Enterprise Voice. CQM é mais explicado na [metodologia de qualidade da chamada](http://go.microsoft.com/fwlink/p/?linkid=615208). Este artigo e o pôster são resumos desse conteúdo.

O CQM interrompe a solução de problemas do sistema em três caminhos ou "estradas". Estes são: a estrada do servidor, que examina os servidores e os links entre eles, o ponto final aponta para os dispositivos de usuário e a mídia usada para realizar chamadas e a estrada passada, que aborda a integração de chamadas de rede telefônica comutadas tradicionais.

Cada estrada é dividida em vários segmentos relacionados a uma área ou tópico específico, e em cada definição de segmento é feita sobre o que é um nível de qualidade aceitável, as ações são tomadas para alcançar esse nível de qualidade e um plano de gerenciamento de serviço é colocado no lugar para manter esse nível de qualidade antes de passar para o próximo tópico.

O pôster apresenta o Lync CQM como um jogo de tabuleiro para três jogadores, cada um deles passará por uma das estradas. Os cartões incluídos no download são usados para simular impedimentos de chamar a qualidade que devem ser superadas. Dicas e sugestões sobre alvos e como obtê-los são incluídos nos três caminhos, bem como diretrizes de priorização para as quais você se busca pela primeira vez em aplicativos reais (no jogo, todas as três estradas são abordadas em paralelo).

Como o CQM funciona nas versões anteriores do Lync? CQM é novo para o Lync 2013, mas a maior parte dele pode ser adaptada para ser usada com o Lync 2010. CQM pode funcionar em um certo grau com o Microsoft Office Communicator, mas isso não é testado e não tem suporte.

Se tiver dúvidas sobre como usar o CQM, você pode enviar suas perguntas para cqmfeedback@microsoft.com.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priorizar: executar consultas de tendências

A primeira etapa no CQM é executar cada uma das consultas de tendências por duas semanas e, em seguida, analisar os resultados. Priorize a ação corretiva pelo maior colaborador de fluxo, a melhor taxa de fluxo de baixa qualidade, e áreas gerenciadas (aquelas que você controla).Se a unidade de controle de vários pontos de áudio/vídeo (AV MCU) ou as consultas de mediação mostrarem resultados deficientes, comece na estrada vermelha ou em instalações do servidor.Se as consultas com fio ou sem fio mostrarem resultados ruins, comece pela estrada azul ou da última quilometragem.Se as consultas de VPN ou externa mostrarem resultados deficientes, comece na estrada verde ou de ponto de extremidade.

Depois de escolher uma estrada para começar, defina um destino para cada área (Assert), trabalhe para atender ao destino (alcançar) e, em seguida, implemente os procedimentos para ficar no destino (manter). Você também pode usar esse pôster como um jogo para compreender os princípios por trás do CQM.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

A ferramenta de diagnóstico de chamadas (PCD) ajudará você a identificar e diagnosticar problemas na sua rede de perímetro (o banco de dados de QoE não coletará informações na sua rede de perímetro ou perímetro) e também para solucionar problemas de conexão na última quilometragem. A ferramenta está disponível como um aplicativo moderno do Windows 8 ou um aplicativo da área de http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88trabalho do Windows em.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Gerenciado/não gerenciado

A implantação do Lync Server e a infraestrutura de rede geralmente podem ser divididas em espaços gerenciados e não gerenciados. O espaço gerenciado inclui todo o espaço dentro da infraestrutura de rede e servidor com fio. O espaço não gerenciado é a infraestrutura sem fio e a infraestrutura de rede externa.

Fazer essa distinção aumenta a clareza dos seus dados e ajuda a sua organização a se concentrar em cargas de trabalho que terão um impacto mensurável sobre a qualidade da voz e do vídeo dos seus usuários. Os usuários têm uma expectativa de qualidade diferente se a chamada for feita na infraestrutura que você possui (gerenciada) versus infraestrutura que está parcialmente sob o controle de alguma outra entidade (não gerenciada). Isso não significa que os usuários sem fio são deixados para seus próprios dispositivos para ter experiências excelentes com o Lync Server.

Melhorar a qualidade da voz no espaço não gerenciado exige que você tenha alta qualidade no espaço gerenciado. Se a tecnologia sem fio (Wi-Fi) é considerada um espaço gerenciado ou não gerenciado está na sua organização. As técnicas para obter um ambiente saudável são diferentes nos dois espaços, como as soluções.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>A estrada da planta do servidor

O segmento 1 da estrada da planta do servidor aborda os servidores reais na implementação do Lync. Coletar dados do KHI sobre o próprio servidor e sua função na implementação e analisar o resultado. Se a ação estiver garantida, corrija os problemas encontrados. Mais detalhes sobre este tópico são apresentados no artigo sobre os [principais indicadores de integridade no Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) que acompanham o pôster khi.

O próximo segmento aborda fluxos de mídia entre o servidor AV MCU e o servidor de mediação. Comece determinando seus destinos para limiares de fluxo de baixa qualidade. Fluxos deficientes geralmente são \> PacketLossRate 0,01 ou \> PacketLossRateMax. 05. Outro alvo desejável é PoorStreamsRatio \< 2%. Em seguida, use consultas detalhadas para localizar pares de servidores de AVMCU e mediação com fluxos ruins, investigar a causa de fluxos deficientes, ver o equipamento de rede nos caminhos de fluxo ruim, corrigir fluxos ruins e definir a configuração ideal ou "ouro" para a rede material. Para manter sua conquista, implemente processos e ferramentas para gerenciar a descompasso de configuração e relatar novas áreas problemáticas.

Em seguida, examine os fluxos de mídia entre o servidor de mediação e o gateway PSTN (rede telefônica pública comutada). Comece determinando seus destinos para limiares de fluxo de baixa qualidade. Fluxos deficientes geralmente são \> PacketLossRate 0,01 ou \> PacketLossRateMax. 05. Outro alvo desejável é PoorStreamsRatio \< 2%. Em seguida, use consultas detalhadas para localizar pares de servidor de mediação e gateway com fluxos ruins, investigar a causa de fluxos ruins, ver o equipamento de rede nos caminhos de fluxo ruim, corrigir fluxos ruins e definir a configuração ideal ou "ouro" para a rede material. Para manter sua conquista, implemente processos e ferramentas para gerenciar a descompasso de configuração e relatar novas áreas problemáticas.

Por fim, examine as métricas de integridade do seu gateway PSTN. Identifique as estatísticas que mostram integridade e definem os alvos contra elas. Nenhuma orientação específica é fornecida aqui, pois muitos possíveis gateways podem ser usados. Depois que os destinos forem estabelecidos, corrija-os conforme necessário para obter o destino; no processo, é provável que você defina uma "ouro" ou uma configuração ideal para o gateway. Para manter sua conquista, implemente processos e ferramentas para gerenciar a descompasso de configuração e relatar novas áreas problemáticas. Lembre-se de que as atualizações de firmware e software podem alterar a configuração ou conduzir você a alterar a definição da configuração "ouro", portanto, aborde essas atividades com cuidado.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>A estrada do último milhar

Das duas maneiras como os clientes se conectam à rede, espera-se que o cabo tenha a qualidade mais alta e que isso deve ser o foco inicial para os problemas de última quilometragem. Use a consulta com fio CQM (\_LastMile\_0 com fio) e os dados de taxa de fluxos fracos que ele fornece. Sugerimos definir um Target PoorStreamsRatio \< 5% para sites com \> 300 streams). Para obter seus destinos, corrija as sub-redes pedidas do pior ao melhor e implemente a QoS.

Depois de otimizar a qualidade das suas conexões com fio, melhorar a qualidade da rede sem fio se torna mais fácil porque a infraestrutura sem fio está acima do núcleo cabeado em cada local. Fluxos sem fio ruins em um site com boa qualidade com fio devem ser atribuídos a componentes sem fio específicos. A consulta sem fio do CQM\_(\_LastMile 1 Wireless) opera em um intervalo de datas e retorna todos os fluxos sem fio internos do seu ambiente de clientes do Lync para ou dos servidores de conferência ou servidores de mediação. Sugerimos definir um Target PoorStreamsRatio \< 5% para sites com \> 300 streams). Para obter seus destinos, corrija as sub-redes pedidas do pior ao melhor e implemente a QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>Os pontos de extremidade da estrada

Comece as consultas no ponto de extremidade com fones de ouvido com microfone e outros dispositivos conhecidos para produzir uma qualidade aceitável quando usados com o Lync. Sugerimos um AvgSendListen MOS \> 3,6 de destino para implementações com mais de 100 fluxos.) Obtenha o destino identificando os dispositivos problemáticos e corrija ou substitua-os.

Em seguida, examine o dispositivo ou o computador que está processando o áudio para as chamadas do usuário final. Uma métrica de qualidade de destino sugerida \<é um AudioMicGlitchRate = 1. Ao identificar as configurações ideais do sistema para os sistemas de usuário, defina uma configuração de computador "ouro", incluindo as versões de driver.

Agora examine o caminho de rede que um fluxo de áudio usa de um sistema de ponto de extremidade do Lync, que pode causar uma qualidade de áudio ruim. Se o áudio viajar por uma conexão VPN, você poderá ver problemas de latência. Se um cliente do Lync interno não puder estabelecer um fluxo de mídia direta para outro cliente do Lync interno para uma chamada de dois participantes ou ponto a ponto, ele retornará a um caminho que retransmita por meio de um servidor de borda do Lync, o que leva a problemas de latência, bem como um potencial maior para perda e Tremulação. Sugerimos que você defina uma métrica de qualidade de 0% mídia via VPN. À medida que você se remediar para atingir o destino definido, identificar sub-redes problemáticas e investigar regras de firewall, formas de pacotes e outras configurações de equipamento de rede relevantes.

Os pacotes IP podem usar o protocolo de controle de transmissão (TCP) ou o protocolo de datagrama de usuário (UDP). O TCP é ideal para fluxos de dados. O UDP é sem conexão e é mais eficiente para mídia, já que os mecanismos de recuperação TCP não podem atender à perda de mídia em tempo real. O Lync sempre prefere o UDP, mas reverterá para TCP se não for possível estabelecer uma sessão UDP. As sessões de mídia pelo TCP exibirão uma qualidade inferior a UDP. Recomendamos uma definição de qualidade de 0% conexões via TCP. À medida que você se remediar para atingir o destino definido, identificar sub-redes problemáticas e investigar regras de firewall, formas de pacotes e outras configurações de equipamento de rede relevantes.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Gerenciamento de serviço

Gerenciamento de serviço é o estado final de CQM e o destino de todas as três estradas. Para manter altos níveis de qualidade de chamada, monitore estas áreas:

1.  **Usuários** – as atividades de correção devem mostrar um aumento mensurável na satisfação do usuário. Você pode medir isso por tíquetes de problemas ou outros mecanismos de feedback. Você também pode publicar métricas de qualidade.

2.  **Processo** -define processos diários, semanais e mensais para fazer a operação de cqm. O monitoramento ritmo começa em uma frequência mais alta enquanto você está remediando (diariamente) e se move para uma frequência inferior (mensal) enquanto você estabiliza.

3.  **Ferramentas** – identificar ferramentas para medir e remediar. Pode ser útil automatizar a execução de consultas CQM para dar suporte aos seus processos. A correção pode exigir ferramentas adicionais, por exemplo, para impor configurações padronizadas em elementos de rede ou solucionar problemas de perda em fluxos ruins.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Regras do jogo de tabuleiro

Você pode usar esse pôster como uma referência a uma implementação do CQM ou como um jogo para praticar os conceitos. Para jogar, você precisará de uma matriz de 1 6 e os cartões fornecidos. Uma versão para download dos cartões está disponível para impressão em cartões de visita padrão Avery 5871.

O jogo é para três jogadores. Há três caminhos que os jogadores podem usar para obter a qualidade desejada e alcançar o estado de gerenciamento do serviço central: planta do servidor, ponto final e último milha. Cada caminho para de acordo com o jeito de você declarar metas de qualidade, atingir metas e manter um aspecto do seu sistema. Coloque os cartões na área indicada acima e, em seguida, desenhe 5 cartas. Revise os cartões que você desenhou e coloque-os no segmento de quadro relevante. Cada jogador percorre os cartões em seu caminho passo a passo, declarando as metas de qualidade, obtendo esses destinos e mantendo os níveis de serviço. O jogo é concluído quando todos os jogadores chegam ao estado de gerenciamento do serviço do centro. Regras mais detalhadas são fornecidas com o download do cartão de jogo.

Para **declarar** um destino de qualidade, revise os parâmetros aplicáveis a esse destino e informe o que você vai e não aceitará. Recomendamos pontos de início, mas você deve fazer a chamada final. A exceção é KHI dados, onde os padrões estabelecidos pela Microsoft devem ser usados. Veja o pôster KHI relacionado.

Para fazer **isso** no jogo, use os cartões fornecidos no lugar dos dados do khi e consultas do sistema. Se, no início do jogo, você não tiver desenhado um cartão relativo a um determinado aspecto, você pode continuar a colá-lo. Se houver um cartão relevante, role a matriz. Se você tiver revertido o número indicado no cartão, terá êxito. Se você reverter o número indicado, você deve desenhar outro cartão do baralho. Se o cartão indicar que dois ou mais jogadores precisam ser dimensionados, eles devem ser acumulados com êxito.

Para **manter** no jogo, desbotamos em voz alta o plano de gerenciamento de serviços sobre esse aspecto do ambiente do Lync.

</div>

<div>

## <a name="see-also"></a>Confira também


[Guia de rede do Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Principais indicadores de integridade: a base para a manutenção de servidores de Lync saudáveis](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodologia de qualidade de chamada do Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

