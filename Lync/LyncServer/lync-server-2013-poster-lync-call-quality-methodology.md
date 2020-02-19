---
title: 'Lync Server 2013: cartaz: metodologia de qualidade de chamada do Lync'
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
ms.openlocfilehash: e35627633839f294cebced6df47a90919e7fc5ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Metodologia de qualidade de chamada do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-06-24_

Este artigo é um complemento ao cartaz da [metodologia de qualidade de chamada do Lync](https://go.microsoft.com/fwlink/?linkid=391841) , que pode ser baixado do centro de download.

![Cartaz que descreve o processo CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Cartaz que descreve o processo CQM")

Você pode usar este cartaz para saber mais sobre o CQM, a metodologia de qualidade de chamada para Lync 2013 e 2010 que ajuda você a encontrar e eliminar problemas que afetam a qualidade da chamada e a experiência do usuário para implementações do Lync que incluem recursos do Enterprise Voice. A metodologia de qualidade de chamada é uma nova estrutura de solução de problemas e de gerenciamento de serviços que pode focalizar melhor os serviços do Enterprise Voice no Lync. Neste artigo, você pode aprender mais sobre o CQM, os tipos de servidores e soluções que são monitorados e o que fazer com os dados de telemetria coletados.

Se você tiver dúvidas sobre como usar o CQM, você pode enviar suas perguntas para o cqmfeedback@microsoft.com.

O cartaz explica as seguintes áreas:

  - O que é Lync CQM?

  - Priorizar: executar consultas de tendências

  - PCD

  - Gerenciado/não gerenciado

  - A estrada da planta do servidor

  - A estrada da última

  - O ponto final aponta

  - Gerenciamento de serviços

  - Regras de Game de placa

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>O que é Lync CQM?

A metodologia de qualidade de chamada é uma nova estrutura de solução de problemas e de gerenciamento de serviços que pode focalizar melhor os serviços do Enterprise Voice no Lync. Quando você usa o CQM, é necessário menos esforço para garantir a qualidade da chamada e a satisfação do usuário para os serviços do Enterprise Voice. CQM é mais explicado na [metodologia de qualidade de chamada](https://go.microsoft.com/fwlink/p/?linkid=615208). Este artigo e o cartaz são resumos desse conteúdo.

O CQM interrompe a solução de problemas do sistema para três caminhos ou "estradas". Estes são: a estrada do servidor, que examina os servidores e os links entre eles, o ponto final, que examina os dispositivos do usuário e a mídia usados para realizar chamadas e a estrada da última viagem, que aborda a integração de chamadas de rede telefônica comutada tradicional.

Cada estrada é dividida em vários segmentos relacionados a uma área ou um tópico específico e, em cada definição de segmento, é feita sobre o que é um nível de qualidade aceitável, as ações são tomadas para atingir esse nível de qualidade e um plano de gerenciamento de serviço é implementado para manter esse nível de qualidade antes de passar para o próximo tópico.

O cartaz apresenta o Lync CQM como um jogo de tabuleiro para três jogadores, cada um deles passará por uma das estradas. Os cartões incluídos no download são usados para simular impedimentos de chamar a qualidade que devem ser superados. Dicas e sugestões sobre os destinos e como obtê-los são incluídos nos três caminhos, bem como as diretrizes de priorização para as quais se buscam primeiro nos aplicativos reais (no jogo, todas as três estradas são abordadas em paralelo).

Como o CQM funciona em versões anteriores do Lync? CQM é novo no Lync 2013, mas a maior parte dele pode ser adaptada para ser usada com o Lync 2010. O CQM pode funcionar para um diploma com o Microsoft Office Communicator, mas isso não é testado e não tem suporte.

Se você tiver dúvidas sobre como usar o CQM, você pode enviar suas perguntas para o cqmfeedback@microsoft.com.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priorizar: executar consultas de tendências

A primeira etapa no CQM é executar cada uma das consultas de tendências por duas semanas e, em seguida, analisar os resultados. Priorize a ação corretiva pelo maior colaborador de fluxo, a maior taxa de fluxo ruim e áreas gerenciadas (que você controla).Se a unidade de controle multiponto de áudio/vídeo (AV MCU) ou as consultas de mediação mostrarem resultados ruins, inicie na estrada da planta vermelha ou do servidor.Se as consultas com fio ou sem fio mostrarem resultados ruins, inicie na estrada azul ou da última quilometragem.Se as consultas VPN ou externas mostrarem resultados ruins, inicie na estrada verde ou de ponto.

Depois de escolher uma estrada para começar, defina um destino para cada área (Assert), trabalhe para atender a esse destino (obter) e, em seguida, implemente os procedimentos para permanecer no destino (manutenção). Você também pode usar este cartaz como um jogo para entender os princípios por trás do CQM.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

A ferramenta de diagnóstico de chamadas (PCD) ajudará você a identificar e diagnosticar problemas em sua rede de perímetro (o banco de dados de QoE não coletará informações na sua rede de borda ou de perímetro) e também solucionará problemas de conexões na última milha. A ferramenta está disponível como um aplicativo moderno do Windows 8 ou um aplicativo da área de http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88trabalho do Windows em.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Gerenciado/não gerenciado

A infraestrutura de implantação e rede do Lync Server normalmente pode ser dividida em espaços gerenciados e não gerenciados. O espaço gerenciado inclui toda a sua infraestrutura de rede com fio e de servidor. O espaço não gerenciado é a infraestrutura sem fio e a infraestrutura de rede externa.

Fazer essa distinção aumenta a clareza de seus dados e ajuda sua organização a se concentrar nas cargas de trabalho que terão um impacto mensurável na qualidade de vídeo e voz de seus usuários. Os usuários têm uma expectativa de qualidade diferente se a chamada é feita na infraestrutura que você possui (gerenciada) versus infraestrutura que está parcialmente sob o controle de outra entidade (não gerenciada). Isso não significa que os usuários sem fio são deixados para seus próprios dispositivos para ter excelentes experiências com o Lync Server.

Melhorar a qualidade de voz no espaço não gerenciado exige que você tenha alta qualidade no espaço gerenciado. Se a tecnologia sem fio (Wi-Fi) é considerada como gerenciada ou se o espaço não gerenciado estiver em sua organização. As técnicas para atingir um ambiente saudável são diferentes nos dois espaços, como são as soluções.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>A estrada da planta do servidor

O segmento 1 da estrada de planta de servidor aborda os servidores reais na implementação do Lync. Coletar dados do KHI sobre o próprio servidor e sua função na implementação e analisar o resultado. Se a ação for garantida, corrija os problemas encontrados. Mais detalhes sobre este tópico são apresentados no artigo sobre os [principais indicadores de integridade no Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) que acompanham o pôster do khi.

O próximo segmento aborda os fluxos de mídia entre o servidor AV MCU e o servidor de mediação. Comece determinando seus destinos para limiares de fluxo ruim. Fluxos ruins geralmente são PacketLossRate \> 0,01 ou PacketLossRateMax \> . 05. Outro alvo desejável é PoorStreamsRatio \< 2%. Em seguida, use consultas detalhadas para localizar pares de servidor de mediação e AVMCU com fluxos ruins, investigar a causa de fluxos ruins, observar o equipamento de rede nos caminhos de fluxo ruins, corrigir fluxos ruins e definir a configuração ideal ou "ouro" para a rede equipa. Para manter sua conquista, implemente processos e ferramentas para gerenciar a descompasso de configuração e para relatar novas áreas problemáticas.

Em seguida, examine os fluxos de mídia entre o servidor de mediação e o gateway PSTN (rede telefônica pública comutada). Comece determinando seus destinos para limiares de fluxo ruim. Fluxos ruins geralmente são PacketLossRate \> 0,01 ou PacketLossRateMax \> . 05. Outro alvo desejável é PoorStreamsRatio \< 2%. Em seguida, use consultas detalhadas para localizar pares de servidor de mediação e gateway com fluxos ruins, investigar a causa de fluxos ruins, observar o equipamento de rede nos caminhos de fluxo ruins, corrigir fluxos ruins e definir a configuração ideal ou "ouro" para a rede equipa. Para manter sua conquista, implemente processos e ferramentas para gerenciar a descompasso de configuração e para relatar novas áreas problemáticas.

Por fim, examine as métricas de integridade do seu gateway PSTN. Identificar as estatísticas que mostram a integridade e definir os destinos. Nenhuma orientação específica é fornecida aqui, pois muitos gateways possíveis podem ser usados. Depois que os destinos forem estabelecidos, remediar conforme necessário para obter o destino; no processo, é provável que você defina uma "ouro" ou uma configuração ideal para o gateway. Para manter sua conquista, implemente processos e ferramentas para gerenciar a descompasso de configuração e para relatar novas áreas problemáticas. Lembre-se de que as atualizações de firmware e software podem alterar sua configuração ou conduzir a você alterar a definição da configuração "ouro", portanto, considere essas atividades com cuidado.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>A estrada da última

Entre as duas maneiras como os clientes se conectam à rede, espera-se que os cabos forneçam a qualidade mais alta e, de forma correspondente, este deve ser o foco inicial para os problemas da última quilometragem. Use a consulta com fio CQM (\_LastMile\_0 com fio) e os dados de taxa de fluxos ruins que ele fornece. Sugerimos definir um destino de \< PoorStreamsRatio 5% para sites \> com 300 streams). Para atingir seus alvos, corrija as sub-redes ordenadas do pior para o melhor e implemente a QoS.

Após otimizar a qualidade de suas conexões com fio, melhorar a qualidade sem fio fica mais fácil porque a infraestrutura sem fio está acima do núcleo com fio em cada local. Os fluxos sem fio ruins em um site com boa qualidade com fio devem ser atribuídos aos componentes sem fio específicos. A consulta sem fio do CQM\_(\_LastMile 1 sem fio) opera em um intervalo de datas e retornará todos os fluxos sem fio internos no seu ambiente de clientes do Lync para ou de servidores de conferência ou servidores de mediação. Sugerimos definir um destino de \< PoorStreamsRatio 5% para sites \> com 300 streams). Para atingir seus alvos, corrija as sub-redes ordenadas do pior para o melhor e implemente a QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>O ponto final aponta

Comece as consultas nos pontos de extremidade com fones de ouvido e outros dispositivos conhecidos para produzir qualidade aceitável quando usados com o Lync. Sugerimos um AvgSendListen MOS \> 3,6 de destino para implementações com mais de 100 fluxos.) Obter o destino identificando dispositivos problemáticos e corrigi-los ou substituí-los.

Em seguida, examine o dispositivo ou computador que está processando o áudio para chamadas do usuário final. Uma métrica de qualidade de destino sugerida \<é uma AudioMicGlitchRate = 1. Ao identificar as configurações ideais do sistema para os sistemas de usuário, defina uma configuração de computador "ouro", incluindo as versões de driver.

Agora, examine o caminho de rede que um fluxo de áudio utiliza de um sistema de ponto de extremidade do Lync, o que pode causar uma qualidade de áudio ruim. Se o áudio viajar por uma conexão VPN, você poderá ver problemas de latência. Se um cliente do Lync interno não puder estabelecer um fluxo de mídia direto para outro cliente do Lync interno para uma chamada ponto a ponto ou de duas partes, ele será redirecionado para um caminho que retransmite por um servidor de borda do Lync, o que leva a problemas de latência, bem como maior potencial para perda e Tremulação. Sugerimos que você defina uma métrica de qualidade de 0% de mídia sobre VPN. À medida que você corrige para obter o destino definido, identifique sub-redes problemáticas e investigue as regras de firewall, as formas de pacote e outras configurações de equipamento de rede relevantes.

Os pacotes IP podem usar TCP (Transmission Control Protocol) ou UDP (User Datagram Protocol). TCP é ideal para fluxos de dados. O UDP é sem conexão e é mais eficiente para mídia, já que os mecanismos de recuperação TCP não podem resolver a perda na mídia em tempo real. O Lync sempre prefere o UDP, mas reverterá ao TCP se não for possível estabelecer uma sessão UDP. As sessões de mídia sobre TCP exibirão uma qualidade inferior à de UDP. Recomendamos uma definição de qualidade de 0% de conexões por TCP. À medida que você corrige para obter o destino definido, identifique sub-redes problemáticas e investigue as regras de firewall, as formas de pacote e outras configurações de equipamento de rede relevantes.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Gerenciamento de serviços

O gerenciamento de serviços é o estado final do CQM e o destino de todas as três estradas. Para manter altos níveis de qualidade de chamada, monitore estas áreas:

1.  **Os usuários** – as atividades de correção devem mostrar um aumento mensurável na satisfação do usuário. Você pode medir isso por tíquetes de problema ou outros mecanismos de comentários. Você também pode publicar métricas de qualidade.

2.  **Process** -define processos diários, semanais e mensais para a operação de cqm. O monitoramento do ritmo começa com uma frequência maior enquanto você estiver corrigindo (diariamente) e se moverá para uma frequência inferior (mensal) à medida que você estabilizar.

3.  **Ferramentas** – identificar ferramentas para medir e corrigir. Você pode achar útil automatizar a execução das consultas do CQM para dar suporte aos seus processos. A correção pode exigir ferramentas adicionais, por exemplo, para impor configurações padronizadas em elementos de rede ou solucionar problemas de perda de fluxos ruins.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Regras de Game de placa

Você pode usar esse pôster como uma referência a uma implementação do CQM ou como um jogo para praticar os conceitos. Para jogar, você precisará do chip de 1 6 e dos cartões fornecidos. Uma versão baixável dos cartões está disponível para impressão nos cartões de visita Standard 5871 Avery.

O jogo é para 3 Players. Há três caminhos que os jogadores podem usar para obter a qualidade desejada e alcançar o estado de gerenciamento do serviço central: fábrica de servidor, ponto de extremidade e última quilometragem. Cada caminho foi interrompido ao longo da forma como você declara metas de qualidade, alcança as metas e mantém um aspecto do sistema. Coloque os cartões na área indicada acima e, em seguida, desenhe 5 cartas. Revise os cartões que você desenhou e coloque-os no segmento de quadro relevante. Cada jogador percorre os cartões em seu caminho passo a passo, declarando metas de qualidade, obtendo esses destinos e mantendo os níveis de serviço. O jogo é concluído quando todos os jogadores atingem o estado de gerenciamento do serviço do centro. Regras mais detalhadas são fornecidas com o download do cartão de jogo.

Para **declarar** um alvo de qualidade, revise os parâmetros aplicáveis a esse destino e informe o que você vai e não aceitará. Recomendamos pontos iniciais, mas você deve fazer a chamada final. A exceção são os dados do KHI, onde os padrões estabelecidos pela Microsoft devem ser usados. Confira o pôster KHI que acompanha.

Para **obter** no jogo, use os cartões fornecidos no lugar de dados do khi e as consultas do sistema. Se no início do jogo você não tiver desenhado um cartão relacionado a um determinado aspecto, você poderá continuar a colá-lo. Se houver um cartão relevante, role a matriz. Se você tiver revertido o número indicado no cartão, terá êxito. Se você rolar pelo número indicado ou acima dele, você deve desenhar outro cartão do baralho. Se o cartão indicar que dois ou mais jogadores precisam ser distribuídos, todos eles devem ser acumulados com êxito.

Para **manter** no jogo, informe em voz alta o plano de gerenciamento de serviços sobre esse aspecto do ambiente do Lync.

</div>

<div>

## <a name="see-also"></a>Confira também


[Guia de rede do Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[Principais indicadores de integridade: a base para manter os servidores de Lync saudáveis](https://go.microsoft.com/fwlink/?linkid=391838)  
[Metodologia de qualidade de chamada do Lync](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

