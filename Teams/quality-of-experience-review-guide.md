---
title: Usar o CQD para gerenciar a qualidade da chamada e da reunião no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Saiba como analisar e gerenciar o desempenho de mídia em tempo real no Microsoft Teams usando o Painel de Qualidade de Chamada (CQD).
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 45a52e438fb74286a571cd81461e3de174f9a38f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675053"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usar o CQD para gerenciar a qualidade da chamada e da reunião no Microsoft Teams 

Este artigo ajudará você , o administrador ou engenheiro de suporte e assistência técnica do Teams, a desenvolver um processo para monitorar e manter a qualidade de chamadas e reuniões para sua organização usando o CQD (Painel de Qualidade de Chamadas) do Microsoft Teams. Nossas diretrizes enfatizam cenários de qualidade de áudio porque quaisquer melhorias de rede feitas para melhorar a experiência de áudio serão convertida em melhorias no vídeo e no compartilhamento.

A chave para essas diretrizes são os dois modelos [de CQD coletados](https://aka.ms/QERtemplates) – recomendamos que você os baixe antes de passar pelas diretrizes neste artigo.

Este artigo pressupõe que você já [configurou o CQD](turning-on-and-using-call-quality-dashboard.md).


## <a name="categories-to-monitor-and-maintain"></a>Categorias a serem monitoradas e mantidas

Depois de distribuir reuniões e voz Teams, você precisará de um plano para monitoramento e manutenção contínuos. Isso garantirá que o Teams esteja sempre em execução de forma ideal. Esse plano deve incluir as principais áreas listadas abaixo. Você também deve estabelecer metas para métricas de qualidade e um plano para solucionar problemas e isolar problemas quando eles ocorrem.

<table>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Qualidade da chamada</strong></td>
<td>
<p>Dividir as métricas por chamadas internas (em sua organização, como VPN, WiFi, com fio) ou chamadas externas</p>
<p>Dividir as métricas criando ou rede</p>
<p>Chamadas VPN</p>
<p>Chamadas usando TCP, UDP ou proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Confiabilidade de chamadas</strong></td>
<td><p>Identificar e corrigir problemas de rede ou firewall</p>
<p>Obtenha informações sobre os percentuais de configuração de chamada e falhas de descarte</p>
<p>Saiba onde ocorre a maioria das falhas de configuração e descarte de chamadas</p>
</td>
</tr>
<tr class="odd">
<td><strong>Pesquisa de usuário</strong></td>
<td>
<p>Usar dados de Rate My Call para saber mais sobre a experiência real dos usuários</p>
<p>Onde estão ocorrendo as experiências ruins?</p>
<p>Correlacionar a experiência ruim com a qualidade da chamada, a confiabilidade e os dispositivos</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivos</strong></td>
<td><p>Saiba quais microfones e alto-falantes são mais comumente usados e seu impacto na qualidade da chamada</p>
<p>Os drivers de áudio, vídeo, USB e WiFi de suporte estão sendo corrigidos regularmente?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clientes</strong></td>
<td>
<p>Saiba quais tipos de cliente e versões estão sendo usados e seu impacto na qualidade e na confiabilidade da chamada  </p>
</ol></td>
</tr>
</tbody>
</table>

Ao avaliar e corrigir continuamente as áreas descritas neste artigo, você pode reduzir o potencial deles para afetar negativamente os usuários. A maioria dos problemas do usuário pode ser agrupada nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy
-   Cobertura insatisfatória da rede Wi-Fi
-   Largura de banda insuficiente
-   VPN
-   Drivers e versões de cliente inconsistentes ou desatualizados
-   Dispositivos de áudio não otimizados ou internos
-   Dispositivos de rede ou sub-redes com problemas

Por meio de planejamento e design adequados antes de implantar o Teams ou o Skype for Business Online, você pode reduzir a quantidade de esforço que será necessária para manter experiências de alta qualidade.

Este artigo se concentra no uso do CQD (Painel de Qualidade de Chamada) Online como a principal ferramenta para relatar e investigar cada área, com ênfase especial no áudio para maximizar a adoção e o impacto. Quaisquer melhorias feitas na rede para melhorar a experiência de áudio também serão diretamente convertida em melhorias no compartilhamento de vídeo e área de trabalho.

Para acelerar sua avaliação, dois modelos [CQD coletados são fornecidos](https://aka.ms/qertemplates) : um é para gerenciar todas as redes e o outro é filtrado somente para redes gerenciadas (internas). Embora os relatórios de modelo todas as redes estejam configurados para exibir informações de construção e rede, eles ainda podem ser usados enquanto você trabalha para coletar e carregar informações de construção. Carregar informações de compilação no CQD permite que o serviço aprimora os relatórios adicionando informações personalizadas de construção, rede e localização, diferenciando internas de sub-redes externas. Para obter mais informações, leia Mapeamento [de construção](CQD-building-mapping.md).

### <a name="intended-audience"></a>Público-alvo pretendido

Este artigo destina-se a ser usado por stakeholders de parceiros e clientes com funções como Líder/Arquiteto de Colaboração, Consultor, Especialista em Gerenciamento de Alterações/Adoção, Líder de Suporte/Suporte Técnico, Líder de Rede, Líder de Área de Trabalho e Administração.

Este artigo também se destina a ser usado pelos campeões de qualidade designados. Para obter mais informações, consulte [a função Defensor da Qualidade](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>O que é qualidade?

Nesse contexto, a qualidade é uma combinação de métricas de serviço e experiência do usuário.


### <a name="service-metrics"></a>Métricas de serviço

As métricas de serviço consistem em métricas específicas baseadas em cliente. Durante cada chamada, o cliente coleta telemetria para a chamada e envia um relatório no final de cada chamada que pode ser acessado posteriormente no CQD ou na análise de chamadas por [usuário](set-up-call-analytics.md). Essas métricas incluem (mas não estão limitadas a):

-   Fluxo ruim (entrada e saída)
-   Taxa de falha de instalação
-   Taxa de falha de queda


#### <a name="poor-stream-rate"></a>Taxa de fluxo ruim

A PSR (taxa de fluxo ruim) representa o percentual geral de fluxos da organização que têm baixa qualidade. Essa métrica destina-se a destacar áreas em que sua organização pode concentrar esforços para ter o impacto mais forte para reduzir esse valor e melhorar a experiência do usuário[](#managed-versus-unmanaged-networks), por isso as redes gerenciadas são o foco principal ao examinar a PSR. Os usuários externos também são importantes, mas a investigação difere em uma base organizacional. Considere fornecer práticas recomendadas para usuários externos e investigar chamadas externas independentemente da organização geral.

A medida real no CQD varia de acordo com a carga de trabalho, mas, para os fins deste artigo, nos concentramos principalmente na medida _Audio Poor Percentage_ . A PSR é composta das cinco médias de métrica de rede descritas na tabela a seguir. Para que um fluxo seja classificado como ruim, apenas uma métrica precisa exceder o limite definido. O CQD fornece o "Pobre Devido a..." medidas para entender melhor qual condição fez com que o fluxo seja classificado como ruim. Para saber mais, leia [a classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> O CQD fornece o "Pobre devido a..." medidas para entender melhor qual condição fez com que o fluxo seja classificado como ruim.


##### <a name="audio-poor-quality-metrics"></a>Métricas de qualidade ruim de áudio

| Média de métrica     | Descrição     | Experiência de usuário |
|-------------|-----------------|-----------------|
| Tremulação \>30 ms        | Essa é a alteração média no atraso entre pacotes sucessivos. Teams e Skype for Business podem se adaptar a alguns níveis de tremulação por meio do buffer. É somente quando a tremulação excede o buffer que um participante percebe os efeitos da tremulação.      | Os pacotes que chegam em velocidades diferentes fazem com que a voz de um locutor pareça robótica.   |
| Taxa de perda de \>pacotes de 10% ou 0,1        | Isso geralmente é definido como uma porcentagem de pacotes que são perdidos. A perda de pacotes afeta diretamente a qualidade do áudio, de pacotes perdidos pequenos e individuais que quase não têm impacto nas perdas de intermitência de trás para trás que fazem com que o áudio seja cortado completamente.     | Os pacotes que estão sendo descartados e não chegam ao destino pretendido causam lacunas na mídia, resultando em sílabas e palavras perdidas e vídeo e compartilhamento irregulares. |
| Tempo de ida e volta \>de 500 ms        | Esse é o tempo necessário para obter um pacote IP do ponto A para o ponto B e de volta para o ponto A. Esse atraso de propagação de rede está vinculado à distância física entre os dois pontos e a velocidade da luz e inclui sobrecarga adicional tomada pelos vários dispositivos no caminho da rede.      | Os pacotes demorando muito para chegar ao destino causam um efeito walkie-talkie.   |


##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Por que preferimos usar fluxos em vez de chamadas?

Fluxos nos informe qual segmento específico da chamada foi ruim- saída ou entrada. Ao examinar a análise de chamadas para uma chamada ruim, determine se a chamada ruim ocorreu devido ao fluxo do chamador (saída) ou ao fluxo do chamador (entrada). Determinar qual fluxo está afetando a qualidade das chamadas é ainda mais importante para conferências. Se você estiver examinando apenas os dados de chamada, verá quantas conferências uma pessoa participa, mas não verá quais pessoas são palestrantes ativas, fazendo o maior compartilhamento de tela.

Os dados de chamada fornecem métricas de uso, mas não necessariamente levarão você à causa raiz da baixa qualidade da chamada. Examinando a direção do fluxo, você pode identificar fatores como uma chamada que não está em uma rede gerenciada, uma chamada de um não funcionário (por exemplo, um fornecedor ou alguém em uma rede diferente). Nesses casos, se a conexão de rede da outra pessoa for ruim, a chamada inteira será sinalizada como ruim. Você não pode fazer nada sobre fatores externos, portanto, esses dados não são úteis.

A direção do fluxo também pode ajudá-lo a identificar dispositivos ou clientes problemáticos.

 - Por exemplo, se você tiver um orçamento limitado para dispositivos e quiser fornecer dispositivos somente para usuários de áudio intenso, use o relatório de uso de áudio (VoIP) e filtre por fluxos de saída e conferência. Procure usuários de áudio de alto volume que estão falando em microfones internos– eles podem se correlacionar com uma qualidade de chamada mais baixa (e talvez você queira fornecer dispositivos de áudio para essas pessoas). Para maior clareza, você pode filtrar a utilização de pacotes, o que permitirá direcionar especialmente usuários de áudio de alto volume. 

  - Outro exemplo envolve o compartilhamento de tela. Se um cliente estiver usando um cliente Teams, o desempenho do compartilhamento de tela poderá ser afetado. Você pode resolver esse problema priorizando as atualizações de cliente para pessoas que fazem muito compartilhamento de tela.

 - Ao identificar qual direção de um fluxo está causando baixa qualidade de chamada, você pode determinar se você tem um problema de QoS ou de largura de banda. Se você ainda não implementou totalmente a QoS ou se marcar apenas pacotes no cliente e não no fluxo de entrada, poderá ver uma qualidade de chamada mais ruim. Ao examinar a direção do fluxo, você pode obter uma exibição mais granular de perda de pacote, latência ou tremulação em uma direção específica. 

   - Por exemplo, digamos que um usuário reclama de áudio robótico enquanto está em uma conexão com fio (tremulação). Examinando o fluxo e a direção, você pode determinar que o problema ocorre no fluxo de entrada, somente para um conjunto específico de sub-redes. Depois de fornecer essas informações à sua equipe de rede, ela poderá rastreá-la para um acelerador de WAN configurado incorretamente que não estava ignorando o tráfego de mídia. Depois que a equipe de rede reconfigura o acelerador de WAN, a tremulação desaparece e a qualidade da chamada melhora. 


#### <a name="setup-failure-rate"></a>Taxa de falha de instalação

A taxa de falha de configuração, também conhecida como medida percentual de falha de configuração de chamada _total_ no CQD, é o número de fluxos em que o caminho de mídia não pôde ser estabelecido entre os pontos de extremidade no início da chamada.

Isso representa qualquer fluxo de mídia que não pôde ser estabelecido. Considerando a gravidade do impacto desse problema na experiência do usuário, a meta é reduzir esse valor o mais próximo possível de zero. Um valor alto para essa métrica é mais comum em novas implantações com regras de firewall incompletas do que em uma implantação madura, mas ainda é importante observar regularmente.

Essa métrica é calculada usando o número total de fluxos que não foram configurados divididos pelo número total de fluxos que enviou um CDR (registro de detalhes de chamada) bem-sucedido:

-   **Taxa de falha de instalação** = Contagem total de fluxos com falha na instalação da chamada/Contagem total de fluxos disponíveis do CDR

#### <a name="drop-failure-rate"></a>Taxa de falha de queda

A taxa de falha de queda, também conhecida  como a medida percentual de falha total de chamada descartada no CQD, é o percentual de fluxos estabelecidos com êxito em que o caminho de mídia não foi encerrado normalmente.

Isso representa qualquer fluxo de mídia que foi encerrado inesperadamente. Embora o impacto disso não seja tão grave quanto um fluxo que não foi configurado, ele ainda afeta negativamente a experiência do usuário. As quedas de mídia repentinas e frequentes não só podem ter um impacto grave na experiência do usuário, como resultam na necessidade de os usuários se reconectarem, resultando em perda de produtividade (sem mencionar frustração).

A métrica é calculada usando o número total de fluxos descartados divididos pela contagem total de fluxos que foram configurados com êxito:

-   **Taxa de falha de queda** = Contagem total de fluxos de chamada descartada/contagem de fluxos de configuração de chamada total bem-sucedida

### <a name="define-your-target-metrics"></a>Definir suas métricas de destino

Esta seção discute algumas das principais métricas de serviço que usamos para avaliar a integridade dos serviços. Ao avaliar e impulsionar continuamente os esforços para manter essas métricas abaixo das metas definidas, você ajudará a garantir que os usuários experimentem uma qualidade de chamada consistente e confiável. Como ponto de partida, use os destinos sugeridos na tabela abaixo. Ajuste as metas conforme necessário para atender aos seus objetivos de negócios.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de rede</th><th rowspan="1">Metas de qualidade</th><th colspan="2">Destinos de confiabilidade</th></tr>
<tr><th>Taxa de fluxo de áudio ruim</th><th>Taxa de falha de instalação</th><th>Taxa de falha de queda</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Geral</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conferências</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interno com fio</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interno de 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interno de 2,4 GHz</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Geral</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Com fio/Wi-Fi 5 GHz interno</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Com fio/Wi-Fi 5 GHz no geral</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>Geral</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Experiência de usuário

Analisar a experiência do usuário é mais arte do que ciência, porque as métricas coletadas aqui nem sempre significam que há um problema com a rede ou o serviço, mas, em vez disso, eles simplesmente indicam que o usuário percebe um problema. O CQD inclui um mecanismo de pesquisa interno — Rate My Call (RMC) — para ajudar a medir a experiência geral do usuário. O RMC fornecerá informações sobre as seguintes perguntas da perspectiva dos usuários:

-   Eu sei como usar a solução?
-   A solução é fácil de usar e intuitiva e dá suporte às minhas necessidades de comunicação diárias?
-   A solução me ajuda a fazer meu trabalho?
-   Qual é a minha percepção geral da solução?
-   Posso usar a solução a qualquer momento, independentemente de onde eu esteja?
-   Posso configurar e manter uma chamada?

#### <a name="rate-my-call"></a>Classificar Minha Chamada 

Rate My Call (RMC) é integrado Teams e Skype for Business. Ele aparece automaticamente após uma em cada 10 chamadas ou 10%. Esta breve pesquisa pede ao usuário para classificar a chamada e fornecer um pouco de contexto para o motivo pelo qual a qualidade da chamada pode ter sido ruim. Uma ou duas classificações são consideradas ruins, três a quatro é boa e cinco é excelente. Embora seja um indicador de um pouco de retardo, essa é uma métrica útil para descobrir problemas que as métricas de serviço podem perder.

> [!Note]
> O fator humano: os usuários geralmente ignoram a pesquisa quando a qualidade da chamada é boa e a preenchem quando a qualidade da chamada é ruim. Como resultado, os relatórios do RMC podem ser distorcidos para o lado ruim, mesmo enquanto as métricas de serviço são boas.

Você pode usar o CQD para relatar respostas de usuário RMC e relatórios de exemplo estão incluídos no modelo CQD. No entanto, eles não são discutidos em detalhes neste artigo. 

#### <a name="client-and-device-readiness"></a>Preparação do cliente e do dispositivo

Você precisa de uma estratégia sólida de cliente e dispositivo para ajudar a garantir que os usuários tenham uma experiência de usuário consistente e positiva. Alguns princípios-chave orientam cada estratégia de preparação.

##### <a name="client-readiness"></a>Preparação do cliente

Manter o Teams cliente atualizado garante que os usuários sempre estejam obtendo a melhor experiência possível. A Microsoft lança atualizações [frequentes](teams-client-update.md) para o cliente Teams (a atualização é instalada em segundo plano, a menos que você tenha desativado essa funcionalidade , o que não recomendamos). Também é importante lembrar-se de corrigir drivers de rede, vídeo, USB e áudio, pois eles geralmente são ignorados e podem afetar a qualidade da chamada e da reunião. Considere adicionar drivers de rede, Wi-Fi, vídeo, USB e áudio ao processo de gerenciamento de patch atual.


##### <a name="device-readiness"></a>Preparação do dispositivo

Nenhuma estratégia única pode afetar a experiência do usuário mais do que a estratégia de preparação do dispositivo. Por exemplo, os usuários que dependem de seus alto-falantes de laptop e microfone experimentarão muito ruído de fundo em chamadas e reuniões. Teams é projetado para funcionar com quase qualquer dispositivo, mas se você estiver tendo problemas relacionados ao dispositivo, confira Telefone [para](./devices/phones-for-teams.md) Teams.


### <a name="categories-of-quality"></a>Categorias de qualidade

Operacionalizar um conjunto de práticas de gerenciamento de qualidade – isso oferece a melhor chance de uma boa chamada e qualidade de reunião. Um plano de gerenciamento de boa qualidade aborda estas categorias:

-   **Rede:** Qualidade de áudio focada na métrica PSR (Taxa de Fluxo Ruim), uso de TCP, sub-redes com fio e sem fio e identificação do uso de proxies HTTP e VPN

-   **Extremidade:** Dispositivos de áudio e clientes atualizados

-   **Gerenciamento de Serviços:** Essa categoria compreende duas seções:

    -   Primeiro, é responsabilidade da Microsoft gerenciar e manter os serviços Teams e Skype for Business Online.

    -   Em segundo lugar estão as tarefas que sua organização gerencia para garantir o acesso confiável ao serviço, como atualizar informações de criação e manter firewalls para novos endereços IP do Office 365 à medida que a infraestrutura é adicionada ao serviço.

![Graph das categorias de qualidade em uma organização.](media/qerguide-image-categories.png "As categorias de qualidade em uma organização: gerenciamento de serviços, pontos de extremidade e rede.")

Examine a lista de tarefas a seguir recomendadas para manter a qualidade. Você deve executar essas tarefas regularmente , por exemplo, semanalmente.

#### <a name="service-management-tasks"></a>Tarefas de gerenciamento de serviço

Essas tarefas vão desde garantir que haja largura de banda suficiente para alcançar o serviço sem saturar links da Internet, validar que a QoS (qualidade de serviço) está em vigor em todas as áreas de rede gerenciadas e manter-se sobre os [intervalos de IP Office 365 em firewalls](/microsoft-365/enterprise/urls-and-ip-address-ranges).

#### <a name="network-tasks"></a>Tarefas de rede

Há duas categorias de tarefas de rede: confiabilidade e qualidade. A confiabilidade se concentra em medir a capacidade do usuário de fazer chamadas com êxito e permanecer conectado. A qualidade se concentra na telemetria agregada enviada ao Teams e Skype for Business Online pelo cliente do usuário durante a chamada e depois que ela foi encerrada. 

Dado o impacto crítico que a confiabilidade tem na experiência do usuário, recomendamos que você avalie e investigue as métricas de confiabilidade antes de se aprofundar na qualidade. 

#### <a name="endpoints-tasks"></a>Tarefas de pontos de extremidade

A tarefa principal nessa categoria removendo quaisquer obstáculos para [atualizações Teams cliente regulares](teams-client-update.md). Por padrão, Teams é atualizado automaticamente regularmente (a menos que você desative essa configuração, o que não recomendamos). 

Você também deve monitorar dispositivos e fornecer atualizações sempre que identificar problemas relacionados a um dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usar o CQD para gerenciar a qualidade da chamada

Depois de configurar [o CQD](turning-on-and-using-call-quality-dashboard.md), você estará pronto para começar a usá-lo para gerenciar a qualidade da chamada e da reunião para sua organização.

A maioria dos problemas Teams desempenho se enquadram nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy
-   Cobertura insatisfatória da rede Wi-Fi
-   Largura de banda insuficiente
-   VPN
-   Drivers e versões de cliente inconsistentes ou desatualizados
-   Dispositivos de áudio não otimizados ou internos
-   Dispositivos de rede ou sub-redes com problemas

Se você aproveitar o tempo antes de implantar o Teams para avaliar essas áreas e corrigir as deficiências, reduzirá a quantidade de esforço necessária para manter uma experiência de Teams alta qualidade para todos os seus usuários. Para obter ajuda para avaliar sua rede em preparação para Teams distribuição, leia Supervisor para Teams [](use-advisor-teams-roll-out.md) e prepare sua rede para [Teams](prepare-network.md).

### <a name="expectations-using-cqd"></a>Expectativas usando o CQD

Use o CQD (Painel de Qualidade de Chamadas) para obter informações sobre a qualidade das chamadas feitas usando Teams e Skype for Business serviços. O CQD foi projetado para ajudar Teams e Skype for Business administradores e engenheiros de rede a otimizar a rede e ficar atento à qualidade, à confiabilidade e à experiência do usuário. O CQD examina a telemetria agregada para toda a organização, em que os padrões gerais podem se tornar aparentes; isso permite que você faça avaliações informadas e planeje a correção. O CQD fornece relatórios de métricas que fornecem informações sobre a qualidade geral, a confiabilidade e a experiência do usuário.

O CQD, embora seja útil para analisar tendências e sub-redes, nem sempre fornece uma causa específica para um determinado cenário. É importante entender isso e definir a expectativa correta ao usar o CQD:

-   O CQD não fornecerá a causa raiz para cada cenário
-   O CQD não conterá Sistema de Telefonia ou Audioconferência fluxos
-   O CQD chamará áreas para uma investigação mais aprofundada com base nas tendências

### <a name="cqd-reports-overview"></a>Visão geral dos relatórios do CQD

Use o menu suspenso na parte superior da tela para abrir um relatório. Para obter uma lista dos dados fornecidos em cada relatório, leia [Os dados disponíveis em relatórios CQD](CQD-data-and-reports.md#data-available-in-cqd-reports).

Novidade em janeiro de 2020: [baixe Power BI de consulta para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos Power BI personalizados que você pode usar para analisar e relatar seus dados CQD.


### <a name="teams-vs-skype-for-business"></a>Teams versus Skype for Business

O CQD pode relatar Teams e Skype for Business. No entanto, pode haver ocasiões em que você deseja desenvolver um relatório para examinar Teams telemetria separada de Skype for Business.

#### <a name="summary-reports"></a>Relatórios de resumo

Para modificar a página de relatórios de resumo para examinar apenas Teams ou Skype for Business, selecione o menu suspenso Filtro de  Produto na parte superior da tela e, em seguida, selecione o produto desejado.

![Captura de tela do menu suspenso mostrando as opções de filtro.](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Relatórios detalhados

Para filtrar todos os relatórios detalhados, na barra do navegador, acrescente o seguinte ao final da URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Exemplo:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obter mais informações sobre filtros de URL, leia [Relatórios de filtragem](CQD-data-and-reports.md#report-filters) posteriormente nesta seção.

Para filtrar um relatório detalhado individual, adicione o filtro ``Is Teams`` ao relatório e defina-o como True ou False.

![Captura de tela da página Adicionar filtro.](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Redes gerenciadas versus não gerenciadas

Por padrão, todos os pontos de extremidade no CQD são classificados como externos. Assim que um arquivo de construção for introduzido, podemos começar a examinar os dados do ponto de extremidade gerenciado. Conforme discutido anteriormente, as redes no CQD são definidas como:

-   Uma _rede gerenciada_, geralmente conhecida como interna ou interna, pode ser influenciada e controlada pela organização. Isso inclui a LAN interna, a WAN remota e a VPN.
-   Uma _rede não gerenciada_, geralmente conhecida como externa ou externa, não pode ser influenciada ou controlada pela organização. Um exemplo de uma rede não gerenciada é uma rede de hotel ou aeroporto.

### <a name="dimensions-measures-and-filters"></a>Dimensões, medidas e filtros

Uma consulta CQD bem formada contém todos os três dos seguintes parâmetros:

-   **Dimensão:** Como eu quero dinamização nos dados.

-   **Medida:** O que eu quero relatar.

-   **Filtro:** Como quero reduzir o conjunto de dados que a consulta retorna.

Outra maneira de examinar isso é que uma dimensão _é a função_ de agrupamento, uma medida  é os dados nos quais estou interessado e um filtro é como  eu quero restringir os resultados àqueles que são relevantes para minha consulta.

Um exemplo de uma consulta bem formada é Show **me Poor Fluxos [Measure] by Subnet [Dimension] for Building 6 [Filter]**. Para obter mais informações, [consulte Dimensões e medidas disponíveis no CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="first-vs-second"></a>Primeiro vs. segundo 

Muitas das dimensões e medidas no CQD são classificadas como primeira ou segunda. O CQD não usa campos de chamador/receptor — eles foram renomeados primeiro e segundo  porque há  etapas interveniente entre o chamador e o chamador. A lógica a seguir determina qual ponto de extremidade envolvido é rotulado como primeiro:

-   **Primeiro** sempre será um ponto de extremidade do servidor (Servidor de Conferência, Servidor de Mediação e assim por diante) se um servidor estiver envolvido no fluxo ou na chamada.

-   **O** segundo sempre será um ponto de extremidade do cliente, a menos que o fluxo esteja entre dois pontos de extremidade do servidor.

-   Se ambos os pontos de extremidade forem do mesmo tipo, a escolha será baseada primeiro na ordenação interna da categoria do agente do usuário. Isso garante que a ordenação seja consistente.

Para obter mais informações sobre como determinar o primeiro ou o segundo ponto de extremidade quando ambos forem iguais, consulte Dimensões e medidas disponíveis [no CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="stream-vs-call"></a>Fluxo versus chamada

Você precisa entender a diferença entre uma chamada e um fluxo para escolher corretamente quais dimensões ou medidas serão observadas no CQD. Embora o foco principal do CQD esteja em fluxos, as medidas baseadas em chamadas também estão disponíveis.

-   **Fluxo:** Existe _um fluxo_ entre apenas dois pontos de extremidade. Há apenas um fluxo para cada direção e dois fluxos são necessários para comunicação. Fluxos são úteis para investigar edifícios, redes ou sub-redes. Em alguns casos, a chamada e o fluxo são usados no nome da medida (por exemplo, Fluxo de Instalação de Chamada ou Fluxo de Chamada Descartado). Eles ainda são classificados como fluxos.

-   **Chamar:** Uma _chamada_ é um agrupamento de todos os fluxos de todos os participantes. Uma chamada consiste em, no mínimo, dois fluxos. Uma única chamada terá pelo menos dois pontos de extremidade, cada um com um mínimo de um fluxo.

Para obter diretrizes adicionais sobre se a dimensão ou medida está se referindo a uma chamada ou um fluxo, consulte Dimensões e medidas [disponíveis no CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="good-poor-and-unclassified-calls"></a>Chamadas boas, pobres e não classificadas

Uma chamada é categorizada como boa, ruim ou não classificada. Vamos dar um tempo para falar mais detalhadamente sobre cada um deles.

-   **Bom ou ruim:** Uma chamada boa ou ruim consiste em uma chamada que contém um conjunto completo de métricas de serviço, para o qual um relatório de QoE completo foi gerado e recebido pelo serviço. Determinar se um fluxo é bom ou ruim é descrito [anteriormente neste artigo](#poor-stream-rate).

-   **Unclassified:** Um fluxo não classificado não contém um conjunto completo de métricas de serviço. Essas chamadas podem ser curtas, geralmente menos de 60 segundos, em que as médias não puderam ser computadas e um relatório de QoE não foi gerado. O motivo mais comum para as chamadas não serem classificadas é que houve pouca ou nenhuma utilização de pacotes. Um exemplo disso seria um participante que ingressa em uma reunião em mudo e nunca fala. O participante está recebendo, mas não transmitindo, mídia. Sem a transmissão de mídia, não haverá nenhuma métrica disponível para o CQD usar para classificar o fluxo de mídia de saída do ponto de extremidade.

Para saber mais, leia [a classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Sub-redes comuns

Sub-redes comuns são sub-redes privadas específicas que são usadas por hotéis, redes de residência, hotspots e áreas semelhantes. Essas sub-redes são difíceis de realizar a triagem devido ao uso difundido. Se sua organização usar uma dessas sub-redes comuns, recomendamos que você mova essa rede para outra sub-rede. Isso facilitará o relatório no CQD. Quando notados, os relatórios no modelo Todas as Redes foram configurados para excluir essas sub-redes para eliminá-las como uma fonte de baixa qualidade. As sub-redes comuns são definidas abaixo; seu impacto variará de acordo com a organização.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Ao investigar uma rede gerenciada que usa uma sub-rede comum, você precisará usar a segunda dimensão de IP local reflexivo para agrupar sub-redes. Essa dimensão contém o endereço IP público do ponto de extremidade.


## <a name="reliability-investigations"></a>Investigações de confiabilidade

A primeira etapa para melhorar a qualidade é avaliar o estado de confiabilidade em toda a organização. Como a confiabilidade é vital para uma experiência positiva do usuário, começamos com os dois componentes que medem a confiabilidade:

1.  **Falhas de instalação:** Não foi possível estabelecer a chamada.

2.  **Descartar falhas:** A chamada foi estabelecida e encerrada inesperadamente.

Ao longo desta seção, abordaremos os métodos para investigar ambas as áreas.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo. No entanto, os métodos de investigação explicados abaixo ainda se aplicam. Consulte a descrição do relatório individual para obter mais informações.


### <a name="setup-failures"></a>Falhas de instalação

Priorize a correção de falhas de configuração nessa área primeiro, pois essas falhas têm um impacto negativo significativo na experiência do usuário.

Comece sua investigação avaliando o percentual de falhas gerais de configuração para a organização e, em seguida, priorize as áreas de investigação com base no percentual mais alto por compilação ou rede. 

#### <a name="setup-failure-trend-analysis"></a>Análise de tendência de falha de instalação

Esse relatório exibe a quantidade total de fluxos, falhas de configuração de fluxo e a taxa de falha de configuração do fluxo. Aponte para qualquer uma das colunas para exibir seus valores individuais. 

##### <a name="analysis"></a>Análise

Usando esse relatório, você pode responder às seguintes perguntas e determinar seu próximo curso de ação:

-   Qual é o percentual total de falha de configuração de chamada para o mês atual?

-   O percentual total de falha de configuração de chamada está abaixo ou acima da métrica de destino definida?

-   A tendência de falha é pior ou melhor do que o mês anterior?

-   A tendência de falha está aumentando, estável ou diminuindo?

Independentemente de suas respostas a essas perguntas, reserve um tempo para investigar mais usando os sub-relatórios complementares para procurar quaisquer edifícios individuais ou sub-redes que possam precisar de correção. Embora a taxa de falha geral possa estar abaixo da métrica de destino, as taxas de falha para um ou mais edifícios ou redes podem estar acima da métrica de destino e precisam de investigação.

#### <a name="setup-failure-investigations"></a>Investigações de falha de instalação 

Esse relatório de resumo é usado para descobrir e isolar quaisquer edifícios ou redes que possam precisar de correção.

> [!NOTE]
> Certifique-se de ajustar o filtro de relatório ano mês para o mês atual. Selecione **Editar** e ajuste o filtro **de relatório ano** mês para salvar o novo mês padrão.

##### <a name="remediation"></a>Remediação 

Concentre seus primeiros esforços de correção em edifícios ou sub-redes que têm o maior volume de falhas. Isso maximizará o impacto na experiência do usuário e ajudará a reduzir rapidamente a taxa de falhas de configuração de chamadas organizacionais. A tabela a seguir lista os dois motivos para falhas de configuração, conforme relatado pelo CQD.

| Motivo das falhas de configuração de chamada       | Causa típica                    |
|----------------------------------|----------------------------------|
| Regra de isenção de inspeção profunda de pacotes FW ausente | Indica que o equipamento de rede ao longo do caminho impediu que o caminho de mídia seja estabelecido devido a regras profundas de inspeção de pacotes. Isso provavelmente ocorre devido a regras de firewall não estar configuradas corretamente. Nesse cenário, o handshake TCP foi bem-sucedido, mas o handshake SSL não.      |
| Regra de exceção de bloco ip de FW ausente      | Indica que o equipamento de rede ao longo do caminho impediu que o caminho de mídia seja estabelecido para a rede Microsoft 365 ou Office 365 rede. Isso pode ser devido a regras de proxy ou firewall não estar configuradas corretamente para permitir o acesso a endereços IP e portas usadas para Teams e Skype for Business tráfego. |

Ao começar a correção, você pode concentrar seus esforços em um edifício ou sub-rede específico. Como mostra a tabela anterior, esses problemas ocorrem devido a configurações de firewall ou proxy. Examine as opções na tabela a seguir para obter ações de correção.

|      Remediação      |Orientação  |
|-----------------------|----------|
| Configurar firewalls | Trabalhe com sua equipe de rede e verifique a configuração de firewalls na [Office 365 de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).<br><br>Verifique se as [sub-redes de mídia e](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) as portas estão incluídas nas regras de firewall. <br><br>Verifique se as [portas necessárias](prepare-network.md) estão abertas no firewall. O UDP deve ter prioridade porque o TCP é considerado um protocolo de failback para compartilhamento de tela baseado em áudio, vídeo e vídeo, e seu uso afetará a qualidade da chamada. O compartilhamento de aplicativo RDP herdado usa apenas TCP.|

### <a name="drop-failures"></a>Descartar falhas

Ao contrário dos códigos de falha de instalação, o CQD não tem código de falha de soltar para indicar por que ocorrem falhas de soltar, o que dificulta a isolação de uma causa raiz específica. Para melhorar as falhas de descarte de triagem, use uma abordagem inferida. Ao corrigir quaisquer áreas de interesse para mídia, corrigir clientes e drivers e impulsionar o uso de dispositivos certificados para Teams e Skype for Business, você pode esperar que falhas de queda recuse.

#### <a name="drop-failure-trend-analysis"></a>Análise de tendência de falha de descarte

Esse relatório exibe a quantidade total de fluxos de áudio, o total de falhas de queda e a taxa de falha de queda. Aponte para qualquer uma das colunas para exibir seus valores. 


##### <a name="analysis"></a>Análise

Usando esse tipo de relatório, você pode responder às seguintes perguntas:

-   Qual é a taxa de falha de queda atual?
-   A taxa de falha de queda está abaixo da métrica de destino definida?
-   A tendência de falha é pior ou melhor do que o mês anterior?
-   A tendência de falha está aumentando, estável ou diminuindo?

Independentemente das respostas às perguntas acima, reserve um tempo para investigar usando os sub-relatórios para procurar quaisquer edifícios ou redes que possam precisar de correção. Embora a taxa de falha geral de queda possa estar abaixo da métrica de destino, a taxa de falha de queda para um ou mais edifícios ou redes pode estar acima da métrica de destino e precisar de investigação.

#### <a name="drop-failure-investigations"></a>Descartar investigações de falha

Falhas relatadas aqui indicam que a chamada foi descartada inesperadamente e resultou em uma experiência de usuário negativa. Ao contrário dos relatórios mais populares, esses relatórios fornecem informações adicionais sobre sub-redes específicas que precisam de mais investigação.


##### <a name="remediation"></a>Remediação

Usando os relatórios de tabela incluídos, você pode isolar áreas de problema na rede em que a taxa de queda está acima da métrica de destino que você definiu. Concentre seus primeiros esforços de correção em edifícios ou sub-redes que têm a maior contagem total de fluxos para fazer o maior impacto.

Causas comuns de quedas de chamada:

-   Saída de internet ou rede sub provisionada
-   Nenhuma QoS configurada em redes restritas
-   Versões mais antigas do cliente
-   Comportamento do usuário

Depois de descobrir suas áreas problemáticas, você [](use-call-analytics-to-troubleshoot-poor-call-quality.md) pode usar a análise de chamadas por usuário para examinar ainda mais os usuários nesse prédio em caso de problemas específicos. A análise de chamadas contém dados EUII adicionais e pode ser útil para isolar ainda mais os possíveis motivos para as falhas de descarte.

Independentemente da próxima etapa, é uma boa prática notificar o suporte técnico de que um problema foi descoberto com edifícios ou sub-redes específicos. Isso permite que a assistência técnica responda rapidamente às chamadas de entrada e aos usuários de triagem com mais eficiência. Os usuários sinalizados podem ser relatados de volta à equipe de engenharia para investigação posterior.

A tabela a seguir lista alguns métodos comuns para gerenciar e corrigir falhas de soltar.

| Remediação                              | Orientação                      |
|------------------------------------------|-------------------------------|
| **Rede/Internet**                         | **Congestionamento**: trabalhe com sua equipe de rede para monitorar a largura de banda em edifícios/sub-redes específicos para confirmar se há problemas com a superutilização. Se você confirmar que há congestionamento de rede, considere aumentar a largura de banda para esse edifício ou aplicar a QoS. Use os relatórios de resumo [do Quality Poor Stream](#quality-investigations) incluídos para examinar as sub-redes com problemas com tremulação, latência e perda de pacotes, pois eles geralmente precederão um fluxo descartado.<br><br>**QoS**: se o aumento da largura de banda for impraticável ou proibitivo de custo, considere implementar a QoS. Essa ferramenta é muito eficaz no gerenciamento de tráfego congestionado e pode garantir que os pacotes de mídia na rede gerenciada sejam priorizados acima do tráfego de não mídia. Como alternativa, se não houver nenhuma evidência clara de que a largura de banda é a culpada, considere estas soluções:<ul><li>[Microsoft Teams de QoS](qos-in-teams.md)</li></ul><br>**Executar** uma avaliação de preparação de rede: uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com alterações de largura de banda e rede e práticas de rede recomendadas para Teams e Skype for Business. Usando a tabela anterior como sua fonte, você tem uma lista de edifícios ou sub-redes que são excelentes candidatos para uma avaliação.<ul><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li></ul> |
| **Clientes (somente Skype for Business Online)** | Alguns clientes Skype for Business mais antigos têm problemas documentados e conhecidos com a confiabilidade de mídia. Examine os relatórios da Análise de Chamadas de vários usuários afetados ou crie um relatório de tabela de versão do cliente personalizado no CQD filtrado para edifícios ou sub-redes específicos com a medida % de falha total de chamada descartada. Essas informações ajudarão você a entender se existe uma relação entre quedas de chamada nesse prédio específico e uma versão específica do cliente.     |
| **Dispositivos**                                  |Se os dispositivos forem o culpado em problemas de qualidade de chamada, considere atualizar dispositivos incorretos. Leia [Telefones para Teams](./devices/phones-for-teams.md) para saber mais. |
| **Comportamento do usuário**                            | Se você determinar que nem rede, dispositivos ou clientes são o problema, considere desenvolver uma estratégia de adoção do usuário para instruir os usuários a ingressar e sair melhor das reuniões. Um usuário Teams e Skype for Business mais inteligente produzirá uma melhor experiência do usuário para todos os participantes da reunião. Por exemplo, um usuário que colocar seu laptop para suspensão (fechando a tampa) sem sair da reunião será classificado como uma queda inesperada de chamada.   |

## <a name="quality-investigations"></a>Investigações de qualidade

A próxima etapa para avaliar o estado da qualidade do áudio em toda a organização é investigar a PSR (Taxa de Fluxo Ruim), o TCP e o uso de proxy. É importante lembrar que os dados do CQD não fornecem uma causa raiz específica, mas, em vez disso, fornecem áreas com problemas prováveis para iniciar uma conversa colaborativa com as equipes apropriadas para atividades de correção. 

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo; no entanto, os métodos de investigação explicados abaixo ainda se aplicarão a esses relatórios. Consulte a descrição do relatório individual para obter mais informações. 

### <a name="quality"></a>Qualidade

Os percentuais de PSR são usados para indicar se a organização está a atender às metas de métrica definidas para uma determinada área de foco. É importante observar que, mesmo que os percentuais de alto nível estejam dentro do destino definido, sub-redes individuais ou edifícios podem não atender aos destinos definidos e, portanto, precisam de mais investigação. Por exemplo, se o percentual geral de PSR de áudio for de 2% em abril, que atenda ao destino de exemplo, os edifícios individuais e as sub-redes ainda poderão ter experiências ruins, dependendo da distribuição geral desses 2%. 

Para avaliar o percentual de fluxos ruins, use os relatórios de qualidade. Vários relatórios de qualidade são fornecidos para examinar as métricas de geral, conferência, duas partes, chamada PSTN, VPN e salas de reunião. Relatórios mensais, semanais e diários são fornecidos para auxiliar nesse processo. Relatórios semanais e diários são limitados ao modelo de Redes Gerenciadas para aumentar sua eficácia e reduzir o ruído. 

#### <a name="quality-trend-analysis"></a>Análise de tendência de qualidade

Os relatórios populares exibem informações de qualidade ao longo do tempo e são usados para ajudar a identificar e entender as tendências de qualidade em cada área de interesse. Conforme mencionado acima, há árvores de relatório incluídas nos modelos para investigar a qualidade; conferência, duas partes, chamada PSTN, VPN e salas de reunião. Para fins de análise de qualidade, o processo investigativo é o mesmo. No entanto, recomendamos que você comece com a conferência primeiro, pois quaisquer melhorias na qualidade da conferência também afetarão positivamente todas as outras áreas. 

> [!Note]
> Investigar chamadas PSTN e salas de reunião de duas partes é semelhante a investigar conferências. O foco é isolar edifícios ou sub-redes que têm a pior qualidade e identificar o motivo da baixa qualidade.

> [!Important]
> Os relatórios baseados em VPN são filtrados usando a segunda dimensão vpn. Essa dimensão exige que o adaptador de rede VPN seja registrado corretamente como um Adaptador de Acesso Remoto. Os fornecedores de VPN não usam esse sinalizador de forma confiável e sua quilometragem variará dependendo do fornecedor de VPN implantado em sua organização. Modifique [os relatórios de VPN](CQD-upload-tenant-building-data.md#vpn) , se necessário, usando o nome do edifício ou da rede.

##### <a name="investigation"></a>Investigação

Usando esses relatórios, você pode responder às seguintes perguntas:

-   Qual é o total de PSR para o mês atual?
-   O PSR está abaixo da métrica de destino definida?
-   A PSR é pior ou melhor do que o mês anterior?
-   A tendência de PSR está aumentando, estável ou diminuindo?

Independentemente das respostas às perguntas acima, reserve um tempo para investigar usando os sub-relatórios para procurar quaisquer edifícios ou sub-redes que possam precisar de investigação. Embora o PSR geral possa estar abaixo da métrica de destino, geralmente o PSR para um ou mais edifícios ou redes está acima da métrica e precisa de correção.

#### <a name="quality-investigations"></a>Investigações de qualidade

Os relatórios de resumo de qualidade fornecem insights mais aprofundados sobre o que contribuiu para que os fluxos sejam classificados como ruins e ajuda a isolar áreas problemáticas na rede gerenciada.

Embora as dimensões usadas possam diferir ligeiramente entre o relatório, cada relatório incluirá medidas para o total de fluxos, fluxos totais ruins, PSR e baixa qualidade devido a. Relatórios foram criados para cada área de interesse: conferência, duas partes, chamada PSTN, VPN e salas de reunião. O modelo rede gerenciada inclui relatórios adicionais para aproveitar as informações de localização carregadas por meio do arquivo de construção.


> [!Note]
> As sub-redes comuns são difíceis de realizar a triagem devido ao uso difundido. Um relatório separado que exibe o IP público do cliente (SEGUNDO IP Local Reflexivo) foi adicionado ao modelo Todas as Redes para auxiliar na correção de escritórios que usam redes comuns.


![Captura de tela mostrando o resumo de fluxo de áudio ruim.](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Remediação

Concentre seus esforços de correção em edifícios ou sub-redes que têm o maior volume de fluxos, pois isso maximizará o impacto e ajudará a melhorar a experiência do usuário rapidamente. Use as medidas de tremulação, perda de pacotes e RTT (tempo de ida e volta) para entender o que está contribuindo para a baixa qualidade (é possível que haja mais de um problema):

-   **Tremulação**: os pacotes de mídia estão chegando em velocidades diferentes, o que faz com que um alto-falante pareça robótico.
-   **Perda de** pacotes: pacotes de mídia estão sendo descartados, o que cria o efeito de palavras ou sílabas ausentes.
-   **RTT**: Os pacotes de mídia estão demorando muito para chegar ao destino, o que cria um efeito walkie-talkie.

Para ajudar sua investigação sobre problemas de qualidade, use [a análise de chamadas por usuário](use-call-analytics-to-troubleshoot-poor-call-quality.md). Com a Análise de Chamadas, você pode examinar uma conferência específica ou o relatório de chamada do usuário. Esse relatório conterá dados EUII/PII e será útil quando você estiver procurando a causa de uma falha. Depois de saber qual prédio é afetado, deve ser simples rastrear os usuários nesse prédio. 

Não se esqueça de informar à assistência técnica que essas redes estão enfrentando problemas de qualidade, para que elas possam fazer uma triagem rápida e responder a chamadas recebidas.

| Remediação                              | Orientação                         |
|------------------------------------------|----------------------------------|
| **Redes**                                 | **Congestionamento**: uma rede subutilizada ou sub provisionada pode causar problemas com a qualidade da mídia. Trabalhe com a equipe de rede para determinar se as conexões de rede do usuário com o ponto de saída da Internet têm largura de banda suficiente para dar suporte à mídia. <br><br>**Executar** uma avaliação de preparação de rede: uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com alterações de largura de banda e rede e práticas de rede recomendadas para Teams e Skype for Business. Usando a tabela anterior como sua fonte, você tem uma lista de edifícios ou sub-redes que são excelentes candidatos para uma avaliação.<ul><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li></ul>|
| **Qualidade de serviço (QoS)**  | A QoS é uma ferramenta comprovada para ajudar a priorizar pacotes em uma rede congestionada para garantir que eles cheguem ao destino intactos e a tempo. Considere implementar a QoS em toda a sua organização para maximizar a qualidade da experiência do usuário em que a largura de banda é restrita. A QoS ajudará a resolver problemas normalmente associados a altos níveis de perda de pacotes e, em menor grau, tremulação e tempos de ida e volta.<ul><li>[Teams diretrizes de QoS](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Wi-Fi pode ter um impacto significativo na qualidade da chamada. Wi-Fi implantações normalmente não levam em consideração os requisitos de rede para serviços VoIP e geralmente são uma fonte de baixa qualidade. Para obter mais informações sobre como otimizar sua infraestrutura Wi-Fi, consulte [este artigo sobre Wi-Fi planejamento](/skypeforbusiness/certification/plan-wifi).<br><br>**Driver sem** fio: verifique se os drivers sem fio estão atualizados. Isso ajudará a atenuar qualquer experiência de usuário ruim relacionada a um driver desatualizado. Muitas organizações não incluem drivers sem fio em seus ciclos de patch, e esses drivers podem ficar sem patch por anos. Muitos problemas sem fio são resolvidos garantindo que os drivers sem fio estejam atualizados.<br><br>**WMM**: WmM (Wireless Multimedia Extensions), também conhecido como Wi-Fi Multimídia, fornece recursos básicos de QoS para redes sem fio. Redes sem fio modernas devem dar suporte a muitos dispositivos. Esses dispositivos competem por largura de banda e podem levar a problemas de qualidade para serviços VoIP, em que velocidade e latência são vitais. Consulte seu fornecedor sem fio para obter informações específicas e considere implementar o WMM em sua rede sem fio para priorizar Skype for Business e Teams mídia.<br><br>**Densidade do ponto de acesso**: os pontos de acesso podem estar muito distantes ou não estar em um local ideal. Para minimizar possíveis interferências, coloque pontos de acesso extras em salas de conferência e em locais que não estão obstruídos por paredes ou outros objetos em que o sinal Wi-Fi está fraco.<br><br>**2,4 GHz versus 5 GHz: 5 GHz** fornece menos interferência em segundo plano e velocidades mais altas e deve ser priorizado ao implantar VoIP por Wi-Fi. No entanto, 5 GHz não é tão forte quanto 2,4 GHz e não penetra paredes tão facilmente. Examine o layout do prédio para determinar em qual frequência você pode contar para a melhor conexão. |
|**Dispositivo de rede** | Organizações maiores podem ter centenas de dispositivos espalhados pela rede. Trabalhe com sua equipe de rede para garantir que os dispositivos de rede do usuário para a Internet sejam mantidos e atualizados. |
| **VPN**  | Os dispositivos VPN não são tradicionalmente projetados para lidar com cargas de trabalho de mídia em tempo real. Algumas configurações de VPN proíbem o uso de UDP (que é o protocolo preferencial para mídia) e dependem apenas do TCP. Considere implementar uma solução de túnel dividido vpn para ajudar a reduzir a VPN como uma fonte de baixa qualidade. |
| **Clientes** <br>(Skype for Business somente Online) | Verifique se todos os clientes estão sendo atualizados regularmente. |
| **Dispositivos** | Se os dispositivos forem o culpado em problemas de qualidade de chamada, considere atualizar dispositivos incorretos. Leia [Telefones para Teams](./devices/phones-for-teams.md) para saber mais. |
| **Drivers** | A aplicação de patch de rede (Ethernet e Wi-Fi), áudio, vídeo e drivers USB deve fazer parte de sua estratégia geral de gerenciamento de patch. Muitos problemas de qualidade são resolvidos pela atualização de drivers. |
| **Salas de reunião em Wi-Fi** | É altamente recomendável que os dispositivos de sala de reunião sejam conectados à rede usando pelo menos uma conexão Ethernet de 1 Gbps. Os dispositivos de sala de reunião normalmente incluem vários fluxos de áudio e vídeo, juntamente com conteúdo de reunião, como compartilhamento de tela, e têm requisitos de rede mais altos do que outros Teams ou Skype for Business de extremidade. As salas de reunião são, por definição, dispositivos estacionários Wi-Fi que permitem um benefício somente durante a instalação.<br><br>As salas de reunião precisam ser tratadas com cuidado extra e atenção para garantir que a experiência usando esses dispositivos esteja a atender ou exceder as expectativas. Os problemas de qualidade com salas de reunião geralmente serão escalonados rapidamente, pois geralmente são usados pela equipe de nível sênior.<br><br>Com todas as coisas sendo iguais (além da conveniência), Wi-Fi desempenho geralmente é menor que uma conexão com fio. Com o aumento das políticas de "traga seu próprio dispositivo" e a proliferação de laptops, Wi-Fi pontos de acesso geralmente são superutilados. A mídia em tempo real pode não ser priorizada em redes Wi-Fi, o que pode levar a problemas de qualidade durante os horários de pico de uso. Esse uso intenso pode coincidir com uma reunião em que pode haver uma dúzia de pessoas presentes, cada uma com seu próprio laptop e smartphone, todos conectados ao mesmo ponto de acesso Wi-Fi que o dispositivo de sala de reunião.<br><br>Wi-Fi deve ser considerado apenas como uma solução temporária, para uma instalação móvel ou quando o Wi-Fi tiver sido provisionado corretamente para dar suporte à mídia baseada em tempo real e de classe empresarial. |


### <a name="tcp"></a>TCP 

O protocolo TCP é considerado um transporte de failback e não o transporte primário que você deseja para mídia em tempo real. O motivo pelo qual é um transporte de failback é devido à natureza com estado do TCP. Por exemplo, se uma chamada for feita em uma rede latente e os pacotes de mídia forem atrasados, os pacotes de alguns segundos atrás , que não são mais úteis, competirão pela largura de banda para chegar ao receptor, o que pode piorar uma situação ruim. Isso faz com que o reparador de áudio costura e alonge o áudio, resultando em artefatos audíveis, geralmente na forma de tremulação.

Os relatórios nesta seção não fazem uma distinção entre fluxos bons e ruins. Considerando que o UDP é preferencial, os relatórios pesquisam o uso de TCP para VBSS (compartilhamento de tela baseado em áudio, vídeo e vídeo). Taxas de fluxo ruins são fornecidas para ajudar a comparar a qualidade do UDP versus a qualidade do TCP para que você possa concentrar seus esforços onde o impacto é o maior. O uso de TCP é causado principalmente por regras de firewall incompletas. Para obter mais informações sobre regras de firewall para Teams e Skype for Business Online, consulte [Microsoft 365 e Office 365 URLs e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).

> [!Note]
> Áudio, vídeo e VBSS preferem o UDP como seu transporte principal. A carga de trabalho de Compartilhamento de Aplicativo RDP herdada usa apenas TCP.

#### <a name="tcp-usage"></a>Uso de TCP

Os relatórios TCP indicam o uso geral do TCP nos últimos sete meses. Todos os relatórios adicionais nesta seção se concentrarão em restringir edifícios e sub-redes específicas em que o TCP é usado com mais frequência. Relatórios separados estão disponíveis para conferências e fluxos de duas partes.

![Gráfico mostrando a porcentagem de fluxos de áudio que usam TCP.](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Investigação

Usando esse relatório, você pode responder às seguintes perguntas:

-   Qual é o volume total de fluxos TCP para o mês atual?
-   É pior ou melhor do que o mês anterior?
-   A tendência de uso do TCP está aumentando, estável ou diminuindo?
-   O PSR TCP é o mesmo que meu PSR geral?

Se você observar que a tendência de uso do TCP está aumentando ou acima do uso mensal normal, reserve um tempo para investigar usando os sub-relatórios para procurar quaisquer edifícios ou redes que possam precisar de correção. O ideal é que você queira o menor número possível de sessões de áudio baseadas em TCP na rede gerenciada.

#### <a name="tcp-vs-udp"></a>TCP versus UDP

Esse relatório identifica o volume de relatórios de uso de TCP versus UDP no mês mais recente para VBSS (compartilhamento de tela baseado em áudio, vídeo e vídeo). 

![Relatório mostrando o volume de fluxos que usam TCP versus UDP.](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Análise

Embora você queira que o uso de TCP seja o mais baixo possível, você pode ver um pouco de uso de TCP em uma implantação íntegra de outra forma. O TCP por si só não contribuirá para uma chamada ruim, portanto, as taxas de fluxo são fornecidas para ajudar a identificar se o uso do TCP é um colaborador para a baixa qualidade. 

#### <a name="tcp-investigations"></a>Investigações de TCP

Nos modelos CQD fornecidos, navegue até o Fluxos TCP criando e sub-rede usando o modelo Redes Gerenciadas ou Todas as Redes. Para investigar o uso do TCP, o processo é o mesmo, portanto, vamos concentrar a discussão aqui na conferência.


##### <a name="remediation"></a>Remediação

Este relatório identifica edifícios e sub-redes específicos que estão contribuindo para o volume de uso de TCP. Um relatório adicional também é incluído para identificar o IP de Retransmissão da Microsoft que foi usado na chamada para ajudar a isolar as regras de firewall ausentes. Concentre seus esforços de correção nos edifícios que têm o maior volume de fluxos TCP para maximizar o impacto.

A causa mais comum de uso de TCP são as regras de exceção ausentes em firewalls ou proxies. Vamos falar sobre proxies na próxima seção, portanto, por enquanto, concentre seus esforços nos firewalls. Usando o prédio ou a sub-rede fornecida, você pode determinar qual firewall precisa ser atualizado.

| Remediação        | Orientação     |
|--------------------|--------------------------------------|
| Configurar firewall | Verifique se [Microsoft 365 ou Office 365 ip e endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) foram excluídos do firewall. Para problemas de TCP relacionados à mídia, concentre seus esforços iniciais no seguinte:<ul><li>Verifique se as sub-redes de mídia do cliente 13.107.64.0/18 e 52.112.0.0/14 estão em suas regras de firewall.</li><li>As portas UDP 3478-3481 são as portas de mídia necessárias e devem ser abertas; caso contrário, o cliente fará failback para a porta TCP 443.</li></ul> |
| Verificar             | Use a [Ferramenta de](https://www.microsoft.com/download/details.aspx?id=53885) Avaliação de Rede da Microsoft para verificar se há problemas de conectividade com endereços MICROSOFT 365 ou Office 365 IP específicos e portas do edifício ou sub-rede afetado.    |

### <a name="http-proxy"></a>Proxy HTTP

Os proxies HTTP não são o caminho preferencial para estabelecer sessões de mídia, por vários motivos. Muitos contêm recursos de inspeção de pacotes profundos que podem impedir que as conexões com o serviço sejam concluídas e introduzir interrupções. Além disso, quase todos os proxies forçam o TCP em vez de permitir o UDP, o que é recomendado para uma qualidade de áudio ideal.

Sempre recomendamos que você configure o cliente para se conectar diretamente aos Teams e Skype for Business serviços. Isso é especialmente importante para o tráfego baseado em mídia.


> [!IMPORTANT]
> Recomendamos que você carregue um [arquivo de construção válido](CQD-upload-tenant-building-data.md) para que possa distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

O relatório de fluxo de proxy HTTP nesta seção do modelo é muito parecido com os relatórios TCP. Ele não verifica se as chamadas são ruins ou boas, mas se a chamada está conectada via HTTP.

![Captura de tela do relatório de fluxos de áudio que usam HTTP.](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Análise

Você deseja ver o menor possível os fluxos de mídia HTTP. Se você tiver fluxos atravessando seu proxy, consulte sua equipe de rede para garantir que as exclusões adequadas estejam em vigor para que os clientes sejam roteados diretamente para sub-redes de mídia Teams ou Skype for Business Online.

Se você tiver apenas um proxy de Internet em sua organização, verifique as Microsoft 365 ou Office 365 urLs e as exclusões de intervalo [de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Se mais de um proxy de Internet estiver configurado em sua organização, use o sub-relatório HTTP para isolar qual construção ou sub-rede é afetada.

Para organizações que não podem ignorar o proxy, verifique se o cliente Skype for Business está configurado para entrar corretamente quando ele está localizado atrás de um proxy, conforme descrito no artigo Skype for Business deve usar o [servidor proxy](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin) para entrar em vez de tentar a conexão direta. 


#### <a name="http-proxy-investigations"></a>Investigações de proxy HTTP

Este relatório identifica edifícios e sub-redes específicos que estão contribuindo para o uso de HTTP.


##### <a name="remediation"></a>Remediação

[Recomendamos que](proxy-servers-for-skype-for-business-online.md) você sempre ignore proxies para Skype for Business e Teams, especialmente o tráfego de mídia. Os proxies não tornam a Skype for Business mais segura, pois seu tráfego já está criptografado. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Problemas como esses resultarão em uma experiência negativa com áudio, vídeo e compartilhamento de tela, em que os fluxos em tempo real são essenciais.

A causa mais comum de uso de HTTP são as regras de exceção ausentes em proxies. Usando o edifício ou a sub-rede fornecida, você pode determinar rapidamente qual proxy precisa ser configurado para bypass de mídia.

Verifique se os Microsoft 365 [ou Office 365 FQDNs](/microsoft-365/enterprise/urls-and-ip-address-ranges) necessários são adicionados a uma lista de permissões no proxy.

## <a name="endpoint-investigations"></a>Investigações de ponto de extremidade

Esta seção se concentra nas tarefas para relatórios sobre versões de cliente e o uso de dispositivos certificados. Os relatórios estão disponíveis para descrever o uso de versões de cliente, tipo de cliente, dispositivos de captura e drivers (microfone), dispositivos de captura de vídeo e Wi-Fi de fornecedor e driver.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo; no entanto, os métodos de investigação explicados abaixo ainda se aplicam. Consulte a descrição do relatório individual para obter mais informações.

### <a name="client-versions"></a>Versões do cliente

Esses relatórios se concentram na identificação Skype for Business versões do cliente em uso e seu volume relativo no ambiente.

> [!IMPORTANT]
> Atualmente, Teams clientes são distribuídos e atualizados automaticamente por meio da Rede de Distribuição de Conteúdo do Azure e serão mantidos atualizados pelo serviço. Como resultado, você não precisa monitorar Teams versões do cliente (a menos que desative a atualização automática, o que não recomendamos).

A menos que você exclua dados de participantes federados, esses relatórios incluirão a telemetria do cliente de pontos de extremidade federados. Para excluir pontos de extremidade federados, você deve adicionar um filtro de consulta para a segunda ID de locatário definida à ID de locatário da [sua organização](CQD-data-and-reports.md#how-to-find-your-tenant-id). Como alternativa, você pode usar um filtro [de URL para](CQD-data-and-reports.md#url-filters) excluir a telemetria de participantes federados.



#### <a name="remediation"></a>Remediação

Uma parte crítica da condução de experiências de usuário de alta qualidade é garantir que os clientes gerenciados estejam executando versões atualizadas do Skype for Business, além de garantir que os drivers de áudio, vídeo, rede e USB de suporte estejam atualizados. Isso oferece vários benefícios, entre eles: 

-   É mais fácil gerenciar algumas versões em comparação com muitas versões.
-   Ele fornece um nível de consistência de experiência.
-   Isso facilita a solução de problemas com qualidade e usabilidade de chamadas.
-   A Microsoft continuamente faz melhorias e otimizações gerais em todo o produto. Garantir que os usuários recebam essas atualizações reduz o risco de ter um problema que já foi resolvido.

Limitar sua implantação a versões de cliente com menos de seis meses melhorará a experiência geral do usuário e melhorará a capacidade de gerenciamento, reduzindo o número de versões que precisam ter suporte.

Se você estiver usando apenas Office Clique para Executar, estará automaticamente dentro da janela de seis meses. Nenhuma ação adicional é necessária.

Se você tiver uma combinação de pacotes clique para executar e de instalador (MSI), poderá usar o relatório para verificar se os clientes MSI estão sendo atualizados regularmente. Se você observar que os clientes estão ficando para trás, trabalhe com a equipe responsável por gerenciar atualizações de Office e verifique se eles estão aprovando e implantando patches de cliente regularmente.

Também é importante considerar e garantir que os drivers de rede, vídeo, USB e áudio também estejam sendo corrigidos. Pode ser fácil ignorar esses drivers e não incluí-los em sua estratégia de gerenciamento de patch.

Os números de Skype for Business podem ser encontrados por meio dos links abaixo:

-   [Informações de versão para atualizações do Microsoft 365 Apps](/officeupdates/release-notes-office365-proplus)
-   [Histórico de atualizações para Microsoft 365 Apps para Grandes Empresas](/officeupdates/update-history-office365-proplus-by-date)
-   [Downloads e atualizações do Skype for Business](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para usar o relatório do dispositivo de microfone, precisamos entender o conceito da MOS (pontuação média de opinião). O MOS é a medida padrão ouro para medir a qualidade de áudio percebida. Ele é representado como uma classificação de inteiro de 0 a 5.

A base de todas as medidas de qualidade de voz é como uma pessoa percebe a qualidade da fala. Porque é afetado pela percepção humana, é inerentemente subjetivo. Há várias metodologias diferentes para testes subjetivos. A maioria das medidas de qualidade de voz se baseia em uma escala de ACR (classificação de categorização absoluta).

Em um teste subjetivo de ACR, um número estatisticamente significativo de pessoas taxa sua qualidade de experiência em uma escala de 1 (ruim) a 5 (excelente). A média das pontuações é a MOS. O MOS resultante depende do intervalo de experiências que foram expostas ao grupo e do tipo de experiência que está sendo classificada.

Como é impraticável realizar testes subjetivos de qualidade de voz para um sistema de comunicação ao vivo, o Microsoft Teams e o Skype for Business geram valores de MOS usando algoritmos avançados para prever objetivamente os resultados de um teste subjetivo.

O conjunto disponível de MOS e métricas associadas fornece uma visão da qualidade da experiência que está sendo entregue aos usuários por um dispositivo de áudio. 

Ao fornecer aos usuários dispositivos certificados para Teams e Skype for Business, você reduz a probabilidade de encontrar experiências negativas devido ao próprio dispositivo (o que é mais provável, por exemplo, com alto-falantes e microfones de laptop internos). Para obter mais informações, consulte estes artigos sobre o programa de [certificação e](/SkypeForBusiness/certification/overview) o catálogo [de soluções de parceiros](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Os relatórios de dispositivo são usados para avaliar o uso do dispositivo por volume e pontuação de MOS (somente áudio) e podem ser encontrados nos modelos de acompanhamento em Clientes & Dispositivos. 

> [!IMPORTANT]
> A menos que você exclua dados de participantes federados, esses relatórios incluirão a telemetria do cliente de pontos de extremidade federados. Para excluir pontos de extremidade federados, você deve adicionar um filtro de consulta para a **segunda ID** de locatário definida à ID de locatário da [sua organização](CQD-data-and-reports.md#how-to-find-your-tenant-id). ALternatively, você pode usar um filtro [de URL para](CQD-data-and-reports.md#url-filters) excluir a telemetria de participante federado.


> [!Note]
> Você pode observar ao exibir esse relatório que vê o mesmo dispositivo relatado várias vezes. Isso ocorre devido à maneira como o dispositivo é relatado ao CQD. Diferenças no hardware e na localidade do sistema operacional causam diferenças em como os dados do dispositivo são relatados.

##### <a name="remediation"></a>Remediação

Normalmente, você precisará descobrir e desabilitar dispositivos não certificados e substituí-los por dispositivos certificados. Algumas considerações ao examinar os relatórios do dispositivo incluem:

-   Os dispositivos em uso são certificados para Teams e Skype for Business? 
-   Você pode identificar usuários de um dispositivo específico usando a [análise de chamadas por usuário](use-call-analytics-to-troubleshoot-poor-call-quality.md). Verifique se eles têm os drivers de dispositivo mais recentes e se o dispositivo não está conectado por meio de um hub USB ou estação de encaixe. 
-   Quantas versões diferentes de vários drivers estão em uso? Eles estão sendo corrigidos regularmente? Garantir que os drivers de áudio, vídeo e Wi-Fi sejam corrigidos regularmente ajudará a eliminá-los como uma fonte de problemas de qualidade e tornar a experiência do usuário mais previsível e consistente.

##### <a name="audio"></a>Áudio

A próxima tarefa é determinar o uso geral de dispositivos [de áudio certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Recomendamos que pelo menos 80% de todos os fluxos de áudio usem um dispositivo de áudio certificado. Isso é melhor feito exportando o relatório de dispositivos de microfone Excel para calcular o uso de dispositivos certificados ou aprovados. As organizações normalmente mantêm uma lista de todos os dispositivos aprovados, portanto, a filtragem e a classificação dos dados devem ser simples.

##### <a name="video"></a>Vídeo

Os drivers de vídeo também são importantes para serem atualizados. Garantir que as placas de vídeo estejam sendo corrigidas regularmente ajudará a excluir drivers de vídeo como uma fonte de baixa qualidade para fluxos de vídeo. O [uso de dispositivos de vídeo](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) certificados ajudará a garantir uma experiência do usuário suave e de alta qualidade. Os dispositivos de vídeo que dão suporte à codificação nativa H.264 são preferenciais para reduzir o uso da CPU durante a videoconferência.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi drivers também precisam ser corrigidos em uma cadência regular e devem ser incluídos em sua estratégia de gerenciamento de patch. Muitos problemas de qualidade podem ser corrigidos mantendo os drivers de Wi-Fi atualizados. Para obter mais informações sobre como otimizar sua infraestrutura Wi-Fi, consulte [este artigo sobre Wi-Fi planejamento](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Tópicos relacionados

[Usar Supervisor para Teams](use-advisor-teams-roll-out.md)

[Preparar sua rede para o Teams](prepare-network.md)

[Office 365 de conectividade de rede](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Análises e relatórios do Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Gerenciar seus dispositivos no Teams](./devices/device-management.md)

[Melhorar e monitorar a qualidade da chamada para Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload locatário e criação de dados](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
