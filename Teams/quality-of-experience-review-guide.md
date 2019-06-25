---
title: Qualidade da experiência do guia de avaliação do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guia para analisar o desempenho de mídia em tempo real do Microsoft Teams usando o painel de qualidade de chamada (CQD).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b29506a30f20056b422b7780896d5661326986e0
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198656"
---
# <a name="quality-of-experience-review-guide"></a>Guia de revisão da experiência de qualidade

<!-- Note that this link to the Word doc is intentionally NOT the aka.ms/qerquide link -->
Este guia se refere à fase valor do drive do Microsoft Teams e do Skype for Business online. Você pode [baixar uma versão do Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) deste guia.

## <a name="introduction"></a>Introdução

Para ter o maior impacto para melhorar a experiência do usuário, as organizações precisam fazer a operação de áreas importantes que são mostradas na figura a seguir. As áreas adicionais incluem a identificação de tarefas operacionais, o estabelecimento de destinos para métricas de qualidade, a tarefa de garantir que as métricas sejam usadas para medir o sucesso organizacional e a limitação de áreas de investigação conforme necessário.


![Áreas chave para a qualidade da experiência do usuário] (media/qerguide-image-keyareas.png "As áreas chave para a qualidade da experiência do usuário incluem áudio, confiabilidade, pesquisas de usuários, dispositivos e clientes.")

_Figura 1: principais áreas operacionais abordadas em todo este guia_

Ao avaliar continuamente e corrigir as áreas descritas neste guia, você pode reduzir o potencial de afetar negativamente a qualidade da experiência dos seus usuários. A maioria dos problemas de experiência do usuário encontrada em uma implantação pode ser agrupada nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy
-   Cobertura insatisfatória da rede Wi-Fi
-   Largura de banda insuficiente
-   VPN
-   Versões e drivers inconsistentes ou desatualizados do cliente
-   Dispositivos de áudio não otimizados ou internos
-   Dispositivos de rede ou sub-redes com problemas

Por meio de planejamento e design adequados antes de implantar o Skype for Business ou o Skype for Business Online, você pode reduzir a quantidade de esforço que será necessária para manter experiências de alta qualidade.

Este guia se concentra em usar o painel de qualidade de chamada (CQD) online como a principal ferramenta para denunciar e investigar cada área, com uma ênfase especial no áudio para melhorar a adoção e o impacto. Qualquer melhoria feita na rede para melhorar a experiência de áudio também será traduzida diretamente para melhorias no vídeo e no compartilhamento de área de trabalho.

Para acelerar a avaliação, [dois modelos do CQD](https://aka.ms/qertemplates) são fornecidos: um é para gerenciar todas as redes e a outra é filtrada somente para redes gerenciadas (internas). Embora os relatórios de modelo todas as redes sejam configurados para exibir informações de construção e de rede, eles ainda podem ser usados enquanto você trabalha para coletar e carregar informações de construção. Carregar as informações de construção no CQD permite que o serviço Aprimore os relatórios ao adicionar informações personalizadas de construção, rede e localização, ao diferenciar internas de sub-redes externas. Para obter mais informações, consulte [criando mapeamento](#building-mapping) mais adiante neste guia.

### <a name="intended-audience"></a>Público-alvo

Este guia se destina a ser usado por parceiros e interessados do cliente com funções como líder de colaboração/arquiteto, consultor, gerenciamento de alterações/especialista de adoção, líder de suporte/suporte técnico, líder de rede, líder de desktop e administrador de ti.

Este guia também deve ser usado pelo (s) especialista (s) de qualidade designado (s). Para obter mais informações, consulte [a função Champion de qualidade](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar este guia, verifique se você tem as [funções](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) de locatário adequadas atribuídas para poder acessar o CQD.

-   **Função de administrador global do Office 365** 

-   **Função de administrador do Skype for Business** 

-   **Função de administrador do teams Service** 

-   **Função do engenheiro de suporte de comunicações do teams** 

-   **Função de especialista de suporte às comunicações de equipe** 

Como alternativa, você pode atribuir a função a seguir a uma conta de usuário do Office 365 para permitir o acesso somente aos recursos de relatório.

-   **Leitor de relatórios:** Pode exibir todos os [relatórios de atividades](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no centro de administração do Office 365, todos os relatórios do [pacote de conteúdo de adoção do Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e relatórios do CQD.

## <a name="what-is-quality"></a>O que é qualidade?

Ao discutir qualidade no Teams e no Skype for Business, é importante definir o termo para obter uma compreensão comum. Qualidade, conforme definido aqui, é uma combinação de métricas de serviço e experiência do usuário.

<!-- Note: need to update graphic-->
![Ilustração de métricas de serviço e experiência do usuário] (media/qerguide-image-whatisquality.png "As métricas do serviço são formadas por baixa taxa de fluxo, confiabilidade, pontos de extremidade/dispositivos e versões de cliente. A experiência do usuário é composta pela percepção do usuário sobre a qualidade do serviço.")

_Figura 2: o que é a qualidade?_

### <a name="service-metrics"></a>Métricas do serviço

As métricas do serviço consistem em métricas específicas baseadas no cliente. Durante cada chamada, o cliente coleta informações de telemetria sobre a chamada e envia um relatório no final de cada chamada que pode ser acessada posteriormente por meio do CQD ou da [análise de chamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Essas métricas incluem:

-   Taxa de fluxo ruim
-   Taxa de falha de configuração
-   Taxa de falha de soltura


#### <a name="poor-stream-rate"></a>Taxa de fluxo ruim

A taxa de fluxo deficiente (PSR) representa a porcentagem geral de fluxos da organização que têm baixa qualidade. Essa métrica se destina a destacar áreas em que a sua organização pode concentrar esforços para ter o maior impacto em relação à redução desse valor e melhorar a experiência do usuário, que é por isso que as [redes gerenciadas](#managed-vs-unmanaged-networks) são o foco principal ao olhar para o PSR. Os usuários externos também são importantes, mas a investigação é diferente de acordo com a organização. Considere fornecer práticas recomendadas para usuários externos e investigar chamadas externas independentemente da organização como um todo.

A medida real no CQD varia de acordo com a carga de trabalho, mas para fins de revisão da experiência de qualidade, nos concentramos principalmente na medição de _porcentagem de porcentagem de áudio_ . PSR é composto de cinco médias de métricas de rede descritas na tabela a seguir. Para que um fluxo seja classificado como ruim, apenas uma métrica precisa exceder o limite definido. Para obter mais informações sobre o processo de classificação de fluxo, consulte [Este artigo](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> O CQD fornece o "fraco devido a..." medidas para entender melhor qual condição fez com que o fluxo seja classificado como ruim.


_Tabela 1-métricas de áudio de baixa qualidade_

| Média métrica     | Descrição     | Experiência do usuário |
|-------------|-----------------|-----------------|
| Tremulação \>de 30 ms        | Esta é a alteração média no atraso entre pacotes sucessivos. O Microsoft Teams e o Skype for Business podem adaptar-se a alguns níveis de tremulação por meio do buffer. Só quando a tremulação excede o buffer que um participante observa os efeitos de tremulação.      | Os pacotes que chegam em diferentes velocidades fazem com que a voz de um palestrante seja Sound robótico.   |
| Taxa \>de perda de pacotes 10% ou 0,1        | Isso geralmente é definido como uma porcentagem de pacotes perdidos. A perda de pacotes afeta diretamente a qualidade do áudio, desde pacotes pequenos e perdidos individuais que praticamente não afetam as perdas de intermitência back-to-back que fazem com que o áudio seja recortado completamente.     | Os pacotes que estão sendo ignorados e não chegando ao destino pretendidos causam lacunas na mídia, resultando em sílabas e palavras perdidas e vídeo e compartilhamento instável. |
| Tempo \>de ida e volta 500 MS        | Esse é o tempo necessário para obter um pacote IP de um ponto a para o ponto B e voltar ao ponto a. Esse atraso de propagação de rede está ligado à distância física entre os dois pontos e a velocidade da luz e inclui a sobrecarga adicional tomada pelos vários dispositivos no caminho de rede.      | Os pacotes que demoram muito tempo para chegarem ao destino causam um efeito de faça de fala.   |
| Média \>de degradação de NMOS 1,0         | Média de [pontuação média média de opinião (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) para o fluxo. Representa o quanto a perda de rede e a tremulação afetaram a qualidade do áudio recebido que fez com que o NMOS essoltar em mais de um ponto. | Isso é uma combinação de tremulação, perda de pacote e, até um menor grau, um aumento no tempo de ida e volta. O usuário pode estar enfrentando uma combinação desses sintomas.   |
| Índice médio de amostras \>ocultas 7% ou 0, 7 | Razão média do número de quadros de áudio com amostras ocultas geradas pelo reparo de perda de pacotes para o número total de quadros de áudio. Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede ignorados.      | Valores altos indicam que os níveis significativos de ocultação de perda foram aplicados e resultaram em um áudio distorcido ou perdido.     |

#### <a name="setup-failure-rate"></a>Taxa de falha de configuração

A taxa de falha de configuração, caso contrário, conhecida como a medida de _porcentagem total da falha de configuração de chamada_ no CQD, é o número de fluxos nos quais o caminho da mídia não pôde ser estabelecido entre os pontos de extremidade no início da chamada.

Isso representa qualquer fluxo de mídia que não pode ser estabelecido. Devido à gravidade do impacto sobre a experiência do usuário medida aqui, o objetivo é reduzir esse valor o mais próximo do zero possível. Um valor alto para essa métrica é mais comum em novas implantações com regras de firewall incompletas do que uma implantação maduro, mas ainda é importante assistir regularmente.

Essa métrica é calculada pela criação do número total de fluxos que falharam ao configurar dividido pelo número total de fluxos que enviaram um registro de detalhe de chamada (CDR) bem-sucedido:

-   **Taxa de falha de configuração** = total da configuração da chamada falha na contagem do fluxo/total do fluxo de CDR disponível

#### <a name="drop-failure-rate"></a>Taxa de falha de soltura

A taxa de falha de soltura, caso contrário, conhecida como a medida de _porcentagem de falha de chamada ignorada_ no CQD, é a porcentagem de fluxos estabelecidos com êxito onde o caminho da mídia não terminou normalmente.

Isso representa qualquer fluxo de mídia que foi encerrado inesperadamente. Embora o impacto disso não seja tão grave quanto um fluxo que falhou ao configurar, ele afetará negativamente a experiência do usuário. Quedas de mídia súbitas e frequentes não só podem ter um sério impacto sobre a experiência do usuário, elas resultam na necessidade de reconexão dos usuários, resultando em perda de produtividade.

A métrica é calculada com o número total de fluxos soltos dividido pela contagem total de fluxos configurados com êxito:

-   **Ignorar taxa de falha** = número total de chamadas ignoradas contagem de fluxo/configuração da chamada total de fluxo

### <a name="define-your-target-metrics"></a>Definir suas métricas de destino

Esta seção discute algumas das métricas básicas de serviço que usamos para avaliar a integridade da experiência dos serviços. Ao avaliar e dirigir continuamente os esforços para manter essas métricas abaixo dos seus destinos definidos, você ajudará a garantir que seus usuários tenham uma qualidade de chamada consistente e confiável. Para começar, os seguintes destinos são fornecidos.

_Tabela 2: principais métricas de avaliação da integridade do alvo_
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


É importante discutir e definir os alvos da sua organização para atender aos objetivos de seus negócios.

### <a name="user-experience"></a>Experiência do usuário

A análise da experiência do usuário é mais moderna do que a ciência, pois as métricas coletadas aqui nem sempre significam que há um problema com a rede ou o serviço, mas elas simplesmente indicam que o usuário percebe um problema. A Microsoft oferece um mecanismo de pesquisa incorporado, conhecido como Tarifa minha chamada (RMC), para ajudar a avaliar a experiência geral do usuário. O RMC ajudará você a responder às seguintes perguntas da perspectiva dos usuários:

-   Eu sei como usar a solução?
-   A solução é fácil de usar e intuitiva e oferece suporte a minhas necessidades de comunicação do dia-a-dia?
-   A solução me ajuda a fazer com que meu trabalho seja feito?
-   Qual é a minha percepção geral da solução?
-   Posso usar a solução em qualquer point-in-time, independentemente de onde estou?
-   Eu posso configurar e manter uma chamada?

#### <a name="rate-my-call"></a>Classificar minha chamada 

Classificar minha chamada (RMC) incorpora-se ao Teams e ao Skype for Business e é configurada automaticamente para ser exibido para o participante após um a cada 10 chamadas ou 10%. Esta pesquisa rápida pede que o usuário avalie a chamada e forneça um pequeno contexto para o motivo pelo qual a qualidade da chamada pode ter sido ruim. Uma ou duas classificações são consideradas ruins, de três a quatro são boas e cinco são excelentes. Embora seja um indicador de defasagem, essa é uma métrica útil para a descoberta de problemas que as métricas de serviço podem perder.

> [!Note]
> Até que os usuários sejam instruídos a responder às pesquisas do RMC, além de uma boa opinião, as respostas são normalmente revertidas como negativas intensamente. A maioria dos usuários responde apenas quando a qualidade da chamada é ruim. Por isso, seus relatórios do RMC podem ser distorcidos para o lado fraco, mesmo que as métricas do serviço sejam boas.

Você pode usar o CQD para relatar as respostas de usuários do RMC e os relatórios de exemplo estão incluídos no modelo CQD. No entanto, elas não são discutidas detalhadamente neste guia. Para obter mais informações sobre o RMC no Skype for Business Online e sobre como instruir os usuários a fornecer respostas RMC úteis, consulte [esta postagem de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Preparação do cliente e do dispositivo

Você precisa de uma estratégia de cliente e dispositivo sólida para ajudar a garantir que seus usuários tenham uma experiência de usuário consistente e positiva. Alguns princípios importantes impulsionam cada estratégia de preparação.

##### <a name="client-readiness"></a>Preparação do cliente

Uma sólida estratégia de preparação para o cliente garante que seus usuários estejam executando a versão mais recente do cliente, aproveitando a melhor experiência possível. Patches rotineiros da Microsoft para o cliente Skype for Business; garantir que você o mantenha atualizado em seu ambiente é vital para o seu sucesso geral. Também é importante se lembrar de corrigir drivers de rede, vídeo, USB e áudio, pois eles geralmente são ignorados e podem afetar a experiência do usuário. Considere adicionar drivers de rede, Wi-Fi, de vídeo, USB e de áudio ao seu processo atual de gerenciamento de patches.

Recomendamos que você não deixe que as versões do cliente fiquem atrás por mais de seis meses. Se estiver usando o Office com Clique para executar, você já está sendo mantido atualizado pelo serviço. Use as [versões de cliente](#client-versions)incluídas, conforme descrito mais adiante neste guia para ajudá-lo com esse processo. Você também pode aproveitar os relatórios de exemplo de taxa de chamada para aprimorar ainda mais a estratégia de preparação do cliente.

> [!IMPORTANT]
> Atualmente, os clientes do teams são distribuídos e atualizados automaticamente por meio da rede de distribuição de conteúdo do Azure e serão mantidos em dia pelo serviço. Devido a isso, as atividades de preparação e investigação do cliente não se aplicam ao Teams.


##### <a name="device-readiness"></a>Preparação do dispositivo

Nenhuma estratégia única pode afetar a experiência do usuário mais do que a estratégia de preparação do dispositivo. A maioria das organizações está contente em remover dispositivos desnecessários (por exemplo, telefones de mesa ou outros dispositivos de áudio dedicados) dos usuários, e isso é muitas vezes uma justificativa de negócios básica para alternar para o Microsoft Teams ou o Skype for Business. No entanto, essas mesmas organizações às vezes hesitam em fornecer dispositivos de substituição, mesmo que esses dispositivos sejam menos caros. Os computadores e laptops modernos, embora equipados com microfone e alto-falantes integrados, não são otimizados para voz sobre IP (VoIP) de classe empresarial. Geralmente, isso cria uma experiência ruim para todos os participantes, especialmente se o alto-falante estiver em um ambiente barulhento. O programa de certificação de dispositivos da Microsoft garante que, quando um usuário participar de uma chamada telefônica, usar qualquer dispositivo certificado para Teams ou Skype for Business, ele produz uma experiência superior a um dispositivo não certificado. 

Sempre recomendamos que as equipes e os usuários do Skype for Business usem um fone de ouvido com microfone certificado ou um palestrante ao participar de uma chamada de voz pelo cliente da área de trabalho. Para obter mais informações sobre os dispositivos certificados da Microsoft, confira estes artigos sobre o [programa de certificação](/SkypeForBusiness/certification/overview) e veja o catálogo de [soluções de parceiros](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Use o [relatório de dispositivos](#devices), descrito mais adiante neste guia, para obter assistência com o gerenciamento de seus dispositivos.


### <a name="categories-of-quality"></a>Categorias de qualidade

O sucesso da operação em uma implantação de alta qualidade e confiabilidade depende do rigor operacional do edifício. Especificamente, preste atenção especial às três categorias ilustradas na figura a seguir; Estes são os focos deste guia:

-   **Rede:** Qualidade de áudio focada na métrica de baixa taxa de fluxo (PSR), uso do TCP, sub redes com fio e sem fio e identificação do uso de proxies HTTP e VPN.

-   **Pontos de extremidade:** Dispositivos de áudio e versões de cliente (somente Skype for Business).

-   **Gerenciamento de serviços:** Esta categoria contém duas seções:

    -   A primeira é a responsabilidade da Microsoft de gerenciar e manter o Teams e os serviços do Skype for Business online.

    -   Segundo estão as tarefas que sua organização deve gerenciar para garantir o acesso confiável ao serviço, como a atualização de informações de construção e a manutenção de firewalls de novos endereços IP do Office 365 à medida que a infraestrutura é adicionada ao serviço.

![Gráfico das categorias de qualidade em uma organização] (media/qerguide-image-categories.png "As categorias de qualidade em uma organização: gerenciamento de serviços, pontos de extremidade e rede.")

_Figura 3: categorias essenciais para o Teams e implantação do Skype for Business Online_

O gráfico a seguir descreve as tarefas que você deve executar em cada categoria. Recomendamos que você execute essas tarefas uma vez por semana, no mínimo.

Na primeira vez que você executar essas tarefas, você terá mais esforço do que as iterações subsequentes, pois muitas dessas categorias exigem que você valide as configurações de implantação. Depois de alcançar o estado desejado ao atender os destinos que você definiu, a execução dessas tarefas vai ajudá-lo a manter esse estado.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Lista de tarefas semanais por categoria de qualidade] (media/qerguide-image-tasks.png "Lista de tarefas semanais por categoria de qualidade")

#### <a name="service-management-tasks"></a>Tarefas de gerenciamento de serviço

Em uma nuvem-primeiro mundo, você deve executar determinadas tarefas de gerenciamento de serviço para manter experiências de usuário de alta qualidade. Essas tarefas variam desde a garantia de que há largura de banda suficiente para acessar o serviço sem saturating links de Internet, Validando que a QoS (qualidade de serviço) está em vigor em todas as áreas de rede gerenciadas e, em última parte, manter-se atualizado sobre os [intervalos de IP do Office 365 em firewalls](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Tarefas de rede

Há duas categorias de tarefas de rede: confiabilidade e qualidade. A confiabilidade se concentra em avaliar a capacidade do usuário de fazer chamadas com êxito e manter-se conectado. A qualidade se concentra na telemetria agregada enviada ao Teams e ao Skype for Business online pelo cliente do usuário durante a chamada e depois que ele termina. 

Devido ao impacto crítico que a confiabilidade tem sobre a experiência do usuário, é importante começar a avaliar e investigar essas métricas antes de se aprofundar na qualidade. 

#### <a name="endpoints-tasks"></a>Tarefas de pontos de extremidade

A principal tarefa nessa categoria é validar quais versões do cliente estão executando o Skype for Business nas versões de área de trabalho dos últimos seis meses, para garantir que os usuários obtenham o benefício das otimizações contínuas feitas ao cliente de desktop do Skype for Business. Além disso, isso simplifica as tarefas gerais de gerenciamento do cliente e oferece uma experiência de usuário consistente.

A outra área importante é monitorar quais dispositivos são predominantes na sua implantação e conduzir o uso de dispositivos certificados para fornecer a melhor experiência do usuário.


> [!IMPORTANT]
> Atualmente, os clientes do teams são distribuídos e atualizados automaticamente por meio da rede de distribuição de conteúdo do Azure e serão mantidos em dia pelo serviço. As atividades de preparação e investigação do cliente não são aplicáveis ao Teams.

## <a name="cqd-basics"></a>Noções básicas do CQD

Esta seção descreve os conceitos básicos de como trabalhar com o CQD. As diretrizes são fornecidas para os seguintes tópicos:

-   O que é CQD?
-   Expectativas usando o CQD
-   Localizando sua ID de locatário
-   Relatórios do Microsoft Teams versus Skype for Business
-   Primeiro versus segundo classificações
-   Dimensões, medidas e filtros
-   Fluxos versus chamadas
-   Chamadas boas, ruins e não classificadas
-   Sub-redes comuns

Para obter treinamento e recursos mais aprofundados, consulte o [Apêndice](#other-resources).

### <a name="what-is-cqd"></a>O que é CQD?

Use o painel de qualidade de chamada (CQD) para obter informações sobre a qualidade das chamadas feitas usando o Microsoft Teams e os serviços do Skype for Business. O CQD foi projetado para ajudar os administradores do Skype for Business e do Teams e os engenheiros de rede a otimizar a rede e ter um olho próximo na qualidade, na confiabilidade e na experiência do usuário. CQD examina a telemetria de agregação para uma organização inteira, em que os padrões gerais podem se tornar aparentes, permitindo que a equipe faça avaliações e atividades de correção bem fundamentadas para maximizar o impacto. O CQD fornece relatórios de métricas que proporcionam uma visão geral da qualidade, da confiabilidade e da experiência do usuário.

> [!Note]
> O CQD não contém informações de identificação pessoal (PII). PII são informações que podem ser usadas por conta própria ou por outras informações para identificar, contatar ou localizar uma única pessoa, ou para identificar um indivíduo no contexto.

Este guia ajudará a compreender os principais conceitos do CQD para ajudar a maximizar o impacto que você pode fazer para melhorar a experiência dos seus usuários com o Microsoft Teams ou o Skype for Business online. Recursos adicionais do CQD podem ser encontrados no [Apêndice](#other-resources).

### <a name="expectations-using-cqd"></a>Expectativas usando o CQD

CQD, embora útil para analisar tendências e sub-redes, nem sempre fornece uma causa específica para um determinado cenário. É importante entender isso e definir a expectativa correta ao usar o CQD:

-   O CQD não fornecerá a causa básica para todos os cenários.
-   O CQD não conterá fluxos de sistema de telefonia ou de audioconferência.
-   O CQD chamará as áreas para uma investigação mais profunda com base nas tendências.
-   CQD não contém PII.

### <a name="report-editions"></a>Edições de relatório

Há duas edições de relatório no CQD online: Resumo e detalhadas. Use o menu suspenso localizado na barra azul, na parte superior da tela, para abrir uma edição de relatório. O nome da edição de relatório selecionada é exibido na parte superior da tela.

-   Os relatórios resumidos são estáticos e não podem ser editados, baixados ou exportados. 
-   Relatórios detalhados são totalmente personalizáveis e podem ser baixados para um arquivo CSV, exportados ou clonados.

Para obter uma descrição completa da diferença entre as duas edições, confira [Este artigo](turning-on-and-using-call-quality-dashboard.md).

![Captura de tela do menu suspenso com relatórios de resumo selecionados](media/qerguide-image-reportcategories.png)

_Figura 4-categorias de relatórios do CQD_

Os relatórios resumidos são divididos em quatro categorias:

-   Os **relatórios** resumidos se concentram em analisar tendências de qualidade com relatórios diários, mensais e de tabela para ajudar a identificar sub-redes com baixa qualidade. Esta é a página de destino padrão quando você entra pela primeira vez no CQD online.
-   **Local-os relatórios avançados** se concentram em analisar tendências de qualidade com base nas informações de localização. Para usar esses relatórios, você deve ter carregado um arquivo de construção.
-   Os **relatórios de confiabilidade** se concentram em analisar as tendências de confiabilidade de áudio, vídeo, compartilhamento de tela baseado em vídeo (vBSS) e compartilhamento de aplicativos.
-   Os **relatórios de qualidade da experiência** são uma versão "reduzida" dos modelos detalhados do qer, com foco em áreas essenciais para a análise da qualidade e da confiabilidade do áudio.

### <a name="report-types"></a>Tipos de relatório

Você pode escolher entre dois tipos de relatórios no CQD, dependendo de como você deseja exibir seus dados. Embora este guia não aborde os detalhes específicos da criação de um tipo de relatório sobre outro, os modelos QER CQD fornecem uma combinação de relatórios personalizados de gráficos e tabelas para você usar:

-   Relatórios de gráfico Crie gráficos de barras gráficos para representar dados em um formato visual. Os relatórios de gráfico são melhor usados para visualizar dados durante um determinado período de tempo.
-   Os relatórios de tabela são úteis para analisar medidas e dimensões individuais ao exportar os relatórios para arquivos CSV para manipulação no Microsoft Excel.

### <a name="tenant-id"></a>ID do locatário

Alguns relatórios do CQD exigem que você inclua um filtro para a sua ID de locatário. Devido à maneira como o CQD agrega dados, a telemetria do participante federado está incluída. Embora isso possa ser valioso ao analisar tendências, os relatórios do cliente e do dispositivo exigem que você filtre os dados em um locatário específico para excluir a telemetria federada do participante. Se não souber a ID do locatário, você pode usar um dos seguintes métodos para localizá-la.

> [!Note]
> Esses métodos exigem as seguintes permissões:<ul><li>Função de administrador global</li><li>Função de administrador do Skype for Business</li></ul>

#### <a name="azure-portal"></a>Portal do Azure

1.  Entre no portal do Microsoft Azure:<https://portal.azure.com>

2.  Selecione **Azure Active Directory**.

3.  Em **gerenciar**, selecione **Propriedades**. A ID do locatário é mostrada na caixa **ID do diretório** .

#### <a name="azure-powershell"></a>PowerShell do Azure

1. [Instale o módulo de gerenciamento de serviço do Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2. Abra uma janela de comando do PowerShell PowerShell e execute o seguinte script, insira suas credenciais do Office 365 quando solicitado: 

   ```
   Login-AzureRmAccount
   ```

3. A ID do locatário está listada na saída.

#### <a name="skype-for-business-online-admin-center"></a>Centro de administração do Skype for Business Online

1.  Vá para <https://portal.office.com>.

2.  Entre com sua conta organizacional de administrador de locatários.

3.  Selecione **Skype for Business** em **centros de administração**.

4.  A ID do locatário está listada como **ID da organização** na página de boas-vindas.

#### <a name="skype-for-business-online-using-powershell"></a>Skype for Business online usando o PowerShell

1. [Configurar seu computador para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Execute o seguinte comando:

   ```
   (Get-cstenant).tenantid
   ```

3. A ID do locatário é exibida como um GUID.

### <a name="teams-vs-skype-for-business"></a>Teams versus Skype for Business

CQD pode denunciar nas equipes e na telemetria do Skype for Business. No entanto, pode haver ocasiões em que você queira desenvolver um relatório para ver a telemetria de equipes separada do Skype for Business.

#### <a name="summary-reports"></a>Relatórios de resumo

Para modificar a página relatórios resumidos para ver apenas as equipes ou o Skype for Business, selecione o menu suspenso de **filtro do produto** na parte superior da tela e selecione o produto desejado.

![Captura de tela do menu suspenso mostrando as opções de filtro](media/qerguide-image-productfilter.png)

_Figura 5: selecionar um filtro de produto_

#### <a name="detailed-reports"></a>Relatórios detalhados

Para filtrar todos os relatórios detalhados, na barra do navegador, acrescente o seguinte ao final da URL:

```
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Exemplo**

```https://cqd.lync.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obter mais informações sobre filtros de URL, consulte [Filtrar relatórios](#filtering-reports) mais adiante nesta seção.

Para filtrar um relatório detalhado individual, adicione o filtro ``Is Teams`` ao relatório e defina-o como verdadeiro ou falso. Para obter mais informações, consulte [editando relatórios](#editing-reports) mais adiante nesta seção.

![Captura de tela da página Adicionar filtro](media/qerguide-image-addteamsfilter.png)

_Figura 6: adicionando um filtro do Microsoft Teams a um relatório_


### <a name="managed-vs-unmanaged-networks"></a>Redes gerenciadas versus não gerenciadas

Por padrão, todos os pontos de extremidade no CQD são classificados como externos. Assim que um arquivo de criação é introduzido, podemos começar a examinar dados de ponto de extremidade gerenciados. Conforme discutido anteriormente, as redes no CQD são definidas como:

-   Uma _rede gerenciada_, geralmente conhecida como interna ou interna, pode ser influenciada e controlada pela organização. Isso inclui a LAN interna, a WAN remota e a VPN.
-   Uma _rede_não gerenciada, muitas vezes conhecida como externa ou externa, não pode ser influenciada ou controlada pela organização. Um exemplo de uma rede não gerenciada é uma rede de Hotel ou aeroporto.

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

-   **Bom ou ruim:** Uma chamada boa ou ruim consiste em uma chamada que contém um conjunto completo de métricas de serviço, para o qual um relatório de QoE completo foi gerado e recebido pelo serviço. Determinar se um fluxo é bom ou ruim é descrito [anteriormente neste guia](#poor-stream-rate).

-   Não **classificado:** Um fluxo não classificado não contém um conjunto completo de métricas de serviço. Elas podem ser chamadas curtas, geralmente menores do que 60 segundos, em que as médias não poderiam ser calculadas e um relatório de QoE não foi gerado. O motivo mais comum para que as chamadas sejam não classificadas é que não havia pouca utilização de pacote. Um exemplo disso seria um participante que ingressou em uma reunião em mudo e nunca falar. O participante está recebendo, mas não transmitindo, mídia. Sem a transmissão de mídia, não haverá métricas disponíveis para o CQD usar para classificar o fluxo de mídia de saída do ponto de extremidade.

Para obter mais informações sobre o processo de classificação de fluxo, consulte [Este artigo](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Sub-redes comuns

As sub-redes comuns são sub-redes privadas específicas usadas por Hotéis, redes domésticas, pontos de acesso e áreas semelhantes. Essas sub-redes são difíceis de fazer a triagem devido ao uso generalizado. Se a sua organização usa uma dessas sub-redes comuns, recomendamos que você mova essa rede para outra sub-rede. Isso fará com que o relatório seja mais fácil no CQD. Quando observados, os relatórios no modelo todas as redes foram configurados para excluir essas sub-redes para eliminá-las como uma fonte de baixa qualidade. Sub-redes comuns são definidas abaixo; o impacto varia de acordo com a organização.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Ao investigar uma rede gerenciada que usa uma sub-rede comum, você precisará usar a segunda dimensão de IP local reflexivo para agrupar sub-redes. Essa dimensão contém o endereço IP público do ponto de extremidade.

## <a name="cqd-online"></a>CQD online

Esta seção descreve os conceitos básicos de acesso ao CQD. As diretrizes são fornecidas para os seguintes tópicos:

-   Acessando o CQD online
-   Introdução ao CQD
-   Editando relatórios no CQD
-   Filtrar relatórios no CQD
-   Importar relatórios no CQD

Para obter treinamento e recursos mais aprofundados, consulte o [Apêndice](#other-resources).

### <a name="access-cqd-online"></a>Access CQD online

Você pode acessar o CQD de uma destas três maneiras:

-   Vá para <https://cqd.lync.com>.

-   Vá para **centro de administração do Microsoft Teams** e selecione o link para CQD, conforme mostrado na ilustração a seguir.

![Captura de tela do painel de qualidade da chamada selecionado.] (media/qerguide-image-mopo.png "No painel de navegação à esquerda, o link para o painel de qualidade de chamada é selecionado.")

_Figura 7 – acessando o CQD por meio do centro de administração do Microsoft Teams_

-   Vá para as > **ferramentas**herdadas do **centro de administração do Skype for Business**e selecione o link para CQD, conforme mostrado na ilustração a seguir.

![Captura de tela de CQD selecionada no painel principal.] (media/qerguide-image-legacyui.png "Ferramentas está selecionada no painel de navegação à esquerda e o link para CQD está selecionado no painel principal.")

_Figura 8-acessando o CQD por meio do centro de administração do Skype for Business_


### <a name="getting-started"></a>Introdução

Ao navegar pela primeira vez para CQD, você verá a página relatórios de resumo. A maioria dos relatórios descritos neste guia são relatórios detalhados personalizados. Para começar a usar os relatórios detalhados, selecione **relatórios** resumidos na parte superior da página e, em seguida, escolha **relatórios detalhados**.

![Captura de tela mostrando tipos de relatórios disponíveis no CQD](media/qerguide-image-choosereports.png)

_Figura 9: navegando para relatórios detalhados_

A página relatórios detalhados no CQD é semelhante à ilustração a seguir.

![captura de tela ilustrando elementos que compõem um relatório detalhado](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior] (media/qerguide-image-callout1.png "um") | O painel Resumo mostra o contexto para o conjunto de relatórios que aparece à direita. |
| ![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior] (media/qerguide-image-callout2.png "duas") | Você pode selecionar **Editar** no painel Resumo para definir as propriedades de nível de relatório (incluindo a altura do eixo y) e para importar novos modelos. |
| ![Ícone do número 3, fazendo referência a um texto explicativo na captura de tela anterior] (media/qerguide-image-callout3.png "três") | O breadcrumb ajuda os usuários a identificar sua localização atual na hierarquia de conjuntos de relatórios. |
| ![Ícone do número 4, fazendo referência a um texto explicativo na captura de tela anterior] (media/qerguide-image-callout4.png "quatro") | Os relatórios que têm relatórios secundários são mostrados com um link azul. Ao selecionar o link, você pode fazer uma busca detalhada nos relatórios filho. |

_Figura 10-página relatórios detalhados_

Aponte para gráficos de barras e linhas de tendências no relatório para exibir valores detalhados. O relatório que tem o foco mostrará o menu de ação: **Editar**, **clonar**, **excluir**, **baixar**e **Exportar árvore de relatórios**.

### <a name="editing-reports"></a>Editando relatórios

Ao selecionar **Editar** no menu de ação de um relatório, você abrirá o editor de consultas. Cada relatório é apoiado por uma consulta para CQD. Um relatório é uma visualização dos dados retornados por sua consulta. O editor de consultas é uma interface do usuário para a edição dessas consultas, além das opções de exibição do relatório, conforme ilustrado na figura a seguir.

![Captura de tela ilustrando elementos que compõem um relatório sendo editado.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior] (media/qerguide-image-callout1.png "um") | Escolha dimensões, medidas e filtros no painel esquerdo. A apontar para um valor existente exibe um botão fechar (**X**) você pode selecionar para remover o valor.<ul><li>Ao selecionar a dimensão ou medida, você pode alterar o título editando o campo de **título** . Você também pode alterar a ordem selecionando as setas azuis para cima ou para baixo no painel superior.</li><li>Selecionar (**+**) ao lado de um título abre a caixa de diálogo para adicionar uma nova dimensão, medida ou filtro.</li><li>Insira as primeiras letras da dimensão, medida ou filtro no campo **localizar um** para filtrar a lista para facilitar a pesquisa.</li></ul> |
| ![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior] (media/qerguide-image-callout2.png "duas") | O painel superior mostra opções para personalização do gráfico. |
| ![Ícone do número 3, fazendo referência a um texto explicativo na captura de tela anterior] (media/qerguide-image-callout3.png "três") | O editor de consultas mostra uma visualização do relatório. |
| ![Ícone do número 4, fazendo referência a um texto explicativo na captura de tela anterior] (media/qerguide-image-callout4.png "quatro") | Use a caixa **Editar** na parte inferior da tela para criar ou editar uma descrição detalhada do relatório. |

_Figura 11-editor de consulta_

### <a name="filtering-reports"></a>Filtrar relatórios

Os modelos fornecidos incluem várias consultas internas e filtros de relatório. As seções a seguir descrevem os filtros mais comuns usados em todos os modelos.

#### <a name="url-filter"></a>Filtro de URL

Você pode usar um filtro de URL para filtrar cada relatório de uma dimensão específica. Os filtros de URL mais comuns são usados para filtrar relatórios e excluir telemetria de participantes federados ou se concentrar no Teams ou no Skype for Business online. Recomendamos que, ao usar filtros, você os marque para facilitar a referência. 

Excluir dados federados dos relatórios do CQD é útil quando você está remediando prédios gerenciados ou redes nas quais pontos de extremidade federados podem influenciar seus relatórios.

Para implementar um filtro de URL, na barra de endereços do navegador, adicione o seguinte ao final da URL:

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemplo  

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Para filtrar os relatórios do teams ou do Skype for Business, acrescente o seguinte ao final da URL:

```
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Exemplo

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Os exemplos de URL acima são apenas para representação visual. Use o link CQD padrão de <https://cqd.lync.com>.


#### <a name="query-filters"></a>Filtros de consulta

Os filtros de consulta são implementados usando o editor de consultas no CQD. Esses filtros são usados para reduzir o número de registros retornados pela CQD, minimizando assim o tamanho geral do relatório e os tempos de consulta. Isso é especialmente útil para filtrar redes não gerenciadas. Os filtros listados na tabela a seguir usam expressões regulares (RegEx).

_Tabela 3-filtros de consulta_

| Filter         | Descrição          | Exemplo de filtro de consulta CQD      |
|----------------|----------------------|-------------------------------|
| Nenhum valor em branco   | Alguns filtros não têm a opção de filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e defina o filtro para igual ou não igual, dependendo das suas necessidades.      | Segundo \< \> \^nome \\da compilação s\*\$                       |
| Excluir sub-redes comuns | Sem um arquivo de construção válido para separar o gerenciamento de redes não gerenciadas, as redes domésticas serão incluídas nos relatórios. Essas sub-redes residenciais estão fora do escopo do controle de ti e podem ser rapidamente excluídas de um relatório. As sub-redes comuns, conforme definido neste guia, são 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Segunda sub-rede \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Exibir somente dentro  | Usado para filtrar um relatório para gerenciado (interno) ou não gerenciado (externo). O modelo CQD gerenciado já está pré-configurado com esses filtros.       | Segunda interna Corp = Inside        |

#### <a name="report-filters"></a>Filtros de relatório

Os filtros de relatório são implementados adicionando-se um filtro ao relatório renderizado no editor de consultas ou diretamente ao relatório. Os filtros de relatório a seguir são usados em todo o modelo.

_Tabela 4-filtros de relatório_

| Filter     | Descrição                            | Exemplo de filtro de relatório CQD         |
|------------|----------------------------------------|-----------------------------------|
| Mensais      | Comece com o ano primeiro e, em seguida, mês. | 2017-10                           |
| Maiúscula | Filtros para qualquer caractere alfabético. | [a-z]                             |
| Alfanumérico    | Filtros para caracteres numéricos.    | [0-9]                             |
| Porcentual | Filtros para uma porcentagem.              | ([3-9]\\.) \|([3-9])\|([1-9] [0-9]) |

## <a name="import-the-cqd-templates"></a>Importar os modelos do CQD

Este guia inclui [dois modelos de CQD organizadas](https://aka.ms/qertemplates). Esses modelos aceleram o uso do CQD e fornecem a você uma oportunidade de aproveitar rapidamente os recursos da CQD para causar um impacto nas equipes dos seus usuários ou na experiência do Skype for Business. O modelo todas as redes, embora otimizado para trabalhar com um arquivo de construção de dados, pode ser usado enquanto você trabalha para coletar e carregar informações de construção no CQD, conforme descrito na próxima seção.

**Para importar os modelos (. CQDX) no CQD online**

1. Vá para <https://cqd.lync.com>.

2. Autentique usando suas credenciais administrativas do Office 365.

   > [!NOTE]
   > Você deve ter o administrador global do Office 365, o administrador do Skype for Business ou a função de leitores de relatório para acessar o CQD. 

3. Selecione o menu **relatórios de resumo** na parte superior da página e, em seguida, escolha **relatórios detalhados**.

4. No painel Resumo, selecione **importar**. Vá para o local salvo do CQDX, selecione o modelo CQDX e, em seguida, selecione **abrir**.

5. Após o carregamento do modelo, uma janela pop-up exibirá a mensagem "relatório de importação foi bem-sucedido". Selecione **OK.**

   ![Captura de tela de uma notificação de importação bem-sucedida] (media/qerguide-image-importmessage.png "Notificação de que o modelo foi importado com êxito")

6. Repita as etapas 4 e 5 para o segundo modelo CQD.

> [!NOTE]
> Os modelos do CQD são importados por usuário. Se usuários adicionais precisarem usar o relatório, eles devem entrar e importar os modelos para a sua instância do CQD. 


## <a name="building-mapping"></a>Criando mapeamento

Em uma implantação do teams ou do Skype for Business Online, todos os clientes são externos. Isso tem a implicação de que, por padrão, todos os clientes são reportados como externos no CQD online, independentemente de o cliente ter sido conectado a uma rede corporativa interna.

Ao trabalhar com o CQD, você precisa saber a localização de um ponto de extremidade e se ele está conectado a uma rede que você pode gerenciar ou uma rede que não pode gerenciar — pressupõe-se que você só possa melhorar as redes que pode gerenciar. Carregando a sub-rede e criando informações para o CQD online, você habilita o CQD para determinar se o ponto de extremidade foi conectado a uma rede corporativa/gerenciada interna ou a uma rede externa/não gerenciada.

### <a name="building-data-file-structure"></a>Criando a estrutura de arquivos de dados

O formato do arquivo de dados que você carrega deve atender aos seguintes requisitos para passar a verificação de validação antes de carregar.

-   O arquivo deve ser um arquivo TSV, o que significa que, para cada linha, cada coluna é separada por um caractere de tabulação — ou um arquivo CSV no qual cada coluna é separada por uma vírgula.

-   O arquivo não pode ter mais de 50 MB.

-   O conteúdo do arquivo de dados *não deve incluir cabeçalhos de tabela*. Em outras palavras, a primeira linha do arquivo de dados deve ser dados reais, e não títulos de coluna, como "rede".

-   Para cada coluna, o tipo de dados só pode ser String, Number ou bool. Se o tipo de dados for núm, o valor deve ser um valor numérico; Se for bool, o valor deve ser 0 ou 1.

-   Para cada coluna, se o tipo de dados for String, os dados podem ficar vazios (mas ainda devem ser separados por um delimitador adequado, ou seja, um caractere de tabulação ou uma vírgula). Isso apenas atribui um valor de cadeia de caracteres vazia a um campo.

-   Deve haver 14 colunas para cada linha. Cada coluna deve ter o tipo de dados descrito na tabela a seguir, e as colunas devem estar na ordem listada na tabela.

_Tabela 5 – criando a estrutura de arquivos_

| Nome da coluna        | Tipo de dados | Exemplo                   | Orientação    |
|--------------------|-----------|---------------------------|-------------|
| Rede            | Cadeia de caracteres    | 192.168.1.0               | Obrigatório    |
| NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-SEA-1 | Obrigatório\*  |
| NetworkRange       | Número    | 26                        | Obrigatório    |
| BuildingName       | Cadeia de caracteres    | SEATTLE-SEA-1             | Obrigatório\*  |
| Propriedadetype      | Cadeia de caracteres    | Contoso.com                   | Opcional    |
| Buildingtype       | Cadeia de caracteres    | Terminações            | Opcional    |
| BuildingOfficeType | Cadeia de caracteres    | Engineer               | Opcional    |
| Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado |
| ZipCode            | Cadeia de caracteres    | 98001                     | Recomendado |
| País            | Cadeia de caracteres    | Junte                        | Recomendado |
| Estado              | Cadeia de caracteres    | WA                        | Recomendado |
| Região             | Cadeia de caracteres    | MSUS                      | Recomendado |
| InsideCorp         | Bool      | 1                         | Obrigatório    |
| ExpressRoute       | Bool      | 0                         | Obrigatório    |

\*Embora não seja exigido pela CQD, os modelos são configurados para exibir o prédio e o nome da rede.

#### <a name="supernetting"></a>Combinação de sub-redes

Você pode usar a combinação de redes, comumente chamada de roteamento Inter-Domain sem classe (CIDR), no lugar da definição de cada sub-rede. Um *Supernet* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de sub-rede. Há suporte para a combinação de sub-redes, mas não recomendamos usá-la.

Por exemplo, a compilação de marketing da Contoso é composta pelas subredes abaixo:

-   10.1.0.0/24 — primeiro andar
-   10.1.1.0/24 — segundo andar
-   10.1.2.0/24 – terceiro andar
-   10.1.3.0/24 – quarto andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de sub-rede e, neste exemplo, 10.1.0.0/22.

-   Network = 10.1.0.0
-   Intervalo de rede = 22

Aqui estão algumas coisas a serem consideradas antes de implementar a combinação de sub-redes:

-   A combinação de redes só pode ser usada em um mapeamento de sub-rede com máscara de 8 bits a 28 bits.

-   A combinação de sub-redes leva menos tempo, mas tem o custo de reduzir a riqueza dos seus dados. Digamos que há um problema de qualidade envolvendo a subnet 200.1.2.0. Se você implementou a combinação de redes, não sabe onde está localizado o que está criando a sub-rede ou qual é o tipo da rede (por exemplo, um laboratório). Se você definiu todas as sub-redes para criar e carregar as informações de localização de chão, você poderá ver essa distinção.

-   É importante certificar-se de que o endereço de sub-rede está correto e não está capturando sub-redes não desejadas.

-   É muito comum localizar 192.168.0.0 nos dados. Para muitas organizações, isso indica que o usuário está em casa. Para outros, é o esquema de endereço IP para um escritório de satélite. Se a sua organização tem escritórios que usam essa configuração, não a inclua em seu arquivo de construção porque é difícil distinguir entre redes domésticas e internas usando sub-redes comuns. Consulte a seção sobre as [sub-redes comuns](#common-subnets), anteriormente neste guia.

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar um Supernet. Todos os novos carregamentos de arquivos de dados de construção serão verificados em busca de intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar se há sobreposições e corrigir o problema. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos errados de sub-redes para edifícios nos relatórios.

#### <a name="vpn"></a>VPN

Os dados de qualidade da experiência (QoE) que os clientes enviam para o Office 365, onde os dados do CQD são originados a partir de — inclui um sinalizador de VPN. O CQD o verá como a primeira e a segunda dimensões de VPN e VPN. No entanto, esse sinalizador depende dos relatórios de fornecedores de VPN para Windows que o adaptador de rede VPN está cadastrado é um adaptador de acesso remoto. Nem todos os fornecedores de VPN registram corretamente adaptadores de acesso remoto. Por isso, talvez você não possa usar os filtros de consulta VPN internos. Há duas abordagens para acomodar sub-redes VPN no arquivo de informações de construção:

- Defina um **nome de rede** usando o texto "VPN" nesse campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando VPN usando o nome da rede](media/qerguide-image-vpnnetworkname.png)

  _Figura 12-VPN usando o nome da rede_

- Defina um **nome de edifício** usando o texto "VPN" nesse campo para sub-redes VPN.

  ![Captura de tela do relatório QCD mostrando VPN usando o nome da construção](media/qerguide-image-vpnbuildingname.png)

  _Figura 13-VPN usando o nome da construção_

> [!IMPORTANT]
> Algumas implementações de VPN não relatam precisamente as informações de sub-rede. Se isso ocorrer em seus relatórios, recomendamos que, ao adicionar uma sub-rede VPN ao arquivo de construção, em vez de uma entrada para a sub-rede, adicione entradas separadas para cada endereço na sub-rede VPN como uma rede de 32 bits separada. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você tem 253 linhas com uma linha para cada endereço de 172.16.18.1/32 a 172.16.18.254/32, inclusive.


> [!NOTE]
> As conexões VPN receberam a identificação da conexão de rede com fio como conectado quando a conexão à Internet subjacente é sem fio. Ao examinar a qualidade em conexões VPN, você não pode presumir que o tipo de conexão foi identificado de forma precisa.

### <a name="uploading-building-information"></a>Carregando informações de construção

O painel relatórios de resumo CQD inclui uma página de **carregamento de dados** de locatários, acessada selecionando a marca link de **carregamento de dados do locatário** no canto superior direito (procure o ícone de engrenagem). Esta página é usada para os administradores carregarem suas próprias informações, como o mapeamento de endereços IP e informações geográficas, o mapeamento de cada ponto de acesso sem fio e seu endereço MAC e assim por diante.

1. Acesse CQD online navegando até <https://cqd.lync.com>.

2. Selecione o ícone de engrenagem no canto superior direito e escolha **carregar dados do locatário** na página **relatórios de resumo** .

   ![Captura de tela da caixa de diálogo que aparece enquanto os dados são carregados](media/qerguide-image-tenantdataupload.png)

   _Figura 14-menu de carregamento de dados do locatário_

3. Ou, se esta for a primeira vez que visitar CQD, você será solicitado a carregar os dados de construção. Você pode selecionar **carregar agora** para navegar rapidamente até a página de **carregamento de dados do locatário** .

   ![Captura de tela da faixa que notifica um usuário para carregar dados de construção](media/qerguide-image-buildingdatauploadbanner.png)

   _Figura 15: criando faixa de carregamento de dados_

4. Na página **carregamento de dados do locatário** , selecione **procurar** para escolher um arquivo de dados.

5. Depois de selecionar um arquivo de dados, especifique **data de início** e, opcionalmente, especifique uma data de término.

6. Depois de selecionar **data de início**, selecione **carregar** para carregar o arquivo para CQD. <br><br>Antes de o arquivo ser carregado, ele é validado. Se a validação falhar, uma mensagem de erro será exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro que ocorre quando o número de colunas no arquivo de dados está incorreto.

   ![Exemplo de caixa de diálogo exibindo um erro de carregamento de dados de construção](media/qerguide-image-buildingdatauploaderror.png)
 
   _Figura 16-erro de carregamento de dados de construção_

7. Se não ocorrerem erros durante a validação, o carregamento do arquivo será bem-sucedido. Em seguida, você pode ver o arquivo de dados carregado na tabela **My uploads** , que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já carregou um arquivo de construção e precisa adicionar sub-redes que possam ter sido perdidos ou excluídos, modifique o arquivo original adicionando as novas sub-redes, remova o arquivo atual e carregue novamente o arquivo recentemente editado. Pode haver apenas um arquivo de criação de dados ativo no CQD. 


### <a name="updating-a-building-file"></a>Atualizando um arquivo de construção

Durante a coleta de informações de construção e de sub-rede, os administradores geralmente carregam o arquivo de construção em várias iterações ao longo do tempo, adicionando novas sub-redes e suas informações de construção à medida que se tornam disponíveis. Quando isso ocorrer, será necessário carregar novamente o seu arquivo de construção. Esse processo é como o upload inicial, conforme descrito na seção anterior, com algumas exceções, conforme observado na seção a seguir.

> [!Important]
> Somente um arquivo de construção pode estar ativo por vez. Vários arquivos de construção não são cumulativos.

#### <a name="adding-net-new-subnets"></a>Adicionando redes novas de rede

Há ocasiões em que você precisará adicionar novas sub-redes ao CQD que não faziam parte da topologia de rede. Para adicionar novas sub-redes, faça o seguinte no portal de carregamento de dados de locatários do CQD:

1.  Edite o arquivo de construção original e forneça uma data de término que ocorra pelo menos um dia antes da aquisição da nova sub-rede.
2.  Baixe o arquivo original, caso ainda não tenha uma cópia atualizada.
3.  Acrescente novas sub-redes ao arquivo de construção original.
4.  Carregue o arquivo de criação recém modificado seguindo o mesmo processo descrito acima e defina a data de início para um dia após o término do arquivo de construção anterior.

#### <a name="updating-the-current-building-file"></a>Atualizando o arquivo de construção atual

Se um arquivo de criação já estiver carregado, mas você precisar adicionar sub-redes ausentes, faça o seguinte no portal de carregamento de dados de locatários do CQD:

1.  Baixe o arquivo original, caso ainda não tenha uma cópia atualizada.
2.  Remova o arquivo atual no CQD.
3.  Acrescentar as novas sub-redes ao arquivo original.
4.  Carregue o arquivo de construção. Certifique-se de definir a data de início com pelo menos oito meses antes de que o CQD processe dados históricos.

### <a name="missing-subnets"></a>Sub-redes ausentes

Depois de carregar as informações de construção para redes gerenciadas, cada rede gerenciada deve ter uma associação de construção. No entanto, isso nem sempre é o caso; Geralmente, algumas sub-redes são perdidas. Esta seção aborda como validar essas redes ausentes.

Navegue até a página **relatórios detalhados** no CQD online e navegue até o **relatório de sub-rede ausente** incluído nos modelos do CQD. Isso apresenta todas as sub-redes com 10 ou mais fluxos de áudio que não são definidos no arquivo de dados de construção e são marcados como externos. Certifique-se de que não há redes gerenciadas nesta lista. Se as sub-redes estiverem ausentes, atualize o arquivo de dados de construção original e carregue-o novamente para CQD.

> [!IMPORTANT]
> Você precisará adicionar sua ID de locatário como um filtro de consulta para a **segunda ID de locatário** a esse relatório para filtrar o relatório e exibir somente os dados locatários da sua organização. Caso contrário, o relatório mostrará sub-redes federadas.

> [!NOTE] 
> Certifique-se de ajustar o filtro de relatório de ano do mês para o mês atual. Selecione **Editar**e ajuste o filtro relatório de **ano do mês** para salvar o novo mês padrão.

![Captura de tela mostrando relatório de sub-rede ausente](media/qerguide-image-missingbuildingreport.png)

_Figura 17-relatório de construção ausente_

### <a name="building-mapping-tools"></a>Ferramentas de mapeamento de construção

Vamos encarar o seu nome, o mapeamento de sub-redes em sua organização pode ser difícil. Grandes redes globais são muito complexas, com diferentes equipes que gerenciam suas respectivas regiões, e pode não haver uma única fonte de verdade para a topologia de rede. Há duas ferramentas disponíveis para ajudar a iniciar o exercício de criação de mapeamento, descrito nas seções a seguir.

#### <a name="cqd-tools"></a>Ferramentas de CQD

Essas ferramentas se baseiam no PowerShell e podem aproveitar os sites e serviços do Active Directory (AD) e os serviços DHCP da Microsoft para ajudar a preencher previamente o seu arquivo de construção.  Essas ferramentas ajudarão nas seguintes tarefas:

1.  Consultar sites e serviços de anúncios e criar um arquivo de construção com base nas informações contidas em.
2.  Consulta um servidor ou servidores DHCP da Microsoft para extrair informações de sub-rede e criar automaticamente um arquivo de construção.
3.  Valide um arquivo de construção existente, verificando se há duplicatas e sobrepostas.
4.  Localizar sub-redes não mapeadas no CQD.

Para obter mais informações sobre essa ferramenta, consulte [esta postagem de blog](https://aka.ms/cqdtools).

#### <a name="network-planner"></a>Network Planner

O planejador de rede determina e organiza os requisitos de rede para a implantação de voz em nuvem em apenas algumas etapas simples. Ao fornecer os detalhes da rede da sua organização e o uso de voz na nuvem, você pode obter um cálculo aproximado dos requisitos de rede para a implantação de voz em nuvem, gerenciar e exportar esses detalhes para relatórios e exibir áreas para investigação adicional e próximas etapas.

Apesar de o planejador de rede não automatizar o processo de mapeamento de construção completamente, após a inserção das informações de rede no planejador de rede, ele pode ser exportado para um arquivo de construção pronto para carregamento.

## <a name="diagnostic-alerts"></a>Alertas de diagnóstico

A Microsoft monitora proativamente a telemetria do CQD para criar alertas de diagnóstico para problemas conhecidos que afetam negativamente a experiência do usuário. Esses alertas serão entregues automaticamente ao administrador do serviço por meio do centro de mensagens. A tabela a seguir descreve os alertas de diagnóstico mostrados no centro de mensagens, além de links para obter mais informações.

_Tabela 6 – alertas de diagnóstico_

| Alertas                                                                | Mais informações             |
|----------------------------------------------------------------------|------------------------------|
| As versões do cliente com mau desempenho desconhecido estão em uso                   | [Versões do cliente](#client-versions)              |
| Drivers de áudio estão causando quedas de chamadas                                 | [Dispositivos](#devices)                      |
| Restrições no firewall estão causando falhas de configuração de chamada         | [Investigações de falha na configuração](#setup-failure-investigations) |
| A inspeção de pacotes profunda está causando falhas de configuração de chamadas                | [Investigações de falha na configuração](#setup-failure-investigations) |
| Os dispositivos de sala de reunião em redes Wi-Fi estão causando uma qualidade de chamada ruim | [Investigações de qualidade](#quality-investigations)       |
| O tráfego UDP está sendo limitado, o que provoca uma baixa qualidade de chamada         | [TCP](#tcp)                          |
| O uso de VPN está afetando a qualidade das chamadas                                  | [Investigações de qualidade](#quality-investigations)       |


### <a name="message-center"></a>Centro de mensagens

O centro de mensagens alerta sobre novas atualizações, recursos ou problemas. O centro de mensagens está disponível no centro de administração do Microsoft 365 para administradores de serviço. Cada postagem fornece uma visão geral de alto nível de como a atualização, o recurso ou o problema afeta seus usuários e fornece links para informações mais detalhadas.

Para abrir o centro de mensagens, no centro de administração do Microsoft 365, vá para**centro de mensagens**de **saúde** > ou selecione o cartão central de mensagens no painel **página inicial** . O painel exibe as três últimas mensagens que foram postadas e links para a página completa do centro de mensagens.
 

![Captura de tela do centro de mensagens mostrando as três últimas mensagens postadas](media/qerguide-image-messagecentercard.png)

_Figura 18-cartão do centro de mensagens_

Você também pode usar o [aplicativo de administração do Office 365](https://go.microsoft.com/fwlink/p/?linkid=627216) em seu dispositivo móvel para ver o centro de mensagens, que é uma ótima maneira de ficar atualizado com as notificações por push. Para obter mais informações, consulte [Este artigo](https://support.office.com/article/Message-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093).

## <a name="reliability-investigations"></a>Investigações de confiabilidade

A primeira etapa para melhorar a qualidade é avaliar o estado da confiabilidade em toda a organização. Como a confiabilidade é vital para uma experiência positiva do usuário, começamos com os dois componentes que avaliam a confiabilidade:

1.  **Falhas de configuração:** Não foi possível estabelecer a chamada.

2.  **Falhas de soltura:** A chamada foi estabelecida e terminada inesperadamente.

Nesta seção, abordaremos métodos para investigar ambas as áreas.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia.  No entanto, os métodos de investigação explicados abaixo ainda se aplicam. Confira a descrição do relatório individual para obter mais informações.


### <a name="setup-failures"></a>Falhas de configuração

Priorize a correção de falhas de configuração nesta área primeiro, pois essas falhas têm um impacto negativo significativo na experiência do usuário.

Comece a investigar avaliando a porcentagem de falhas gerais de configuração para a organização e, em seguida, Priorize as áreas de investigação com base na porcentagem mais alta ao criar ou à rede. 

#### <a name="setup-failure-trend-analysis"></a>Análise de tendência de falha de configuração

Este relatório exibe a quantidade total de fluxos, falhas de configuração do fluxo e a taxa de falha na configuração do fluxo. Aponte para qualquer uma das colunas para exibir seus valores individuais, conforme mostrado na figura a seguir. 

![Gráfico que mostra a porcentagem de falhas de configuração do fluxo](media/qerguide-image-streamsetupfailures.png)

_Figura 19-confiabilidade de áudio-falhas na configuração do fluxo_

##### <a name="analysis"></a>Análise

Ao usar este relatório, você pode responder às seguintes perguntas e determinar o próximo curso de ação:

-   Qual é a porcentagem de falha de configuração de chamada total para o mês atual?

-   A porcentagem de falha de configuração de chamada foi completada abaixo ou acima da métrica de destino definida?

-   A tendência de falha é pior ou melhor do que o mês anterior?

-   A tendência de falha está aumentando, estável ou decrescente?

Independentemente das respostas anteriores, dedique mais tempo para investigar usando os sub-relatórios complementares para procurar por prédios ou sub-redes individuais que possam precisar de correção. Embora a taxa de falha geral possa estar abaixo da métrica de destino, as tarifas de falha para um ou mais prédios ou redes podem estar acima da métrica de destino e precisam de investigação.

#### <a name="setup-failure-investigations"></a>Investigações de falha na configuração 

Este relatório de resumo é usado para descobrir e isolar quaisquer prédios ou redes que possam precisar de correção.

> [!NOTE]
> Certifique-se de ajustar o filtro de relatório de ano do mês para o mês atual. Selecione **Editar**e ajuste o filtro relatório de **ano do mês** para salvar o novo mês padrão.


![Captura de tela mostrando falhas de configuração](media/qerguide-image-setupfailuresbysubnet.png)

_Figura 20-falhas de configuração de áudio por sub-rede_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você recebeu um alerta de diagnóstico "restrições do firewall estão causando falhas de configuração de chamada" ou "a inspeção de pacotes profunda está causando falhas de configuração de chamadas", concentre seus esforços de correção nas sub-redes identificadas primeiro. O alerta identificou sub-redes que afetam negativamente a confiabilidade das chamadas. Você pode usar os relatórios de falhas de configuração encontrados na seção confiabilidade para auxiliar na correção.

##### <a name="remediation"></a>NAP 

Concentre seus primeiros esforços de correção em prédios ou sub-redes com o maior volume de falhas. Isso irá maximizar o impacto na experiência do usuário e ajudará a reduzir rapidamente a taxa de falhas de configuração da chamada organizacional. A tabela a seguir lista os dois motivos para falhas de configuração, conforme relatado pela CQD.

_Tabela 7 – motivos para falhas de configuração de chamada_

| Motivo da falha na configuração da chamada       | Causa típica                    |
|----------------------------------|----------------------------------|
| Regra de isenção de inspeção de pacotes profunda do FW ausente | Indica que o equipamento de rede ao longo do caminho impedia o caminho de mídia de ser estabelecido devido a regras de inspeção de pacotes profundas. Isso provavelmente aconteceu porque as regras de firewall não estão sendo configuradas corretamente. Nesse cenário, o handshake TCP foi concluído com êxito, mas o handshake SSL não.      |
| Regra de exceção de bloqueio de IP do FW ausente      | Indica que o equipamento de rede ao longo do caminho impedia o caminho de mídia de ser estabelecido para a rede do Office 365. Isso pode ser devido a regras de proxy ou de firewall não estarem configuradas corretamente para permitir o acesso a endereços IP e portas usados para o Microsoft Teams e o tráfego do Skype for Business. |

Agora que você começa a remediação, pode concentrar seus esforços em um determinado prédio ou sub-rede. Como mostra a tabela anterior, esses problemas são devido a configurações de firewall ou proxy. Examine as opções na tabela a seguir para ações de correção.

_Tabela 8 – próximas etapas para a correção de falha na configuração de chamada_


|      NAP      |                                                                                                                                                                                                                                                                                                                                                                   Orientação                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar firewall (s) | Trabalhe com sua equipe de rede e verifique a configuração de firewall (s) [na lista de endereços IP do Office 365](https://aka.ms/o365ips).<br><br>Verifique se as [sub-redes](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) e as portas de mídia estão incluídas nas regras de firewall. <br><br>Verifique se as portas necessárias (listadas abaixo) estão abertas no firewall. O UDP deve ter prioridade porque o TCP é considerado um protocolo de failback para compartilhamento de tela de áudio, vídeo e com base em vídeo, e seu uso afetará a qualidade da chamada. O compartilhamento de aplicativos RDP herdado usa apenas TCP.<br><ul><li>**TCP:** porta 443</li><li>**UDP:** portas 3478 – 3481</li><ul> |
|        Verificar         |                                                                                                                                                                                                                                                                 Use a [ferramenta de avaliação de rede da Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar a conectividade da compilação ou sub-rede afetada usando a função verificação de conectividade.                                                                                                                                                                                                                                                                  |

### <a name="drop-failures"></a>Falhas de soltura

Ao contrário dos códigos de falha de configuração, o CDQ não tem código de falha de soltura para indicar por que as falhas de soltura ocorrem, o que torna difícil isolar uma causa raiz específica. Para melhorar as falhas de descartar a triagem, use uma abordagem inferida. Ao corrigir qualquer área de interesse para mídia, corrigir clientes e drivers e conduzir o uso de dispositivos certificados para o Teams e o Skype for Business, você pode esperar falhas de soltura para recusar.

#### <a name="drop-failure-trend-analysis"></a>Ignorar análise de tendências de falha

Este relatório exibe a quantidade total de fluxos de áudio, as falhas de descarte total e a taxa de falha de soltura. Aponte para qualquer uma das colunas para exibir seus valores, conforme mostrado na figura a seguir. 

![Gráfico mostrando a porcentagem de fluxos que foram descartados](media/qerguide-image-droppedstreamrate.png)

_Figura 21-taxa de fluxo descartada_

##### <a name="analysis"></a>Análise

Ao usar esse tipo de relatório, você pode responder às seguintes perguntas:

-   Qual é a taxa de falha de soltura atual?
-   A taxa de falha suspensa está abaixo da métrica de destino definida?
-   A tendência de falha é pior ou melhor do que o mês anterior?
-   A tendência de falha está aumentando, estável ou decrescente?

Independentemente das respostas às perguntas acima, tome o tempo para investigar usando os sub-relatórios para procurar por prédios ou redes que possam precisar de correção. Embora a taxa de falha de soltura geral possa estar abaixo da métrica de destino, a taxa de falha de soltura para um ou mais prédios ou redes pode estar acima da métrica de destino e precisa de investigação.

#### <a name="drop-failure-investigations"></a>Eliminar investigações de falha

Falhas relatadas aqui indicam que a chamada foi cancelada inesperadamente e resultou em uma experiência de usuário negativa. Ao contrário dos relatórios de tendências, esses relatórios fornecem ideias adicionais em sub-redes específicas que exigem investigação adicional.

> [!NOTE]
> Certifique-se de ajustar o filtro de ano do mês para o mês atual. Selecione **Editar**e ajuste **ano do mês** para salvar o novo mês padrão.


![Relatório que lista o número e a porcentagem de falhas de soltura](media/qerguide-image-dropfailuresbysubnet.png)

_Figura 22 – eliminar falhas por sub-rede_

##### <a name="remediation"></a>NAP

Usando os relatórios de tabela incluídos, você pode isolar áreas problemáticas na rede em que a taxa de descarte está acima da métrica de destino que você definiu. Concentre seus primeiros esforços de correção em prédios ou sub-redes que tenham o maior número total de fluxo, para causar o maior impacto.

Causas comuns de cancelamentos de chamadas:

-   Saída de rede subprovisionada ou de Internet
-   Nenhuma QoS configurada em redes restritas
-   Versões mais antigas do cliente
-   Comportamento do usuário

Depois de descobrir suas áreas problemáticas, você pode usar a [análise de chamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) para revisar os usuários que estão criando problemas específicos. A análise de chamadas contém dados PII e pode ser útil para isolar ainda mais possíveis motivos para as falhas de soltura.

Independentemente da sua próxima etapa, é uma prática recomendada notificar a assistência técnica de que um problema foi descoberto com prédios ou sub-redes específicos. Dessa forma, eles podem responder rapidamente às chamadas recebidas e fazer a triagem dos usuários com mais eficiência. Os usuários sinalizados podem ser relatados para a equipe de engenharia para que você possa fazer uma investigação adicional.

A tabela a seguir lista alguns métodos comuns para gerenciar e corrigir falhas de soltura.

_Tabela 9-próximas etapas para correção de chamada_

| NAP                              | Orientação                      |
|------------------------------------------|-------------------------------|
| **Rede/Internet**                         | **Congestionamento**: trabalhe com sua equipe de rede para monitorar a largura de banda em prédios/sub-redes específicos para confirmar se há problemas com a superutilização. Se você confirmar que há um congestionamento de rede, considere aumentar a largura de banda para criar ou aplicar QoS. Use os [relatórios de Resumo de fluxo ruim de qualidade](#quality-investigations) incluídos para analisar as sub-redes problemáticas para problemas com tremulação, latência e perda de pacote, pois elas muitas vezes precederão um fluxo solto.<br><br>**QoS**: se o aumento da largura de banda for impraticável ou de custo inviável, considere implementar QoS. Essa ferramenta é muito eficiente no gerenciamento de tráfego congestionado e pode garantir que pacotes de mídia na rede gerenciada sejam priorizados acima do tráfego não relacionado à mídia. Ou, se não houver evidências evidentes de que a largura de banda seja a culpa, considere estas soluções:<ul><li>[Orientação QoS do Microsoft Teams](qos-in-teams.md)</li></ul><br>**Realize uma avaliação de preparação de rede**: uma avaliação de rede fornece detalhes sobre o uso de largura de banda esperado, como lidar com alterações de largura de banda e rede e práticas de rede recomendadas para o Teams e o Skype for Business. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são excelentes candidatos para uma avaliação.<ul><li>[Avaliação de preparação de rede do Microsoft Teams](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Ferramenta de avaliação de rede da Microsoft:** Use essa ferramenta para fazer um teste simples do desempenho da rede para determinar como a rede seria executada para uma equipe ou chamada do Skype for Business online. A ferramenta ajuda você a avaliar o desempenho de uma sub-rede e a validar a prontidão da rede em relação [aos requisitos](https://aka.ms/performancerequirements)de desempenho da Microsoft.<ul><li>[Baixar a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul> |
| **Clientes (somente Skype for Business online)** | Alguns clientes mais antigos têm problemas conhecidos e documentados com a confiabilidade de mídia. Revise os relatórios de análise de chamadas de vários usuários afetados ou crie um relatório de tabela de versão de cliente personalizada no CQD filtrado para prédios ou sub-redes específicos com a medida total de falha de chamada eliminada%. Essas informações ajudarão você a entender se uma relação existe entre quedas de chamadas nesse edifício específico e uma versão específica do cliente.     |
| **Dispositivos**                                  | Recomendamos que todos os usuários que tenham quedas de chamadas, ou chamadas ruinss, sejam provisionados em geral, e os dispositivos integrados devem ser provisionados com um [fone de ouvido com microfone certificado ou viva-voz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) para eliminá-lo como fonte potencial de baixa qualidade e confiabilidade. |
| **Comportamento do usuário**                            | Se você determinar que a rede, dispositivos ou clientes são o problema, considere o desenvolvimento de uma estratégia de adoção do usuário para ensinar aos usuários como ingressar e sair da melhor reunião. Uma equipe mais inteligente e o usuário do Skype for Business produzirão uma experiência de usuário melhor para todos os participantes da reunião. Um usuário que coloca o laptop em repouso (fechando a tampa) sem sair da reunião será classificado como uma queda de chamada inesperada.   |

## <a name="quality-investigations"></a>Investigações de qualidade

A próxima etapa para avaliar o estado de qualidade de áudio em toda a organização é investigar a taxa de fluxo de pico (PSR), TCP e uso de proxy. É importante lembrar que os dados do CQD não fornecem uma causa raiz específica, mas, em vez disso, fornecem a você as áreas de problemas prováveis para iniciar uma conversa colaborativa com as equipes adequadas para atividades de correção. 

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia; no entanto, os métodos de investigação explicados abaixo ainda serão aplicados a esses relatórios. Consulte a descrição do relatório individual para obter mais informações. 

### <a name="quality"></a>Qualidade

As porcentagens PSR são usadas para indicar se a organização está na reunião alvos de métrica definidos para uma determinada área de foco. É importante observar que, mesmo se as porcentagens de alto nível estiverem dentro do destino definido, as sub-redes ou edifícios individuais podem não atender aos alvos definidos e, portanto, precisam de investigação adicional. Por exemplo, se a porcentagem geral de PSR de áudio for 2% em abril, o que atende à amostra de destino, os prédios e as sub-redes individuais ainda podem estar com experiências ruins, dependendo da distribuição geral de 2%. 

Para avaliar a porcentagem de fluxos deficientes, use os relatórios de qualidade. Vários relatórios de qualidade são fornecidos para examinar as métricas gerais, conferências, chamadas de duas partes, chamadas PSTN, VPN e salas de reunião. Relatórios mensais, semanais e diários são fornecidos para ajudar nesse processo. Relatórios semanais e diários limitam-se ao modelo de redes gerenciadas para aumentar a eficácia e reduzir o ruído. 

#### <a name="quality-trend-analysis"></a>Análise de tendências de qualidade

Os relatórios de tendências exibem informações de qualidade ao longo do tempo e são usadas para ajudar a identificar e compreender as tendências de qualidade dentro de cada área de interesse. Conforme observado acima, há árvores de relatório incluídas nos modelos de qualidade de investigação; Conferência, duas pessoas, chamadas PSTN, VPN e salas de reunião. Para a finalidade de analisar a qualidade, o processo investigativo é o mesmo. No entanto, recomendamos que você comece com a conferência primeiro, pois as melhorias na qualidade da conferência também afetarão positivamente todas as outras áreas. 

> [!Note]
> A investigação de chamadas de duas partes, PSTN e salas de reunião é semelhante à investigação de conferências. O foco é para prédios ou sub-redes isloate que tenham a pior qualidade e identifiquem o motivo da má qualidade.

> [!Important]
> Relatórios baseados em VPN são filtrados usando a segunda dimensão de VPN. Essa dimensão requer que o adaptador de rede VPN seja devidamente registrado como um adaptador de acesso remoto. Os fornecedores de VPN não usam esse sinalizador com confiabilidade, e a quilometragem varia de acordo com o fornecedor de VPN implantado em sua organização. Siga as diretrizes descritas [anteriormente neste guia](#vpn) para modificar os relatórios de VPN, se necessário, usando o prédio ou o nome de rede.

![Gráfico mostrando a porcentagem de fluxos de baixa qualidade](media/qerguide-image-audioqualityconferencing.png)

_Figura 23 – qualidade de áudio – conferência_

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

> [!NOTE]
> Certifique-se de ajustar o filtro de ano do mês para o mês atual. Selecione **Editar**e ajuste **ano do mês** para salvar o novo mês padrão.

> [!Note]
> Sub-redes comuns são difíceis de fazer a triagem devido ao uso difundido. Um relatório separado que exibe o IP público do cliente (segundo IP local reflexivo) foi adicionado ao modelo todas as redes para auxiliar na correção de escritórios que usam redes comuns.


![Captura de tela mostrando o resumo do fluxo de áudio ruim](media/qerguide-image-poorqualitysummary.png)

_Figura 24 – Resumo de fluxo de áudio ruim por prédio e conferência_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você recebeu um alerta de diagnóstico "os dispositivos da sala de reunião em redes Wi-Fi estão causando uma qualidade de chamada ruim", inclua e Priorize esses dispositivos em seus esforços de correção. O alerta identificou salas de reunião em Wi-Fi que estão contribuindo ativamente para a baixa qualidade da chamada.

Se você receber um alerta de diagnóstico "o uso da VPN está afetando a qualidade da chamada", investigue uma solução de tunelamento dividido para ignorar o aparelho VPN e permitir que a mídia se conecte diretamente ao serviço. O alerta identificou que a VPN está afetando negativamente a qualidade da chamada.

##### <a name="remediation"></a>NAP

Concentre seus esforços de correção em prédios ou sub-redes que tenham o maior volume de fluxos, pois isso irá melhorar o impacto e ajudar a melhorar a experiência do usuário rapidamente. Use as medidas de tremulação, perda de pacote e RTT (tempo de ida e volta) para entender o que está contribuindo para a qualidade ruim (é possível que haja mais de um problema):

-   **Tremulação**: pacotes de mídia estão chegando em diferentes velocidades, o que faz com que um alto-falante Sound robótico.
-   **Perda de pacote**: pacotes de mídia estão sendo ignorados, o que cria o efeito de palavras ausentes ou sílabas.
-   **RTT**: pacotes de mídia estão demorando muito para chegar ao destino dele, o que cria um efeito de faça de fala.

Para ajudar a investigar problemas de qualidade, você pode usar a [análise de chamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Com o recurso de análise de chamadas, você pode examinar uma conferência específica ou um relatório de chamadas detalhados dos usuários. Esse relatório conterá dados PII e será útil quando você estiver procurando por causa de uma falha. Depois que você sabe qual é a criação, deve ser fácil rastrear os usuários nesse prédio. 

Não se esqueça de permitir que a assistência técnica saiba que essas redes estão apresentando problemas de qualidade, para que elas possam fazer a triagem e responder rapidamente às chamadas recebidas.

_Tabela 10-colaboradores comuns para o High PSR_

| NAP                              | Orientação                         |
|------------------------------------------|----------------------------------|
| **Network**                                 | **Congestionamento**: uma rede superutilizada ou subprovisionada pode causar problemas com a qualidade da mídia. Trabalhe com a equipe de rede para determinar se as conexões de rede do ponto de saída do usuário para a Internet têm largura de banda suficiente para dar suporte à mídia. <br><br>**Realize uma avaliação de preparação de rede**: uma avaliação de rede fornece detalhes sobre o uso de largura de banda esperado, como lidar com alterações de largura de banda e rede e práticas de rede recomendadas para o Teams e o Skype for Business. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são excelentes candidatos para uma avaliação.<ul><li>[Avaliação de preparação de rede do Microsoft Teams](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Ferramenta de avaliação de rede da Microsoft:** Use essa ferramenta para fazer um teste simples do desempenho da rede para determinar como a rede seria executada para uma equipe ou chamada do Skype for Business online. A ferramenta ajuda você a avaliar o desempenho de uma sub-rede e a validar a prontidão da rede em relação [aos requisitos](https://aka.ms/performancerequirements)de desempenho da Microsoft.<ul><li>[Baixar a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br> |
| **Qualidade de serviço (QoS)**  | QoS é uma ferramenta comprovada para ajudar a priorizar pacotes em uma rede congestionada para garantir que eles cheguem ao seu destino intactos e no prazo. Considere implementar a QoS em sua organização para maximizar a qualidade da experiência do usuário em que a largura de banda é restrita. A QoS ajudará a solucionar problemas geralmente associados a altos níveis de perda de pacotes, e — a um menor grau de tempo de tremulação e ida e voltagem.<ul><li>[Orientação QoS do Microsoft Teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | O Wi-Fi pode ter um impacto significativo na qualidade da chamada. Implantações de Wi-Fi geralmente não levam em consideração os requisitos de rede para serviços de VoIP e são muitas vezes uma fonte de baixa qualidade. Para obter mais informações sobre como otimizar sua infraestrutura Wi-Fi, consulte [Este artigo sobre o planejamento de Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Driver sem fio**: Certifique-se de que os drivers sem fio estejam atualizados. Isso ajudará a reduzir qualquer mau uso do usuário relacionado a um driver desatualizado. Muitas organizações não incluem drivers sem fio nos ciclos de patch, e esses drivers podem não ser corrigidos há anos. Muitos problemas sem fio são resolvidos garantindo que os drivers sem fio estejam atualizados.<br><br>**WMM**: o WMM (ramais de multimídia sem fio), também conhecido como multimídia Wi-Fi, oferece recursos básicos de QoS para redes sem fio. Redes sem fio modernas devem oferecer suporte a muitos dispositivos. Esses dispositivos conpetem largura de banda e podem levar a problemas de qualidade para serviços de VoIP, em que a velocidade e a latência são essenciais. Consulte o fornecedor sem fio para obter especificações e considere a implementação do WMM na sua rede sem fio para priorizar a mídia do Skype for Business e do teams.<br><br>**Densidade do ponto de acesso**: os pontos de acesso podem ser muito distantes ou não em um local ideal. Para minimizar a interferência potencial, coloque pontos de acesso extras em salas de conferência e em locais que não estão obstruídos por paredes ou outros objetos nos quais o sinal de Wi-Fi está fraco.<br><br>**2,4 GHz versus 5 GHz**: 5 GHz fornecem menos interferência em segundo plano e velocidades superiores e devem ser priorizadas ao implantar VoIP via Wi-Fi. No entanto, 5 GHz não é tão forte quanto 2,4 GHz e não penetra nas paredes com a mesma facilidade. Revise o layout da construção para determinar em qual frequência você pode confiar para obter a melhor conexão. |
|**Dispositivo de rede** | Organizações maiores podem ter centenas de dispositivos espalhados pela rede. Trabalhe com sua equipe de rede para garantir que os dispositivos de rede do usuário para a Internet sejam mantidos e atualizados. |
| **VPN**  | Os aparelhos VPN não foram projetados tradicionalmente para lidar com cargas de trabalho de mídia em tempo real. Algumas configurações de VPN proíbem o uso do UDP (que é o protocolo preferencial para mídia) e depende somente do TCP. Considere a implementação de uma solução de tunelamento de VPN para ajudar a reduzir a VPN como uma fonte de baixa qualidade. |
| **Clientes** <br>(Somente Skype for Business online) | Verifique se todos os clientes estão sendo atualizados regularmente. |
| **Dispositivos** | O uso de [dispositivos otimizados](https://partnersolutions.skypeforbusiness.com/solutionscatalog) pode ajudar a melhorar significativamente a experiência do usuário. Com todas as coisas iguais, os dispositivos otimizados são projetados para maximizar a experiência do usuário com o Microsoft Teams e o Skype for Business e produzir qualidade superior. |
| **Drivers** | O patch de rede (Ethernet e Wi-Fi), áudio, vídeo e drivers USB devem fazer parte de sua estratégia geral de gerenciamento de patches. Muitos problemas de qualidade são resolvidos com a atualização de drivers. |
| **Salas de reunião em Wi-Fi** | É altamente recomendável que os dispositivos da sala de reunião sejam conectados à rede usando pelo menos uma conexão Ethernet de 1 Gbps. Em geral, os dispositivos da sala de reunião incluem vários fluxos de áudio e vídeo, além de conteúdo da reunião, como compartilhamento de tela, e têm requisitos de rede mais altos do que outras equipes ou pontos de extremidade do Skype for Business. As salas de reunião são, por definição, dispositivos fixos nos quais Wi-Fi proporciona um benefício apenas durante a instalação.<br><br>As salas de reunião precisam ser tratadas com cuidado adicional e atenção para garantir que a experiência que usa esses dispositivos seja atender ou ultrapassar as expectativas. Problemas de qualidade com as salas de reunião geralmente vão ser escalonados rapidamente, porque geralmente são usados pela equipe de nível sênior.<br><br>Todas as coisas são iguais (além da comodidade), o desempenho do Wi-Fi geralmente é menor que uma conexão com fio. Com o aumento das políticas "Traga seu próprio dispositivo" e a proliferação de laptops, os pontos de acesso Wi-Fi são geralmente superutilizados. A mídia em tempo real pode não ser priorizada em redes Wi-Fi, o que pode levar a problemas de qualidade durante o tempo de pico de uso. Esse uso pesado pode coincidir com uma reunião em que pode haver dúzias de pessoas na participação, cada uma com seu próprio laptop e Smartphone, todas conectadas ao mesmo ponto de acesso Wi-Fi que o dispositivo da sala de reunião.<br><br>O Wi-Fi só deve ser considerado como uma solução temporária, para uma instalação móvel ou quando o Wi-Fi foi provisionado corretamente para dar suporte a mídias de classe empresarial em tempo real. |


### <a name="tcp"></a>TCP

O TCP é considerado um transporte de failback e não o transporte primário que você deseja para mídia em tempo real. O motivo é um transporte de failback devido à natureza de estado do TCP. Por exemplo, se uma chamada for feita em uma rede de acordo com pacotes de mídia e de mídia, os pacotes de alguns segundos atrás, que não são mais úteis, conpetem pela largura de banda para chegar ao receptor, o que pode piorar uma situação ruim. Isso faz com que o reparo de áudio seja grampeado e alongue o áudio, resultando em artefatos audíveis, muitas vezes na forma de tremulação.

Os relatórios desta seção não fazem distinção entre fluxos satisfatórios e satisfatórios. Considerando que o UDP é preferencial, os relatórios procuram o uso do TCP para compartilhamento de tela com base em áudio, vídeo e vídeo (VBSS). As tarifas de fluxo deficiente são fornecidas para ajudar a comparar a qualidade UDP versus TCP, para que você possa concentrar seus esforços em que o impacto é o mais alto. O uso do TCP é causado principalmente por regras incompletas do firewall. Para obter mais informações sobre as regras de firewall do Teams e do Skype for Business Online, consulte [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips).

> [!Important]
> Ter um [arquivo de compilação válido](#building-mapping) carregado é altamente recomendado para que você possa distinguir rapidamente dentro de fluxos externos ao examinar o uso do TCP.

> [!Note]
> O áudio, o vídeo e o VBSS são todos os preferenciais do UDP como transporte principal. A carga de trabalho de compartilhamento de aplicativos RDP usa apenas TCP.

#### <a name="tcp-usage"></a>Uso do TCP

Os relatórios TCP indicam o uso geral do TCP nos últimos sete meses. Todos os outros relatórios nesta seção se concentrarão na restrição de prédios e sub-redes específicos em que o TCP é mais comumente usado. Relatórios separados estão disponíveis para conferências e fluxos de duas empresas.

![Gráfico mostrando a porcentagem de fluxos de áudio que usam](media/qerguide-image-audiostreamswithtcp.png)
TCP_Figura 25 – fluxos de áudio com uso do TCP_


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

_Figura 26 – TCP versus UDP-conferência_

##### <a name="analysis"></a>Análise

Embora você queira que o uso do TCP seja o mais baixo possível, talvez veja um pouco de uso do TCP em uma implantação que não esteja íntegra. O TCP por si só não contribuirá com uma chamada ruim, portanto, as tarifas de fluxo são fornecidas para ajudar a identificar se o uso do TCP é um colaborador de baixa qualidade. 

#### <a name="tcp-investigations"></a>Investigações TCP

Nos modelos CQD fornecidos, navegue até os fluxos TCP por meio de relatórios de construção e sub-rede usando o modelo redes gerenciadas ou todas as redes. Para a finalidade da investigação do uso do TCP, o processo é o mesmo, então iremos nos concentrar na conferência aqui.

> [!IMPORTANT]
> Ter um [arquivo de compilação](#building-mapping) válido carregado é recomendado para que você possa distinguir rapidamente dentro de fluxos externos ao examinar o uso do TCP. 

> [!NOTE]
> Certifique-se de ajustar o filtro de ano do mês para o mês atual. Selecione **Editar**e ajuste **ano do mês** para salvar o novo mês padrão.                                  |

![Captura de tela do uso do TCP pelo prédio e pela sub-rede](media/qerguide-image-tcpstreams.png)

_Figura 27 – fluxos TCP por prédio e conferência_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você recebeu um alerta de diagnóstico "o tráfego UDP está sendo limitado, o que causa uma qualidade de baixa qualidade", concentre seus esforços de correção de TCP nessas sub-redes primeiro. O alerta identificou sub-redes em que o uso do TCP está afetando negativamente a qualidade da chamada.

##### <a name="remediation"></a>NAP

Esse relatório identifica construções e sub-redes específicas que contribuem para o volume do uso do TCP. Um relatório adicional também está incluído para identificar o Microsoft Relay IP que foi usado na chamada para ajudar a isolar regras de firewall ausentes. Concentre seus esforços de correção nos prédios que têm o maior volume de fluxos de TCP para melhorar o impacto.

A causa mais comum de uso do TCP são regras de exceção ausentes em firewalls ou proxies. Vamos falar sobre proxies na próxima seção, por isso, por ora, se concentrar em seus esforços nos firewalls. Ao usar o prédio ou a sub-rede fornecida, você pode determinar qual firewall precisa ser atualizado.


_Tabela 11 – orientação de correção para fluxos de TCP por meio de construção e sub-rede_

| NAP        | Orientação     |
|--------------------|--------------------------------------|
| Configurar o firewall | Verifique se [as portas e os endereços IP do Office 365](https://aka.ms/o365ips) estão excluídos do seu firewall. Para problemas de TCP relacionados à mídia, concentre seus esforços iniciais no seguinte:<ul><li>Verifique se as sub-redes de mídia do cliente 13.107.64.0/18 e 52.112.0.0/14 estão nas suas regras de firewall.</li><li>Portas UDP 3478 – 3481 são as portas de mídia necessárias e devem ser abertas, caso contrário, o cliente fará failback para a porta TCP 443.</li></ul> |
| Verificar             | Use a [ferramenta de avaliação de rede da Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar se há problemas de conectividade com endereços IP específicos do Office 365 e portas da compilação ou sub-rede afetada.    |

### <a name="http-proxy"></a>Proxy HTTP

Os proxies HTTP não são o caminho preferencial para estabelecer sessões de mídia, por uma infinidade de motivos. Muitos contêm recursos de inspeção de pacotes profundas que podem impedir que as conexões com o serviço sejam concluídas e apresentar interrupções. Além disso, praticamente todos os proxies forçam o TCP, em vez de permitirem UDP, o que é recomendado para a qualidade de áudio ideal.

Sempre recomendamos que você configure o cliente para se conectar diretamente ao Teams e aos serviços do Skype for Business. Isso é especialmente importante para tráfego baseado em mídia.


> [!IMPORTANT]
> Ter um [arquivo de compilação](#building-mapping) válido carregado torna mais fácil distinguir-se de forma adequada de fluxos de áudio externos ao analisar o uso de proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

O relatório de fluxo de proxy HTTP nesta seção do modelo é muito parecido com os relatórios TCP. Não verifica se as chamadas são ruins ou boas, mas se a chamada está conectada via HTTP.

![Captura de tela do relatório de fluxos de áudio que usam HTTP](media/qerguide-image-audiostreamswithhttp.png)

_Figura 28 – fluxos de áudio com uso de proxy HTTP_

##### <a name="analysis"></a>Análise

Você deseja ver a menor possibilidade possível de fluxos de mídia HTTP. Se você tiver fluxos que atravessam seu proxy, consulte sua equipe de rede para garantir que as exclusões adequadas estejam em vigor para que os clientes sejam direcionados diretamente para as equipes ou para as sub-redes do Skype for Business online.

Se você tiver apenas um proxy da Internet em sua organização, verifique as exclusões corretas de [intervalo de endereços IP e URLs do Office 365](https://aka.ms/o365ips). Se mais de um proxy da Internet estiver configurado em sua organização, use o sub-relatório HTTP para isolar qual construção ou sub-rede será afetada.

Para as organizações que não podem ignorar o proxy, certifique-se de que o cliente Skype for Business está configurado para se conectar corretamente quando ele estiver localizado atrás de um proxy, conforme descrito no artigo o [Skype for Business deve usar o servidor proxy para se conectar em vez de tentar direto conexão](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Investigações de proxy HTTP

Esse relatório identifica construções e sub-redes específicas que contribuem para o uso de HTTP.

> [!IMPORTANT]
> Ter um [arquivo de compilação](#building-mapping) válido carregado torna mais fácil distinguir-se de forma adequada de fluxos de áudio externos ao analisar o uso de proxy.

> [!NOTE]
> Certifique-se de ajustar o filtro de ano do mês para o mês atual. Selecione **Editar**e ajuste **ano do mês** para salvar o novo mês padrão.

![Captura de sreen de um relatório de uso do proxy HTTP por meio da construção e da sub-rede](media/qerguide-image-httpproxyusage.png)

_Figura 29 – uso do proxy HTTP por meio da construção e da sub-rede_

##### <a name="remediation"></a>NAP

[Recomendamos](proxy-servers-for-skype-for-business-online.md) que você sempre ignore proxies do Skype for Business e do Teams, especialmente tráfego de mídia. Os proxies não tornam o Skype for Business mais seguro, pois o tráfego já está criptografado. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Problemas como esses podem resultar em uma experiência negativa com áudio, vídeo e compartilhamento de tela, onde os fluxos em tempo real são essenciais.

A causa mais comum de uso de HTTP são as regras de exceção ausentes nos proxies. Ao usar o edifício ou a sub-rede fornecida, você pode determinar rapidamente qual proxy precisa ser configurado para o bypass de mídia.

Verifique se os [FQDNs do Office 365](https://aka.ms/o365ips) necessários estão na lista negra em seu proxy.

Para obter mais informações sobre como usar proxies com o Skype for Business Online e o Teams, consulte [Este artigo](proxy-servers-for-skype-for-business-online.md).

## <a name="endpoint-investigations"></a>Investigações de ponto de extremidade

Esta seção concentra-se nas tarefas para relatar as versões do cliente e o uso de dispositivos certificados. Os relatórios estão disponíveis para a estrutura de tópicos do uso de versões do cliente, tipo de cliente, dispositivos de captura e drivers (microfone), dispositivos de captura de vídeo e versões de fornecedor e driver de Wi-Fi.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia; no entanto, os métodos de investigação explicados abaixo ainda se aplicam. Consulte a descrição do relatório individual para obter mais informações.

### <a name="client-versions"></a>Versões do cliente

Os relatórios neste espaço se concentram em identificar as versões de cliente do Skype for Business em uso e seu volume relativo no ambiente.

> [!IMPORTANT]
> Atualmente, os clientes do teams são distribuídos e atualizados automaticamente por meio da rede de distribuição de conteúdo do Azure e serão mantidos em dia pelo serviço. As atividades de preparação e investigação do cliente não são aplicáveis ao Teams.

> [!Important]
> A menos que você exclua dados do participante federado, esses relatórios incluirão a telemetria do cliente a partir de pontos de extremidade federados. Para excluir pontos de extremidade federados, você deve adicionar um [filtro de consulta](#query-filters) para a segunda ID de locatário definida como a [ID de locatário](#tenant-id)da sua organização. Você também pode usar um filtro de [URL](#url-filter) para excluir a telemetria de participantes agrupados.

> [!NOTE]
> Certifique-se de ajustar o filtro de ano do mês para o mês atual. Selecione **Editar**e ajuste **ano do mês** para salvar o novo mês padrão.

![Captura de tela do relatório de cliente e dispositivos](media/qerguide-image-clientversionreport.png)

_Figura 30-relatório de versão do cliente_

#### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você recebeu um alerta de diagnóstico "as versões de cliente com desempenho desconhecido estão em uso", concentre-se em atualizar esses clientes primeiro. O alerta identificou que esses clientes estão afetando negativamente a qualidade da chamada. Você pode usar o relatório de dispositivos & cliente (mostrado acima) para ajudar a garantir que os clientes com problemas conhecidos não sejam mais atualizados.

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

-   [Informações de lançamento para atualizações do Office ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Histórico de atualizações do Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
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
> A menos que você exclua dados do participante federado, esses relatórios incluirão a telemetria do cliente a partir de pontos de extremidade federados. Para excluir pontos de extremidade federados, você deve adicionar um filtro de consulta para a **segunda ID de locatário** definida como a [ID de locatário](#tenant-id)da sua organização. Você também pode usar um filtro de [URL](#url-filter) para excluir a telemetria de participantes agrupados.

> [!NOTE] 
> Certifique-se de ajustar o filtro de ano do mês para o mês atual. Selecione **Editar**e ajuste **ano do mês** para salvar o novo mês padrão.

> [!Note]
> Você pode observar quando exibir este relatório de que vê o mesmo dispositivo informado várias vezes. Isso se deve à maneira como o dispositivo é relatado como reportado para CQD. Diferenças na localidade do hardware e do sistema operacional causam diferenças na maneira como os dados do dispositivo são relatados.

![Captura de tela do relatório de dispositivos (microfone)](media/qerguide-image-devicesmicrophone.png)

_Figura 31 – relatório de dispositivos (microfone)_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você recebeu um alerta de diagnóstico, os drivers de áudio estão causando quedas de chamadas, "concentre-se em corrigir esses drivers primeiro. O alerta identificou que drivers inválidos conhecidos estão causando chamadas para soltar e estão afetando negativamente a confiabilidade das chamadas. Você pode usar o relatório de microfone-drivers (mostrado acima), que é encontrado na seção de dispositivos cliente &, para ajudar com o processo.

##### <a name="remediation"></a>NAP

Normalmente, você precisará descobrir e fazer uma fase de descontinuação de dispositivos não certificados e substituí-los por dispositivos certificados. Algumas considerações ao analisar os relatórios do dispositivo incluem:

-   Os dispositivos em uso são certificados para o Teams e o Skype for Business? 
-   Você pode identificar os usuários de um dispositivo específico por meio da [análise de chamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Verifique se eles têm os drivers de dispositivo mais recentes e se o dispositivo não está conectado por meio de um hub USB ou de uma docking station. 
-   Quantas versões diferentes de vários drivers estão em uso? Eles estão sendo corrigidos regularmente? Garantir que os drivers de áudio, vídeo e Wi-Fi sejam corrigidos regularmente ajudarão a eliminá-los como uma fonte de problemas de qualidade e tornar a experiência do usuário mais previsível e consistente.

##### <a name="audio"></a>Áudio

A próxima tarefa é determinar o uso geral dos [dispositivos de áudio certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Recomendamos que pelo menos 80% de todos os fluxos de áudio usem um dispositivo de áudio certificado. Isso é melhor realizado ao exportar o relatório de dispositivos de microfone para o Excel para calcular o uso de dispositivos certificados ou aprovados. Geralmente, as organizações mantêm uma lista de todos os dispositivos aprovados, portanto, a filtragem e a classificação dos dados devem ser diretas.

##### <a name="video"></a>Vídeo

Os drivers de vídeo são importantes também para manter a atualização. Verificar se as placas de vídeo estão sendo corrigidas regularmente ajudarão a excluir drivers de vídeo como uma fonte de baixa qualidade para fluxos de vídeo. O uso de [dispositivos de vídeo certificados](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) ajudará a garantir uma experiência de usuário tranqüila e de alta qualidade. Os dispositivos de vídeo que dão suporte a codificação nativa H. 264 são preferenciais, para reduzir o uso da CPU durante videoconferência.

##### <a name="wi-fi"></a>Wi-Fi

Os drivers de Wi-Fi também precisam ser corrigidos em uma cadência regular e devem ser incluídos na estratégia de gerenciamento de patches. Muitos problemas de qualidade podem ser corrigidos mantendo drivers Wi-Fi atualizados. Para obter mais informações sobre como otimizar sua infraestrutura Wi-Fi, consulte [Este artigo sobre o planejamento de Wi-Fi](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>Anexo 

### <a name="office-365-network-connectivity-principles"></a>Princípios de conectividade de rede do Office 365

Antes de começar a planejar sua rede para a conectividade de rede do Office 365, é importante entender os princípios de conectividade para gerenciar com segurança o tráfego do Office 365 e obter o melhor desempenho possível. O artigo a seguir vai ajudá-lo a entender as orientações mais recentes para otimizar com segurança a conectividade de rede do Office 365:

[Princípios de conectividade de rede do Office 365](https://aka.ms/pnc)

### <a name="planning-for-wi-fi"></a>Planejamento para Wi-Fi

A abordagem da Microsoft para impulsionar a qualidade e a agilidade nas redes sem fio vem em três partes: planejamento final a fim, práticas recomendadas em implantação, manutenção e operações proativas. Este resumo da solução orienta você por meio desse processo para garantir uma experiência sem fio do Skype for Business sem fio de classe empresarial:

[Como garantir uma experiência sem fio para o Skype for Business de classe empresarial](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Guia de rede do Lync

Para obter mais informações detalhadas sobre os conceitos de rede do Teams e do Skype for Business e o raciocínio por trás da importância da qualidade, o [Guia de rede do Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) ainda é aplicável.

### <a name="network-performance-requirements"></a>Requisitos de desempenho de rede

A qualidade da mídia em tempo real (compartilhamento de áudio, vídeo e aplicativos) por IP é muito afetada pela qualidade da conectividade de rede de ponta a ponta. Para as equipes ideais ou a qualidade de mídia do Skype for Business, sua rede deve atender às seguintes métricas de desempenho de rede.

_Tabela 12-requisitos de desempenho de rede_

| Indicador                            | Cliente para Microsoft Edge           | Borda do cliente ao Microsoft Edge    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latência (de uma maneira)                 | \<50 ms                            | \<30 ms                            |
| Latência (RTT ou tempo de viagem de ida e volta) | \<100 ms                           | \<60 MS                            |
| Perda de pacote intermitente                 | \<10% durante qualquer 200-MS Interval   | \<1% durante qualquer 200-MS Interval    |
| Perda de pacote                       | \<1% durante qualquer intervalo de 15 segundos    | \<0,1% durante qualquer intervalo de 15 segundos  |
| Tremulação entre entradas do pacote       | \<30 ms durante qualquer intervalo de 15 segundos | \<15 MS durante qualquer intervalo de 15 segundos |
| Reordenação de pacotes                    | \<0, 5% de pacotes fora da ordem       | \<0, 1% de pacotes fora da ordem      |

Para obter mais informações, consulte [Este artigo sobre qualidade de mídia e desempenho de rede](https://aka.ms/performancerequirements) do Teams e do Skype for Business online.

### <a name="other-resources"></a>Outros recursos

#### <a name="building-data-file"></a>Criando arquivo de dados

-   [Ativar e usar o painel de qualidade da chamada para Microsoft Teams e Skype for Business Online](turning-on-and-using-call-quality-dashboard.md)

#### <a name="cqd-training"></a>Treinamento do CQD

-   <https://aka.ms/sof-cqd>

-   [Introdução ao](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) guia e workshop CQD

-   [Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Treinamento de análise de chamadas

-   [Apresentando a análise de chamadas](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar Análise de Chamada](set-up-call-analytics.md)

-   [Qual é a diferença entre a análise de chamadas e o painel de qualidade da chamada?](difference-between-call-analytics-and-call-quality-dashboard.md)

-   [Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

### <a name="call-analytics-support"></a>Suporte a análises de chamadas

-   Comunidade: [programa de visualização do Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

### <a name="devices"></a>Dispositivos

-   [Catálogos de soluções do Skype for Business para periféricos pessoais & PCs](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Relatórios de locatário

-   [Pacote de conteúdo de adoção do Office 365](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Análise de uso do Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Relatórios do Skype for Business Online](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Relatórios do Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
