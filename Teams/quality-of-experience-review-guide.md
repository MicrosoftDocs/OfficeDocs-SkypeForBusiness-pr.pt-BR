---
title: Usar o CQD para gerenciar a qualidade de chamada e reunião no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Saiba como analisar e gerenciar o desempenho de mídia em tempo real no Microsoft Teams usando o CQD (Painel de Qualidade da Chamada).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: f4221b08742d27b4dbe360dfd345142795640588
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581182"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usar o CQD para gerenciar a qualidade de chamada e reunião no Microsoft Teams 

Este artigo ajudará você , o administrador ou o suporte e o engenheiro técnico do Teams, a desenvolver um processo para monitorar e manter a qualidade de chamada e reunião para sua organização usando o CQD (Painel de Qualidade de Chamada) do Microsoft Teams. Nossa orientação enfatiza cenários de qualidade de áudio, pois quaisquer melhorias de rede feitas para melhorar a experiência de áudio serão traduzidas para melhorias no vídeo e no compartilhamento.

A chave para essa orientação são os dois modelos [CQD](https://aka.ms/QERtemplates) com orientação: recomendamos baixá-los antes de passar pelas orientações neste artigo.

Este artigo pressu que você já [tenha definido o CQD.](turning-on-and-using-call-quality-dashboard.md)


## <a name="categories-to-monitor-and-maintain"></a>Categorias para monitorar e manter

Depois de lançar reuniões e voz no Teams, você precisará de um plano para monitoramento e manutenção contínuos. Isso garantirá que o Teams sempre seja executado de forma ideal. Este plano deve incluir as principais áreas listadas abaixo. Você também deve estabelecer metas para métricas de qualidade e um plano para solução de problemas e isolação de problemas quando elas acontecem.

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
<p>Quebre as métricas por chamadas internas (em sua organização, como VPN, WiFi, com fio) ou chamadas externas</p>
<p>Quebrar as métricas criando ou rede</p>
<p>Chamadas VPN</p>
<p>Chamadas usando TCP, UDP ou proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Confiabilidade de chamada</strong></td>
<td><p>Identificar e remediar qualquer problema de rede ou firewall</p>
<p>Obtenha informações sobre as porcentagens de falhas de configuração e redução de chamada</p>
<p>Saiba onde ocorre a maioria das falhas de configuração e soltar chamada</p>
</td>
</tr>
<tr class="odd">
<td><strong>Pesquisa do usuário</strong></td>
<td>
<p>Usar dados de Taxa Minha Chamada para saber mais sobre a experiência real dos usuários</p>
<p>Onde estão ocorrendo as experiências ruins?</p>
<p>Correlacionar a experiência ruim com a qualidade da chamada, a confiabilidade e os dispositivos</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivos</strong></td>
<td><p>Saiba quais microfones e alto-falantes são mais usados e seu impacto na qualidade da chamada</p>
<p>Os drivers de áudio, vídeo, USB e WiFi de suporte estão sendo regularmente remendados?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clientes</strong></td>
<td>
<p>Saiba quais tipos de cliente e versões estão sendo usados e seu impacto na qualidade e na confiabilidade das chamada  </p>
</ol></td>
</tr>
</tbody>
</table>

Ao avaliar e remediar continuamente as áreas descritas neste artigo, você pode reduzir seu potencial para afetar negativamente seus usuários. A maioria dos problemas do usuário pode ser agrupada nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy
-   Cobertura insatisfatória da rede Wi-Fi
-   Largura de banda insuficiente
-   VPN
-   Drivers e versões inconsistentes ou desatualizadas do cliente
-   Dispositivos de áudio não desenvolvidos ou integrados
-   Dispositivos de rede ou sub-redes com problemas

Por meio do planejamento e design adequados antes de implantar o Teams ou o Skype for Business Online, você pode reduzir a quantidade de esforço necessário para manter experiências de alta qualidade.

Este artigo se concentra no uso do Painel de Qualidade de Chamada (CQD) Online como a principal ferramenta para relatar e investigar cada área, com ênfase especial no áudio para maximizar a adoção e o impacto. Quaisquer melhorias feitas na rede para melhorar a experiência de áudio também serão diretamente traduzidas para melhorias no compartilhamento de vídeo e área de trabalho.

Para acelerar sua avaliação, dois modelos CQD com gerenciamento são [fornecidos:](https://aka.ms/qertemplates) um é para gerenciar todas as redes e o outro é filtrado somente para redes gerenciadas (internas). Embora os relatórios de modelo Todas as Redes sejam configurados para exibir informações de construção e rede, eles ainda podem ser usados enquanto você trabalha para coletar e carregar informações do edifício. O carregamento de informações de criação no CQD permite que o serviço melhore o relatório adicionando informações personalizadas de construção, rede e localização, ao mesmo tempo que diferencia as sub-redes internas das sub-redes externas. Para obter mais informações, leia [o mapeamento de construção.](CQD-building-mapping.md)

### <a name="intended-audience"></a>Público-alvo pretendido

Este artigo destina-se a ser usado por parceiros e participantes do cliente com funções como Líder/Arquiteto de Colaboração, Consultor, Especialista em Gerenciamento de Alterações/Adoção, Suporte/Suporte/Suporte Técnico, Cliente de Rede, Cliente de Área de Trabalho e Administrador de TI.

Este artigo também se destina a ser usado pelo(s) campeão(s) de qualidade designado(s). Para obter mais informações, consulte [a função Descampo da Qualidade.](4-envision-plan-my-service-management.md#the-quality-champion-role)


## <a name="what-is-quality"></a>O que é qualidade?

Nesse contexto, a qualidade é uma combinação de métricas de serviço e experiência do usuário.


### <a name="service-metrics"></a>Métricas de serviço

As métricas de serviço consistem em métricas específicas baseadas em cliente. Durante cada chamada, o cliente coleta telemetria para a chamada e envia um relatório no final de cada chamada que pode ser acessado posteriormente no CQD ou na análise de chamada por [usuário.](set-up-call-analytics.md) Essas métricas incluem (mas não se limitam a):

-   Fluxo Ruim (entrada e saída)
-   Taxa de Falha na Configuração
-   Drop Failure Rate


#### <a name="poor-stream-rate"></a>Taxa de fluxo ruim

A taxa de fluxo ruim (PSR) representa a porcentagem geral de fluxos da organização com baixa qualidade. Essa métrica é para destacar áreas onde sua organização pode concentrar o esforço para ter [](#managed-versus-unmanaged-networks) o maior impacto na redução desse valor e na melhoria da experiência do usuário, por isso as redes gerenciadas são o foco principal ao se olhar para PSR. Os usuários externos também são importantes, mas a investigação difere de forma organizacional. Considere fornecer práticas recomendadas para usuários externos e investigar chamadas externas independentemente da organização geral.

A medida real no CQD varia de acordo com a carga de trabalho, mas para os fins deste artigo, nos concentramos principalmente na medida _de Audio Poor Percentage._ A PSR é uma das cinco médias métricas de rede descritas na tabela a seguir. Para que um fluxo seja classificado como ruim, apenas uma métrica precisa exceder o limite definido. O CQD fornece o "Poor Due To..." medidas para entender melhor qual condição fez com que o fluxo fosse classificado como ruim. Para saber mais, leia [a classificação stream no CQD.](stream-classification-in-call-quality-dashboard.md)

> [!Note]
> O CQD fornece o "Ruim devido a..." medidas para entender melhor qual condição fez com que o fluxo fosse classificado como ruim.


##### <a name="audio-poor-quality-metrics"></a>Métricas de baixa qualidade de áudio

| Média métrica     | Descrição     | Experiência de usuário |
|-------------|-----------------|-----------------|
| Jitter \> 30 ms        | Essa é a alteração média de atraso entre pacotes sucessivos. O Teams e o Skype for Business podem se adaptar a alguns níveis de tremida por meio do armazenamento em buffer. É somente quando a tremagem excede o armazenamento em buffer que um participante percebe os efeitos da tremagem.      | Os pacotes que chegam em velocidades diferentes faz com que a voz do alto-falante soe inodentante.   |
| Taxa de perda de \> pacote de 10% ou 0,1        | Isso geralmente é definido como uma porcentagem de pacotes que são perdidos. A perda de pacote afeta diretamente a qualidade do áudio— de pacotes perdidos pequenos e individuais que quase não têm impacto nas perdas de intermões de trás para trás, o que faz com que o áudio seja cortado completamente.     | Os pacotes que estão sendo descartados e não chegam ao destino pretendido causam lacunas na mídia, resultando em sílabas e palavras perdidas, e vídeos e compartilhamentos inooss. |
| Tempo de ida e volta \> 500 ms        | Esse é o tempo necessário para obter um pacote IP do ponto A para o ponto B e de volta ao ponto A. Esse atraso de propagação de rede está vinculado à distância física entre os dois pontos e a velocidade da luz e inclui sobrecarga adicional realizada pelos vários dispositivos no caminho da rede.      | Os pacotes demorando muito para chegar ao destino causam um efeito walkie-talkie.   |
| Média de degradação de NMOS \> 1,0         | Média [da degradação de NMOS (Network Mean Opinion Score)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) para o fluxo. Representa o quanto a perda de rede e a tremida afetaram a qualidade do áudio recebido, o que fez com que os NMOS caiam mais de um ponto. | Essa é uma combinação de tremida, perda de pacotes e, em um grau menor, maior tempo de ida e volta. O usuário pode estar enfrentando uma combinação desses sintomas.   |
| Taxa média de amostras ocultas \> 7% ou 0,07 | Taxa média do número de quadros de áudio com amostras ocultas geradas pela perda de pacotes para o número total de quadros de áudio. Uma amostra de áudio oculta é uma técnica usada para suavizar a transição que normalmente seria causada por pacotes de rede descartados.      | Valores altos indicam que níveis significativos de ocultação de perda foram aplicados e resultaram em áudio distorcido ou perdido.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Por que prefere usar fluxos em vez de chamadas?

Os fluxos nos permitem saber qual trecho específico da chamada estava ruim: saída ou entrada. Quando você estiver analisando a análise de chamada para uma chamada ruim, determine se a chamada ruim ocorreu devido ao fluxo de chamada (saída) ou ao fluxo de chamada (entrada). Determinar qual fluxo está afetando a qualidade da chamada é ainda mais importante para conferências. Se você estiver vendo apenas os dados da chamada, verá em quantas conferências uma pessoa participa, mas não verá quais pessoas são falantes ativas, fazendo o compartilhamento de tela com mais opções.

Os dados de chamada proporcionam métricas de uso, mas não necessariamente levam você à causa raiz da baixa qualidade da chamada. Ao olhar para a direção do fluxo, você pode identificar fatores como uma chamada que não está em uma rede gerenciada, uma chamada de um não funcionário (por exemplo, um fornecedor ou alguém em uma rede diferente). Nesses casos, se a conexão de rede de outra pessoa estava ruim, a chamada inteira será sinalizada como ruim. Não é possível fazer nada sobre fatores externos, portanto, esses dados não são úteis.

A direção do fluxo também pode ajudá-lo a identificar dispositivos ou clientes problemáticos.

 - Por exemplo, se você tiver um orçamento limitado para dispositivos e quiser fornecer dispositivos somente para usuários de áudio pesado, use o relatório de uso de áudio (VoIP) e filtre por fluxos de saída e conferência. Procure usuários de áudio de alto volume que estão falando em microfones integrados– eles podem estar correlacionados à qualidade de chamada mais baixa (e talvez você queira fornecer dispositivos de áudio para essas pessoas). Para maior clareza, você pode filtrar a utilização de pacotes, o que permitirá direcionar usuários de áudio especialmente de alto volume. 

  - Outro exemplo envolve o compartilhamento de tela. Se um cliente estiver usando um cliente antigo do Teams, o desempenho do compartilhamento de tela poderá ser afetado. Você pode resolver esse problema priorizando as atualizações do cliente para pessoas que fazem muito compartilhamento de tela.

 - Ao identificar qual direção de um fluxo está causando baixa qualidade de chamada, você pode determinar se você tem um QoS ou um problema relacionado à largura de banda. Se você ainda não implementou totalmente a QoS ou se apenas marcar pacotes no cliente e não no fluxo de entrada, talvez veja uma qualidade de chamada mais ruim. Ao olhar para a direção do fluxo, você pode obter uma exibição mais granular de perda de pacote, latência ou tremulação em uma direção específica. 

   - Por exemplo, digamos que um usuário reclame de áudio descarada enquanto está em uma conexão com fio (tremida). Analisando o fluxo e a direção, você pode determinar que o problema acontece no fluxo de entrada, somente para um conjunto específico de sub-redes. Depois que você der essas informações à sua equipe de rede, eles poderão rastreá-los para um acelerador WAN configurado inconfigurado que não estava ignorando o tráfego de mídia. Depois que a equipe de rede reconfigura o acelerador WAN, a trem tremida desaparece e a qualidade da chamada melhora. 


#### <a name="setup-failure-rate"></a>Taxa de Falha na Configuração

A taxa de falha de configuração, também conhecida como a medida porcentagem de falha de configuração de chamada _total_ no CQD, é o número de fluxos onde o caminho de mídia não pôde ser estabelecido entre os pontos de extremidade no início da chamada.

Isso representa qualquer fluxo de mídia que não pôde ser estabelecido. Considerando a gravidade do impacto desse problema na experiência do usuário, o objetivo é reduzir esse valor para o mais próximo de zero possível. Um alto valor para essa métrica é mais comum em novas implantações com regras de firewall incompletas do que uma implantação madura, mas ainda é importante observar regularmente.

Essa métrica é calculada pela tomada do número total de fluxos que falharam na configuração dividida pelo número total de fluxos que enviou um CDR (registro de detalhes de chamada) bem-sucedido:

-   **Taxa de Falha de Configuração** = Total Call Setup Failed Stream Count / Total CDR Available Stream Count

#### <a name="drop-failure-rate"></a>Drop Failure Rate

A taxa de falha na  entrega, também conhecida como a medida total de porcentagem de falha na chamada no CQD, é a porcentagem de fluxos estabelecidos com êxito onde o caminho de mídia não terminou normalmente.

Isso representa qualquer fluxo de mídia que terminou inesperadamente. Embora o impacto disso não seja tão grave quanto um fluxo que falhou na configuração, isso ainda afetará negativamente a experiência do usuário. Gotas de mídia inesperadas e frequentes não só podem ter um impacto grave na experiência do usuário, mas também na necessidade de reconectar os usuários, resultando em perda de produtividade (sem mencionar a frustração).

A métrica é calculada pela tomada do número total de fluxos descartados dividido pela contagem total de fluxos que configuraram com êxito:

-   **Drop Failure Rate** = Total Call Dropped Stream Count / Total Call Setup Succeeded Stream Count

### <a name="define-your-target-metrics"></a>Definir suas métricas de destino

Esta seção discute algumas das principais métricas de serviço que usamos para avaliar a saúde dos serviços. Avaliando continuamente e direcionando esforços para manter essas métricas abaixo das metas definidas, você ajudará a garantir que seus usuários experimentem uma qualidade de chamada consistente e confiável. Como ponto de partida, use as metas sugeridas na tabela abaixo. Ajuste as metas conforme necessário para atender aos seus objetivos comerciais.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de rede</th><th rowspan="1">Metas de qualidade</th><th colspan="2">Destinos de confiabilidade</th></tr>
<tr><th>Audio Poor Stream Rate</th><th>Taxa de Falha na Configuração</th><th>Drop Failure Rate</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Geral</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conferências</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interna com fio</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interna de 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interna de 2,4 GHz</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Geral</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Com fio/Wi-Fi 5 GHz interno</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wired/Wi-Fi 5 GHz geral</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>Geral</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Experiência de usuário

Analisar a experiência do usuário é mais arte do que ciência, pois as métricas coletadas aqui nem sempre significam que há um problema com a rede ou serviço, mas, em vez disso, eles simplesmente indicam que o usuário percebe um problema. O CQD inclui um mecanismo de pesquisa interna — Taxa minha chamada (RMC) — para ajudar a avaliar a experiência geral do usuário. A RMC lhe dará informações sobre as seguintes perguntas da perspectiva dos usuários:

-   Eu sei como usar a solução?
-   A solução é fácil de usar e intuitiva e dá suporte às minhas necessidades de comunicação diárias?
-   A solução ajuda a fazer meu trabalho?
-   Qual é minha percepção geral da solução?
-   Posso usar a solução a qualquer momento, independentemente de onde esteja?
-   Posso configurar e manter uma chamada?

#### <a name="rate-my-call"></a>Taxa Minha Chamada 

O RMC (Rate My Call) é integrado ao Teams e ao Skype for Business. Ela aparece automaticamente após uma em cada 10 chamadas ou 10%. Esta breve pesquisa solicita que o usuário adque a chamada e forneça um pouco de contexto sobre por que a qualidade da chamada pode ter sido ruim. Uma ou duas classificações é considerada ruim, três a quatro é boa e cinco é excelente. Embora seja um indicador de atraso, essa é uma métrica útil para descobrir problemas que as métricas de serviço podem perder.

> [!Note]
> O fator humano: os usuários geralmente ignoram a pesquisa quando a qualidade da chamada é boa e a preenchem quando a qualidade da chamada é ruim. Como resultado, seus relatórios RMC podem estar distorcendo para o lado ruim, mesmo enquanto as métricas de serviço são boas.

Você pode usar o CQD para relatar respostas de usuários RMC, e exemplos de relatórios são incluídos no modelo CQD. No entanto, eles não são discutidos em detalhes neste artigo. 

#### <a name="client-and-device-readiness"></a>Preparação do cliente e do dispositivo

Você precisa de uma estratégia sólida de cliente e dispositivo para ajudar a garantir que seus usuários tenham uma experiência de usuário consistente e positiva. Alguns princípios fundamentais conduzem cada estratégia de preparação.

##### <a name="client-readiness"></a>Preparação do cliente

Manter o cliente do Teams atualizado garante que os usuários sempre obterão a melhor experiência possível. A Microsoft lança atualizações [frequentes](teams-client-update.md) para o cliente do Teams (a atualização se instala em segundo plano, a menos que você tenha desligado essa funcionalidade, o que não recomendamos). Também é importante lembrar de corrigir drivers de rede, vídeo, USB e áudio, pois eles geralmente são ignorados e podem afetar a qualidade da chamada e da reunião. Considere adicionar drivers de rede, Wi-Fi, vídeo, USB e áudio ao seu processo de gerenciamento de patch atual.


##### <a name="device-readiness"></a>Preparação do dispositivo

Nenhuma única estratégia pode afetar a experiência do usuário mais do que a estratégia de preparação do dispositivo. Por exemplo, os usuários que dependem dos alto-falantes e do microfone do laptop terão muito ruído de fundo em chamadas e reuniões. O Teams foi projetado para funcionar com quase qualquer dispositivo, mas se você estiver com problemas relacionados ao dispositivo, confira [o telefone para o Teams.](phones-for-teams.md)


### <a name="categories-of-quality"></a>Categorias de qualidade

Operacionalize um conjunto de práticas de gerenciamento de qualidade- isso oferece a melhor chance de boa qualidade de chamada e reunião. Um plano de gerenciamento de boa qualidade trata dessas categorias:

-   **Rede:** Qualidade de áudio voltada para a métrica PSR (Taxa de Fluxo Ruim), uso de TCP, sub-redes com fio e sem fio e identificação do uso de proxies HTTP e VPN

-   **Pontos de extremidade:** Dispositivos de áudio e clientes atualizados

-   **Gerenciamento de serviços:** Esta categoria compreende duas seções:

    -   Em primeiro lugar, é responsabilidade da Microsoft gerenciar e manter os serviços do Teams e do Skype for Business Online.

    -   Em segundo lugar estão as tarefas que sua organização gerencia para garantir um acesso confiável ao serviço, como atualizar informações de construção e manter firewalls para novos endereços IP do Office 365, pois a infraestrutura é adicionada ao serviço.

![Gráfico das categorias de qualidade em uma organização](media/qerguide-image-categories.png "As categorias de qualidade em uma organização: gerenciamento de serviços, pontos de extremidade e rede.")

Revise a lista de tarefas a seguir recomendadas para manter a qualidade. Você deve executar essas tarefas regularmente, por exemplo, semanalmente.

#### <a name="service-management-tasks"></a>Tarefas de gerenciamento de serviço

Essas tarefas variam desde garantir que haja largura de banda suficiente para alcançar o serviço sem saturar links de Internet, validar que a qualidade do serviço (QoS) está em uso em todas as áreas de rede gerenciadas e manter-se no topo dos intervalos IP do [Office 365 em firewalls.](https://aka.ms/o365ips)

#### <a name="network-tasks"></a>Tarefas de rede

Há duas categorias de tarefas de rede: confiabilidade e qualidade. A confiabilidade se concentra em medir a capacidade do usuário de fazer chamadas com êxito e permanecer conectado. A qualidade se concentra na telemetria agregada enviada para o Teams e o Skype for Business Online pelo cliente do usuário durante a chamada e depois que ela terminou. 

Dado o impacto crítico que a confiabilidade tem na experiência do usuário, recomendamos avaliar e investigar as métricas de confiabilidade antes de começar a usar a qualidade. 

#### <a name="endpoints-tasks"></a>Tarefas de pontos de extremidade

A tarefa principal nesta categoria remove quaisquer obstáculos para as atualizações regulares do cliente [teams.](teams-client-update.md) Por padrão, o Teams é atualizado automaticamente regularmente (a menos que você desligue essa configuração, o que não recomendamos). 

Você também deve monitorar dispositivos e fornecer atualizações sempre que identificar problemas relacionados a um dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usar o CQD para gerenciar a qualidade da chamada

Depois de configurar [o CQD,](turning-on-and-using-call-quality-dashboard.md)você estará pronto para começar a usá-lo para gerenciar a qualidade de chamada e reunião da sua organização.

A maioria dos problemas de desempenho do Teams se enquadra nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy
-   Cobertura insatisfatória da rede Wi-Fi
-   Largura de banda insuficiente
-   VPN
-   Drivers e versões inconsistentes ou desatualizadas do cliente
-   Dispositivos de áudio não desenvolvidos ou integrados
-   Dispositivos de rede ou sub-redes com problemas

Se você aproveitar o tempo antes de lançar o Teams para avaliar essas áreas e remediar todas as deficiências, reduzirá o esforço necessário para manter uma experiência de alta qualidade do Teams para todos os usuários. Para ajudar a avaliar sua rede em preparação para a distribuição do Teams, leia [o Consultor](use-advisor-teams-roll-out.md) do Teams e prepare sua rede para [o Teams.](prepare-network.md)

### <a name="expectations-using-cqd"></a>Expectativas usando o CQD

Use o Painel de Qualidade de Chamada (CQD) para obter informações sobre a qualidade das chamadas feitas usando o Teams e os serviços do Skype for Business. O CQD foi projetado para ajudar os administradores do Teams e o Skype for Business e os engenheiros de rede a otimizar a rede e ficar de olho na qualidade, na confiabilidade e na experiência do usuário. O CQD analisa a telemetria agregada de uma organização inteira, onde os padrões gerais podem se tornar aparentes; isso permite que você faça avaliações informadas e planeje a correção. O CQD fornece relatórios de métricas que fornecem informações sobre a qualidade geral, a confiabilidade e a experiência do usuário.

O CQD, embora útil para analisar tendências e sub-redes, nem sempre fornece uma causa específica para um determinado cenário. É importante entender isso e definir a expectativa correta ao usar o CQD:

-   O CQD não fornecerá a causa raiz para cada cenário
-   O CQD não conterá fluxos do Sistema de Telefonia ou audioconferência
-   O CQD chamará áreas para investigação posterior com base em tendências

### <a name="cqd-reports-overview"></a>Visão geral dos relatórios do CQD

Use o menu suspenso na parte superior da tela para abrir um relatório. Para uma lista dos dados fornecidos em cada relatório, leia Os dados [disponíveis em relatórios CQD.](CQD-data-and-reports.md#data-available-in-cqd-reports)

Novo em janeiro de 2020: Baixe modelos de consulta [do Power BI para CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados CQD.


### <a name="teams-vs-skype-for-business"></a>Teams vs. Skype for Business

O CQD pode relatar tanto o Teams quanto o Skype for Business. No entanto, pode haver ocasiões em que você queira desenvolver um relatório para ver a telemetria do Teams separada do Skype for Business.

#### <a name="summary-reports"></a>Relatórios resumidos

Para modificar a página de relatórios de resumo para  ver apenas o Teams ou o Skype for Business, selecione o menu suspenso Filtro de Produto na parte superior da tela e selecione o produto que você deseja.

![Captura de tela do menu suspenso mostrando as opções de filtro](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Relatórios detalhados

Para filtrar todos os relatórios detalhados, na barra do navegador, adente o seguinte ao final da URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Exemplo:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obter mais informações sobre filtros de URL, leia [relatórios de filtragem](CQD-data-and-reports.md#report-filters) mais adiante nesta seção.

Para filtrar um relatório detalhado individualmente, adicione o filtro ao ``Is Teams`` relatório e de defini-lo como Verdadeiro ou Falso.

![Captura de tela da página Adicionar filtro](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Redes gerenciadas versus não gerenciadas

Por padrão, todos os pontos de extremidade no CQD são classificados como externos. Assim que um arquivo de construção for introduzido, podemos começar a ver os dados do ponto de extremidade gerenciados. Conforme discutido anteriormente, as redes no CQD são definidas como:

-   Uma _rede gerenciada,_ geralmente chamada de interna ou interna, pode ser influenciada e controlada pela organização. Isso inclui a LAN interna, a WAN remota e VPN.
-   Uma _rede não controlada,_ geralmente chamada de externa ou externa, não pode ser influenciada ou controlada pela organização. Um exemplo de rede nãomanada é uma rede de hotel ou aeroporto.

### <a name="dimensions-measures-and-filters"></a>Dimensões, medidas e filtros

Uma consulta CQD bem formada contém todos os três parâmetros a seguir:

-   **Dimensão:** Como eu quero girar os dados.

-   **Medida:** Sobre o que eu quero relatar.

-   **Filtro:** Como quero reduzir o conjuntos de dados que a consulta retorna.

Outra maneira de ver isso é que uma dimensão  é _a_ função de agrupação,  uma medida é os dados em que estou interessado e um filtro é como eu quero restringir os resultados para aqueles que são relevantes para minha consulta.

Um exemplo de uma consulta bem formada é **Mostrar-me Fluxos Ruins [Medida] pela Sub-rede [Dimensão]** para o Prédio 6 [Filtro] . Para obter mais informações, [consulte Dimensões e medidas disponíveis no CQD.](https://aka.ms/cqd-dm)

### <a name="first-vs-second"></a>Primeiro vs. segundo 

Muitas das dimensões e medidas no CQD são classificadas como primeira ou segunda. O CQD não usa campos de chamador/chamador—  eles foram renomeados primeiro e segundo porque há etapas intermediando entre o chamador e o chamador.  A seguinte lógica determina qual ponto de extremidade envolvido é rotulado como primeiro:

-   **Primeiro** será sempre um ponto de extremidade de servidor (Servidor de Conferência, Servidor de Mediação e assim por diante) se um servidor estiver envolvido no fluxo ou chamada.

-   **O** segundo sempre será um ponto de extremidade do cliente, a menos que o fluxo esteja entre dois pontos de extremidade do servidor.

-   Se ambos os pontos de extremidade são do mesmo tipo, a escolha dos quais primeiro se baseia na ordenação interna da categoria do agente do usuário. Isso garante que a ordenação seja consistente.

Para obter mais informações sobre como determinar o primeiro ou segundo ponto de extremidade quando ambos são iguais, consulte Dimensões e medidas disponíveis [no CQD.](https://aka.ms/cqd-dm)

### <a name="stream-vs-call"></a>Stream vs. call

Você precisa entender a diferença entre uma chamada e um fluxo para escolher corretamente quais dimensões ou medidas você verá no CQD. Embora o foco principal do CQD seja os fluxos, as medidas baseadas em chamada também estão disponíveis.

-   **Stream:** Existe _um fluxo_ entre apenas dois pontos de extremidade. Há apenas um fluxo para cada direção, e dois fluxos são necessários para comunicação. Os fluxos são úteis para investigar edifícios, redes ou sub-redes. Em alguns casos, tanto a chamada quanto o stream são usados no nome da medida (por exemplo, Fluxo de Configuração de Chamada ou Fluxo de Chamada Descartado). Eles ainda são classificados como fluxos.

-   **Chamada:** Uma _chamada_ é um grupo de todos os fluxos de todos os participantes. Uma chamada consiste em, no mínimo, dois fluxos. Uma única chamada terá pelo menos dois pontos de extremidade, cada um com um fluxo mínimo.

Para obter orientações adicionais sobre se a dimensão ou medida faz referência a uma chamada ou a um fluxo, consulte Dimensões e medidas disponíveis [no CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Chamadas boas, ruins e não classificadas

Uma chamada é categorizada como boa, ruim ou não classificada. Vamos demorar um pouco para falar sobre cada uma delas com mais detalhes.

-   **Bom ou ruim:** Uma chamada boa ou ruim consiste em uma chamada que contém um conjunto completo de métricas de serviço, para as quais um relatório de QoE completo foi gerado e recebido pelo serviço. Determinar se um fluxo é bom ou ruim é descrito [anteriormente neste artigo.](#poor-stream-rate)

-   **Não classificado:** Um fluxo não classificado não contém um conjunto completo de métricas de serviço. Podem ser chamadas curtas, geralmente menores que 60 segundos, em que as médias não puderam ser calculadas e um relatório de QoE não foi gerado. O motivo mais comum para as chamadas não serem classificadas é que houve pouca ou nenhuma utilização de pacote. Um exemplo disso seria um participante que participa de uma reunião com mudo mudo e nunca fala. O participante está recebendo, mas não está transmitindo, mídia. Sem a transmissão de mídia, não haverá métricas disponíveis para o CQD usar para classificar o fluxo de mídia de saída do ponto de extremidade.

Para saber mais, leia [a classificação stream no CQD.](stream-classification-in-call-quality-dashboard.md)

### <a name="common-subnets"></a>Sub-redes comuns

Sub-redes comuns são sub-redes particulares específicas que são usadas por hoteleiros, redes de residência, hotspots e áreas semelhantes. Essas sub-redes são difíceis de triagem devido ao seu uso generalizado. Se sua organização usa uma dessas sub-redes comuns, recomendamos que você mova essa rede para outra sub-rede. Isso facilitará o relatório no CQD. Quando notados, os relatórios no modelo Todas as Redes foram configurados para excluir essas sub-redes para eliminá-las como uma fonte de baixa qualidade. As sub-redes comuns são definidas abaixo; o impacto varia de acordo com a organização.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Ao investigar uma rede gerenciada que usa uma sub-rede comum, você precisará usar a dimensão IP Local Segunda Reflexiva para agrupar sub-redes. Essa dimensão contém o endereço IP público do ponto de extremidade.


## <a name="reliability-investigations"></a>Investigações de confiabilidade

A primeira etapa para melhorar a qualidade é avaliar o estado de confiabilidade em toda a organização. Como a confiabilidade é essencial para uma experiência positiva do usuário, começamos com os dois componentes que medem a confiabilidade:

1.  **Falhas de configuração:** A chamada não pôde ser estabelecida.

2.  **Falhas de soltar:** A chamada foi estabelecida e encerrada inesperadamente.

Nesta seção, abrangemos os métodos para investigar as duas áreas.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo. No entanto, os métodos de investigação explicados abaixo ainda se aplicam. Consulte a descrição individual do relatório para obter mais informações.


### <a name="setup-failures"></a>Falhas de configuração

Priorize a priorização da correção de falhas de configuração nessa área, pois essas falhas têm um impacto negativo significativo na experiência do usuário.

Comece sua investigação avaliando a porcentagem de falhas de configuração gerais da organização e priorizando áreas de investigação com base na porcentagem mais alta, criando ou rede. 

#### <a name="setup-failure-trend-analysis"></a>Análise de tendência de falha de configuração

Este relatório exibe a quantidade total de fluxos, as falhas de configuração de fluxo e a taxa de falha de configuração de fluxo. Aponte para qualquer uma das colunas para exibir seus valores individuais. 

##### <a name="analysis"></a>Análise

Usando este relatório, você pode responder às seguintes perguntas e determinar seu próximo curso de ação:

-   Qual é a porcentagem total de falha de configuração de chamada para o mês atual?

-   A porcentagem de falha na configuração total de chamada está abaixo ou acima da métrica de destino definida?

-   A tendência de falha é pior ou melhor do que o mês anterior?

-   A tendência de falha está aumentando, constante ou diminuindo?

Independentemente de suas respostas a essas perguntas, aproveite o tempo para investigar mais, usando os sub-relatórios de adição para procurar qualquer edifício individual ou sub-redes que possam precisar de correção. Embora a taxa de falha geral possa estar abaixo da métrica de destino, as taxas de falha para um ou mais edifícios ou redes podem estar acima da métrica de destino e precisam de investigação.

#### <a name="setup-failure-investigations"></a>Investigações de falha de configuração 

Este relatório de resumo é usado para descobrir e isolar quaisquer edifícios ou redes que possam precisar de correção.

> [!NOTE]
> Certifique-se de ajustar o filtro do relatório Ano Mensal ao mês atual. Selecione **Editar** e ajuste o filtro de relatório **Ano** Mensal para salvar o novo mês padrão.

##### <a name="remediation"></a>Remediação 

Concentre seus primeiros esforços de correção em edifícios ou sub-redes que têm o maior volume de falhas. Isso maximizará o impacto na experiência do usuário e ajudará a reduzir rapidamente a taxa de falhas de configuração de chamada organizacional. A tabela a seguir lista os dois motivos para falhas de configuração conforme relatado pelo CQD.

| Motivo de falhas de configuração de chamada       | Causa típica                    |
|----------------------------------|----------------------------------|
| Missing FW Deep Packet Inspection Exemption Rule | Indica que o equipamento de rede ao longo do caminho impediu que o caminho de mídia fosse estabelecido devido a regras de inspeção profunda de pacotes. Isso é provável porque as regras de firewall não estão sendo configuradas corretamente. Nesse cenário, o handshake TCP conseguiu, mas o handshake SSL não.      |
| Regra de exceção do bloco IP de FW ausente      | Indica que o equipamento de rede ao longo do caminho impediu que o caminho de mídia fosse estabelecido para a rede do Microsoft 365 ou do Office 365. Isso pode acontecer porque as regras de proxy ou firewall não estão configuradas corretamente para permitir o acesso a endereços IP e portas usados para o tráfego do Teams e do Skype for Business. |

Ao iniciar a correção, você pode concentrar seus esforços em um edifício ou sub-rede específico. Como mostra a tabela anterior, esses problemas ocorrem devido a configurações de proxy ou firewall. Revise as opções na tabela a seguir para ver as ações de correção.

|      Remediação      |Orientação  |
|-----------------------|----------|
| Configurar firewalls | Trabalhe com sua equipe de rede e verifique a configuração de firewalls em relação à lista de [endereços IP do Office 365.](https://aka.ms/o365ips)<br><br>Verifique se as [sub-redes de mídia e](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) as portas estão incluídas nas regras de firewall. <br><br>Verifique se as [portas necessárias](prepare-network.md) estão abertas no firewall. O UDP deve ter prioridade porque o TCP é considerado um protocolo de failback para compartilhamento de tela baseado em áudio, vídeo e vídeo, e seu uso afetará a qualidade da chamada. O compartilhamento de aplicativo RDP herddo usa apenas TCP.|

### <a name="drop-failures"></a>Falhas de soltar

Ao contrário dos códigos de falha de configuração, o CQD não tem código de falha de soltar para indicar por que ocorrem falhas de soltar, o que dificulta a isolação de uma causa raiz específica. Para melhorar as falhas de queda de triagem, use uma abordagem inferida. Ao corrigir quaisquer áreas de interesse para mídia, corrigir clientes e drivers e impulsionar o uso de dispositivos certificados para o Teams e o Skype for Business, você pode esperar que as falhas de entrega rebaixem.

#### <a name="drop-failure-trend-analysis"></a>Análise de tendência de falha na entrega

Este relatório exibe a quantidade total de fluxos de áudio, as falhas de queda total e a taxa de falha na entrega. Aponte para qualquer uma das colunas para exibir seus valores. 


##### <a name="analysis"></a>Análise

Usando esse tipo de relatório, você pode responder às seguintes perguntas:

-   Qual é a taxa de falha na entrega atual?
-   A taxa de falha na entrega está abaixo da métrica de destino definida?
-   A tendência de falha é pior ou melhor do que o mês anterior?
-   A tendência de falha está aumentando, constante ou diminuindo?

Independentemente das respostas às perguntas acima, aproveite o tempo para investigar usando os sub-relatórios para procurar qualquer prédio ou rede que precise de correção. Embora a taxa geral de falhas de queda possa estar abaixo da métrica de destino, a taxa de falha de queda para um ou mais edifícios ou redes pode estar acima da métrica de destino e precisar de investigação.

#### <a name="drop-failure-investigations"></a>Drop failure investigations

As falhas relatadas aqui indicam que a chamada foi lançada inesperadamente e resultaram em uma experiência de usuário negativa. Ao contrário dos relatórios mais recentes, esses relatórios fornecem informações adicionais sobre sub-redes específicas que precisam de mais investigação.


##### <a name="remediation"></a>Remediação

Usando os relatórios de tabela incluídos, você pode isolar áreas de problemas na rede onde a taxa de drop está acima da métrica de destino que você definiu. Concentre seus primeiros esforços de correção em edifícios ou sub-redes que possuem a maior contagem total de fluxos, para fazer o maior impacto.

Causas comuns de gotas de chamada:

-   Saída de rede ou internet sub provisionada
-   Nenhuma QoS configurada em redes restritas
-   Versões mais antigas do cliente
-   Comportamento do usuário

Depois de descobrir suas áreas [](use-call-analytics-to-troubleshoot-poor-call-quality.md) de problema, você pode usar a análise de chamada por usuário para revisar ainda mais os usuários nesse prédio para problemas específicos. A análise de chamada contém dados adicionais do EUII e pode ser útil para isolar ainda mais os possíveis motivos para as falhas na entrega.

Independentemente da próxima etapa, é uma boa prática notificar sua equipe de ajuda de que um problema foi descoberto com edifícios ou sub-redes específicos. Isso permite que a ajuda responda rapidamente a chamadas de entrada e a usuários de triagem com mais eficiência. Os usuários sinalizados podem então ser reportados à equipe de engenharia para investigação posterior.

A tabela a seguir lista alguns métodos comuns para gerenciar e remediar falhas de soltar.

| Remediação                              | Orientação                      |
|------------------------------------------|-------------------------------|
| **Rede/internet**                         | **Congestionamento:** trabalhe com sua equipe de rede para monitorar a largura de banda em edifícios/sub-redes específicos para confirmar que há problemas com o uso em excesso. Se você confirmar que há congestionamento de rede, considere aumentar a largura de banda para esse prédio ou aplicar QoS. Use os relatórios resumidos de [Quality Poor Stream](#quality-investigations) incluídos para revisar as sub-redes de problemas para problemas de tremulação, latência e perda de pacotes, pois eles geralmente precederão um fluxo descartado.<br><br>**QoS:** se o aumento de largura de banda for impraticável ou proibitivo de custos, considere a implementação de QoS. Essa ferramenta é muito eficaz no gerenciamento de tráfego congestionado e pode garantir que os pacotes de mídia na rede gerenciada sejam priorizados acima do tráfego não mídia. Como alternativa, se não houver evidências claras de que a largura de banda é a causa da causa, considere estas soluções:<ul><li>[Orientação de QoS do Microsoft Teams](qos-in-teams.md)</li></ul><br>**Realize uma avaliação** de preparação de rede: uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com as alterações de largura de banda e de rede e as práticas de rede recomendadas para o Teams e o Skype for Business. Usando a tabela anterior como fonte, você tem uma lista de edifícios ou sub-redes que são excelentes candidatos a uma avaliação.<ul><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li></ul> |
| **Clientes (somente Skype for Business Online)** | Alguns clientes mais antigos do Skype for Business conheceram e documentaram problemas com a confiabilidade de mídia. Revise os relatórios de Análise de Chamada de vários usuários afetados ou crie um relatório de tabela de versão do cliente personalizada no CQD filtrado para edifícios ou sub-redes específicos com a medida de % de falha total de chamada. Essas informações ajudarão você a entender se existe uma relação entre as gotas de chamada nesse edifício específico e uma versão específica do cliente.     |
| **Dispositivos**                                  |Se os dispositivos são os responsáveis por problemas de qualidade de chamada, considere atualizar dispositivos ofensivos. Leia [telefones para Teams](phones-for-teams.md) para saber mais. |
| **Comportamento do usuário**                            | Se você determinar que não há rede, dispositivos ou clientes como problema, considere o desenvolvimento de uma estratégia de adoção de usuários para instruir os usuários a ingressar e sair melhor das reuniões. Um usuário mais inteligente do Teams e do Skype for Business produzirá uma melhor experiência de usuário para todos os participantes da reunião. Por exemplo, um usuário que colocar seu laptop para dormir (fechando a tampa) sem sair da reunião será classificado como uma chamada inesperada.   |

## <a name="quality-investigations"></a>Investigações de qualidade

A próxima etapa para avaliar o estado da qualidade do áudio em toda a organização é investigar A taxa de fluxo ruim (PSR), TCP e uso de proxy. É importante lembrar-se de que os dados do CQD não fornecem uma causa raiz específica, mas, em vez disso, fornece áreas de problemas prováveis para iniciar uma conversa colaborativa com as equipes apropriadas para atividades de correção. 

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo; no entanto, os métodos de investigação explicados abaixo ainda se aplicarão a esses relatórios. Consulte a descrição individual do relatório para obter mais informações. 

### <a name="quality"></a>Qualidade

As porcentagens PSR são usadas para indicar se a organização está a fim de atender a metas métricas definidas para uma determinada área de foco. É importante observar que, mesmo que as porcentagens de alto nível estão dentro da meta definida, sub-redes individuais ou edifícios podem não atender às metas definidas e, portanto, precisam de mais investigação. Por exemplo, se a porcentagem geral de PSR de áudio for de 2% em abril, que atenda à meta de exemplo, os edifícios individuais e sub-redes ainda poderão ter experiências ruins, dependendo da distribuição geral desses 2%. 

Para avaliar a porcentagem de fluxos ruins, use os relatórios de qualidade. Vários relatórios de qualidade são fornecidos para revisar as métricas de geral, conferência, chamada PSTN, VPN e salas de reunião. Relatórios mensais, semanais e diários são fornecidos para auxiliar nesse processo. Relatórios semanais e diários são limitados ao modelo Redes Gerenciadas para aumentar sua eficácia e reduzir o ruído. 

#### <a name="quality-trend-analysis"></a>Análise de tendência de qualidade

Os relatórios mais recentes exibem informações de qualidade ao longo do tempo e são usados para ajudar a identificar e entender as tendências de qualidade em cada área de interesse. Conforme mencionado acima, há árvores de relatório incluídas nos modelos para investigar a qualidade; conferência, chamada PSTN, VPN e salas de reunião de duas partes. Para fins de análise de qualidade, o processo é o mesmo. No entanto, recomendamos que você comece com a conferência primeiro, pois quaisquer melhorias na qualidade da conferência também afetarão positivamente todas as outras áreas. 

> [!Note]
> Investigar a chamada PSTN e as salas de reunião de duas pessoas é semelhante à investigação da conferência. O foco é isolar edifícios ou sub-redes que têm a pior qualidade e identificar o motivo da baixa qualidade.

> [!Important]
> Os relatórios baseados em VPN são filtrados usando a dimensão Segunda VPN. Essa dimensão exige que o adaptador de rede VPN seja registrado corretamente como um Adaptador de Acesso Remoto. Os fornecedores de VPN não usam confiável esse sinalizador, e sua quilometragem varia de acordo com o fornecedor de VPN implantado em sua organização. Modifique os [relatórios VPN,](CQD-upload-tenant-building-data.md#vpn) se necessário, usando o nome do edifício ou da rede.

##### <a name="investigation"></a>Investigação

Usando esses relatórios, você pode responder às seguintes perguntas:

-   Qual é o total de PSR do mês atual?
-   O PSR está abaixo da métrica de destino definida?
-   A PSR é pior ou melhor do que o mês anterior?
-   A tendência PSR está aumentando, constante ou diminuindo?

Independentemente das respostas para as perguntas acima, aproveite o tempo para investigar usando os sub-relatórios para procurar quaisquer edifícios ou sub-redes que possam precisar de investigação. Embora a PSR geral possa estar abaixo da métrica de destino, muitas vezes o PSR para um ou mais edifícios ou redes está acima da métrica e precisa de correção.

#### <a name="quality-investigations"></a>Investigações de qualidade

Os relatórios resumidos de qualidade dão uma visão mais aprofundada do que contribuiu para que os fluxos fosse classificados como ruins e ajudam a isolar áreas de problemas na rede gerenciada.

Embora as dimensões usadas possam diferir ligeiramente entre o relatório, cada relatório incluirá medidas para o total de fluxos, fluxos totais ruins, PSR e baixa qualidade devido a. Foram criados relatórios para cada área de interesse: conferência, conferência de duas partes, chamada PSTN, VPN e salas de reunião. O modelo rede gerenciada inclui relatórios adicionais para aproveitar as informações de localização carregadas por meio do arquivo de construção.


> [!Note]
> As sub-redes comuns são difíceis de triagem devido ao seu uso generalizado. Um relatório separado que exibe o IP público do cliente (Second Reflexive Local IP) foi adicionado ao modelo Todas as Redes para ajudar na correção de escritórios que usam redes comuns.


![Captura de tela mostrando o resumo do fluxo de áudio ruim](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Remediação

Concentre seus esforços de correção em edifícios ou sub-redes que têm o maior volume de fluxos, pois isso maximizará o impacto e ajudará a melhorar a experiência do usuário rapidamente. Use as medidas de tremição, perda de pacote e tempo de viagem de ida e volta (RTT) para entender o que está contribuindo para a baixa qualidade (é possível que haja mais de um problema):

-   **Tremagem:** Pacotes de mídia estão chegando em velocidades diferentes, o que faz com que um alto-falante soe estranho.
-   **Perda de pacotes:** Pacotes de mídia estão sendo descartados, o que cria o efeito de palavras ou sílabas ausentes.
-   **RTT:** Os pacotes de mídia estão demorando muito para chegar ao destino, o que cria um efeito walkie-talkie.

Para ajudar sua investigação a problemas de qualidade, use a análise de chamada [por usuário.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Com o Recurso de Análise de Chamada, você pode ver uma conferência específica ou o relatório de chamada do usuário. Este relatório conterá dados EUII/PII e será útil quando você estiver procurando a causa de uma falha. Depois que você sabe qual prédio é afetado, deve ser simples rastrear usuários nesse prédio. 

Não se esqueça de dizer à sua equipe de ajuda que essas redes estão enfrentando problemas de qualidade, para que elas possam fazer uma triagem rápida e responder a chamadas recebidas.

| Remediação                              | Orientação                         |
|------------------------------------------|----------------------------------|
| **Redes**                                 | **Congestionamento:** uma rede sobreutilizada ou sub provisionada pode causar problemas com a qualidade da mídia. Trabalhe com a equipe de rede para determinar se as conexões de rede do usuário com o ponto de saída da Internet têm largura de banda suficiente para dar suporte à mídia. <br><br>**Realize uma avaliação** de preparação de rede: uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com as alterações de largura de banda e de rede e as práticas de rede recomendadas para o Teams e o Skype for Business. Usando a tabela anterior como fonte, você tem uma lista de edifícios ou sub-redes que são excelentes candidatos a uma avaliação.<ul><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li></ul>|
| **Qualidade de serviço (QoS)**  | A QoS é uma ferramenta comprovada para ajudar a priorizar pacotes em uma rede congestionada para garantir que eles cheguem ao destino intactos e dentro do prazo. Considere implementar a QoS em toda a sua organização para maximizar a qualidade da experiência do usuário onde a largura de banda está restrita. A QoS ajudará a resolver problemas normalmente associados a altos níveis de perda de pacotes e, em um grau menor, a tremidos e tempos de ida e volta.<ul><li>[Diretrizes de QoS do Teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Wi-Fi pode ter um impacto significativo na qualidade da chamada. Wi-Fi implantações normalmente não levam em consideração os requisitos de rede dos serviços VoIP e geralmente são uma fonte de baixa qualidade. Para saber mais sobre como otimizar sua infraestrutura de Wi-Fi, consulte [este artigo sobre Wi-Fi planejamento.](/skypeforbusiness/certification/plan-wifi)<br><br>**Driver sem** fio: certifique-se de que os drivers sem fio estão atualizados. Isso ajudará a reduzir qualquer experiência ruim do usuário relacionada a um driver desatualizado. Muitas organizações não incluem drivers sem fio em seus ciclos de patch, e esses drivers podem ficar sem sinal por anos. Muitos problemas sem fio são resolvidos garantindo que os drivers sem fio estão atualizados.<br><br>**WMM:** O WMM (Wireless Multimedia Extensions), também conhecido como Wi-Fi Multimídia, fornece recursos básicos de QoS para redes sem fio. Redes sem fio modernas devem dar suporte a vários dispositivos. Esses dispositivos competem pela largura de banda e podem levar a problemas de qualidade para os serviços VoIP, onde a velocidade e a latência são essenciais. Consulte seu fornecedor sem fio para saber detalhes e considere a implementação de WMM em sua rede sem fio para priorizar as mídias do Skype for Business e do Teams.<br><br>**Densidade de pontos de acesso:** os pontos de acesso podem estar muito separados ou não estão em um local ideal. Para minimizar possíveis interferências, coloque pontos de acesso extras em salas de conferência e em locais que não estão obstruídos por paredes ou outros objetos em que o sinal Wi-Fi sinal está fraco.<br><br>**2,4 GHz versus 5 GHz: 5 GHz** fornece menos interferência de plano de fundo e velocidades mais altas, e deve ser priorizado ao implantar VoIP por Wi-Fi. No entanto, 5 GHz não é tão forte quanto 2,4 GHz e não invade paredes tão facilmente. Revise o layout do prédio para determinar com qual frequência você pode contar para a melhor conexão. |
|**Dispositivo de rede** | Organizações maiores podem ter centenas de dispositivos espalhados pela rede. Trabalhe com sua equipe de rede para garantir que os dispositivos de rede do usuário para a Internet sejam mantidos e atualizados. |
| **VPN**  | Os dispositivos VPN não são corretamente projetados para lidar com cargas de trabalho de mídia em tempo real. Algumas configurações de VPN proíbem o uso de UDP (que é o protocolo preferencial para mídia) e dependem apenas de TCP. Considere implementar uma solução de divisão de túnel VPN para ajudar a reduzir a VPN como uma fonte de baixa qualidade. |
| **Clientes** <br>(Somente Skype for Business Online) | Verifique se todos os clientes estão sendo atualizados regularmente. |
| **Dispositivos** | Se os dispositivos são os responsáveis por problemas de qualidade de chamada, considere atualizar dispositivos ofensivos. Leia [telefones para Teams](phones-for-teams.md) para saber mais. |
| **Drivers** | A rede de patch (Ethernet e Wi-Fi), os drivers de áudio, vídeo e USB devem fazer parte da sua estratégia geral de gerenciamento de patch. Muitos problemas de qualidade são resolvidos com a atualização de drivers. |
| **Salas de reunião em Wi-Fi** | É altamente recomendável que dispositivos de sala de reunião sejam conectados à rede usando pelo menos uma conexão Ethernet de 1 Gbps. Os dispositivos de sala de reunião geralmente incluem vários fluxos de áudio e vídeo, além de conteúdo de reunião, como compartilhamento de tela, e têm requisitos de rede mais altos do que outros pontos de extremidade do Teams ou skype for Business. As salas de reunião são, por definição, dispositivos de papel Wi-Fi que proporcionam um benefício somente durante a instalação.<br><br>As salas de reunião precisam ser tratadas com mais cuidado e atenção para garantir que a experiência usando esses dispositivos seja atendida ou exceda as expectativas. Problemas de qualidade com salas de reunião geralmente serão escalonados rapidamente, pois são frequentemente usados pela equipe de nível sênior.<br><br>Com todas as coisas iguais (exceto conveniência), Wi-Fi desempenho geralmente é menor do que uma conexão com fio. Com a ascensão das políticas de "traga seu próprio dispositivo" e a multiplicação de laptops, Wi-Fi pontos de acesso são frequentemente utilizados em excesso. As mídias em tempo real podem não ser priorizadas em redes Wi-Fi, o que pode levar a problemas de qualidade durante os períodos de uso máximo. Esse uso pesado pode coincidir com uma reunião em que pode haver uma dezena de pessoas presentes, cada uma com seu próprio laptop e smartphone, todos conectados ao mesmo ponto de acesso Wi-Fi que o dispositivo da sala de reunião.<br><br>Wi-Fi deve ser considerada apenas como uma solução temporária, para uma instalação móvel ou quando o Wi-Fi tiver sido provisionado corretamente para dar suporte a mídias de classe empresarial e baseadas em tempo real. |


### <a name="tcp"></a>TCP 

O Protocolo de Controle de Transmissão (TCP) é considerado um transporte de failback e não o transporte principal que você deseja para mídia em tempo real. O motivo pelo qual é um transporte de failback é devido à natureza estado do TCP. Por exemplo, se uma chamada for feita em uma rede latente e os pacotes de mídia atrasarem, então os pacotes de alguns segundos atrás, que não são mais úteis, competem pela largura de banda para chegar ao receptor, o que pode tornar uma situação ruim pior. Isso faz com que o audiovisdor se desesque e estenque o áudio, resultando em artefatos audíveis, geralmente na forma de tremida.

Os relatórios desta seção não fazem distinção entre fluxos bons e ruins. Como o UDP é preferencial, os relatórios pesquisam o uso de TCP para áudio, vídeo e compartilhamento de tela baseado em vídeo (VBSS). Taxas de fluxos ruins são fornecidas para ajudar a comparar a qualidade UDP versus a qualidade TCP para que você possa concentrar seus esforços onde o impacto é maior. O uso de TCP é causado principalmente por regras de firewall incompletas. Para obter mais informações sobre regras de firewall para o Teams e o Skype for Business Online, consulte URLs e intervalos de endereços IP do [Microsoft 365 e office 365.](https://aka.ms/o365ips)

> [!Note]
> Áudio, vídeo e VBSS preferem UDP como seu transporte principal. A carga de trabalho de Compartilhamento de Aplicativo RDP herdda usa apenas TCP.

#### <a name="tcp-usage"></a>Uso de TCP

Os relatórios TCP indicam o uso geral de TCP nos últimos sete meses. Todos os relatórios nesta seção se concentrarão em restringir edifícios e sub-redes específicos onde o TCP é mais usado. Os relatórios separados estão disponíveis para fluxos de conferência e de duas partes.

![Gráfico mostrando a porcentagem de fluxos de áudio que usam TCP](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Investigação

Usando este relatório, você pode responder às seguintes perguntas:

-   Qual é o volume total de fluxos TCP do mês atual?
-   É pior ou melhor do que o mês anterior?
-   A tendência de uso de TCP está aumentando, constante ou diminuindo?
-   O PSR TCP é igual ao meu PSR geral?

Se você perceber que a tendência de uso de TCP está aumentando ou acima do uso mensal normal, tire um tempo para investigar usando os sub-relatórios para procurar quaisquer edifícios ou redes que possam precisar de correção. O ideal é que você queira o máximo de sessões de áudio baseadas em TCP na rede gerenciada.

#### <a name="tcp-vs-udp"></a>TCP vs. UDP

Este relatório identifica o volume de relatórios de uso TCP versus UDP no mês mais recente para compartilhamento de tela baseado em áudio, vídeo e vídeo (VBSS). 

![Relatório mostrando o volume de fluxos que usam TCP versus UDP](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Análise

Embora você queira que o uso de TCP seja o mais baixo possível, talvez você veja um pouco de uso de TCP em uma implantação de outra forma saudável. O TCP por si só não contribui para uma chamada ruim, portanto, as taxas de fluxo são fornecidas para ajudar a identificar se o uso de TCP contribui para a baixa qualidade. 

#### <a name="tcp-investigations"></a>Investigações TCP

Nos modelos CQD fornecidos, navegue até os Fluxos TCP criando e sub-rede usando o modelo Redes Gerenciadas ou Todas as Redes. Para fins de investigação do uso de TCP, o processo é o mesmo, portanto, concentraremos a discussão aqui na conferência.


##### <a name="remediation"></a>Remediação

Este relatório identifica edifícios e sub-redes específicos que contribuem para o volume de uso de TCP. Um relatório adicional também é incluído para identificar o IP do Microsoft Relay que foi usado na chamada para ajudar a isolar as regras de firewall ausentes. Concentre seus esforços de correção nos edifícios que têm o maior volume de fluxos TCP para maximizar o impacto.

A causa mais comum do uso de TCP é a falta de regras de exceção em firewalls ou proxies. Vamos falar sobre proxies na próxima seção, portanto, por enquanto, concentre seus esforços nos firewalls. Usando o edifício ou a sub-rede fornecida, você pode determinar qual firewall precisa ser atualizado.

| Remediação        | Orientação     |
|--------------------|--------------------------------------|
| Configurar firewall | Verifique se as portas e endereços IP do [Microsoft 365 ou office 365](https://aka.ms/o365ips) foram excluídos do firewall. Para problemas TCP relacionados à mídia, concentre seus esforços iniciais no seguinte:<ul><li>Verifique se as sub-redes de mídia do cliente 13.107.64.0/18 e 52.112.0.0/14 estão em suas regras de firewall.</li><li>As portas UDP 3478-3481 são as portas de mídia necessárias e devem ser abertas, caso contrário, o cliente falhará novamente na porta TCP 443.</li></ul> |
| Verificar             | Use a [Ferramenta de](https://www.microsoft.com/download/details.aspx?id=53885) Avaliação de Rede da Microsoft para verificar se há problemas de conectividade com endereços IP específicos do Microsoft 365 ou office 365 e portas do edifício ou da sub-rede afetados.    |

### <a name="http-proxy"></a>Proxy HTTP

Os proxies HTTP não são o caminho preferencial para estabelecer sessões de mídia, por vários motivos. Muitos contêm recursos de inspeção profunda de pacotes que podem impedir a conclusão de conexões com o serviço e introduzir interrupções. Além disso, quase todos os proxies forçam TCP em vez de permitir UDP, o que é recomendável para uma ótima qualidade de áudio.

Sempre recomendamos que você configure o cliente para se conectar diretamente ao Teams e aos serviços do Skype for Business. Isso é especialmente importante para o tráfego baseado em mídia.


> [!IMPORTANT]
> Recomendamos que você carregue um [arquivo de](CQD-upload-tenant-building-data.md) construção válido para que possa distinguir dentro de fluxos de áudio externos ao analisar o uso do proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

O relatório de fluxo proxy HTTP nesta seção do modelo é muito parecido com os relatórios TCP. Ele não vê se as chamadas são ruins ou boas, mas se a chamada está conectada por HTTP.

![Captura de tela do relatório de fluxos de áudio que usam HTTP](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Análise

Você deseja ver o máximo de fluxos de mídia HTTP possível. Se você tiver fluxos que atravessam o proxy, consulte sua equipe de rede para garantir que as exclusões adequadas sejam realizadas para que os clientes sejam roteando diretamente para as sub-redes de mídia do Teams ou do Skype for Business Online.

Se você tiver apenas um proxy da Internet em sua organização, verifique as [URLs adequadas do Microsoft 365 ou office 365](https://aka.ms/o365ips)e as exclusões de intervalo de endereços IP. Se mais de um proxy da Internet estiver configurado em sua organização, use o sub-relatório HTTP para isolar qual edifício ou sub-rede será afetado.

Para organizações que não conseguem ignorar o proxy, certifique-se de que o cliente Skype for Business está configurado para entrar corretamente quando estiver localizado atrás de um proxy, conforme descrito no artigo [Skype for Business](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin)deve usar o servidor proxy para entrar em vez de tentar conexão direta. 


#### <a name="http-proxy-investigations"></a>Investigações de proxy HTTP

Este relatório identifica edifícios e sub-redes específicos que contribuem para o uso de HTTP.


##### <a name="remediation"></a>Remediação

Recomendamos [que](proxy-servers-for-skype-for-business-online.md) você sempre ignore proxies para o Skype for Business e o Teams, especialmente o tráfego de mídia. Proxies não tornar o Skype for Business mais seguro, porque seu tráfego já está criptografado. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Problemas como esses resultarão em uma experiência negativa com áudio, vídeo e compartilhamento de tela, onde os fluxos em tempo real são essenciais.

A causa mais comum do uso de HTTP é a falta de regras de exceção em proxies. Usando o edifício ou sub-rede fornecido, você pode determinar rapidamente qual proxy precisa ser configurado para ignorar mídia.

Verifique se os FQDNs necessários do [Microsoft 365 ou do Office 365](https://aka.ms/o365ips) estão na lista de branco no seu proxy.

## <a name="endpoint-investigations"></a>Investigações do ponto de extremidade

Esta seção se concentra nas tarefas para relatórios sobre versões do cliente e o uso de dispositivos certificados. Os relatórios estão disponíveis para uso de contorno para versões do cliente, tipo de cliente, dispositivos de captura e drivers (microfone), dispositivos de captura de vídeo e Wi-Fi versões de fornecedor e driver.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo; no entanto, os métodos de investigação explicados abaixo ainda se aplicam. Consulte a descrição individual do relatório para obter mais informações.

### <a name="client-versions"></a>Versões do cliente

Esses relatórios se concentram na identificação das versões do cliente Skype for Business em uso e no volume relativo no ambiente.

> [!IMPORTANT]
> Atualmente, os clientes do Teams são distribuídos e atualizados automaticamente por meio da Rede de Distribuição de Conteúdo do Azure e serão atualizados pelo serviço. Como resultado, você não precisa monitorar as versões do cliente do Teams (a menos que você desligue a atualização automática, o que não recomendamos).

A menos que você exclua dados de participantes federados, esses relatórios incluirão a telemetria do cliente de pontos de extremidade federados. Para excluir pontos de extremidade federados, você deve adicionar um filtro de consulta para a ID do Segundo Locatário definida à ID de locatário da [sua organização.](CQD-data-and-reports.md#how-to-find-your-tenant-id) Como alternativa, você pode usar um filtro [de URL](CQD-data-and-reports.md#url-filters) para excluir a telemetria de participantes federados.



#### <a name="remediation"></a>Remediação

Uma parte fundamental para impulsionar as experiências de usuário de alta qualidade é garantir que os clientes gerenciados estão executando versões atualizadas do Skype for Business, além de garantir que os drivers de áudio, vídeo, rede e USB de suporte estão atualizados. Isso fornece vários benefícios, entre eles: 

-   É mais fácil gerenciar algumas versões em comparação com muitas versões.
-   Ele fornece um nível de consistência de experiência.
-   Isso facilita a solução de problemas com a qualidade e a usabilidade das chamada.
-   A Microsoft continuamente faz melhorias e otimizações gerais em todo o produto. Garantir que os usuários recebam essas atualizações reduz o risco de se deem conta de um problema que já foi resolvido.

Limitar sua implantação a versões do cliente com menos de seis meses melhorará a experiência geral do usuário e melhorará a capacidade de gerenciamento reduzindo o número de versões que precisam ser suportadas.

Se você estiver usando apenas o Office com Clique para Executar, estará automaticamente dentro da janela de seis meses. Nenhuma ação é necessária.

Se você tiver uma combinação de pacotes Clique para Executar e instalador (MSI), poderá usar o relatório para verificar se os clientes MSI estão sendo atualizados regularmente. Se você perceber que os clientes estão ficando para trás, trabalhe com a equipe responsável pelo gerenciamento de atualizações do Office e certifique-se de que eles estão aprovando e implantando patches de cliente regularmente.

Também é importante considerar e garantir que os drivers de rede, vídeo, USB e áudio também estão sendo remendados. Pode ser fácil ignorar esses drivers e não incluí-los em sua estratégia de gerenciamento de patch.

Os números de versão do Skype for Business podem ser encontrados nos links abaixo:

-   [Informações de versão para atualizações para aplicativos do Microsoft 365](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Histórico de atualizações para aplicativos do Microsoft 365 para empresas](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Downloads e atualizações do Skype for Business](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para usar o relatório do dispositivo de microfone, precisamos entender o conceito da média de MOS (pontuação média de opinião). MOS é a medida padrão-ouro para avaliar a qualidade de áudio percebida. Ela é representada como uma classificação inteira de 0 a 5.

A base de todas as medidas de qualidade da voz é como uma pessoa percebe a qualidade da fala. Como ela é afetada pela percepção humana, é inerentemente subjetivo. Há várias metodologias diferentes para testes subjetivos. A maioria das medidas de qualidade de voz se baseia em uma escala de classificação de categorização absoluta (ACR).

Em um teste subjetivo ACR, um número significativo considerável de pessoas taxa sua qualidade de experiência em uma escala de 1 (ruim) para 5 (excelente). A média das pontuações é o MOS. As MOS resultantes dependem do intervalo de experiências que foram expostas ao grupo e do tipo de experiência que está sendo classificada.

Como não é prático realizar testes subjetivos de qualidade de voz para um sistema de comunicação ao vivo, o Microsoft Teams e o Skype for Business geram valores de MOS usando algoritmos avançados para prever objetivamente os resultados de um teste subjetivo.

O conjunto disponível de MOS e métricas associadas fornece uma visão da qualidade da experiência que está sendo entregue aos usuários por um dispositivo de áudio. 

Ao fornecer aos usuários dispositivos certificados para o Teams e o Skype for Business, você reduz a probabilidade de encontrar experiências negativas devido ao próprio dispositivo (o que é mais provável, por exemplo, com alto-falantes e microfones de laptop interno). Para obter mais informações, consulte estes artigos sobre o programa [de certificação](/SkypeForBusiness/certification/overview) e o catálogo de [soluções de parceiros.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

Os relatórios de dispositivo são usados para avaliar o uso do dispositivo por volume e pontuação de MOS (somente áudio) e podem ser encontrados nos modelos que acompanham em Clientes & Dispositivos. 

> [!IMPORTANT]
> A menos que você exclua dados de participantes federados, esses relatórios incluirão a telemetria do cliente de pontos de extremidade federados. Para excluir pontos de extremidade federados, você deve adicionar um filtro de consulta para a **ID** do Segundo Locatário definida à ID de locatário da [sua organização.](CQD-data-and-reports.md#how-to-find-your-tenant-id) ALternatively, você pode usar um filtro [de URL](CQD-data-and-reports.md#url-filters) para excluir a telemetria de participantes federados.


> [!Note]
> Você pode notar ao exibir este relatório que vê o mesmo dispositivo relatado várias vezes. Isso ocorre devido à maneira como o dispositivo é reportado ao CQD. As diferenças no hardware e na localidade do sistema operacional causam diferenças na forma como os dados do dispositivo são relatados.

##### <a name="remediation"></a>Remediação

Normalmente, você precisará descobrir e fases de dispositivos não certificados e substituí-los por dispositivos certificados. Algumas considerações ao revisar os relatórios do dispositivo incluem:

-   Os dispositivos em uso estão certificados para o Teams e o Skype for Business? 
-   Você pode identificar usuários de um dispositivo específico usando a análise de chamada [por usuário.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Verifique se eles têm os drivers de dispositivo mais recentes e se o dispositivo não está conectado por meio de um hub USB ou de uma estação de encaixe. 
-   Quantas versões diferentes de vários drivers estão em uso? Eles estão sendo remendados regularmente? Garantir que os drivers de áudio, vídeo e Wi-Fi sejam remendados regularmente ajudarão a eliminá-los como uma fonte de problemas de qualidade e tornar a experiência do usuário mais previsível e consistente.

##### <a name="audio"></a>Áudio

A próxima tarefa é determinar o uso geral de dispositivos [de áudio certificados.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) Recomendamos que pelo menos 80% de todos os fluxos de áudio usem um dispositivo de áudio certificado. Isso é melhor feito exportando o relatório de dispositivos de microfone para o Excel para calcular o uso de dispositivos certificados ou aprovados. Normalmente, as organizações mantêm uma lista de todos os dispositivos aprovados, portanto, a filtragem e a classificação dos dados devem ser simples.

##### <a name="video"></a>Vídeo

Os drivers de vídeo também são importantes para se manterem atualizados. Garantir que as placas de vídeo sejam regularmente corrigidas ajudará a excluir drivers de vídeo como uma fonte de baixa qualidade para fluxos de vídeo. Usar [dispositivos de vídeo](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) certificados ajudará a garantir uma experiência tranquila e de alta qualidade do usuário. Os dispositivos de vídeo compatíveis com codificação nativa H.264 são preferenciais para reduzir o uso da CPU durante a videoconferência.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi drivers também precisam ser remendados regularmente e devem ser incluídos em sua estratégia de gerenciamento de patch. Muitos problemas de qualidade podem ser corrigidos mantendo os drivers de Wi-Fi atualizados. Para saber mais sobre como otimizar sua infraestrutura de Wi-Fi, consulte [este artigo sobre Wi-Fi planejamento.](/skypeforbusiness/certification/networking-wifi)


## <a name="related-topics"></a>Tópicos relacionados

[Usar o Advisor para Teams](use-advisor-teams-roll-out.md)

[Preparar sua rede para o Teams](prepare-network.md)

[Princípios de Conectividade de Rede do Office 365](https://aka.ms/pnc)

[Análises e relatórios do Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Gerenciar seus dispositivos no Teams](device-management.md)

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados de locatário e de construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de Fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
