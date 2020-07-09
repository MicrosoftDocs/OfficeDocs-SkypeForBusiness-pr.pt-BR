---
title: Usar o CQD para gerenciar a qualidade da chamada e da reunião no Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Saiba como analisar e gerenciar o desempenho de mídia em tempo real no Microsoft Teams usando o painel de qualidade de chamada (CQD).
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
ms.openlocfilehash: 60d3c2ad7c7f8c77fb9d6d7f01f937ffb0998a08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085977"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usar o CQD para gerenciar a qualidade da chamada e da reunião no Microsoft Teams 

Este artigo ajudará você-o administrador de equipes ou o engenheiro de suporte e assistência técnica a desenvolver um processo para monitorar e manter a qualidade da chamada e da reunião da sua organização usando o painel de qualidade de chamada do Microsoft Teams (CQD). Nossas diretrizes enfatizam os cenários de qualidade de áudio porque qualquer melhoria de rede que você fizer para melhorar a experiência de áudio será traduzida para melhorias no vídeo e no compartilhamento.

A chave para esta orientação são os dois [modelos de CQD organizados](https://aka.ms/QERtemplates) -recomendamos que você o Baixe antes de seguir as diretrizes deste artigo.

Este artigo pressupõe que você já [configurou o CQD](turning-on-and-using-call-quality-dashboard.md).


## <a name="categories-to-monitor-and-maintain"></a>Categorias para monitorar e manter

Depois de organizar reuniões e voz no Microsoft Teams, você precisará de um plano para monitoramento e manutenção contínuos. Isso garantirá que o Microsoft Teams esteja sempre funcionando de forma ideal. Esse plano deve incluir as principais áreas listadas abaixo. Você também deve estabelecer alvos para métricas de qualidade e um plano para solucionar problemas e isolar problemas quando eles acontecem.

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
<p>Divida as métricas por chamadas internas (em sua organização, como VPN, WiFi, com fio) ou chamadas externas</p>
<p>Divida as métricas pelo prédio ou pela rede</p>
<p>Chamadas de VPN</p>
<p>Chamadas usando TCP, UDP ou proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Confiabilidade da chamada</strong></td>
<td><p>Identificar e corrigir problemas de rede ou firewall</p>
<p>Obter ideias sobre as porcentagens de configuração de chamadas e falhas de soltura</p>
<p>Saiba onde a maioria das falhas de configuração de chamada e queda ocorre</p>
</td>
</tr>
<tr class="odd">
<td><strong>Pesquisa de usuário</strong></td>
<td>
<p>Use taxas de dados de minha chamada para saber mais sobre a experiência real dos usuários</p>
<p>Onde ocorrem as experiências ruins?</p>
<p>Correlacione a experiência deficiente com a qualidade da chamada, a confiabilidade e os dispositivos</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivos</strong></td>
<td><p>Saiba quais microfones e alto-falantes são usados com mais frequência e o impacto sobre a qualidade da chamada</p>
<p>Os drivers de suporte de áudio, vídeo, USB e WiFi estão sendo corrigidos regularmente?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clientes</strong></td>
<td>
<p>Saiba quais tipos e versões de cliente estão sendo usados e o impacto sobre a qualidade da chamada e a confiabilidade  </p>
</ol></td>
</tr>
</tbody>
</table>

Ao avaliar continuamente e corrigir as áreas descritas neste artigo, você pode reduzir o potencial de afetar negativamente seus usuários. A maioria dos problemas de usuário pode ser agrupada nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy
-   Cobertura insatisfatória da rede Wi-Fi
-   Largura de banda insuficiente
-   VPN
-   Versões e drivers inconsistentes ou desatualizados do cliente
-   Dispositivos de áudio não otimizados ou internos
-   Dispositivos de rede ou sub-redes com problemas

Por meio de planejamento e design adequados antes de implantar o Skype for Business ou o Skype for Business Online, você pode reduzir a quantidade de esforço que será necessária para manter experiências de alta qualidade.

Este artigo se concentra em usar o painel de qualidade de chamada (CQD) online como a principal ferramenta para denunciar e investigar cada área, com uma ênfase especial no áudio para melhorar a adoção e o impacto. Qualquer melhoria feita na rede para melhorar a experiência de áudio também será traduzida diretamente para melhorias no vídeo e no compartilhamento de área de trabalho.

Para acelerar a avaliação, [dois modelos do CQD](https://aka.ms/qertemplates) são fornecidos: um é para gerenciar todas as redes e a outra é filtrada somente para redes gerenciadas (internas). Embora os relatórios de modelo todas as redes sejam configurados para exibir informações de construção e de rede, eles ainda podem ser usados enquanto você trabalha para coletar e carregar informações de construção. Carregar as informações de construção no CQD permite que o serviço Aprimore os relatórios ao adicionar informações personalizadas de construção, rede e localização, ao diferenciar internas de sub-redes externas. Para obter mais informações, leia [mapeamento de edifício](CQD-building-mapping.md).

### <a name="intended-audience"></a>Público-alvo

Este artigo destina-se a ser usado por parceiros e clientes interessados com funções como líder de colaboração/arquiteto, consultor, gerenciamento de alterações/especialista de adoção, líder de suporte/suporte técnico, líder de rede, líder de desktop e administrador de ti.

Este artigo também deve ser usado pelo (s) especialista (s) de qualidade designado (s). Para obter mais informações, consulte [a função Champion de qualidade](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>O que é qualidade?

Nesse contexto, a qualidade é uma combinação de métricas de serviço e experiência do usuário.


### <a name="service-metrics"></a>Métricas do serviço

As métricas do serviço consistem em métricas específicas baseadas no cliente. Durante cada chamada, o cliente coleta a telemetria para a chamada e envia um relatório no final de cada chamada que pode ser acessada posteriormente no CQD ou na [análise de chamadas por usuário](set-up-call-analytics.md). Essas métricas incluem (mas não estão limitadas a):

-   Fluxo ruim (entrada e saída)
-   Taxa de falha de configuração
-   Taxa de falha de soltura


#### <a name="poor-stream-rate"></a>Taxa de fluxo ruim

A taxa de fluxo deficiente (PSR) representa a porcentagem geral de fluxos da organização que têm baixa qualidade. Essa métrica se destina a destacar áreas em que a sua organização pode concentrar esforços para ter o maior impacto em relação à redução desse valor e melhorar a experiência do usuário, que é por isso que as [redes gerenciadas](#managed-versus-unmanaged-networks) são o foco principal ao olhar para o PSR. Os usuários externos também são importantes, mas a investigação é diferente de acordo com a organização. Considere fornecer práticas recomendadas para usuários externos e investigar chamadas externas independentemente da organização como um todo.

A medida real no CQD varia de acordo com a carga de trabalho, mas para os fins deste artigo, nos concentramos principalmente na medição de _porcentagem de porcentagem de áudio ruim_ . PSR é composto de cinco médias de métricas de rede descritas na tabela a seguir. Para que um fluxo seja classificado como ruim, apenas uma métrica precisa exceder o limite definido. O CQD fornece o "fraco devido a..." medidas para entender melhor qual condição fez com que o fluxo seja classificado como ruim. Para saber mais, leia [classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> O CQD fornece o "fraco devido a..." medidas para entender melhor qual condição fez com que o fluxo seja classificado como ruim.


##### <a name="audio-poor-quality-metrics"></a>Métricas de áudio de baixa qualidade

| Média métrica     | Descrição     | Experiência do usuário |
|-------------|-----------------|-----------------|
| Tremulação de \> 30 ms        | Esta é a alteração média no atraso entre pacotes sucessivos. O Microsoft Teams e o Skype for Business podem adaptar-se a alguns níveis de tremulação por meio do buffer. Só quando a tremulação excede o buffer que um participante observa os efeitos de tremulação.      | Os pacotes que chegam em diferentes velocidades fazem com que a voz de um palestrante seja Sound robótico.   |
| Taxa de perda \> de pacotes 10% ou 0,1        | Isso geralmente é definido como uma porcentagem de pacotes perdidos. A perda de pacotes afeta diretamente a qualidade do áudio, desde pacotes pequenos e perdidos individuais que praticamente não afetam as perdas de intermitência back-to-back que fazem com que o áudio seja recortado completamente.     | Os pacotes que estão sendo ignorados e não chegando ao destino pretendidos causam lacunas na mídia, resultando em sílabas e palavras perdidas e vídeo e compartilhamento instável. |
| Tempo de ida e volta \> 500 MS        | Esse é o tempo necessário para obter um pacote IP de um ponto a para o ponto B e voltar ao ponto a. Esse atraso de propagação de rede está ligado à distância física entre os dois pontos e a velocidade da luz e inclui a sobrecarga adicional tomada pelos vários dispositivos no caminho de rede.      | Os pacotes que demoram muito tempo para chegarem ao destino causam um efeito de faça de fala.   |
| Média de degradação de NMOS \> 1,0         | Média de [pontuação média média de opinião (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) para o fluxo. Representa o quanto a perda de rede e a tremulação afetaram a qualidade do áudio recebido que fez com que o NMOS essoltar em mais de um ponto. | Isso é uma combinação de tremulação, perda de pacote e, até um menor grau, um aumento no tempo de ida e volta. O usuário pode estar enfrentando uma combinação desses sintomas.   |
| Índice médio de amostras ocultas \> 7% ou 0, 7 | Razão média do número de quadros de áudio com amostras ocultas geradas pelo reparo de perda de pacotes para o número total de quadros de áudio. Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede ignorados.      | Valores altos indicam que os níveis significativos de ocultação de perda foram aplicados e resultaram em um áudio distorcido ou perdido.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Por que preferimos usar fluxos em vez de chamadas?

Os fluxos nos permitem saber qual trecho específico da chamada foi mal-enviado ou recebido. Quando você estiver olhando para a análise de chamadas para uma chamada ruim, determine se a chamada baixa era devido ao fluxo do chamador (de saída) ou do receptor do chamador (de entrada). Determinar qual fluxo está afetando a qualidade das chamadas é ainda mais importante para conferências. Se você estiver apenas procurando dados da chamada, verá quantas conferências uma pessoa participa, mas não verá quais pessoas são caixas acústicas ativas, fazendo a maioria dos recursos de compartilhamento de tela.

Os dados de chamadas fornecem métricas de uso, mas não levarão isso necessariamente para a causa básica de uma qualidade de chamada ruim. Ao olhar a direção do fluxo, você pode identificar fatores como uma chamada que não está em uma rede gerenciada, uma chamada de um não funcionário (por exemplo, um fornecedor ou alguém em uma rede diferente). Nesses casos, se a conexão de rede da outra pessoa fosse ruim, toda a chamada será sinalizada como ruim. Você não pode fazer nada sobre fatores externos, portanto, esses dados não são úteis.

A direção do fluxo também pode ajudá-lo a identificar dispositivos ou clientes problemáticos.

 - Por exemplo, se você tiver um orçamento limitado para dispositivos e quiser fornecer dispositivos somente para usuários pesados de áudio, use o relatório de uso de áudio (VoIP) e o filtro para fluxos de trabalho de saída e conferência. Procure por usuários de áudio de alto volume, que estão falando em microfones integrados, que podem ser correlacionados a uma qualidade de chamada mais baixa (e você talvez queira fornecer dispositivos de áudio para essas pessoas). Para maior clareza, você pode filtrar por utilização de pacotes, o que permite que você direcione especialmente para usuários de áudio de alto volume. 

  - Outro exemplo envolve o compartilhamento de tela. Se um cliente estiver usando um antigo cliente do Teams, o desempenho do compartilhamento de tela pode ser afetado. Para solucionar esse problema, Priorize as atualizações do cliente para as pessoas que fazem muita parte do compartilhamento de tela.

 - Ao identificar qual direção de um fluxo está causando baixa qualidade de chamadas, você pode determinar se tem um problema de QoS ou relacionado à largura de banda. Se você não implementou completamente a QoS ou se apenas marcar os pacotes no cliente e não no fluxo de entrada, talvez veja uma qualidade de chamada inferior. Ao olhar a direção do fluxo, você pode obter uma visão mais granular da perda de pacotes, latência ou tremulação em uma direção específica. 

   - Por exemplo, digamos que um usuário faça uma reclamação de áudio robótico em uma conexão com fio (tremulação). Olhando no fluxo e na direção, você pode determinar que o problema ocorre no fluxo de entrada, somente para um conjunto específico de sub-redes. Depois de fornecer essas informações para a sua equipe de rede, elas podem controlá-la para um acelerador WAN mal configurado que não ignorasse o tráfego de mídia. Depois que a equipe de rede reconfigurar o acelerador WAN, a tremulação da tremulação desaparece e a qualidade da chamada melhora. 


#### <a name="setup-failure-rate"></a>Taxa de falha de configuração

A taxa de falha de configuração, caso contrário, conhecida como a medida de _porcentagem total da falha de configuração de chamada_ no CQD, é o número de fluxos nos quais o caminho da mídia não pôde ser estabelecido entre os pontos de extremidade no início da chamada.

Isso representa qualquer fluxo de mídia que não pode ser estabelecido. Devido à gravidade do impacto desse problema na experiência do usuário, o objetivo é reduzir esse valor o mais próximo do zero possível. Um valor alto para essa métrica é mais comum em novas implantações com regras de firewall incompletas do que uma implantação maduro, mas ainda é importante assistir regularmente.

Essa métrica é calculada pela criação do número total de fluxos que falharam ao configurar dividido pelo número total de fluxos que enviaram um registro de detalhe de chamada (CDR) bem-sucedido:

-   **Taxa de falha de configuração** = total da configuração da chamada falha na contagem do fluxo/total do fluxo de CDR disponível

#### <a name="drop-failure-rate"></a>Taxa de falha de soltura

A taxa de falha de soltura, caso contrário, conhecida como a medida de _porcentagem de falha de chamada ignorada_ no CQD, é a porcentagem de fluxos estabelecidos com êxito onde o caminho da mídia não terminou normalmente.

Isso representa qualquer fluxo de mídia que foi encerrado inesperadamente. Embora o impacto disso não seja tão grave quanto um fluxo que falhou ao configurar, ele ainda afeta negativamente a experiência do usuário. Quedas de mídia súbitas e frequentes não só podem ter um sério impacto sobre a experiência do usuário, elas resultam na necessidade dos usuários se reconectarem, resultando em perda de produtividade (não para mencionar frustração).

A métrica é calculada com o número total de fluxos soltos dividido pela contagem total de fluxos configurados com êxito:

-   **Ignorar taxa de falha** = número total de chamadas ignoradas contagem de fluxo/configuração da chamada total de fluxo

### <a name="define-your-target-metrics"></a>Definir suas métricas de destino

Esta seção discute algumas das métricas básicas de serviço que usamos para avaliar a integridade dos serviços. Ao avaliar e dirigir continuamente os esforços para manter essas métricas abaixo dos seus destinos definidos, você ajudará a garantir que seus usuários tenham uma qualidade de chamada consistente e confiável. Como ponto de partida, use os alvos sugeridos na tabela abaixo. Ajuste os destinos conforme necessário para atender seus objetivos de negócios.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de rede</th><th rowspan="1">Metas de qualidade</th><th colspan="2">Metas de confiabilidade</th></tr>
<tr><th>Taxa de fluxo de áudio ruim</th><th>Taxa de falha de configuração</th><th>Taxa de falha de soltura</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Geral</td><td>3,0%</td><td>1,0%</td><td>3,0%</td></tr>
<tr><td rowspan="5"><strong>Conferências</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Com fio interno</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Conexão interna Wi-Fi 5 GHz</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 2,4 GHz interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Geral</td><td>2,0%</td><td>0,5%</td><td>3,0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Conexão interna com fio/Wi-Fi 5 GHz</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Com fio/Wi-Fi 5 GHz em geral</td><td>2,0%</td><td>1,0%</td><td>1,0%</td></tr>
<tr><td>Geral</td><td>2,0%</td><td>1,0%</td><td>3,0%</td></tr>
</table>

### <a name="user-experience"></a>Experiência do usuário

A análise da experiência do usuário é mais moderna do que a ciência, pois as métricas coletadas aqui nem sempre significam que há um problema com a rede ou o serviço, mas elas simplesmente indicam que o usuário percebe um problema. O CQD inclui um mecanismo de pesquisa incorporado — classifique minha chamada (RMC), para ajudar a medir a experiência geral do usuário. O RMC fornecerá uma visão geral das seguintes perguntas da perspectiva de seus usuários:

-   Eu sei como usar a solução?
-   A solução é fácil de usar e intuitiva e oferece suporte a minhas necessidades de comunicação do dia-a-dia?
-   A solução me ajuda a fazer com que meu trabalho seja feito?
-   Qual é a minha percepção geral da solução?
-   Posso usar a solução em qualquer point-in-time, independentemente de onde estou?
-   Eu posso configurar e manter uma chamada?

#### <a name="rate-my-call"></a>Classificar minha chamada 

Classifique minha chamada (RMC) incorporada ao Teams e ao Skype for Business. Ele é automaticamente exibido após uma a cada 10 chamadas ou 10%. Esta pesquisa rápida pede que o usuário avalie a chamada e forneça um pequeno contexto para o motivo pelo qual a qualidade da chamada pode ter sido ruim. Uma ou duas classificações são consideradas ruins, de três a quatro são boas e cinco são excelentes. Embora seja um indicador de defasagem, essa é uma métrica útil para a descoberta de problemas que as métricas de serviço podem perder.

> [!Note]
> O fator humano: os usuários costumam ignorar a pesquisa quando a qualidade da chamada é boa e elas o preenchem quando a qualidade da chamada é ruim. Como resultado, seus relatórios do RMC podem ser distorcidos para o lado fraco, mesmo que as métricas do serviço sejam boas.

Você pode usar o CQD para relatar as respostas de usuários do RMC e os relatórios de exemplo estão incluídos no modelo CQD. No entanto, eles não são discutidos detalhadamente neste artigo. 

#### <a name="client-and-device-readiness"></a>Preparação do cliente e do dispositivo

Você precisa de uma estratégia de cliente e dispositivo sólida para ajudar a garantir que seus usuários tenham uma experiência de usuário consistente e positiva. Alguns princípios importantes impulsionam cada estratégia de preparação.

##### <a name="client-readiness"></a>Preparação do cliente

Manter o cliente do teams atualizado garante que seus usuários sempre estejam obtendo a melhor experiência possível. A Microsoft libera [atualizações frequentes para o cliente do teams](teams-client-update.md) (a atualização é instalada em segundo plano, a menos que você tenha desativado essa funcionalidade, que não recomendamos). Também é importante lembrar-se de corrigir drivers de rede, vídeo, USB e áudio, pois eles geralmente são ignorados e podem afetar a qualidade da chamada e da reunião. Considere adicionar drivers de rede, Wi-Fi, de vídeo, USB e de áudio ao seu processo atual de gerenciamento de patches.


##### <a name="device-readiness"></a>Preparação do dispositivo

Nenhuma estratégia única pode afetar a experiência do usuário mais do que a estratégia de preparação do dispositivo. Por exemplo, os usuários que dependem de seus alto-falantes de laptops e microfone terão muito ruído de fundo em chamadas e reuniões. O Microsoft Teams foi projetado para funcionar com praticamente qualquer dispositivo, mas se você estiver tendo problemas relacionados a dispositivos, confira o [telefone para o Microsoft Teams](phones-for-teams.md).


### <a name="categories-of-quality"></a>Categorias de qualidade

Operacionale um conjunto de práticas de gerenciamento de qualidade: Isso proporciona a melhor probabilidade de boa qualidade de chamada e de qualidade de reunião. Um bom plano de gerenciamento de qualidade aborda estas categorias:

-   **Rede:** Qualidade de áudio focada na métrica de baixa taxa de fluxo (PSR), uso do TCP, sub-redes com fio e sem fio e identificação do uso de proxies HTTP e VPN

-   **Pontos de extremidade:** Dispositivos de áudio e clientes atualizados

-   **Gerenciamento de serviços:** Esta categoria contém duas seções:

    -   A primeira é a responsabilidade da Microsoft de gerenciar e manter o Teams e os serviços do Skype for Business online.

    -   Segundo são tarefas que sua organização gerencia para garantir o acesso confiável ao serviço, como a atualização de informações de construção e a manutenção de firewalls para novos endereços IP do Office 365 à medida que a infraestrutura é adicionada ao serviço.

![Gráfico das categorias de qualidade em uma organização](media/qerguide-image-categories.png "As categorias de qualidade em uma organização: gerenciamento de serviços, pontos de extremidade e rede.")

Examine a lista de tarefas recomendadas a seguir para manter a qualidade. Você deve executar essas tarefas regularmente-por exemplo, semanalmente.

#### <a name="service-management-tasks"></a>Tarefas de gerenciamento de serviço

Essas tarefas variam desde a garantia de que há largura de banda suficiente para acessar o serviço sem saturating links de Internet, Validando que a QoS (qualidade de serviço) está em vigor em todas as áreas de rede gerenciadas e permanecendo na parte superior dos [intervalos de IP do Office 365 em firewalls](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Tarefas de rede

Há duas categorias de tarefas de rede: confiabilidade e qualidade. A confiabilidade se concentra em avaliar a capacidade do usuário de fazer chamadas com êxito e manter-se conectado. A qualidade se concentra na telemetria agregada enviada ao Teams e ao Skype for Business online pelo cliente do usuário durante a chamada e depois que ele termina. 

Devido ao impacto crítico que a confiabilidade tem na experiência do usuário, recomendamos que você avalie e investigue métricas de confiabilidade antes de se aprofundar na qualidade. 

#### <a name="endpoints-tasks"></a>Tarefas de pontos de extremidade

A principal tarefa nessa categoria, removendo os obstáculos para [as atualizações regulares do cliente do teams](teams-client-update.md). Por padrão, o Microsoft Teams atualiza-se regularmente (a menos que você desative essa configuração, o que não recomendamos). 

Você também deve monitorar os dispositivos e fornecer atualizações sempre que identificar problemas relacionados a um dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usar o CQD para gerenciar a qualidade das chamadas

Depois de [Configurar o CQD](turning-on-and-using-call-quality-dashboard.md), você estará pronto para começar a usá-lo para gerenciar a qualidade da chamada e da reunião para a sua organização.

A maioria dos problemas com o desempenho do teams se encaixa nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy
-   Cobertura insatisfatória da rede Wi-Fi
-   Largura de banda insuficiente
-   VPN
-   Versões e drivers inconsistentes ou desatualizados do cliente
-   Dispositivos de áudio não otimizados ou internos
-   Dispositivos de rede ou sub-redes com problemas

Se você levar o tempo antes de distribuir as equipes para avaliar essas áreas e remediar as deficiências, reduza a quantidade de esforço necessária para manter uma experiência de equipe de alta qualidade para todos os usuários. Para obter ajuda para avaliar sua rede em preparação para a distribuição do seu Teams, leia o [Advisor for Teams](use-advisor-teams-roll-out.md) e [Prepare sua rede para o Microsoft Teams](prepare-network.md).

### <a name="expectations-using-cqd"></a>Expectativas usando o CQD

Use o painel de qualidade de chamada (CQD) para obter informações sobre a qualidade das chamadas feitas usando o Microsoft Teams e os serviços do Skype for Business. O CQD foi projetado para ajudar o Microsoft Teams e os administradores de rede e administradores do Skype for Business a otimizar a rede e ter um olho próximo da qualidade, da confiabilidade e da experiência do usuário. CQD examina a telemetria de agregação para uma organização inteira, em que os padrões gerais podem ficar aparentes; Isso permite que você faça avaliações bem fundamentadas e correção de plano. O CQD fornece relatórios de métricas que proporcionam uma visão geral da qualidade, da confiabilidade e da experiência do usuário.

CQD, embora útil para analisar tendências e sub-redes, nem sempre fornece uma causa específica para um determinado cenário. É importante entender isso e definir a expectativa correta ao usar o CQD:

-   O CQD não fornecerá a causa básica para todos os cenários
-   O CQD não conterá fluxos de sistema telefônico ou de conferência de áudio
-   O CQD chamará as áreas para uma investigação mais profunda com base nas tendências

### <a name="cqd-reports-overview"></a>Visão geral dos relatórios do CQD

Use o menu suspenso na parte superior da tela para abrir um relatório. Para obter uma lista dos dados fornecidos em cada relatório, leia os [dados disponíveis nos relatórios do CQD](CQD-data-and-reports.md#data-available-in-cqd-reports).

Novidades em janeiro de 2020: [Baixe os modelos de consulta do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.


### <a name="teams-vs-skype-for-business"></a>Teams versus Skype for Business

CQD pode relatar tanto o Skype for Business Teams quanto o Skype for Business. No entanto, pode haver ocasiões em que você queira desenvolver um relatório para ver a telemetria de equipes separada do Skype for Business.

#### <a name="summary-reports"></a>Relatórios de resumo

Para modificar a página relatórios resumidos para ver apenas as equipes ou o Skype for Business, selecione o menu suspenso de **filtro do produto** na parte superior da tela e selecione o produto desejado.

![Captura de tela do menu suspenso mostrando as opções de filtro](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Relatórios detalhados

Para filtrar todos os relatórios detalhados, na barra do navegador, acrescente o seguinte ao final da URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Exemplo**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obter mais informações sobre filtros de URL, leia [relatórios de filtragem](CQD-data-and-reports.md#report-filters) posteriormente nesta seção.

Para filtrar um relatório detalhado individual, adicione o filtro ``Is Teams`` ao relatório e defina-o como verdadeiro ou falso.

![Captura de tela da página Adicionar filtro](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Redes gerenciadas versus não gerenciadas

Por padrão, todos os pontos de extremidade no CQD são classificados como externos. Assim que um arquivo de criação é introduzido, podemos começar a examinar dados de ponto de extremidade gerenciados. Conforme discutido anteriormente, as redes no CQD são definidas como:

-   Uma _rede gerenciada_, geralmente conhecida como interna ou interna, pode ser influenciada e controlada pela organização. Isso inclui a LAN interna, a WAN remota e a VPN.
-   Uma _rede não gerenciada_, muitas vezes conhecida como externa ou externa, não pode ser influenciada ou controlada pela organização. Um exemplo de uma rede não gerenciada é uma rede de Hotel ou aeroporto.

### <a name="dimensions-measures-and-filters"></a>Dimensões, medidas e filtros

Uma consulta CQD bem formada contém todos os três parâmetros a seguir:

-   **Dimensão:** Como eu quero dinamizar os dados.

-   **Medida:** O que eu quero reportar.

-   **Filtro:** Como quero reduzir o DataSet que a consulta retorna.

Outra maneira de ver isso é que uma _dimensão_ é a função de agrupamento, uma _medida_ é a data em que estou interessado e um _filtro_ é como quero restringir os resultados àqueles que sejam relevantes para a minha consulta.

Um exemplo de uma consulta bem formada é **mostre-me fluxos de baixa qualidade [Measure] por subnet [Dimension] para prédio 6 [filtro]**. Para obter mais informações, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Primeiro x x segundo 

Muitas das dimensões e medidas no CQD são classificadas como primeiro ou segundo. O CQD não usa os campos Caller/Callee — eles foram renomeados _primeiro_ e _segundo_ porque há etapas intervenientes entre o chamador e o receptor. A lógica a seguir determina qual ponto de extremidade envolvido é rotulado como primeiro:

-   O **primeiro** será sempre um ponto de extremidade do servidor (servidor de conferência, servidor de mediação e assim por diante) se um servidor estiver envolvido no fluxo ou na chamada.

-   **Segundo** será sempre um ponto de extremidade do cliente, a menos que o fluxo esteja entre dois pontos de extremidade do servidor.

-   Se os dois pontos de extremidade forem do mesmo tipo, a escolha do que é primeiro é baseada na ordenação interna da categoria do agente do usuário. Isso garante que a solicitação seja consistente.

Para obter mais informações sobre como determinar o primeiro ou o segundo ponto de extremidade quando eles forem iguais, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Fluxo versus ligar

Você precisa compreender a diferença entre uma chamada e um fluxo para escolher adequadamente quais dimensões ou medidas você irá examinar no CQD. Embora o foco principal do CQD esteja em fluxos, as medições baseadas em chamadas também estão disponíveis.

-   **Stream:** Existe um _fluxo_ entre apenas dois pontos de extremidade. Há apenas um fluxo para cada direção e dois fluxos são necessários para a comunicação. Fluxos são úteis para a investigação de edifícios, redes ou sub-redes. Em alguns casos, tanto a chamada quanto o fluxo são usados no nome da medida (por exemplo, fluxo de configuração de chamada ou fluxo de chamada descartada). Eles ainda são classificados como fluxos.

-   **Ligue para:** Uma _chamada_ é um agrupamento de todos os fluxos de todos os participantes. Uma chamada consiste de, pelo menos, dois fluxos. Uma única chamada terá pelo menos dois pontos de extremidade, cada um com um mínimo de um fluxo.

Para obter diretrizes adicionais sobre se a dimensão ou medida está fazendo referência a uma chamada ou a um fluxo, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Chamadas boas, ruins e não classificadas

Uma chamada é categorizada como boa, ruim ou não classificada. Vamos dar um momento para falar sobre cada um deles mais detalhadamente.

-   **Bom ou ruim:** Uma chamada boa ou ruim consiste em uma chamada que contém um conjunto completo de métricas de serviço, para o qual um relatório de QoE completo foi gerado e recebido pelo serviço. Determinar se um fluxo é bom ou ruim é descrito [anteriormente neste artigo](#poor-stream-rate).

-   Não **classificado:** Um fluxo não classificado não contém um conjunto completo de métricas de serviço. Elas podem ser chamadas curtas, geralmente menores do que 60 segundos, em que as médias não poderiam ser calculadas e um relatório de QoE não foi gerado. O motivo mais comum para que as chamadas sejam não classificadas é que não havia pouca utilização de pacote. Um exemplo disso seria um participante que ingressou em uma reunião em mudo e nunca falar. O participante está recebendo, mas não transmitindo, mídia. Sem a transmissão de mídia, não haverá métricas disponíveis para o CQD usar para classificar o fluxo de mídia de saída do ponto de extremidade.

Para saber mais, leia [classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Sub-redes comuns

As sub-redes comuns são sub-redes privadas específicas usadas por Hotéis, redes domésticas, pontos de acesso e áreas semelhantes. Essas sub-redes são difíceis de fazer a triagem devido ao uso generalizado. Se a sua organização usa uma dessas sub-redes comuns, recomendamos que você mova essa rede para outra sub-rede. Isso fará com que o relatório seja mais fácil no CQD. Quando observados, os relatórios no modelo todas as redes foram configurados para excluir essas sub-redes para eliminá-las como uma fonte de baixa qualidade. Sub-redes comuns são definidas abaixo; o impacto varia de acordo com a organização.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Ao investigar uma rede gerenciada que usa uma sub-rede comum, você precisará usar a segunda dimensão de IP local reflexivo para agrupar sub-redes. Essa dimensão contém o endereço IP público do ponto de extremidade.


## <a name="reliability-investigations"></a>Investigações de confiabilidade

A primeira etapa para melhorar a qualidade é avaliar o estado da confiabilidade em toda a organização. Como a confiabilidade é vital para uma experiência positiva do usuário, começamos com os dois componentes que avaliam a confiabilidade:

1.  **Falhas de configuração:** Não foi possível estabelecer a chamada.

2.  **Falhas de soltura:** A chamada foi estabelecida e terminada inesperadamente.

Nesta seção, abordaremos métodos para investigar ambas as áreas.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo. No entanto, os métodos de investigação explicados abaixo ainda se aplicam. Confira a descrição do relatório individual para obter mais informações.


### <a name="setup-failures"></a>Falhas de configuração

Priorize a correção de falhas de configuração nesta área primeiro, pois essas falhas têm um impacto negativo significativo na experiência do usuário.

Comece a investigar avaliando a porcentagem de falhas gerais de configuração para a organização e, em seguida, Priorize as áreas de investigação com base na porcentagem mais alta ao criar ou à rede. 

#### <a name="setup-failure-trend-analysis"></a>Análise de tendência de falha de configuração

Este relatório exibe a quantidade total de fluxos, falhas de configuração do fluxo e a taxa de falha na configuração do fluxo. Aponte para qualquer uma das colunas para exibir seus valores individuais. 

##### <a name="analysis"></a>Análise

Ao usar este relatório, você pode responder às seguintes perguntas e determinar o próximo curso de ação:

-   Qual é a porcentagem de falha de configuração de chamada total para o mês atual?

-   A porcentagem de falha de configuração de chamada foi completada abaixo ou acima da métrica de destino definida?

-   A tendência de falha é pior ou melhor do que o mês anterior?

-   A tendência de falha está aumentando, estável ou decrescente?

Independentemente de suas respostas a essas perguntas, tome o tempo de investigação mais tarde usando os sub-relatórios complementares para procurar por prédios ou sub-redes individuais que possam precisar de correção. Embora a taxa de falha geral possa estar abaixo da métrica de destino, as tarifas de falha para um ou mais prédios ou redes podem estar acima da métrica de destino e precisam de investigação.

#### <a name="setup-failure-investigations"></a>Investigações de falha na configuração 

Este relatório de resumo é usado para descobrir e isolar quaisquer prédios ou redes que possam precisar de correção.

> [!NOTE]
> Certifique-se de ajustar o filtro de relatório de ano do mês para o mês atual. Selecione **Editar**e ajuste o filtro relatório de **ano do mês** para salvar o novo mês padrão.

##### <a name="remediation"></a>NAP 

Concentre seus primeiros esforços de correção em prédios ou sub-redes com o maior volume de falhas. Isso irá maximizar o impacto na experiência do usuário e ajudará a reduzir rapidamente a taxa de falhas de configuração da chamada organizacional. A tabela a seguir lista os dois motivos para falhas de configuração, conforme relatado pela CQD.

| Motivo da falha na configuração da chamada       | Causa típica                    |
|----------------------------------|----------------------------------|
| Regra de isenção de inspeção de pacotes profunda do FW ausente | Indica que o equipamento de rede ao longo do caminho impedia o caminho de mídia de ser estabelecido devido a regras de inspeção de pacotes profundas. Isso provavelmente aconteceu porque as regras de firewall não estão sendo configuradas corretamente. Nesse cenário, o handshake TCP foi concluído com êxito, mas o handshake SSL não.      |
| Regra de exceção de bloqueio de IP do FW ausente      | Indica que o equipamento de rede ao longo do caminho impedia o caminho de mídia de ser estabelecido para a rede do Microsoft 365 ou do Office 365. Isso pode ser devido a regras de proxy ou de firewall não estarem configuradas corretamente para permitir o acesso a endereços IP e portas usados para o Microsoft Teams e o tráfego do Skype for Business. |

À medida que você começa a remediação, pode concentrar seus esforços em um determinado prédio ou sub-rede. Como mostra a tabela anterior, esses problemas são devido a configurações de firewall ou proxy. Examine as opções na tabela a seguir para ações de correção.

|      NAP      |Orientação  |
|-----------------------|----------|
| Configurar firewalls | Trabalhe com sua equipe de rede e verifique a configuração de firewalls [na lista de endereços IP do Office 365](https://aka.ms/o365ips).<br><br>Verifique se as [sub-redes](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) e as portas de mídia estão incluídas nas regras de firewall. <br><br>Verifique se as [portas necessárias](prepare-network.md) estão abertas no firewall. O UDP deve ter prioridade porque o TCP é considerado um protocolo de failback para compartilhamento de tela de áudio, vídeo e com base em vídeo, e seu uso afetará a qualidade da chamada. O compartilhamento de aplicativos RDP herdado usa apenas TCP.|

### <a name="drop-failures"></a>Falhas de soltura

Ao contrário dos códigos de falha de configuração, o CQD não tem código de falha de soltura para indicar por que as falhas de soltura ocorrem, o que torna difícil isolar uma causa raiz específica. Para melhorar as falhas de descartar a triagem, use uma abordagem inferida. Ao corrigir qualquer área de interesse para mídia, corrigir clientes e drivers e conduzir o uso de dispositivos certificados para o Teams e o Skype for Business, você pode esperar falhas de soltura para recusar.

#### <a name="drop-failure-trend-analysis"></a>Ignorar análise de tendências de falha

Este relatório exibe a quantidade total de fluxos de áudio, as falhas de descarte total e a taxa de falha de soltura. Aponte para qualquer uma das colunas para exibir seus valores. 


##### <a name="analysis"></a>Análise

Ao usar esse tipo de relatório, você pode responder às seguintes perguntas:

-   Qual é a taxa de falha de soltura atual?
-   A taxa de falha suspensa está abaixo da métrica de destino definida?
-   A tendência de falha é pior ou melhor do que o mês anterior?
-   A tendência de falha está aumentando, estável ou decrescente?

Independentemente das respostas às perguntas acima, tome o tempo para investigar usando os sub-relatórios para procurar por prédios ou redes que possam precisar de correção. Embora a taxa de falha de soltura geral possa estar abaixo da métrica de destino, a taxa de falha de soltura para um ou mais prédios ou redes pode estar acima da métrica de destino e precisa de investigação.

#### <a name="drop-failure-investigations"></a>Eliminar investigações de falha

Falhas relatadas aqui indicam que a chamada foi cancelada inesperadamente e resultou em uma experiência de usuário negativa. Ao contrário dos relatórios de tendências, esses relatórios fornecem ideias adicionais em sub-redes específicas que exigem investigação adicional.


##### <a name="remediation"></a>NAP

Usando os relatórios de tabela incluídos, você pode isolar áreas problemáticas na rede em que a taxa de descarte está acima da métrica de destino que você definiu. Concentre seus primeiros esforços de correção em prédios ou sub-redes que tenham o maior número total de fluxo, para causar o maior impacto.

Causas comuns de cancelamentos de chamadas:

-   Saída de rede subprovisionada ou de Internet
-   Nenhuma QoS configurada em redes restritas
-   Versões mais antigas do cliente
-   Comportamento do usuário

Depois de descobrir suas áreas problemáticas, você pode usar a [análise de chamadas por usuário](use-call-analytics-to-troubleshoot-poor-call-quality.md) para analisar ainda mais os usuários que estão criando problemas específicos. A análise de chamadas contém dados adicionais do EUII e pode ser útil para isolar ainda mais possíveis motivos para as falhas de soltura.

Independentemente da sua próxima etapa, é uma prática recomendada notificar a assistência técnica de que um problema foi descoberto com prédios ou sub-redes específicos. Isso permite que a assistência técnica responda rapidamente às chamadas de entrada e aos usuários de triagem de forma mais eficiente. Os usuários sinalizados podem ser relatados para a equipe de engenharia para que você possa fazer uma investigação adicional.

A tabela a seguir lista alguns métodos comuns para gerenciar e corrigir falhas de soltura.

| NAP                              | Orientação                      |
|------------------------------------------|-------------------------------|
| **Rede/Internet**                         | **Congestionamento**: trabalhe com sua equipe de rede para monitorar a largura de banda em prédios/sub-redes específicos para confirmar se há problemas com a superutilização. Se você confirmar que há um congestionamento de rede, considere aumentar a largura de banda para criar ou aplicar QoS. Use os [relatórios de Resumo de fluxo ruim de qualidade](#quality-investigations) incluídos para analisar as sub-redes problemáticas para problemas com tremulação, latência e perda de pacote, pois elas muitas vezes precederão um fluxo solto.<br><br>**QoS**: se o aumento da largura de banda for impraticável ou de custo inviável, considere implementar QoS. Essa ferramenta é muito eficiente no gerenciamento de tráfego congestionado e pode garantir que pacotes de mídia na rede gerenciada sejam priorizados acima do tráfego não relacionado à mídia. Ou, se não houver evidências evidentes de que a largura de banda seja a culpa, considere estas soluções:<ul><li>[Orientação QoS do Microsoft Teams](qos-in-teams.md)</li></ul><br>**Realize uma avaliação de preparação de rede**: uma avaliação de rede fornece detalhes sobre o uso de largura de banda esperado, como lidar com alterações de largura de banda e rede e práticas de rede recomendadas para o Teams e o Skype for Business. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são excelentes candidatos para uma avaliação.<ul><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li></ul> |
| **Clientes (somente Skype for Business online)** | Alguns clientes Skype for Business mais antigos têm problemas conhecidos e documentados com a confiabilidade de mídia. Revise os relatórios de análise de chamadas de vários usuários afetados ou crie um relatório de tabela de versão de cliente personalizada no CQD filtrado para prédios ou sub-redes específicos com a medida total de falha de chamada eliminada%. Essas informações ajudarão você a entender se uma relação existe entre quedas de chamadas nesse edifício específico e uma versão específica do cliente.     |
| **Dispositivos**                                  |Se os dispositivos são o culpado em problemas de qualidade de chamada, considere a atualização de dispositivos problemáticos. Leia [telefones para o Teams](phones-for-teams.md) para saber mais. |
| **Comportamento do usuário**                            | Se você determinar que a rede, dispositivos ou clientes são o problema, considere o desenvolvimento de uma estratégia de adoção do usuário para ensinar aos usuários como ingressar e sair da melhor reunião. Uma equipe mais inteligente e o usuário do Skype for Business produzirão uma experiência de usuário melhor para todos os participantes da reunião. Por exemplo, um usuário que coloca o laptop em suspensão (fechando a tampa) sem sair da reunião será classificado como uma queda de chamada inesperada.   |

## <a name="quality-investigations"></a>Investigações de qualidade

A próxima etapa para avaliar o estado de qualidade de áudio em toda a organização é investigar a taxa de fluxo de pico (PSR), TCP e uso de proxy. É importante lembrar que os dados do CQD não fornecem uma causa raiz específica, mas, em vez disso, fornecem a você as áreas de problemas prováveis para iniciar uma conversa colaborativa com as equipes adequadas para atividades de correção. 

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo; no entanto, os métodos de investigação explicados abaixo ainda serão aplicados a esses relatórios. Consulte a descrição do relatório individual para obter mais informações. 

### <a name="quality"></a>Qualidade

As porcentagens PSR são usadas para indicar se a organização está na reunião alvos de métrica definidos para uma determinada área de foco. É importante observar que, mesmo se as porcentagens de alto nível estiverem dentro do destino definido, as sub-redes ou edifícios individuais podem não atender aos alvos definidos e, portanto, precisam de investigação adicional. Por exemplo, se a porcentagem geral de PSR de áudio for 2% em abril, o que atende à amostra de destino, os prédios e as sub-redes individuais ainda podem estar com experiências ruins, dependendo da distribuição geral de 2%. 

Para avaliar a porcentagem de fluxos deficientes, use os relatórios de qualidade. Vários relatórios de qualidade são fornecidos para examinar as métricas gerais, conferências, chamadas de duas partes, chamadas PSTN, VPN e salas de reunião. Relatórios mensais, semanais e diários são fornecidos para ajudar nesse processo. Relatórios semanais e diários limitam-se ao modelo de redes gerenciadas para aumentar a eficácia e reduzir o ruído. 

#### <a name="quality-trend-analysis"></a>Análise de tendências de qualidade

Os relatórios de tendências exibem informações de qualidade ao longo do tempo e são usadas para ajudar a identificar e compreender as tendências de qualidade dentro de cada área de interesse. Conforme observado acima, há árvores de relatório incluídas nos modelos de qualidade de investigação; Conferência, duas pessoas, chamadas PSTN, VPN e salas de reunião. Para a finalidade de analisar a qualidade, o processo investigativo é o mesmo. No entanto, recomendamos que você comece com a conferência primeiro, pois as melhorias na qualidade da conferência também afetarão positivamente todas as outras áreas. 

> [!Note]
> A investigação de chamadas de duas partes, PSTN e salas de reunião é semelhante à investigação de conferências. O foco é isolar prédios ou sub-redes com a pior qualidade e identificar o motivo da qualidade ruim.

> [!Important]
> Relatórios baseados em VPN são filtrados usando a segunda dimensão de VPN. Essa dimensão requer que o adaptador de rede VPN seja devidamente registrado como um adaptador de acesso remoto. Os fornecedores de VPN não usam esse sinalizador com confiabilidade, e a quilometragem varia de acordo com o fornecedor de VPN implantado em sua organização. Modifique os relatórios [VPN](CQD-upload-tenant-building-data.md#vpn) , se necessário, usando o nome de edifício ou de rede.

##### <a name="investigation"></a>Permanente

Ao usar esses relatórios, você pode responder às seguintes perguntas:

-   Qual é o total de PSR para o mês atual?
-   O PSR está abaixo da métrica de destino definida?
-   O PSR é pior ou melhor do que o mês anterior?
-   A tendência PSR está crescente, estável ou decrescente?

Independentemente das respostas às perguntas acima, tome o tempo de investigação usando os sub-relatórios para procurar por prédios ou sub-redes que possam precisar de investigação. Embora o PSR geral possa estar abaixo da métrica de destino, muitas vezes, o PSR para um ou mais prédios ou redes está acima da métrica e precisa de correção.

#### <a name="quality-investigations"></a>Investigações de qualidade

Os relatórios de Resumo de qualidade dão uma percepção mais profunda sobre o que contribuiu para os fluxos que estão sendo classificados como deficientes e ajuda a isolar as áreas de problemas na rede gerenciada.

Embora as dimensões usadas possam variar ligeiramente entre os relatórios, cada relatório inclui medidas para total de fluxos, total de fluxos de mau valor, PSR e baixa qualidade devido a. Os relatórios foram criados para cada área de interesse: conferência, duas pessoas, chamadas PSTN, VPN e salas de reunião. O modelo de rede gerenciada inclui relatórios adicionais para aproveitar as informações de localização carregadas por meio do arquivo de construção.


> [!Note]
> Sub-redes comuns são difíceis de fazer a triagem devido ao uso difundido. Um relatório separado que exibe o IP público do cliente (segundo IP local reflexivo) foi adicionado ao modelo todas as redes para auxiliar na correção de escritórios que usam redes comuns.


![Captura de tela mostrando o resumo do fluxo de áudio ruim](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>NAP

Concentre seus esforços de correção em prédios ou sub-redes que tenham o maior volume de fluxos, pois isso irá melhorar o impacto e ajudar a melhorar a experiência do usuário rapidamente. Use as medidas de tremulação, perda de pacote e RTT (tempo de ida e volta) para entender o que está contribuindo para a qualidade ruim (é possível que haja mais de um problema):

-   **Tremulação**: pacotes de mídia estão chegando em diferentes velocidades, o que faz com que um alto-falante Sound robótico.
-   **Perda de pacote**: pacotes de mídia estão sendo ignorados, o que cria o efeito de palavras ausentes ou sílabas.
-   **RTT**: pacotes de mídia estão demorando muito para chegar ao destino dele, o que cria um efeito de faça de fala.

Para ajudar sua investigação a problemas de qualidade, use [a análise de chamadas por usuário](use-call-analytics-to-troubleshoot-poor-call-quality.md). Com o recurso de análise de chamadas, você pode examinar uma conferência específica ou um relatório de chamadas de um usuário. Esse relatório conterá dados EUII/PII e será útil quando você estiver procurando por causa de uma falha. Depois que você sabe qual é a criação, deve ser fácil rastrear os usuários nesse prédio. 

Não se esqueça de permitir que a sua assistência técnica saiba que essas redes estão com problemas de qualidade, para que elas possam fazer a triagem e responder rapidamente às chamadas recebidas.

| NAP                              | Orientação                         |
|------------------------------------------|----------------------------------|
| **Network**                                 | **Congestionamento**: uma rede superutilizada ou subprovisionada pode causar problemas com a qualidade da mídia. Trabalhe com a equipe de rede para determinar se as conexões de rede do ponto de saída do usuário para a Internet têm largura de banda suficiente para dar suporte à mídia. <br><br>**Realize uma avaliação de preparação de rede**: uma avaliação de rede fornece detalhes sobre o uso de largura de banda esperado, como lidar com alterações de largura de banda e rede e práticas de rede recomendadas para o Teams e o Skype for Business. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são excelentes candidatos para uma avaliação.<ul><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li></ul>|
| **Qualidade de serviço (QoS)**  | QoS é uma ferramenta comprovada para ajudar a priorizar pacotes em uma rede congestionada para garantir que eles cheguem ao seu destino intactos e no prazo. Considere implementar a QoS em sua organização para maximizar a qualidade da experiência do usuário em que a largura de banda é restrita. A QoS ajudará a solucionar problemas geralmente associados a altos níveis de perda de pacotes, e — a um menor grau de tempo de tremulação e ida e voltagem.<ul><li>[Diretrizes QoS de equipes](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | O Wi-Fi pode ter um impacto significativo na qualidade da chamada. Implantações de Wi-Fi geralmente não levam em consideração os requisitos de rede para serviços de VoIP e são muitas vezes uma fonte de baixa qualidade. Para obter mais informações sobre como otimizar sua infraestrutura Wi-Fi, consulte [Este artigo sobre o planejamento de Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Driver sem fio**: Certifique-se de que os drivers sem fio estejam atualizados. Isso ajudará a reduzir qualquer mau uso do usuário relacionado a um driver desatualizado. Muitas organizações não incluem drivers sem fio nos ciclos de patch, e esses drivers podem não ser corrigidos há anos. Muitos problemas sem fio são resolvidos garantindo que os drivers sem fio estejam atualizados.<br><br>**WMM**: o WMM (ramais de multimídia sem fio), também conhecido como multimídia Wi-Fi, oferece recursos básicos de QoS para redes sem fio. Redes sem fio modernas devem oferecer suporte a muitos dispositivos. Esses dispositivos conpetem largura de banda e podem levar a problemas de qualidade para serviços de VoIP, em que a velocidade e a latência são essenciais. Consulte o fornecedor sem fio para obter especificações e considere a implementação do WMM na sua rede sem fio para priorizar a mídia do Skype for Business e do teams.<br><br>**Densidade do ponto de acesso**: os pontos de acesso podem ser muito distantes ou não em um local ideal. Para minimizar a interferência potencial, coloque pontos de acesso extras em salas de conferência e em locais que não estão obstruídos por paredes ou outros objetos nos quais o sinal de Wi-Fi está fraco.<br><br>**2,4 GHz versus 5 GHz**: 5 GHz fornecem menos interferência em segundo plano e velocidades superiores e devem ser priorizadas ao implantar VoIP via Wi-Fi. No entanto, 5 GHz não é tão forte quanto 2,4 GHz e não penetra nas paredes com a mesma facilidade. Revise o layout da construção para determinar em qual frequência você pode confiar para obter a melhor conexão. |
|**Dispositivo de rede** | Organizações maiores podem ter centenas de dispositivos espalhados pela rede. Trabalhe com sua equipe de rede para garantir que os dispositivos de rede do usuário para a Internet sejam mantidos e atualizados. |
| **VPN**  | Os aparelhos VPN não foram projetados tradicionalmente para lidar com cargas de trabalho de mídia em tempo real. Algumas configurações de VPN proíbem o uso do UDP (que é o protocolo preferencial para mídia) e depende somente do TCP. Considere a implementação de uma solução de tunelamento de VPN para ajudar a reduzir a VPN como uma fonte de baixa qualidade. |
| **Clientes** <br>(Somente Skype for Business online) | Verifique se todos os clientes estão sendo atualizados regularmente. |
| **Dispositivos** | Se os dispositivos são o culpado em problemas de qualidade de chamada, considere a atualização de dispositivos problemáticos. Leia [telefones para o Teams](phones-for-teams.md) para saber mais. |
| **Drivers** | O patch de rede (Ethernet e Wi-Fi), áudio, vídeo e drivers USB devem fazer parte de sua estratégia geral de gerenciamento de patches. Muitos problemas de qualidade são resolvidos com a atualização de drivers. |
| **Salas de reunião em Wi-Fi** | É altamente recomendável que os dispositivos da sala de reunião sejam conectados à rede usando pelo menos uma conexão Ethernet de 1 Gbps. Em geral, os dispositivos da sala de reunião incluem vários fluxos de áudio e vídeo, além de conteúdo da reunião, como compartilhamento de tela, e têm requisitos de rede mais altos do que outras equipes ou pontos de extremidade do Skype for Business. As salas de reunião são, por definição, dispositivos fixos nos quais Wi-Fi proporciona um benefício apenas durante a instalação.<br><br>As salas de reunião precisam ser tratadas com cuidado adicional e atenção para garantir que a experiência que usa esses dispositivos seja atender ou ultrapassar as expectativas. Problemas de qualidade com as salas de reunião geralmente vão ser escalonados rapidamente, porque geralmente são usados pela equipe de nível sênior.<br><br>Todas as coisas são iguais (além da comodidade), o desempenho do Wi-Fi geralmente é menor que uma conexão com fio. Com o aumento das políticas "Traga seu próprio dispositivo" e a proliferação de laptops, os pontos de acesso Wi-Fi são geralmente superutilizados. A mídia em tempo real pode não ser priorizada em redes Wi-Fi, o que pode levar a problemas de qualidade durante o tempo de pico de uso. Esse uso pesado pode coincidir com uma reunião em que pode haver dúzias de pessoas na participação, cada uma com seu próprio laptop e Smartphone, todas conectadas ao mesmo ponto de acesso Wi-Fi que o dispositivo da sala de reunião.<br><br>O Wi-Fi só deve ser considerado como uma solução temporária, para uma instalação móvel ou quando o Wi-Fi foi provisionado corretamente para dar suporte a mídias de classe empresarial em tempo real. |


### <a name="tcp"></a>TCP 

O protocolo TCP (Transmission Control Protocol) é considerado um transporte de failback e não o transporte primário que você deseja para mídia em tempo real. O motivo é um transporte de failback devido à natureza de estado do TCP. Por exemplo, se uma chamada for feita em uma rede de acordo com pacotes de mídia e de mídia, os pacotes de alguns segundos atrás, que não são mais úteis, conpetem pela largura de banda para chegar ao receptor, o que pode piorar uma situação ruim. Isso faz com que o reparo de áudio seja grampeado e alongue o áudio, resultando em artefatos audíveis, muitas vezes na forma de tremulação.

Os relatórios desta seção não fazem distinção entre fluxos satisfatórios e satisfatórios. Considerando que o UDP é preferencial, os relatórios procuram o uso do TCP para compartilhamento de tela com base em áudio, vídeo e vídeo (VBSS). As tarifas de fluxo deficiente são fornecidas para ajudar a comparar a qualidade UDP versus TCP, para que você possa concentrar seus esforços em que o impacto é o mais alto. O uso do TCP é causado principalmente por regras incompletas do firewall. Para obter mais informações sobre as regras de firewall do Teams e do Skype for Business Online, consulte [URLs e intervalos de endereços IP do Microsoft 365 e do Office 365](https://aka.ms/o365ips).

> [!Note]
> O áudio, o vídeo e o VBSS são todos os preferenciais do UDP como transporte principal. A carga de trabalho de compartilhamento de aplicativos RDP usa apenas TCP.

#### <a name="tcp-usage"></a>Uso do TCP

Os relatórios TCP indicam o uso geral do TCP nos últimos sete meses. Todos os outros relatórios nesta seção se concentrarão na restrição de prédios e sub-redes específicos em que o TCP é mais comumente usado. Relatórios separados estão disponíveis para conferências e fluxos de duas empresas.

![Gráfico mostrando a porcentagem de fluxos de áudio que usam TCP](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Permanente

Ao usar este relatório, você pode responder às seguintes perguntas:

-   Qual é o volume total de fluxos TCP para o mês atual?
-   É pior ou melhor do que o mês anterior?
-   As tendências de uso do TCP são crescentes, contínuas ou decrescentes?
-   O TCP PSR é o mesmo que meu PSR geral?

Se você observar que a tendência de uso do TCP está aumentando ou acima do uso mensal normal, tome o tempo de investigação usando os sub-relatórios para procurar por quaisquer edifícios ou redes que possam precisar de correção. O ideal é que você queira o menor número possível de sessões de áudio baseado em TCP na rede gerenciada.

#### <a name="tcp-vs-udp"></a>TCP versus UDP

Este relatório identifica o volume de relatório de uso de TCP versus UDP no último mês para compartilhamento de tela com base em áudio, vídeo e vídeo (VBSS). 

![Relatório mostrando o volume de fluxos que usam TCP versus UDP](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Análise

Embora você queira que o uso do TCP seja o mais baixo possível, talvez veja um pouco de uso do TCP em uma implantação que não esteja íntegra. O TCP por si só não contribuirá com uma chamada ruim, portanto, as tarifas de fluxo são fornecidas para ajudar a identificar se o uso do TCP é um colaborador de baixa qualidade. 

#### <a name="tcp-investigations"></a>Investigações TCP

Nos modelos CQD fornecidos, navegue até os fluxos TCP por meio de relatórios de construção e sub-rede usando o modelo redes gerenciadas ou todas as redes. Para a finalidade da investigação do uso do TCP, o processo é o mesmo, então iremos nos concentrar na conferência aqui.


##### <a name="remediation"></a>NAP

Esse relatório identifica construções e sub-redes específicas que contribuem para o volume do uso do TCP. Um relatório adicional também está incluído para identificar o Microsoft Relay IP que foi usado na chamada para ajudar a isolar regras de firewall ausentes. Concentre seus esforços de correção nos prédios que têm o maior volume de fluxos de TCP para melhorar o impacto.

A causa mais comum de uso do TCP são regras de exceção ausentes em firewalls ou proxies. Vamos falar sobre proxies na próxima seção, por isso, por ora, se concentrar em seus esforços nos firewalls. Ao usar o prédio ou a sub-rede fornecida, você pode determinar qual firewall precisa ser atualizado.

| NAP        | Orientação     |
|--------------------|--------------------------------------|
| Configurar o firewall | Verifique se [as portas e os endereços IP do Microsoft 365 ou do Office 365](https://aka.ms/o365ips) estão excluídos do firewall. Para problemas de TCP relacionados à mídia, concentre seus esforços iniciais no seguinte:<ul><li>Verifique se as sub-redes de mídia do cliente 13.107.64.0/18 e 52.112.0.0/14 estão nas suas regras de firewall.</li><li>Portas UDP 3478 – 3481 são as portas de mídia necessárias e devem ser abertas, caso contrário, o cliente fará failback para a porta TCP 443.</li></ul> |
| Verificar             | Use a [ferramenta de avaliação de rede da Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar se há problemas com a conectividade de endereços IP e portas específicos do Microsoft 365 ou do Office 365 da compilação ou sub-rede afetada.    |

### <a name="http-proxy"></a>Proxy HTTP

Os proxies HTTP não são o caminho preferencial para estabelecer sessões de mídia, por uma infinidade de motivos. Muitos contêm recursos de inspeção de pacotes profundas que podem impedir que as conexões com o serviço sejam concluídas e apresentar interrupções. Além disso, praticamente todos os proxies forçam o TCP, em vez de permitirem UDP, o que é recomendado para a qualidade de áudio ideal.

Sempre recomendamos que você configure o cliente para se conectar diretamente ao Teams e aos serviços do Skype for Business. Isso é especialmente importante para tráfego baseado em mídia.


> [!IMPORTANT]
> Recomendamos que você carregue um [arquivo de construção válido](CQD-upload-tenant-building-data.md) para que possa distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

O relatório de fluxo de proxy HTTP nesta seção do modelo é muito parecido com os relatórios TCP. Não verifica se as chamadas são ruins ou boas, mas se a chamada está conectada via HTTP.

![Captura de tela do relatório de fluxos de áudio que usam HTTP](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Análise

Você deseja ver o máximo possível de fluxos de mídia HTTP. Se você tiver fluxos que atravessam seu proxy, consulte sua equipe de rede para garantir que as exclusões adequadas estejam em vigor para que os clientes sejam direcionados diretamente para as equipes ou para as sub-redes do Skype for Business online.

Se você tiver apenas um proxy da Internet em sua organização, verifique as [exclusões adequadas do Microsoft 365 ou do Office 365 para o intervalo de endereços IP](https://aka.ms/o365ips). Se mais de um proxy da Internet estiver configurado em sua organização, use o sub-relatório HTTP para isolar qual construção ou sub-rede será afetada.

Para organizações que não podem ignorar o proxy, certifique-se de que o cliente Skype for Business esteja configurado para se conectar corretamente quando ele estiver localizado atrás de um proxy, conforme descrito no artigo o [Skype for Business deve usar o servidor proxy para se conectar em vez de tentar uma conexão direta](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Investigações de proxy HTTP

Esse relatório identifica construções e sub-redes específicas que contribuem para o uso de HTTP.


##### <a name="remediation"></a>NAP

[Recomendamos](proxy-servers-for-skype-for-business-online.md) que você sempre ignore proxies do Skype for Business e do Teams, especialmente tráfego de mídia. Os proxies não tornam o Skype for Business mais seguro, pois o tráfego já está criptografado. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Problemas como esses podem resultar em uma experiência negativa com áudio, vídeo e compartilhamento de tela, onde os fluxos em tempo real são essenciais.

A causa mais comum de uso de HTTP são as regras de exceção ausentes nos proxies. Ao usar o edifício ou a sub-rede fornecida, você pode determinar rapidamente qual proxy precisa ser configurado para o bypass de mídia.

Verifique se os [FQDNs necessários Microsoft 365 ou Office 365](https://aka.ms/o365ips) são listadas em seu proxy.

## <a name="endpoint-investigations"></a>Investigações de ponto de extremidade

Esta seção concentra-se nas tarefas para relatar as versões do cliente e o uso de dispositivos certificados. Os relatórios estão disponíveis para a estrutura de tópicos do uso de versões do cliente, tipo de cliente, dispositivos de captura e drivers (microfone), dispositivos de captura de vídeo e versões de fornecedor e driver de Wi-Fi.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste artigo; no entanto, os métodos de investigação explicados abaixo ainda se aplicam. Consulte a descrição do relatório individual para obter mais informações.

### <a name="client-versions"></a>Versões do cliente

Esses relatórios enfatizam a identificação de versões de cliente do Skype for Business em uso e seu volume relativo no ambiente.

> [!IMPORTANT]
> Atualmente, os clientes do teams são distribuídos e atualizados automaticamente por meio da rede de distribuição de conteúdo do Azure e serão mantidos em dia pelo serviço. Como resultado, você não precisa monitorar as versões de cliente do Teams (a menos que desative a atualização automática, que não recomendamos).

A menos que você exclua dados do participante federado, esses relatórios incluirão a telemetria do cliente a partir de pontos de extremidade federados. Para excluir pontos de extremidade federados, você deve adicionar um filtro de consulta para a segunda ID de locatário definida como a [ID de locatário](CQD-data-and-reports.md#how-to-find-your-tenant-id)da sua organização. Você também pode usar um filtro de [URL](CQD-data-and-reports.md#url-filters) para excluir a telemetria de participantes agrupados.



#### <a name="remediation"></a>NAP

Uma parte crítica da condução de experiências de usuário de alta qualidade é garantir que os clientes gerenciados estejam executando versões atualizadas do Skype for Business, além de garantir que os drivers de áudio, vídeo, rede e USB em apoio estejam atualizados. Isso oferece vários benefícios, entre eles: 

-   É mais fácil gerenciar algumas versões em vez de muitas versões.
-   Ele fornece um nível de consistência da experiência.
-   Isso facilita a solução de problemas com a qualidade da chamada e a usabilidade.
-   A Microsoft faz continuamente melhorias e otimizações gerais em todo o produto. Garantir que os usuários recebam essas atualizações reduzem o risco de executar um problema que já foi resolvido.

Limitar sua implantação às versões do cliente com menos de seis meses de idade melhorará a experiência geral do usuário e melhorará a capacidade de gerenciamento reduzindo o número de versões que precisam ser compatíveis.

Se você estiver usando apenas o Office com Clique para executar, você estará automaticamente dentro da janela de seis meses. Nenhuma ação adicional é necessária.

Se você tiver uma combinação de pacotes de clique para executar e instalador (MSI), poderá usar o relatório para verificar se os clientes MSI estão sendo atualizados regularmente. Se você perceber que os clientes estão atrasados, trabalhe com a equipe responsável por gerenciar as atualizações do Office e garantir que elas estejam aprovando e implantando correções de cliente regularmente.

Também é importante considerar e garantir que os drivers de rede, vídeo, USB e áudio também estejam sendo corrigidos. Pode ser fácil ignorar esses drivers e não incluí-los na estratégia de gerenciamento de patches.

Os números de versão do Skype for Business podem ser encontrados por meio dos links abaixo:

-   [Informações de lançamento de atualizações para os aplicativos do Microsoft 365](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Histórico de atualizações para aplicativos do Microsoft 365 para empresas](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Downloads e atualizações do Skype for Business](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para usar o relatório de dispositivo de microfone, precisamos entender o conceito da pontuação média de opinião (MOS). MOS é a medida padrão dourada para medir a qualidade de áudio percebida. Ele é representado como uma classificação de número inteiro de 0 a 5.

A base de todas as medidas de qualidade de voz é como uma pessoa percebe a qualidade da fala. Como ele é afetado pela percepção humana, é inerentemente subjetivo. Há várias metodologias diferentes para testes subjetivos. A maioria das medidas de qualidade de voz baseia-se em uma escala de classificação de categorização (ACR) absoluta.

Em um teste de assunto de ACR, um número de pessoas com uma grande quantidade de pessoas classifica a qualidade da sua experiência em uma escala de 1 (ruim) a 5 (excelente). A média da pontuação é o MOS. O MOS resultante depende do intervalo de experiências que foram expostas ao grupo e do tipo de experiência que está sendo avaliado.

Como não é prático conduzir testes subjetivos de qualidade de voz para um sistema de comunicação em tempo real, o Microsoft Teams e o Skype for Business geram valores MOS usando algoritmos avançados para prever objetivamente os resultados de um teste subjetivo.

O conjunto disponível de MOS e métricas associadas proporciona uma visão da qualidade da experiência que está sendo entregue aos usuários por um dispositivo de áudio. 

Ao fornecer aos usuários dispositivos certificados para o Teams e o Skype for Business, você reduz a probabilidade de encontrar experiências negativas devido ao próprio dispositivo (que é mais provável, por exemplo, com alto-falantes de laptop integrados e microfones). Para obter mais informações, consulte estes artigos sobre o [programa de certificação](/SkypeForBusiness/certification/overview) e o catálogo de soluções de [parceiros](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Os relatórios de dispositivo são usados para avaliar o uso do dispositivo por volume e pontuação MOS (somente áudio) e podem ser encontrados nos modelos que acompanham os dispositivos & dispositivos. 

> [!IMPORTANT]
> A menos que você exclua dados do participante federado, esses relatórios incluirão a telemetria do cliente a partir de pontos de extremidade federados. Para excluir pontos de extremidade federados, você deve adicionar um filtro de consulta para a **segunda ID de locatário** definida como a [ID de locatário](CQD-data-and-reports.md#how-to-find-your-tenant-id)da sua organização. Você também pode usar um filtro de [URL](CQD-data-and-reports.md#url-filters) para excluir a telemetria de participantes agrupados.


> [!Note]
> Você pode observar quando exibir este relatório de que vê o mesmo dispositivo informado várias vezes. Isso se deve à maneira como o dispositivo é relatado como reportado para CQD. Diferenças na localidade do hardware e do sistema operacional causam diferenças na maneira como os dados do dispositivo são relatados.

##### <a name="remediation"></a>NAP

Normalmente, você precisará descobrir e fazer uma fase de descontinuação de dispositivos não certificados e substituí-los por dispositivos certificados. Algumas considerações ao analisar os relatórios do dispositivo incluem:

-   Os dispositivos em uso são certificados para o Teams e o Skype for Business? 
-   Você pode identificar usuários de um dispositivo específico usando a [análise de chamadas por usuário](use-call-analytics-to-troubleshoot-poor-call-quality.md). Verifique se eles têm os drivers de dispositivo mais recentes e se o dispositivo não está conectado por meio de um hub USB ou de uma docking station. 
-   Quantas versões diferentes de vários drivers estão em uso? Eles estão sendo corrigidos regularmente? Garantir que os drivers de áudio, vídeo e Wi-Fi sejam corrigidos regularmente ajudarão a eliminá-los como uma fonte de problemas de qualidade e tornar a experiência do usuário mais previsível e consistente.

##### <a name="audio"></a>Áudio

A próxima tarefa é determinar o uso geral dos [dispositivos de áudio certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Recomendamos que pelo menos 80% de todos os fluxos de áudio usem um dispositivo de áudio certificado. Isso é melhor realizado ao exportar o relatório de dispositivos de microfone para o Excel para calcular o uso de dispositivos certificados ou aprovados. Geralmente, as organizações mantêm uma lista de todos os dispositivos aprovados, portanto, a filtragem e a classificação dos dados devem ser diretas.

##### <a name="video"></a>Vídeo

Os drivers de vídeo são importantes também para manter a atualização. Verificar se as placas de vídeo estão sendo corrigidas regularmente ajudarão a excluir drivers de vídeo como uma fonte de baixa qualidade para fluxos de vídeo. O uso de [dispositivos de vídeo certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) ajudará a garantir uma experiência de usuário tranqüila e de alta qualidade. Os dispositivos de vídeo que dão suporte a codificação nativa H. 264 são preferenciais, para reduzir o uso da CPU durante videoconferência.

##### <a name="wi-fi"></a>Wi-Fi

Os drivers de Wi-Fi também precisam ser corrigidos em uma cadência regular e devem ser incluídos na estratégia de gerenciamento de patches. Muitos problemas de qualidade podem ser corrigidos mantendo drivers Wi-Fi atualizados. Para obter mais informações sobre como otimizar sua infraestrutura Wi-Fi, consulte [Este artigo sobre o planejamento de Wi-Fi](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Tópicos relacionados

[Usar o Advisor para Teams](use-advisor-teams-roll-out.md)

[Preparar sua rede para o Teams](prepare-network.md)

[Princípios de conectividade de rede do Office 365](https://aka.ms/pnc)

[Análises e relatórios do Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Gerenciar seus dispositivos no Teams](device-management.md)

[Melhorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o painel de qualidade da chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados do locatário e construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)
