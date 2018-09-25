---
title: Qualidade da experiência Revise o guia para equipes da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Guia para analisar o desempenho de mídia em tempo real for Microsoft Teams usando o painel de controle de qualidade de chamada (CQD).
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 264e3ae4573531cebf8723294f42ee66453bfa73
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013807"
---
# <a name="quality-of-experience-review-guide"></a>Qualidade da experiência Revise o guia

<!-- Note that this link to the Word doc is intentionally NOT the aka.ms/qerquide link -->Este guia é sobre a fase de unidade de valor para o Microsoft Teams e Skype para negócios Online. Você pode [baixar uma versão do Word](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) deste guia.

## <a name="introduction"></a>Introdução

Para que o maior impacto sobre como melhorar a experiência do usuário, as organizações precisam tornem operacional as principais áreas que são mostradas na figura a seguir. Áreas adicionais incluem identificando tarefas operacionais, estabelecimento de metas para métricas de qualidade, averiguar as métricas usar para medir o êxito organizacional e estreitando áreas de investigação conforme necessário.


![Áreas de chave para a qualidade da experiência do usuário incluem áudio, confiabilidade, pesquisas de usuário, dispositivos e clientes.] (media/qerguide-image-keyareas.png "Áreas de chave para a qualidade da experiência do usuário incluem áudio, confiabilidade, pesquisas de usuário, dispositivos e clientes.")

_Figura 1 - operacionais áreas de chave abordadas neste guia_

Continuamente avaliando e correção as áreas descritas neste guia, você pode reduzir seu potencial para afetar negativamente a qualidade da experiência dos usuários. A maioria dos problemas de experiência do usuário encontrados em uma implantação podem ser agrupados nas seguintes categorias:

-   Configuração de firewall ou proxy incompleta
-   Baixa cobertura de Wi-Fi
-   Largura de banda insuficiente
-   VPN
-   Versões de cliente inconsistentes ou desatualizadas e drivers
-   Dispositivos de áudio não otimizados ou internos
-   Sub-redes problemáticos ou dispositivos de rede

Através de planejamento adequado e design antes de implantar equipes ou Skype para Business Online, você pode reduzir a quantidade de esforço que serão necessários para manter experiências de alta qualidade.

Este guia se concentra no uso do Online do painel de controle de qualidade de chamada (CQD) como a ferramenta principal para relatar e investigar cada área, com uma ênfase especial para maximizar a adoção e o impacto de áudio. Todos os aprimoramentos feitos à rede para melhorar a experiência de áudio também diretamente traduzirá melhorias no compartilhamento de área de trabalho e de vídeo.

Para acelerar sua avaliação, [dois modelos CQD curated](https://aka.ms/qertemplates) são fornecidos: uma é para gerenciar todas as redes e o outro fosse filtrado para apenas gerenciadas redes (internos). Embora os relatórios de modelo de todas as redes são configurados para exibir informações de rede e de construção, eles ainda podem ser usados enquanto você trabalha em direção a coleta e carregamento de informações de construção. Carregar informações em CQD do edifício habilita o serviço aperfeiçoar os relatórios adicionando informações personalizadas de construção, rede e local enquanto distinguir interna do sub-redes externos. Para obter mais informações, consulte [mapeamento de criação](#building-mapping) mais adiante neste guia.

### <a name="intended-audience"></a>Público-alvo

Este guia destina-se a ser usado pelo parceiro e cliente participantes com funções como arquiteto/líder de colaboração, consultor, especialista da adoção do gerenciamento de alteração, ajuda/suporte de liderança de mesa, liderança de rede, liderança de área de trabalho e administrador de TI.

Este guia destina-se também a ser usado pelo champion(s) a qualidade designada. Para obter mais informações, consulte [a função campeão de qualidade](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar este guia, verifique se que você tem as [funções](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) de locatário adequadas atribuído para que você possa acessar CQD.

-   **Função Administrador Global do office 365:** Acessa todos os recursos administrativos no conjunto do Office 365 de serviços em seu plano, incluindo Skype para negócios.

-   **Skype para a função de administrador de negócios:** Configura Skype for Business para sua organização e é capaz de exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no Centro de administração do Office 365. Essa função é necessária, mesmo se você implantar apenas equipes.

Como alternativa, você pode atribuir a função a seguir para uma conta de usuário do Office 365 deseja permitir acesso a somente os recursos de relatório.

-   **Relata leitor:** Pode exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no Centro de administração do Office 365, qualquer relatórios do [pacote de conteúdo do Office 365 adoção](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)e relatórios CQD.

## <a name="what-is-quality"></a>Qual é a qualidade?

Ao discutir qualidade em equipes e Skype para os negócios, é importante definir o termo para atingir um entendimento comum. A qualidade, conforme definido aqui, é uma combinação de serviço métricas e experiência do usuário.

<!-- Note: need to update graphic-->
Métricas de serviço ![são compostas de taxa de fluxo de baixa, confiabilidade, pontos de extremidade/dispositivos e versões do cliente. A experiência do usuário é formada pelo percepção do usuário da qualidade do serviço.] Métricas de serviço (media/qerguide-image-whatisquality.png "são compostas de taxa de fluxo de baixa, confiabilidade, pontos de extremidade/dispositivos e versões do cliente. A experiência do usuário é formada pelo percepção do usuário da qualidade do serviço.")

_Figura 2: o que há de qualidade?_

### <a name="service-metrics"></a>Métricas de serviço

Métricas do serviço consistem em métricas específicas baseados no cliente. Durante cada chamada, o cliente coleta informações de telemetria sobre a chamada e envia um relatório no final de cada chamada que possa ser acessado posteriormente através de CQD ou [Chamada de análise](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Esses indicadores incluem:

-   Taxa de fluxo ruim
-   Taxa de falha de instalação
-   Taxa de falha de recebimento


#### <a name="poor-stream-rate"></a>Taxa de fluxo ruim

A taxa de fluxo ruim (PSR) representa a porcentagem geral da organização dos fluxos com baixa qualidade. Essa métrica destina-se para realçar áreas onde sua organização pode se concentrar esforço para ter um impacto mais forte em direção a redução desse valor e aprimorando a experiência do usuário, razão pela qual [redes gerenciadas](#managed-vs-unmanaged-networks) são o foco principal ao olhar PSR. Os usuários externos são muito importantes, mas difere de investigação em uma base organizacional. Considerar o fornecimento de práticas recomendadas para usuários externos e investigar efetuar chamadas externas independentemente do geral da empresa.

A medida real em CQD varia por carga de trabalho, mas para os fins da qualidade da experiência revisão podemos enfocam principalmente a medida _Percentual de áudio ruim_ . PSR é composto de cinco médias de métricas de rede descritas na tabela a seguir. Para um fluxo ser classificadas como insatisfatória, apenas uma métrica deve exceder o limite definido. Para obter mais informações sobre o processo de classificação do fluxo, consulte [Este artigo](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> CQD fornece o "ruim devidos à..." medidas para melhor compreendam qual condição causada stream a serem classificadas como inválida.


_Tabela 1 - métricas de serviço ruim_

| Média de métrica     | Descrição     | Experiência do usuário |
|-------------|-----------------|-----------------|
| Tremulação \>30 ms        | Esta é a média alteração em atraso entre pacotes sucessivos. Equipes e Skype para negócios podem se adaptar alguns níveis de tremulação por meio de armazenamento em buffer. É somente quando a tremulação excede o armazenamento em buffer que um participante avisos os efeitos de variação.      | Os pacotes que chegam em diferentes velocidades causarão voz do alto-falante som robótica.   |
| Taxa de perda de pacote \>10% ou 0,1        | Geralmente, isso é definido como uma porcentagem dos pacotes que são perdidos. Perda de pacotes diretamente afeta a qualidade do áudio — de pequeno, indivíduo pacotes perdidos que têm quase sem afetar a perdas intermitentes em frente e verso que causa áudio Recortar completamente.     | Os pacotes sendo capitular e não chegada a seu destino pretendido causarão lacunas na mídia, resultando em palavras e sílabas perdidas e entrecortada vídeos e compartilhamento. |
| Tempo de ida e volta \>500 ms        | Este é o tempo que leva para obter um pacote IP do ponto A ponto b e voltar para a ponto. Esse atraso de propagação de rede é associado à distância física entre os dois pontos e a velocidade da luz e inclui uma sobrecarga adicional tomada por vários dispositivos no caminho de rede.      | Os pacotes demorando muito para chegar ao seu destino causam um efeito de walkie-talkie.   |
| Média de degradação NMOS \>1.0         | Média de degradação da [Pontuação de opinião média da rede (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) para o fluxo. Representa o quanto a tremulação e perda de rede afetou a qualidade do áudio recebido que causou o NMOS soltar por mais de um ponto. | Isso é uma combinação de tremulação, perda de pacotes, e — a um grau menor — aumento do tempo de ida e volta. O usuário pode estar apresentando uma combinação desses sintomas.   |
| Taxa média de amostras escondidas \>7% ou 0,07 | Taxa média do número de quadros de áudio com amostras escondidas geradas pelo reparo para o número total de quadros de áudio de perda de pacotes. Uma amostra de áudio escondida é uma técnica costumava suave check-out a transição repentina que geralmente seria causada por pacotes de rede capitular.      | Valores altos indicam que significativo níveis de ocultação perda foram aplicados e resultou em áudio distorcido ou perdido.     |

#### <a name="setup-failure-rate"></a>Taxa de falha de instalação

A taxa de falha de instalação, também é conhecida como a medida de _Porcentagem de falha de configuração de chamada Total_ em CQD, é o número de fluxos de onde o caminho de mídia não pôde ser estabelecido entre os pontos de extremidade no início da chamada.

Isso representa qualquer fluxo de mídia que não pôde ser estabelecido. Devido a gravidade do impacto sobre a experiência do usuário medida aqui, o objetivo é reduzir este valor como como próximos de zero possível. Um valor alto para essa métrica é mais comuns em novas implantações com regras de firewall incompleto do que uma implantação desenvolvido, mas ainda é importante observar regularmente.

Essa métrica é calculada de acordo com o número total de fluxos que falhou ao configurar divididos pelo número total de fluxos que enviou um registro de detalhes da chamada bem sucedida (CDR):

-   **Taxa de falha de instalação** = chamada Total configuração contagem de Stream com falha / contagem de fluxo de CDR de Total disponível

#### <a name="drop-failure-rate"></a>Taxa de falha de recebimento

A taxa de falha de recebimento, também é conhecida como a medida de _Chamada queda falha porcentagem Total_ em CQD, é a porcentagem de fluxos estabelecidas com êxito, onde o caminho de mídia não foi encerrada normalmente.

Isso representa qualquer fluxo de mídia que terminou inesperadamente. Embora o impacto disso não tão grave como um fluxo com falha para configurar, negativamente afetará a experiência do usuário. Quedas de mídia repentinas e frequentes não só podem ter um impacto grave na experiência do usuário, eles resultam na necessidade de usuários para se conectar novamente, resultando em uma perda de produtividade.

A métrica é calculada de acordo com o número total de fluxos de capitular dividido pela contagem total de fluxos configurado com êxito:

-   **Taxa de falha de drop** = chamada Total abandonada Stream contagem / instalação chamada Total de contagem de fluxo foi bem-sucedida

### <a name="define-your-target-metrics"></a>Definir seus métricas de destino

Esta seção discute algumas das principais métricas serviço que usamos para avaliar como serviços apresentem integridade. Continuamente avaliando e orientando os esforços para manter essas métricas abaixo seus destinos definidos, você vai ajudar a garantir que seus usuários experimentam a qualidade da chamada consistente e confiável. Para começar, as metas a seguintes são fornecidas.

_Tabela 2 - métricas de avaliação de integridade de destino principais_
<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo de rede</th><th rowspan="1">Destinos de qualidade</th><th colspan="2">Alvos de confiabilidade</th></tr>
<tr><th>Fluxo de áudio de baixa taxa</th><th>Taxa de falha de instalação</th><th>Taxa de falha de recebimento</th></tr>
<tr><td rowspan="2">**All**</td><td>Interno</td><td>% de 2.0</td><td>0,5%</td><td>% de 2.0</td></tr>
<tr><td>Geral</td><td>% de 3.0</td><td>% de 1.0</td><td>% de 3.0</td></tr>
<tr><td rowspan="5">**Conferências**</td><td>Interno</td><td>% de 2.0</td><td>0,5%</td><td>% de 2.0</td></tr>
<tr><td>Com fio interno</td><td>% de 1.0</td><td>0,5%</td><td>% de 1.0</td></tr>
<tr><td>Wi-Fi 5 GHz interno</td><td>% de 1.0</td><td>0,5%</td><td>% de 1.0</td></tr>
<tr><td>Wi-Fi 2,4 GHz interno</td><td>% de 4.0</td><td>0,5%</td><td>% de 2.0</td></tr>
<tr><td>Geral</td><td>% de 2.0</td><td>0,5%</td><td>% de 3.0</td></tr>
<tr><td rowspan="4">**P2P**</td><td>Interno</td><td>% de 2.0</td><td>0,5%</td><td>% de 2.0</td></tr>
<tr><td>Com fio/Wi-Fi 5 GHz interno</td><td>% de 1.0</td><td>0,5%</td><td>% de 1.0</td></tr>
<tr><td>Com fio/Wi-Fi 5 GHz geral</td><td>% de 2.0</td><td>% de 1.0</td><td>% de 1.0</td></tr>
<tr><td>Geral</td><td>% de 2.0</td><td>% de 1.0</td><td>% de 3.0</td></tr>
</table>


É importante discutir e definir as metas da sua organização para atender aos seus objetivos de negócios.

### <a name="user-experience"></a>Experiência do usuário

Analisando a experiência do usuário é mais arte do que ciência, porque as métricas coletadas aqui sempre não significa que há um problema com a rede ou serviço, mas em vez disso, elas simplesmente indicam que o usuário percebe um problema. A Microsoft oferece um mecanismo de pesquisa interno — conhecido como taxa meu chamada (RMC) — para ajudar a estimar a experiência geral do usuário. RMC ajudarão você a responder às seguintes perguntas da perspectiva dos usuários:

-   Saber como usar a solução?
-   É a solução fáceis de usar e intuitiva e oferece suporte a minhas necessidades de comunicação diárias?
-   A solução Ajude-me trabalho?
-   Qual é a minha percepção geral da solução?
-   Posso usar a solução em qualquer ponto no tempo, independentemente de onde estou?
-   É possível configurar e manter uma chamada?

#### <a name="rate-my-call"></a>Classifique minha chamada 

Taxa meu chamada (RMC) está integrado nos equipes e Skype para negócios e é automaticamente configurado para ser exibido para o participante depois que um em cada 10 chamadas ou 10 por cento. Este breve pesquisa pede ao usuário classificar a chamada e fornecer um contexto de pouca para por que a qualidade da chamada pode ter sido ruim. Uma classificação de um ou dois é considerada ruim, três ou quatro é bom e cinco é excelente. Embora seja um pouco de um indicador à demora, essa é uma métrica útil para descobrir problemas que métricas de serviço podem perder.

> [!Note]
> Até que os usuários são instruídos para responder às pesquisas RMC, oferecendo uma boa indicação além das respostas mal, normalmente volte como predominantemente negativo. A maioria dos usuários responder somente quando a qualidade da chamada é ruim. Dessa forma, seus relatórios RMC podem ser enviesados até o lado ruim mesmo enquanto métricas de serviço estão funcionando bem.

Você pode usar CQD para reportar sobre as respostas do usuário RMC e relatórios de exemplo estão incluídos no modelo CQD. No entanto, eles não são abordados em detalhes neste guia. Para obter mais informações sobre o RMC Skype para Business Online e orientações para ensinar os usuários fornecer respostas RMC úteis, consulte [esta postagem de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Preparação de clientes e dispositivos

Você precisa de uma estratégia sólida de clientes e dispositivos para ajudar a garantir que os usuários tenham uma experiência de usuário consistente e positivo. Cada estratégia de preparação de unidade de alguns princípios-chave.

##### <a name="client-readiness"></a>Preparação do cliente

Uma estratégia de preparação de cliente forte garante que os usuários estão executando a versão mais recente do cliente ao mesmo tempo aproveitando a melhor experiência possível. Microsoft rotineiramente patches do Skype para clientes corporativos; garantir que você o mantenha atualizado em seu ambiente é vital para o sucesso geral. Também é importante que se lembrar de rede de patch, vídeo, USB e drivers de áudio, porque eles normalmente estão ignorados e podem afetar a experiência do usuário. Considere a adição de vídeo de rede, Wi-Fi, USB e os drivers de áudio para o seu processo de gerenciamento de patches atual.

Recomendamos que você não permita que as versões de cliente se encaixam por mais de seis meses. Se você estiver usando o Office Click-to-Run, você estiver já sendo mantidos atualizados pelo serviço. Use as [versões de cliente](#client-versions)incluídos, conforme descrito mais adiante neste guia, para ajudá-lo com esse processo. Você também pode aproveitar os relatórios de exemplo de taxa Minhas chamadas para aumentar ainda mais a sua estratégia de preparação de cliente.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Em virtude disso, investigação atividades e preparação de cliente não se aplicam às equipes.


##### <a name="device-readiness"></a>Preparação de dispositivo

Sem uma estratégia de única pode afetar a experiência do usuário mais de sua estratégia de preparação de dispositivo. A maioria das organizações são feliz remover dispositivos desnecessários (por exemplo, telefones de mesa ou outros dispositivos de áudio dedicados) de usuários, e isso é geralmente uma justificativa comercial de núcleo para alternar para equipes ou Skype para negócios. No entanto, dessas organizações mesmas às vezes hesite para fornecer dispositivos de substituição, mesmo se esses dispositivos são baratos. Moderna laptops e PCs, porém equipados com interna microfone e alto-falante, não são otimizadas para empresarial voz sobre IP (VoIP). Isso geralmente cria uma experiência ruim para todos os participantes, especialmente se o alto-falante está em um ambiente com ruído. Programa de certificação da Microsoft dispositivo garante que, quando um usuário participa de uma chamada telefônica usando qualquer dispositivo certificado para equipes ou Skype for Business, ele produzirá uma experiência que é superior a usar um dispositivo não certificados. 

Sempre, recomendamos que equipes e Skype para usuários comerciais usam um fone de ouvido certified ou alto-falante ao participar de uma chamada de voz pelo cliente de desktop. Para obter mais informações sobre dispositivos de certificados da Microsoft, revise estes artigos sobre o [programa de certificação](/SkypeForBusiness/certification/overview) e exibir o [Catálogo de soluções de parceiro](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Use o [relatório de dispositivos](#devices), descrito mais adiante neste guia, para obter ajuda com o gerenciamento de seus dispositivos.


### <a name="categories-of-quality"></a>Categorias de qualidade

O sucesso do operacionalização de uma implantação de alta qualidade e confiável depende da sua rigor operacionais de construção. Especificamente, prestar bastante atenção em três categorias ilustrado na figura a seguir; Estes são o foco deste guia:

-   **Rede:** Qualidade de áudio com foco na métrica de taxa de fluxo ruim (PSR), o uso TCP, sub-redes com e sem fio e identificando o uso de proxies HTTP e VPN.

-   **Pontos de extremidade:** Dispositivos de áudio e versões do cliente (Skype para negócios apenas).

-   **Gerenciamento de serviços:** Essa categoria consiste em duas seções:

    -   A primeira é responsabilidade da Microsoft para gerenciar e manter as equipes e Skype para serviços corporativos Online.

    -   Segundo são tarefas de que sua organização deve gerenciar para garantir acesso confiável ao serviço, atualizando informações de criação e manutenção de firewalls para novos endereços IP do Office 365 infrastructure for adicionada ao serviço.

![As categorias de qualidade em uma organização: serviço de gerenciamento, pontos de extremidade e a rede.] (media/qerguide-image-categories.png "As categorias de qualidade em uma organização: serviço de gerenciamento, pontos de extremidade e a rede.")

_Figura 3 - críticas categorias para equipes e Skype para implantação Business Online_

O gráfico a seguir descreve as tarefas que você deve executar para cada categoria. Recomendamos que você execute essas tarefas uma vez por semana, no mínimo.

Na primeira vez que você executar essas tarefas levarão pouco mais do que as iterações subsequentes, pois muitas dessas categorias exigem que você valide suas configurações de implantação. Depois que você tiver obtido o estado desejado atendendo os destinos que você definiu, execução dessas tarefas ajudará você manter esse estado.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Lista de tarefas semanais por categoria de qualidade] (media/qerguide-image-tasks.png "Lista de tarefas semanais por categoria de qualidade")

#### <a name="service-management-tasks"></a>Tarefas de gerenciamento de serviço

Em um mundo primeiro nuvem, você deve executar algumas tarefas de gerenciamento de serviço para manter as experiências do usuário de alta qualidade. Essas tarefas variam de garantir que não há largura de banda suficiente para alcançar o serviço sem links de internet, validando que qualidade de serviço (QoS) de saturação é no lugar em todas as áreas de rede gerenciada, e — finalmente — permanecendo na parte superior [intervalos de IP do Office 365 em firewalls](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Tarefas de rede

Há duas categorias de tarefas de rede: qualidade e confiabilidade. Confiabilidade enfoca medindo a capacidade do usuário para fazer chamadas com êxito e permanecem conectadas. Qualidade enfoca a telemetria agregada enviada para equipes e Skype para Business Online pelo cliente do usuário durante a chamada e depois que ela for encerrada. 

Dado o impacto crítico que confiabilidade tem sobre a experiência do usuário, é importante começar a avaliar e investigando dessas métricas antes de começar em qualidade. 

#### <a name="endpoints-tasks"></a>Tarefas de pontos de extremidade

A principal tarefa nesta categoria está validando a quais versões do cliente estiver executando o Skype para negócios em compilações da área de trabalho do últimos seis meses, para garantir que os usuários estão obtendo o benefício das otimizações contínuas feitas do Skype para o cliente de desktop de negócios. Além disso, isso simplifica as tarefas de gerenciamento de cliente geral e fornece uma experiência de usuário consistente.

A área de importante é quais dispositivos estão predominantes em sua implantação de monitoramento e orientando o uso de dispositivos de certificados para oferecer a melhor experiência de usuário.


> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.

## <a name="cqd-basics"></a>Noções básicas CQD

Esta seção descreve os conceitos básicos sobre como trabalhar com CQD. Orientação é fornecida para os seguintes tópicos:

-   O que é CQD?
-   Expectativas usando CQD
-   Localizando sua ID de Inquilino
-   Relatórios em equipes da Microsoft versus Skype para negócios
-   Primeiro versus segunda classificações
-   Medidas, dimensões e filtros
-   Fluxos de versus chamadas
-   Chamadas boas, ruins e não classificadas
-   Sub-redes comuns

Para obter mais aprofundado treinamento e recursos, consulte o [Apêndice](#other-resources).

### <a name="what-is-cqd"></a>O que é CQD?

Use o painel de qualidade de chamada (CQD) para obtém ideias sobre a qualidade das chamadas feitas por meio de equipes e Skype para serviços corporativos. CQD foi projetado para ajudar Skype para os administradores corporativos e as equipes e os engenheiros de rede otimização a rede e acompanhe de perto na qualidade, confiabilidade e a experiência do usuário. CQD analisa telemetria agregação para uma organização inteira onde padrões gerais podem se tornar aparentes, permitindo que a equipe fazer avaliações informadas e planejar remediação atividades para maximizar o impacto. CQD fornece relatórios de métricas que fornecem percepção qualidade geral, a confiabilidade e a experiência do usuário.

> [!Note]
> CQD não contém informações de identificação pessoal (PII). PII é informações que podem ser usadas por conta própria ou com outras informações para identificar, entre em contato ou localizar uma única pessoa ou para identificar um indivíduo em contexto.

Este guia o ajudará em Noções básicas sobre os principais conceitos do CQD para ajudar a maximizar o impacto que você pode fazer em melhorar a experiência de seus usuários com equipes ou Skype para Business Online. Recursos CQD adicionais podem ser encontrados no [Apêndice](#other-resources).

### <a name="expectations-using-cqd"></a>Expectativas usando CQD

CQD, embora útil para analisar tendências e sub-redes, nem sempre fornece uma causa específica para um cenário específico. É importante entender isso e definir a expectativa correta ao usar CQD:

-   CQD não fornecerá a causa raiz para cada cenário.
-   CQD não contém fluxos de sistema telefônico ou conferências de áudio.
-   CQD chamará áreas para uma investigação detalhada com base nos tendências.
-   CQD não contém qualquer PII.

### <a name="report-editions"></a>Edições de relatório

Há duas edições do relatório no CQD Online: Resumo e detalhado. Use o menu suspenso localizado na barra de ferramentas azul na parte superior da tela para abrir uma edição de relatório. O nome da edição relatório selecionado é exibido na parte superior da tela.

-   Relatórios de resumo são estáticos e não podem ser editados, exportado ou baixado. 
-   Relatórios detalhados são totalmente personalizáveis e podem ser baixados para um arquivo CSV, exportado ou clonada.

Para obter uma descrição completa da diferença entre as duas edições, consulte [Este artigo](turning-on-and-using-call-quality-dashboard.md).

![Menu suspenso com relatórios de resumo selecionadas](media/qerguide-image-reportcategories.png)

_Figura 4 - categorias de relatório CQD_

Os relatórios de resumo são divididos em quatro categorias:

-   **Relatórios de resumo do** foco na análise de tendências de qualidade com diariamente, mensalmente e os relatórios de tabela para ajudá-lo a identificar sub-redes com baixa qualidade. Esta é a página de aterrissagem padrão quando você entra pela primeira vez CQD online.
-   **Relatórios de Location-Enhanced** foco na análise de tendências de qualidade com base nas informações de local. Para usar esses relatórios, você deve ter carregado um arquivo de construção.
-   **Relatórios de confiabilidade** foco na análise de tendências de confiabilidade para (VBSS) de compartilhamento de tela de áudio, vídeo, com base em vídeo e compartilhamento de aplicativo.
-   **Relatórios de qualidade de experiência** são uma versão "reduzida" dos modelos de QER detalhadas, concentrando-se nas áreas principais para analisar a confiabilidade e a qualidade do áudio.

### <a name="report-types"></a>Tipos de relatório

Você pode escolher entre dois tipos de relatórios no CQD, dependendo de como você deseja exibir os dados. Embora este guia não aborda as especificações de criação de um tipo de relatório sobre a outra, os modelos de QER CQD fornecem uma mistura de relatórios de gráfico e tabela personalizáveis para uso:

-   Relatórios de gráfico criar gráficos de barras gráficos para representar os dados em um formato visual. Relatórios de gráfico melhor são usados para visualizar os dados em um período de tempo determinado.
-   Relatórios de tabela são úteis para olhando dimensões e medidas individuais ao exportar os relatórios para arquivos CSV para manipulação no Microsoft Excel.

### <a name="tenant-id"></a>ID do inquilino

Alguns relatórios CQD exigem a inclusão de um filtro para sua ID de Inquilino. Devido a maneira como CQD agrega os dados de telemetria participantes federada é incluída. Embora isso sejam valioso ao analisar tendências, relatórios de clientes e dispositivos exigem que você filtrar dados para um locatário específico a serem excluídas telemetria participantes federada. Se você não souber seu ID do inquilino, você pode usar um dos métodos a seguir para localizá-lo.

> [!Note]
> Esses métodos exigem as seguintes permissões:<ul><li>Função de administrador global</li><li>Skype para a função de administrador de negócios</li></ul>

#### <a name="azure-portal"></a>Portal do Azure

1.  Logon no portal do Microsoft Azure:<https://portal.azure.com>

2.  Selecione o **Azure Active Directory**.

3.  Em **Gerenciar**, selecione **Propriedades**. A ID do inquilino é mostrada na caixa **ID do diretório** .

#### <a name="azure-powershell"></a>Azure PowerShell

1.  [Instale o módulo de gerenciamento de serviço do Microsoft Azure PowerShell](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2.  Abra uma janela de comando do Azure PowerShell e execute o seguinte script, inserir suas credenciais do Office 365, quando solicitado: 

  ```
  Login-AzureRmAccount
  ```

3.  A ID do inquilino está listada na saída.

#### <a name="skype-for-business-online-admin-center"></a>Skype para negócios Online Admin Center

1.  Vá para <https://portal.office.com>.

2.  Entrar com sua conta organizacional do administrador de locatário.

3.  Selecione **Skype para negócios** sob **Centros do administrador**.

4.  A ID do inquilino está listada como **ID da organização** , na página de boas-vindas.

#### <a name="skype-for-business-online-using-powershell"></a>Skype para negócios Online usando o PowerShell

1.  [Configurar o computador para o Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2.  Execute o seguinte comando:

  ```
  (Get-cstenant).tenantid
  ```

3.  A ID do inquilino é exibida como um GUID.

### <a name="teams-vs-skype-for-business"></a>As equipes versus Skype para negócios

CQD pode relatar equipes e Skype para telemetria de negócios. No entanto, pode haver ocasiões em que você deseja desenvolver um relatório a ser analisado telemetria de equipes separada do Skype para negócios.

#### <a name="summary-reports"></a>Relatórios de resumo

Para modificar a página relatórios de resumo a ser analisado apenas equipes ou Skype para negócios, selecione o menu suspenso de **Filtro de produto** da parte superior da tela e selecione o produto desejado.

![Menu suspenso mostrando a opção de filtragem de relatórios CQD por carga de trabalho](media/qerguide-image-productfilter.png)

_Figura 5 - Selecione um filtro de produto_

#### <a name="detailed-reports"></a>Relatórios detalhados

Para filtrar todos os relatórios detalhados, na barra de tarefas do navegador, acrescente o seguinte ao final da URL:

```
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Exemplo:**

```https://cqd.lync.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Para obter mais informações sobre filtros de URL, consulte [relatórios de filtragem](#filtering-reports) mais adiante nesta seção.

Para filtrar um relatório detalhado individual, adicione o filtro ``Is Teams`` ao relatório e definido para True ou False. Para obter mais informações, consulte [relatórios de edição](#editing-reports) , mais adiante nesta seção.

![Adicione um filtro a um relatório detalhado.](media/qerguide-image-addteamsfilter.png)

_Figura 6 - adicionando um filtro de Teams da Microsoft a um relatório_


### <a name="managed-vs-unmanaged-networks"></a>Recursos gerenciados versus redes não gerenciados

Por padrão, todos os pontos de extremidade CQD são classificados como externa. Assim que um arquivo de construção é lançado, começamos a olhar sobre os dados de ponto de extremidade gerenciado. Conforme discutido anteriormente, redes em CQD são definidos como:

-   Uma _rede gerenciada_, geralmente conhecido como internos ou dentro, podem ser influenciada e controlados pela organização. Isso inclui LAN interna, WAN remoto e VPN.
-   Uma _rede não gerenciada_, geralmente conhecido como externa ou fora, não pode ser influenciada ou controlado pela organização. Um exemplo de uma rede não gerenciada é uma rede de hotel ou aeroporto.

### <a name="dimensions-measures-and-filters"></a>Medidas, dimensões e filtros

Uma consulta CQD bem formada contém todas as três dos parâmetros a seguir:

-   **Dimensão:** Como eu desejo os dados de tabela dinâmica.

-   **Medida:** O que eu quero a ser relatado no.

-   **Filtro:** Como eu desejo reduzir o conjunto de dados a consulta retorna.

Outra maneira de analisar isso é que uma _dimensão_ é a função de agrupamento, uma _medida_ é os dados que estou interessado em e um _filtro_ é como eu quiser restringir os resultados para aqueles que são relevantes à minha consulta.

Um exemplo de uma consulta bem formado é **ruim fluxos de Mostrar-me [medem] pela sub-rede [Dimension] para construção 6 [filtro]**. Para obter mais informações, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Primeiro versus segundo 

Muitas das dimensões e medidas em CQD são classificadas como primeira ou segunda. CQD não usa os campos de chamador/receptor — eles tiverem sido renomeado _primeiro_ e _segundo_ porque há etapas intermediárias entre o chamador e o receptor. A seguinte lógica determina qual ponto de extremidade envolvidos rotulado como primeiro:

-   **Primeiro** sempre será um ponto de extremidade do servidor (servidor de conferência, o servidor de mediação e assim por diante) se um servidor que está envolvido na chamada ou stream.

-   **Segundo** sempre será um ponto de extremidade do cliente, a menos que o stream está entre dois pontos de extremidade do servidor.

-   Se ambos os pontos de extremidade são do mesmo tipo, a escolha do qual é a primeira é baseada em ordem interna da categoria de agente de usuário. Isso assegura que a ordenação seja consistente.

Para obter mais informações sobre como determinar o ponto de extremidade de primeiro ou segundo quando eles estão ambos os mesmos, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream versus chamada

Você precisa entender a diferença entre uma chamada e um stream adequadamente escolher quais dimensões ou medidas você vai ser observando em CQD. Embora o foco principal do CQD em fluxos, medidas baseado em chamada também estão disponíveis.

-   **Stream:** Um _fluxo_ existirá apenas dois pontos de extremidade. Há apenas um fluxo para cada direção e dois fluxos são exigidos para a comunicação. Fluxos são úteis para investigar os prédios, redes ou sub-redes. Em alguns casos, a chamada e stream são usados em nome de medição (por exemplo, fluxo de instalação chamada ou chamada ignorados Stream). Eles ainda são classificados como fluxos.

-   **Chamar:** Uma _chamada_ é um agrupamento de todos os fluxos de todos os participantes. Consiste em uma chamada — no mínimo — dois fluxos. Uma única chamada terá pelo menos dois pontos de extremidade, cada um com um mínimo de um stream.

Para obter orientação adicional sobre a dimensão ou medida fizer referência a uma chamada ou um stream, consulte [dimensões e medidas disponíveis no CQD](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Chamadas boas, ruins e não classificadas

Uma chamada é categorizada por como BOM, baixa ou não classificados. Vamos falar sobre cada uma em mais detalhes um pouco.

-   **BOM ou ruim:** Uma chamada boa ou ruim consiste em uma chamada que contém um conjunto completo de métricas de serviço, para o qual um relatório de QoE completo foi gerado e recebido pelo serviço. Determinar se um fluxo é bom ou ruim está descrito [neste guia](#poor-stream-rate).

-   **Não classificados:** Um fluxo não classificado não contém um conjunto completo de métricas de serviço. Eles podem ser chamadas curtas — geralmente menor que 60 segundos — onde não puderam ser computadas médias e um relatório de QoE não foi gerado. O motivo mais comum de chamadas a ser não classificados é que houve pouco ou nenhum utilização de pacotes. Um exemplo disso seria um participante que ingressa em uma reunião em mudo e nunca fala. O participante está recebendo, mas não transmitir mídia. Sem mídia sendo transmitida, não haver qualquer métricas disponíveis para CQD usar para classificar o fluxo de mídia de saída do ponto de extremidade.

Para obter mais informações sobre o processo de classificação do fluxo, consulte [Este artigo](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Sub-redes comuns

Sub-redes comuns estão sub-redes privadas específicas que são usados pelo hotéis, redes domésticas, pontos de acesso e áreas semelhantes. Essas sub-redes são difíceis de triagem devido ao seu uso amplo. Se sua organização usa uma dessas sub-redes comuns, recomendamos que você mova desta rede para outra sub-rede. Isso tornará o relatório mais fácil no CQD. Quando observado, relatórios do modelo de todas as redes foram configurados para excluir essas sub-redes para eliminá-las como uma fonte de baixa qualidade. Sub-redes comuns estão definidos abaixo; o impacto variam de acordo com a organização.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Ao investigar a uma rede gerenciada que usa uma sub-rede comuns, você precisará usar a dimensão de segunda IP Local reflexiva para sub-redes de grupo. Essa dimensão contém o endereço IP público do ponto de extremidade.

## <a name="cqd-online"></a>CQD Online

Esta seção descreve os conceitos básicos do acessando CQD. Orientação é fornecida para os seguintes tópicos:

-   Acessando CQD online
-   Introdução ao CQD
-   Edição de relatórios no CQD
-   Filtragem de relatórios no CQD
-   Importando os relatórios no CQD

Para obter mais aprofundado treinamento e recursos, consulte o [Apêndice](#other-resources).

### <a name="access-cqd-online"></a>Acesso CQD Online

Você pode acessar CQD uma destas três formas:

-   Vá para <https://cqd.lync.com>.

-   Vá para **equipes da Microsoft & Skype para Business Admin Center** e selecione o link para CQD, conforme mostrado na ilustração a seguir.

![No painel de navegação esquerdo, o link para o painel de controle de qualidade de chamada está selecionado.] (media/qerguide-image-mopo.png "No painel de navegação esquerdo, o link para o painel de controle de qualidade de chamada está selecionado.")

_Figura 7 – acessando CQD através do Skype para Business Admin Center & equipes da Microsoft_

-   Vá até o herdado **Skype para centro de administração de negócios** > **Ferramentas**e selecione o link para CQD, conforme mostrado na ilustração a seguir.

![Ferramentas está selecionado no painel de navegação esquerdo e o link para CQD está selecionado no painel principal.] (media/qerguide-image-legacyui.png "Ferramentas está selecionado no painel de navegação esquerdo e o link para CQD está selecionado no painel principal.")

_Figura 8 - acessando CQD através do Skype para centro de administração de negócios_


### <a name="getting-started"></a>Introdução

Quando você procurar primeiro CQD, você verá a página relatórios de resumo. A maioria dos relatórios descritos neste guia são relatórios detalhados personalizados. Para começar a usar os relatórios detalhados, selecione **Relatórios de resumo** na parte superior da página e escolha **Relatórios detalhados**.

![Diferentes tipos de relatórios que estão disponíveis no CQD](media/qerguide-image-choosereports.png)

_Figura 9 - navegando para relatórios detalhados_

A página de relatórios detalhados no CQD se parece com a ilustração a seguir.

![Diferentes elementos que compõem um relatório detalhado.](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![um] (media/qerguide-image-callout1.png "um") | O painel Resumo mostra contexto para o conjunto de relatório que aparece à direita. |
| ![dois] (media/qerguide-image-callout2.png "dois") | Você pode selecionar **Editar** no painel Resumo para definir propriedades de nível de relatório – (incluindo a altura do eixo y) e importar novos modelos. |
| ![três] (media/qerguide-image-callout3.png "três") | Navegação estrutural ajuda os usuários a identificar sua localização atual na hierarquia do conjunto de relatório. |
| ![quatro] (media/qerguide-image-callout4.png "quatro") | Relatórios que têm filhos relatórios são mostrados com um link azul. Selecionando o link, você pode analisar os relatórios de filho. |

_Figura 10 - página de relatórios detalhados_

Aponte para gráficos de barras e linhas de tendência no relatório para exibir valores detalhados. O relatório que tem o foco mostrará no menu Ação: **Editar**, **Clone**, **Excluir**, **Baixar**e **Exportar árvore de relatório**.

### <a name="editing-reports"></a>Edição de relatórios

Quando você seleciona **Editar** no menu Ação, de um relatório, você vai abrir o Editor de consulta. Cada relatório é feito por uma consulta para CQD. Um relatório é uma visualização dos dados retornados por sua consulta. O Editor de consulta é uma interface do usuário para edição essas consultas além das opções de exibição para o relatório, como ilustrado na figura a seguir.

![Diferentes elementos que compõem um relatório quando o relatório está sendo editado.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![um] (media/qerguide-image-callout1.png "um") | Você escolher medidas, dimensões e filtros de painel à esquerda. Apontando para um valor existente exibe um botão Fechar (**X**) que você pode optar por remover o valor.<ul><li>Selecionando a dimensão ou medida, você pode alterar o título editando o campo **cargo** . Você também pode alterar a ordem selecionando o azul aumentar ou diminuir setas no painel superior.</li><li>Selecionando (**+**) ao lado de um título abre a caixa de diálogo para adicionar uma nova dimensão, uma medida ou um filtro.</li><li>Digite as primeiras letras da dimensão, medida ou filtro no **encontrar um** campo para filtrar a lista para facilitar a pesquisa.</li></ul> |
| ![dois] (media/qerguide-image-callout2.png "dois") | O painel superior mostra as opções de personalização do gráfico. |
| ![três] (media/qerguide-image-callout3.png "três") | O Editor de consulta mostra uma visualização do relatório. |
| ![quatro] (media/qerguide-image-callout4.png "quatro") | Use a caixa **Editar** na parte inferior da tela para criar ou editar uma descrição detalhada do relatório. |

_Figura 11 - Editor de consulta_

### <a name="filtering-reports"></a>Filtragem de relatórios

Os modelos fornecidos incluem várias consultas integradas e filtros do relatório. As seções a seguir descrevem os filtros mais comuns usados em todo os modelos.

#### <a name="url-filter"></a>Filtro de URL

Você pode usar uma URL filtro para filtrar cada relatório para uma dimensão específica. Os filtros de URL mais comuns são usados para filtrar relatórios para excluir telemetria participantes federada ou enfocam equipes ou Skype para negócios Online. Recomendamos que ao usar filtros, você crie um indicador-los para referência fácil. 

Excluindo dados federados de relatórios CQD é útil quando você estiver correção prédios gerenciados ou redes onde os pontos de extremidade federados podem influenciar seus relatórios.

Para implementar um filtro de URL, na barra de endereço do navegador, acrescente o seguinte ao final da URL:

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemplo:  

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Para filtrar os relatórios para equipes ou Skype para os negócios, acrescente o seguinte ao final da URL:

```
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Exemplo:

```https://cqd.lync.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Os exemplos de URL acima são para representação visual apenas. Use o link CQD padrão de <https://cqd.lync.com>.


#### <a name="query-filters"></a>Filtros de consulta

Filtros de consulta são implementados, usando o Editor de consulta em CQD. Esses filtros são usados para reduzir o número de registros retornados por CQD, minimizando o tamanho geral e os tempos de consulta do relatório. Isso é especialmente útil para filtragem de redes não gerenciados. Os filtros listados na seguinte tabela usar expressões regulares (RegEx).

_Tabela 3 - filtros de consulta_

| Filtro         | Descrição          | Exemplo de filtro de consulta CQD      |
|----------------|----------------------|-------------------------------|
| Sem valores em branco   | Alguns filtros não tem a opção para filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e definir o filtro é igual a ou não for igual a, dependendo das suas necessidades.      | Construção do segundo nome \< \> \^ \\s\*\$                       |
| Excluir subredes comuns | Sem um arquivo de construção válido para separar gerenciada de redes não gerenciados, redes domésticas serão incluídos nos relatórios. Essas sub-redes residencial estão fora do escopo do controle de TI e podem ser rapidamente excluídos de um relatório. Sub-redes comuns, como definido neste guia, são 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Segunda sub-rede \< \> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Somente exibição dentro  | Usado para filtrar um relatório para (interna) gerenciado ou (externo). O modelo CQD gerenciado já está pré-configurado com esses filtros.       | Segundo dentro Corp = dentro        |

#### <a name="report-filters"></a>Filtros do relatório

Filtros do relatório são implementados adicionando um filtro ao relatório renderizado tanto no Editor de consulta ou diretamente ao relatório. Os seguintes filtros de relatório são usados em todo o modelo.

_Tabela 4 - filtros do relatório_

| Filtro     | Descrição                            | Exemplo de filtro de relatório CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Comece com o ano primeiro e, em seguida, mês. | 10 de 2017                           |
| Alfabético | Filtra quaisquer caracteres alfabéticos. | [a-z]                             |
| Numérico    | Filtra todos os caracteres numéricos.    | [0-9]                             |
| Porcentagem | Filtra uma porcentagem.              | ([3-9]\\.) \|([3-9])\|([1-9][0-9]) |

## <a name="import-the-cqd-templates"></a>Importar os modelos CQD

Este guia inclui [dois modelos CQD curated](https://aka.ms/qertemplates). Esses modelos aceleram seu uso de CQD e fornecem a você uma oportunidade para aproveitar rapidamente os recursos do CQD para tornar um impacto sobre equipes ou do Skype dos usuários para a experiência de negócios. O modelo de todas as redes, porém otimizado para funcionar com um edifício pode ser usado o arquivo de dados, enquanto você trabalha em direção a coleta e carregamento de informações de construção em CQD, conforme descrito na próxima seção.

**Para importar os modelos (. CQDX) em CQD Online**

1.  Vá para <https://cqd.lync.com>.

2.  Autentica usando suas credenciais administrativas do Office 365.

  > [!NOTE]
  > Você deve ter o Office 365 Global administrador Skype para administrador de negócios ou função de leitores de relatório acessar CQD. 

3.  Selecione o menu de **Relatórios de resumo** na parte superior da página e escolha **Relatórios detalhados**.

4.  No painel Resumo, selecione **Importar**. Vá para o CQDX salvo local, selecione o modelo CQDX e selecione **Abrir**.

5.  Depois que o modelo for carregado, uma janela pop-up será exibida a mensagem "a importação de relatório teve êxito." Selecione **Okey.**

  ![Notificação de que o modelo foi importado com êxito] (media/qerguide-image-importmessage.png "Notificação de que o modelo foi importado com êxito")

6.  Repita as etapas 4 e 5 para o segundo modelo CQD.

> [!NOTE]
> Os modelos CQD são importados por usuário. Se outros usuários precisarem usar o relatório, eles devem entrar e importar os modelos em sua instância CQD. 


## <a name="building-mapping"></a>Mapeamento de construção

Em um equipes ou Skype para implantação Business Online, todos os clientes são externos. Que tem a implicação que, por padrão, todos os clientes são indicados como fora em CQD Online, independentemente de se o cliente foi conectado em uma rede corporativa interna.

Quando você trabalha com CQD, você precisa saber o local de um ponto de extremidade e se ele foi conectado a uma rede que você pode gerenciar ou de uma rede não é possível gerenciar — a pressuposição sendo que você só pode melhorar redes você pode gerenciar. Carregando sub-rede e informações de construção para CQD Online, você deve habilitar CQD determinar se o ponto de extremidade foi conectado a uma rede interna de corporativo/gerenciados ou a uma rede externa/não gerenciados.

### <a name="building-data-file-structure"></a>Estrutura do arquivo de dados de construção

O formato do arquivo de dados que você carrega deve atender aos seguintes requisitos para passar a verificação de validação antes de carregar.

-   O arquivo deve ser um arquivo TSV — que significa que, para cada linha, cada coluna é separada por um caractere de tabulação — ou um arquivo CSV no qual cada coluna é separada por uma vírgula.

-   O arquivo não pode ser maior do que 50 MB.

-   O conteúdo dos dados de arquivo *não deve incluir cabeçalhos de tabela*. Em outras palavras, a primeira linha do arquivo de dados deve ser dados reais, e não os títulos de coluna, como "Rede".

-   Para cada coluna, o tipo de dados só pode ser cadeia de caracteres, número ou Bool. Se o tipo de dados for um número, o valor deve ser um valor numérico; Se for Bool, o valor deve ser 0 ou 1.

-   Para cada coluna, se o tipo de dados é a cadeia de caracteres, os dados podem ser vazios (mas ainda devem ser separados por um delimitador apropriado — ou seja, um caractere de tabulação ou por vírgula). Isso simplesmente atribui esse campo um valor de cadeia de caracteres vazia.

-   Deve haver 14 colunas para cada linha. Cada coluna deve ter o tipo de dados descrito na tabela a seguir, e as colunas devem estar na ordem listada na tabela.

_Tabela 5 - Criando a estrutura do arquivo_

| Nome da coluna        | Tipo de dados | Exemplo                   | Orientação    |
|--------------------|-----------|---------------------------|-------------|
| Rede            | Cadeia de caracteres    | 192.168.1.0               | Obrigatório    |
| NetworkName        | Cadeia de caracteres    | EUA/Seattle/SEATTLE-mar-1 | Obrigatório\*  |
| NetworkRange       | Número    | 26                        | Obrigatório    |
| BuildingName       | Cadeia de caracteres    | SEATTLE-MAR-1             | Obrigatório\*  |
| OwnershipType      | Cadeia de caracteres    | Contoso                   | Opcional    |
| BuildingType       | Cadeia de caracteres    | Terminação de IT            | Opcional    |
| BuildingOfficeType | Cadeia de caracteres    | Engenharia               | Opcional    |
| Cidade               | Cadeia de caracteres    | Seattle                   | Recomendado |
| CEP            | Cadeia de caracteres    | 98001                     | Recomendado |
| País            | Cadeia de caracteres    | CONOSCO                        | Recomendado |
| Estado              | Cadeia de caracteres    | WA                        | Recomendado |
| Região             | Cadeia de caracteres    | MSUS                      | Recomendado |
| InsideCorp         | Bool      | 1                         | Obrigatório    |
| ExpressRoute       | Bool      | 0                         | Obrigatório    |

\*Embora não seja necessário por CQD, os modelos estão configurados para exibir a criação e a rede nome.

#### <a name="supernetting"></a>Combinação de redes

Você pode usar a combinação de redes, geralmente chamado de roteamento entre domínios sem classificação (CIDR), no lugar de definição de cada sub-rede. Uma *super-rede* é uma combinação de várias sub-redes que compartilham um único prefixo de roteamento. Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de supernetted. Combinação de redes é suportada, mas não recomendamos utilizá-lo.

Por exemplo, a construção de marketing da Contoso é composta das sub-redes abaixo:

-   10.1.0.0/24—First andar
-   10.1.1.0/24—Second andar
-   10.1.2.0/24—Third andar
-   10.1.3.0/24—Fourth andar

Em vez de adicionar uma entrada para cada sub-rede, você pode usar o endereço de supernetted — neste exemplo, 10.1.0.0/22.

-   Rede = 10.1.0.0
-   Intervalo de rede = 22

Aqui estão algumas coisas a considerar antes de implementar a combinação de redes:

-   Combinação de redes só pode ser usada em um mapeamento de sub-rede com máscara de 8 bits para 28 bits.

-   Combinação de redes demora menos tempo desde o início, mas que se refere ao custo reduzir o aperfeiçoamento em termos de seus dados. Digamos que não há uma sub-rede de envolvendo do problema de qualidade 200.1.2.0. Se você implementou a combinação de redes, você não saberá onde a sub-rede está localizada no edifício ou tipo de rede que está (por exemplo, um laboratório). Se você tivesse definido todas as sub-redes de um edifício e carregado informações de local andar, você poderá ver essa distinção.

-   É importante garantir que o endereço de supernetted está correto e se não está capturando sub-redes indesejadas.

-   Ele é bastante comum para encontrar 192.168.0.0 nos dados. Para muitas organizações, isso indica que o usuário está em casa. Para outras pessoas, esse é o esquema de endereço IP de um escritório de satélite. Se sua organização tem escritórios que usam essa configuração, não incluí-lo em seu arquivo de construção porque é difícil distinguir entre redes domésticas e internos usando sub-redes comuns. Consulte a seção sobre [sub-redes comuns](#common-subnets), neste guia.

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede. Todas as novas criar carregamentos de arquivos de dados será verificado para todos os intervalos de sobreposição. Caso tenha carregado anteriormente um arquivo de construção, você deve baixar o arquivo atual e carregá-la novamente para identificar qualquer sobreposições e corrigir o problema. Qualquer sobreposição nos arquivos carregados anteriormente pode resultar em mapeamentos de sub-redes aos prédios nos relatórios errados.

#### <a name="vpn"></a>VPN

A qualidade dos dados de experiência (QoE) que os clientes enviam para Office 365 — que é onde os dados CQD originados de — inclui um sinalizador VPN. CQD verá isso como as dimensões VPN primeiro e segundo VPN. No entanto, esse sinalizador depende de relatórios de fornecedores de VPN para Windows que o adaptador de rede VPN registrado é um adaptador de acesso remoto. Nem todos os fornecedores VPN adequadamente registre os adaptadores de acesso remoto. Dessa forma, você não poderá usar os filtros de consulta VPN internos. Há duas abordagens para acomodar sub-redes VPN no edifício arquivo de informações:

-   Defina um **Nome de rede** usando o texto "VPN" neste campo para sub-redes da VPN.

  ![Relatório CQD que define como criar uma sub-rede VPN](media/qerguide-image-vpnnetworkname.png)

  _Figura 12 - VPN usando o nome de rede_

-   Defina um **Nome de construção** usando-se o texto "VPN" neste campo para sub-redes da VPN.

  ![Relatório CQD que define como criar uma definição de construção que consiste em uma sub-rede VPN.](media/qerguide-image-vpnbuildingname.png)

  _Figura 13 - VPN usando o nome do edifício_

> [!IMPORTANT]
> Determinadas implementações de VPN com precisão não relatam informações de sub-rede. Se isso ocorrer em seu relatório, que é recomendável que, quando você adiciona uma sub-rede VPN para o arquivo de construção, em vez de uma entrada para a sub-rede, adicione entradas separadas para cada endereço na sub-rede VPN como uma rede separada de 32 bits. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você tem 253 linhas, com uma linha para cada endereço de 172.16.18.1/32 por meio de 172.16.18.254/32, inclusive.


> [!NOTE]
> Conexões VPN são conhecidas por cometem erros conforme com fio quando a conexão de internet subjacente está na identificação de conexão de rede sem fio. Ao olhar qualidade em conexões VPN, você não pode assumir que o tipo de conexão foi identificado com precisão.

### <a name="uploading-building-information"></a>Carregar informações de construção

O painel de relatórios de resumo de CQD inclui uma página de **Carregamento de dados de Inquilino** , acessada selecionando a marca de link de **Carregamento de dados de Inquilino** no canto superior direito (procure o ícone de engrenagem). Esta página é usada para os administradores para carregar suas próprias informações, como o mapeamento de endereço IP e informações geográficas, mapeando cada ponto de acesso sem fio e seu endereço MAC e assim por diante.

1.  Vá para CQD Online navegando até <https://cqd.lync.com>.

2.  Selecione o ícone de engrenagem no canto superior direito e escolha o **Carregamento de dados de Inquilino** na página **Relatórios de resumo** .

  ![Caixa de diálogo é exibida enquanto está sendo carregados dados](media/qerguide-image-tenantdataupload.png)

  _Figura 14 - menu de carregamento de dados de Inquilino_

3.  Como alternativa, se essa for a primeira vez em que visitando CQD, você será solicitado para carregar dados de construção. Você pode selecionar **Carregar Agora** para navegar rapidamente para a página de **Carregamento de dados de Inquilino** .

  ![Banner que notifica o usuário para carregar dados de construção](media/qerguide-image-buildingdatauploadbanner.png)

  _Figura 15 - criando banner de carregamento de dados_

4.  Na página de **Carregamento de dados de Inquilino** , selecione **Procurar** para escolher um arquivo de dados.

5.  Depois de selecionar um arquivo de dados, especifique a **Data de início** e, opcionalmente, especifique uma data de término.

6.  Depois de selecionar a **Data de início**, selecione **carregar** para carregar o arquivo CQD. <br><br>Antes do arquivo for carregado, ele será validado. Se a validação falhar, uma mensagem de erro é exibida solicitando que você corrija o arquivo. A figura a seguir mostra um erro que ocorrem quando o número de colunas no arquivo de dados está incorreto.

  ![Exemplo de uma caixa de diálogo que exibe uma mensagem de erro ao importar dados de construção](media/qerguide-image-buildingdatauploaderror.png)
 
  _Figura 16 - criando o erro de carregamento de dados_

7.  Se nenhum erro ocorrer durante a validação, o carregamento de arquivo terá êxito. Em seguida, você pode ver o arquivo de dados carregados na **Minhas carregamentos de** tabela, que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.

> [!NOTE]
> Pode levar até quatro horas para concluir o processamento do arquivo de construção. <br><br> Se você já tiver carregado um arquivo de construção e precisa para adicionar as sub-redes que podem ter sido perdidas ou excluídos, modifique o arquivo original adicionando novas sub-redes, remova o arquivo atual e reenvie o arquivo recentemente editado. Pode haver construção ativa apenas um arquivo de dados em CQD. 


### <a name="updating-a-building-file"></a>Atualizando um arquivo de construção

Enquanto que coleta informações de sub-rede e construção, os administradores frequentemente carregar o arquivo de construção em várias iterações ao longo do tempo, adicionar novas sub-redes e suas informações de construção, como ele se tornar disponível. Quando isso ocorre, você precisará reenvie em seu arquivo de construção. Esse processo é como o carregamento inicial, conforme descrito na seção anterior, com algumas poucas exceções, conforme indicado na seção a seguir.

> [!Important]
> Construção de apenas um arquivo pode estar ativo por vez. Vários arquivos de construção não são cumulativos.

#### <a name="adding-net-new-subnets"></a>Adicionar novas sub-redes net

Há ocasiões em que você precisará adicionar novas sub-redes net a CQD que não estavam originalmente parte de sua topologia de rede. Para adicionar novas sub-redes net, faça o seguinte no portal do carregamento de dados de Inquilino CQD:

1.  Editar o arquivo original de construção e forneça uma data final que ocorre ao menos um dia antes do net nova sub-redes foram adquiridos.
2.  Baixe o arquivo original, se você ainda não tiver uma cópia atualizada.
3.  Acrescente as net novas sub-redes do arquivo original de construção.
4.  Carregar o arquivo de construção recentemente modificados seguindo o mesmo processo acima e defina a data inicial para um dia depois que o arquivo de construção anterior termina.

#### <a name="updating-the-current-building-file"></a>Atualizando o arquivo de construção atual

Se um arquivo de construção já foi carregado, mas você precisa adicionar sub-redes ausentes, faça o seguinte no portal do carregamento de dados de Inquilino CQD:

1.  Baixe o arquivo original, se você ainda não tiver uma cópia atualizada.
2.  Remova o arquivo atual no CQD.
3.  Acrescente novas sub-redes para o arquivo original.
4.  Carregar o arquivo de construção. Certifique-se de que defina a data de início para pelo menos oito meses anteriores para que CQD processará dados históricos.

### <a name="missing-subnets"></a>Sub-redes ausentes

Após carregar as informações de construção para redes gerenciadas, cada rede gerenciada deve ter uma associação de construção. No entanto, isso não será sempre o caso; Normalmente, as sub-redes alguns são perdidas. Esta seção aborda como validar as redes ausentes.

Navegue até a página de **Relatórios detalhados** no CQD Online e navegue até o **Relatório de sub-rede ausentes** incluídas nos modelos CQD. Isso apresenta todas as sub-redes com 10 ou mais áudio fluxos que não estão definidos nos dados de criação de arquivo e estão sendo marcados como externa. Certifique-se de que não há nenhuma redes gerenciadas nessa lista. Se não existirem sub-redes, atualize o edifício original do arquivo de dados e reenvie a CQD.

> [!IMPORTANT]
> Você precisará adicionar sua ID de Inquilino como um filtro de consulta para a **Segunda ID do inquilino** para este relatório para filtrar o relatório para exibir somente os dados de inquilinos da sua organização. Caso contrário, o relatório mostrará sub-redes federados.

> [!NOTE] 
> Certifique-se de ajuste o filtro de relatório do mês ano ao mês atual. Selecione **Editar**e ajuste o filtro de relatório do **Mês ano** para salvar o novo mês padrão.

![Relatório mostrando as sub-redes não são incluídos no arquivo de dados de construção CQD que mostram o uso.](media/qerguide-image-missingbuildingreport.png)

_Figura 17 - ausente relatório de construção_

### <a name="building-mapping-tools"></a>Ferramentas de mapeamento de construção

Analisando os fatos, mapeamento de sub-redes em sua organização pode ser difícil. Grandes redes globais são muito complexas, com equipes diferentes Gerenciando seus respectivos regiões e não pode haver nenhum única fonte verdadeira para a topologia de rede. Há duas ferramentas disponíveis para ajudá-lo com iniciando o exercício de mapeamento de construção, descrito nas seções a seguir.

#### <a name="cqd-tools"></a>Ferramentas CQD

Essas ferramentas são baseadas nas PowerShell e podem aproveitar os serviços e Sites do Active Directory (AD) e serviços de DHCP da Microsoft para ajudar a preencher previamente o seu arquivo de construção.  Essas ferramentas ajudarão nas seguintes tarefas:

1.  Consultar os Sites e Serviços AD e criar um arquivo de construção com base nas informações contidas.
2.  Consulte um servidor DHCP da Microsoft ou servidores para receber informações de sub-rede e criar automaticamente um arquivo de construção.
3.  Valide um arquivo de construção existente, a verificação de duplicatas e sobreposições.
4.  Encontre as sub-redes não mapeadas no CQD.

Para obter mais informações sobre essa ferramenta, consulte [esta postagem de blog](https://aka.ms/cqdtools).

#### <a name="network-planner"></a>Planejador de rede

Planejador de rede determina e organiza seus requisitos de rede para sua implantação de voz de nuvem em apenas algumas etapas simples. Fornecendo a que sua organização da rede detalhes e o uso de voz de nuvem, você pode obter um cálculo aproximado dos requisitos de rede para sua implantação de voz de nuvem, gerenciar e exportar esses detalhes para geração de relatórios e exibir áreas para investigação futura e próximas etapas.

Embora Planejador de rede não automatizar o processo de mapeamento de construção inteiramente, depois que as informações de rede são inseridas no planejador de rede, em seguida, ele pode ser exportado para um arquivo de construção pronto para carregamento.

É altamente recomendável que você aproveitar Planejador de rede ao implantar cargas de trabalho de mídia em sua rede para avaliar o impacto geral. Para obter mais informações sobre o Planejador de rede, visite [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).


## <a name="diagnostic-alerts"></a>Alertas de diagnósticos

Microsoft monitora proativamente telemetria CQD para criar alertas de diagnósticos para os problemas conhecidos que afetam negativamente a experiência do usuário. Esses alertas serão entregues automaticamente ao administrador do serviço por meio do Centro de mensagens. A tabela a seguir descreve os alertas de diagnósticos que são mostrados no Centro de mensagens, juntamente com links para mais informações.

_Tabela 6 - alertas de diagnósticos_

| Alerta                                                                | Mais informações             |
|----------------------------------------------------------------------|------------------------------|
| Conhecidos mal executando versões do cliente estão em uso                   | [Versões do cliente](#client-versions)              |
| Drivers de áudio estão causando quedas de chamada                                 | [Dispositivos](#devices)                      |
| Restrições no firewall estão causando falhas de instalação chamada         | [Investigações de falha de instalação](#setup-failure-investigations) |
| Profunda inspeção de pacotes está causando falhas de instalação chamada                | [Investigações de falha de instalação](#setup-failure-investigations) |
| Dispositivos de sala de reunião em redes Wi-Fi estão causando uma qualidade de chamadas ruins | [Investigações de qualidade](#quality-investigations)       |
| Tráfego UDP está sendo limitado, que faz com que a chamada de baixa qualidade         | [TCP](#tcp)                          |
| Uso VPN está afetando a qualidade da chamada                                  | [Investigações de qualidade](#quality-investigations)       |


### <a name="message-center"></a>Centro de mensagens

O Centro de mensagens envia alertas sobre problemas, recursos ou novas atualizações. O Centro de mensagens está disponível no Centro de administração do Office 365 para administradores de serviço. Cada post fornece uma visão geral de como a atualização, o recurso ou o problema afeta os usuários e oferece links para informações mais detalhadas.

Para abrir o Centro de mensagens, no Centro de administração do Office 365, vá para **integridade** > **Centro de mensagens**ou selecione o cartão de centro de mensagem no painel de **casa** . O painel exibe as três últimas mensagens que foram lançadas e links para a página do Centro de mensagem completa.
 

![O cartão de centro de mensagem exibe as três últimas mensagens que foram postadas](media/qerguide-image-messagecentercard.png)

_Figura 18 - cartão do Centro de mensagem_

Você também pode usar o [aplicativo de administração do Office 365](https://go.microsoft.com/fwlink/p/?linkid=627216) no seu dispositivo móvel para exibir o Centro de mensagens, que é uma ótima maneira de permanecer atualizado com as notificações por push. Para obter mais informações, consulte [Este artigo](https://support.office.com/article/Message-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093).

## <a name="reliability-investigations"></a>Investigações de confiabilidade

A primeira etapa para aprimorar a qualidade é para avaliar o estado de confiabilidade em toda a organização. Como confiabilidade é vital para uma experiência de usuário positivo, iniciamos com os dois componentes que medem confiabilidade:

1.  **Falhas de instalação:** A chamada não pôde ser estabelecida.

2.  **Drop falhas:** A chamada foi estabelecida e finalizada inesperadamente.

Ao longo desta seção, abordaremos métodos para ambas as áreas de investigar.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia.  No entanto, os métodos de investigação explicado abaixo ainda se aplicam. Consulte a descrição do relatório individual para obter mais informações.


### <a name="setup-failures"></a>Falhas de instalação

Priorize remediando falhas de instalação nessa área em primeiro lugar, pois essas falhas possuem um impacto negativo significativo na experiência do usuário.

Começar a investigação avaliando a porcentagem de falhas de instalação geral para a organização e, em seguida, priorizar áreas de investigação com base na porcentagem mais alta, criação ou da rede. 

#### <a name="setup-failure-trend-analysis"></a>Análise de tendência de falha da instalação

Este relatório exibe a quantidade total de fluxos de falhas de instalação do stream e a taxa de falha de instalação do stream. Aponte para qualquer uma das colunas para exibir seus valores individuais, conforme mostrado na figura a seguir. 

![Gráfico que mostra o percentual do fluxo de falhas de instalação](media/qerguide-image-streamsetupfailures.png)

_Figura 19 - confiabilidade de áudio - falhas de instalação de fluxo_

##### <a name="analysis"></a>Análise

Usando este relatório, você pode responder às seguintes perguntas e determinar sua próxima ação:

-   Qual é a porcentagem de falha de instalação chamada total para o mês atual?

-   É a porcentagem de falha de instalação chamada total abaixo ou acima a métrica destino definida?

-   É a tendência de falha pior ou melhor do que o mês anterior?

-   É a tendência de falha aumentando, steady, ou diminuindo?

Independentemente das respostas anteriores, reserve um tempo para investigar maior usando os sub-relatórios complementares para procurar por qualquer prédios individuais ou as sub-redes que possam precisar de remediação. Embora a taxa de falha geral pode estar abaixo na métrica de destino, as taxas de falha para uma ou mais redes ou prédios podem ser maior do que a métrica destino e precisam de investigação.

#### <a name="setup-failure-investigations"></a>Investigações de falha de instalação 

Este relatório de resumo é usado para descobrir e isolar qualquer prédios ou redes que possam precisar de remediação.

> [!NOTE]
> Certifique-se de ajuste o filtro de relatório do mês ano ao mês atual. Selecione **Editar**e ajuste o filtro de relatório do **Mês ano** para salvar o novo mês padrão.


![Uma lista das razões para falhas de instalação chamada, organizadas por construir, rede e sub-rede por mês](media/qerguide-image-setupfailuresbysubnet.png)

_Figura 20 - falhas de configuração de áudio pela sub-rede_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você tiver recebido um alerta de diagnóstico "Restrições no firewall estão causando falhas de instalação chamada" ou "profunda inspeção de pacotes está causando falhas de instalação chamada," concentrar os esforços de remediação naqueles identificado pela primeira vez sub-redes. O alerta identificou sub-redes que estão afetando negativamente o confiabilidade de chamada. Você pode usar os relatórios de falhas de instalação encontrados na seção de confiabilidade para ajudar na correção.

##### <a name="remediation"></a>Remediação 

Concentre-se os esforços de remediação primeiro em prédios ou sub-redes que tenham o maior volume de falhas. Isso irá maximizar o impacto sobre a experiência do usuário e ajudam a reduzir rapidamente a taxa de falhas de instalação chamada organizacionais. A tabela a seguir lista as duas razões para falhas de instalação, conforme relatado pelo CQD.

_A tabela 7 – razões para falhas de instalação chamada_

| Chamar o motivo de falhas de instalação       | Causa comum                    |
|----------------------------------|----------------------------------|
| Regra de isenção de inspeção de pacotes de profundidade de firmware de ausentes | Indica que o equipamento de rede ao longo do caminho impedidos o caminho da mídia de sendo estabelecida devido às regras de inspeção de pacotes de profundidade. Isso é provável devido às regras de firewall não está sendo configuradas corretamente. Neste cenário, o handshake TCP foi bem-sucedida, mas não o handshake SSL.      |
| Regra de exceção do bloco de IP de firmware de ausentes      | Indica que o equipamento de rede ao longo do caminho impedidos o caminho da mídia de sendo estabelecida com a rede do Office 365. Isso pode ser devido às regras de firewall ou proxy não está sendo configuradas corretamente para permitir acesso aos endereços IP e portas usadas para equipes e Skype para tráfego de negócios. |

Agora como começar sua remediação, é possível focar seus esforços em um edifício ou sub-rede. Conforme mostra a tabela anterior, esses problemas são devido às configurações de firewall ou proxy. Examine as opções na tabela a seguir para ações de remediação.

_A tabela 8 - próximas etapas para a chamada de correção de falha de instalação_

| Remediação           | Orientação     |
|-----------------------|--------------|
| Configurar firewalls | Trabalhar com a equipe de rede e verifique se a sua configuração de firewalls contra [a lista de endereços IP do Office 365](https://aka.ms/o365ips).<br><br>Verifique se as portas e [sub-redes de mídia](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) são incluídas nas regras de firewall. <br><br>Verifique se as portas necessárias (listadas abaixo) são abertas no firewall. UDP deve ser dada prioridade porque TCP é considerado um protocolo de failback para áudio, vídeo e compartilhamento de tela de vídeo e seu uso afetará a qualidade da chamada. Compartilhamento de aplicativos RDP herdado usa apenas TCP.<br><ul><li>**TCP:** a porta 443</li><li>**UDP:** portas 3478 – 3481</li><ul> |
| Verifique se                | Use a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar a conectividade do edifício afetado ou sub-rede usando a função de verificação de conectividade.    |


### <a name="drop-failures"></a>Falhas de recebimento

Ao contrário de códigos de falhas de instalação, CDQ não tem nenhum código de falha de soltar para indicar por que ocorrem falhas de recebimento, que dificulta isolar uma causa raiz específica. Para melhor triagem drop falhas, use uma abordagem deduzida. Pela correção de quaisquer áreas de interesse para mídia, os clientes de aplicação de patch e drivers e orientando uso de dispositivos de certificados para equipes e Skype for Business, você pode esperar falhas projetada para recusar.

#### <a name="drop-failure-trend-analysis"></a>Descarta a análise de tendências de falha

Este relatório exibe a quantidade total de fluxos de áudio, drop total falhas e a taxa de falha de recebimento. Aponte para qualquer uma das colunas para exibir seus valores, conforme mostrado na figura a seguir. 

![Gráfico mostrando a porcentagem de fluxos que foram cancelados](media/qerguide-image-droppedstreamrate.png)

_Figura 21 - taxa de fluxo capitular_

##### <a name="analysis"></a>Análise

Ao usar esse tipo de relatório, você pode responder às seguintes perguntas:

-   Qual é a taxa de falha de recebimento atual?
-   É a taxa de falha de recebimento abaixo a métrica destino definida?
-   É a tendência de falha pior ou melhor do que o mês anterior?
-   É a tendência de falha aumentando, steady, ou diminuindo?

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que possam precisar de remediação. Embora a taxa de falha geral drop possa estar abaixo na métrica de destino, a taxa de falha de recebimento para uma ou mais redes ou prédios pode ser maior do que a métrica destino e precisam de investigação.

#### <a name="drop-failure-investigations"></a>Drop investigações de falha

Falhas informadas aqui indicam que a chamada foi interrompida inesperadamente e resultou em uma experiência de usuário negativo. Diferentemente dos relatórios de tendências, esses relatórios fornecem visões adicionais sub-redes específicas que precisar de mais investigação.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.


![Relatar que o número de listas e a porcentagem de falhas de recebimento, organizados construindo, a rede e a sub-rede por mês](media/qerguide-image-dropfailuresbysubnet.png)

_Figura 22 – falhas de recebimento na sub-rede_

##### <a name="remediation"></a>Remediação

Usando os relatórios de tabela incluído, você pode isolar o problema áreas na rede onde a taxa de recebimento é acima a métrica destino você tivesse definido. Concentre-se os esforços de remediação primeiro em prédios ou sub-redes que tenham a contagem total stream mais alta, para tornar o maior impacto.

Causas comuns de quedas de chamada:

-   Saída de rede ou internet em provisionado
-   Nenhum QoS configurado em redes restritas
-   Versões mais antigas do cliente
-   Comportamento do usuário

Depois que você descobrir suas áreas de problema, você pode usar o [Analytics chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) revisar ainda mais usuários em que construção para problemas específicos. Análise de chamada contém dados PII e pode ser útil para isolar ainda mais possíveis razões para falhas de recebimento.

Independentemente da sua próxima etapa, é uma boa prática para notificar a helpdesk que foi descoberto um problema com os prédios específicos ou sub-redes. Dessa forma, rapidamente eles podem responder às chamadas recebidas e triagem usuários com mais eficiência. Usuários sinalizados, em seguida, podem ser informados volta para a equipe de engenharia para uma investigação detalhada.

A tabela a seguir lista alguns métodos comuns para gerenciar e corrigir falhas de recebimento.

_A tabela 9 - próximas etapas para chamada drop remediação_

| Remediação                              | Orientação                      |
|------------------------------------------|-------------------------------|
| **Rede/internet**                         | **Congestionamento**: trabalhar com sua equipe de rede para monitorar a largura de banda em prédios/sub-redes específicas para confirmar que não há problemas com excesso. Se você confirmar que não há congestionamento da rede, considere a possibilidade de aumento de largura de banda que construção ou a aplicação de QoS. Use incluído [relatórios resumidos de fluxo de baixa qualidade](#quality-investigations) para revisar as sub-redes de problema para problemas com tremulação, latência e perda de pacotes, porque estes terão precedência sobre um stream capitular com frequência.<br><br>Você também pode usar a [Ferramenta de Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) para ajudar a compreender melhor as necessidades de largura de banda da sua organização.<br><br>**QoS**: se o aumento da largura de banda é impraticável ou caro, considere a implementação de QoS. Essa ferramenta é muito eficiente em gerenciamento de congestionamento de tráfego e pode garantir que os pacotes de mídia na rede gerenciada são priorizados acima tráfego de mídia não. Como alternativa, se não houver nenhuma evidência clara que largura de banda é o responsável, considere estas soluções:<ul><li>[Orientação de QoS de equipes da Microsoft](qos-in-teams.md)</li><li>[Skype para obter orientações de QoS de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul><br>**Executar uma avaliação de prontidão de rede**: uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com largura de banda de rede e altera e redes práticas recomendadas de para equipes e Skype para negócios. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são candidatos excelentes para uma avaliação.<ul><li>[Avaliação de prontidão de rede de equipes da Microsoft](3-envision-evaluate-my-environment.md#test-the-network)</li><li>[Skype para avaliação de prontidão da rede de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Ferramenta de avaliação do Microsoft Network:** Usar essa ferramenta para um teste simples de desempenho de rede para determinar o quão bem a rede deve executar para um equipes ou Skype para chamada de negócios Online. A ferramenta ajuda você a avaliar o desempenho de uma sub-rede e validar a preparação da rede contra os [requisitos](https://aka.ms/performancerequirements)de desempenho da Microsoft.<ul><li>[Baixe a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul> |
| **Clientes (Skype para negócios apenas Online)** | Alguns clientes mais antigos possuem conhecidos, documentados problemas com confiabilidade de mídia. Revise os relatórios de análise de chamada de vários usuários afetados, ou crie um relatório de tabela de versão do cliente personalizado no CQD filtrado específicos prédios ou sub-redes com medida de % do Total de chamadas queda de falha. Essas informações ajudarão você a entender se existe uma relação entre quedas de chamada na que edifício específico e uma versão específica do cliente.     |
| **Dispositivos**                                  | Recomendamos que todos os usuários que estão enfrentando chamar quedas — ou ruins chama em geral — e estão usar dispositivos integrados deve ser provisionado um [certificado headset ou viva-voz](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) para eliminar essa como uma fonte potencial de baixa qualidade e confiabilidade. |
| **Comportamento do usuário**                            | Se achar que nem rede, dispositivos ou clientes são o problema, considere o envolvimento do [Meu Advisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de adoção de usuário para instruir os usuários como práticas ingressar e sair de reuniões. Uma forma mais inteligente equipes e Skype para o usuário de negócios produzirá uma melhor experiência de usuário para todos os participantes da reunião. Um usuário que coloca seus laptops em suspensão (fechando a tampa) sem sair da reunião será classificado como um depósito chamada inesperada.   |

## <a name="quality-investigations"></a>Investigações de qualidade

A próxima etapa para avaliar o estado da qualidade de áudio em toda a organização é investigar a taxa de fluxo ruim (PSR), TCP e uso de proxy. É importante lembrar que os dados CQD não fornecem uma causa raiz específica, mas fornece em vez disso, com áreas de problema provavelmente iniciar uma conversa de colaboração com as equipes apropriadas para atividades de correção. 

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia; No entanto, os métodos de investigação explicado abaixo ainda serão aplicadas para esses relatórios. Consulte a descrição do relatório individual para obter mais informações. 

### <a name="quality"></a>Qualidade

As porcentagens PSR são usadas para indicar se a organização é reunião destinos métricos definidos para uma área de foco determinado. É importante observar que, mesmo se as porcentagens de alto nível dentro de destino definido, sub-redes individuais ou prédios inteiros talvez não cumprir os objetivos definidos e, portanto, precisar de mais investigação. Por exemplo, se a porcentagem PSR geral áudio for 2% em abril, que atende o destino de amostra, prédios individuais e sub-redes pode ainda ser tendo experiências ruins, dependendo da distribuição geral de que % 2. 

Para avaliar a porcentagem de fluxos de baixa, use os relatórios de qualidade. Vários relatórios de qualidade são fornecidos para analisar métricas para geral, conferências, duas partes, PSTN chamar, VPN e salas de reunião. Relatórios de diários, semanais e mensais são fornecidos para ajudá-lo nesse processo. Relatórios semanais e diários são limitados para o modelo de redes gerenciadas para aumentar a eficiência e reduzir o ruído. 

#### <a name="quality-trend-analysis"></a>Análise de tendências de qualidade

Relatórios de tendências exibem informações de qualidade ao longo do tempo e são usados para ajudar a identificar e entender as tendências de qualidade dentro de cada área de interesse. Conforme observado anteriormente, há árvores de relatório incluídas nos modelos para investigar qualidade; conferência, duas partes, chamada de PSTN, VPN e salas de reunião. Para fins de análise de qualidade, o processo de investigação é o mesmo. No entanto, recomendamos que você inicie com a conferência em primeiro lugar, pois qualquer melhorias na qualidade de conferência também positiva afetará todas as outras áreas. 

> [!Note]
> Investigando duas partes, chamada de PSTN e salas de reunião são semelhantes às investigando conferência. O foco é isloate prédios ou sub-redes que têm a qualidade pior e identificam o motivo de baixa qualidade.

> [!Important]
> Relatórios baseados em VPN são filtrados por meio da dimensão segundo VPN. Essa dimensão requer que o adaptador de rede VPN adequadamente ser registrada como um adaptador de acesso remoto. Fornecedores de VPN confiável não usam esse sinalizador e sua mileage irá variar dependendo do fornecedor VPN implantado em sua organização. Siga as orientações relata contorno [anteriores neste guia](#vpn) para modificar a VPN, se necessário, usando o nome de rede ou de construção.

![Gráfico mostrando a porcentagem de fluxos de baixa qualidade](media/qerguide-image-audioqualityconferencing.png)

_Figura 23 – qualidade de áudio - conferência_

##### <a name="investigation"></a>Investigação

Ao usar esses relatórios, você pode responder às seguintes perguntas:

-   Qual é o PSR total para o mês atual?
-   É o PSR abaixo a métrica destino definida?
-   É PSR pior ou melhor do que o mês anterior?
-   É a tendência PSR aumentando, steady, ou diminuindo?

Independentemente das respostas para as perguntas acima, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou as sub-redes que possam precisar de investigação. Embora o PSR geral pode estar abaixo na métrica de destino, frequentemente o PSR para um ou mais prédios ou redes estiver acima na métrica e precisa remediação.

#### <a name="quality-investigations"></a>Investigações de qualidade

A qualidade de relatórios de resumo oferecem mais aprofundada percepção que contribuíram dos fluxos sendo classificada como pobre e ajuda a isolar áreas de problemas na rede gerenciada.

Embora as dimensões usadas poderá diferir ligeiramente entre o relatório, cada relatório incluirá as medidas fluxos total, total de fluxos de baixa, PSR e baixa qualidade devido a. Relatórios que tiverem sido criados para cada área de interesse: conferência, duas partes, salas de PSTN chamar, VPN e a reunião. O modelo de rede gerenciados inclui relatórios adicionais para aproveitar as informações de localização carregadas por meio do arquivo construção.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.

> [!Note]
> Sub-redes comuns são difíceis de triagem devido ao seu uso amplo. Um relatório separado que exibe IP público do cliente (IP Local reflexiva segundo) foi adicionado ao modelo de todas as redes para auxiliar com escritórios remediando que usam redes comuns.


![Fluxo de áudio ruim resumo](media/qerguide-image-poorqualitysummary.png)

_Figura 24 – resumo de fluxo de áudio ruim, criando - e sub-rede conferência_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você tiver recebido um diagnóstico "dispositivos de sala de reunião em redes Wi-Fi estão causando a qualidade de chamadas ruins" incluem e priorizar esses dispositivos em seus esforços de remediação de alerta. O alerta identificou as salas de reunião em Wi-Fi que estão ativamente contribuindo para chamada de baixa qualidade.

Se você receber um alerta de diagnóstico "uso VPN está afetando a qualidade da chamada," investigar uma solução de divisão de túnel para ignorar o aparelho de VPN e permitir a mídia conectar-se diretamente ao serviço. O alerta identificou que VPN negativamente está afetando a qualidade da chamada.

##### <a name="remediation"></a>Remediação

Concentre os esforços de remediação em prédios ou sub-redes que tenham o maior volume de fluxos, porque isso maximizar o impacto e ajudar a melhorar a experiência do usuário rapidamente. Use a tremulação, perda de pacotes e medidas de tempo de ida e volta (tempo de resposta) para entender o que está contribuindo com baixa qualidade (é possível para ter mais de um problema):

-   **Tremulação**: pacotes de mídia chegam ao velocidades diferentes, que faz com que um alto-falante som robótica.
-   **Perda de pacotes**: pacotes de mídia estão sendo eliminados, que cria o efeito das palavras ou sílabas faltando.
-   **Tempo de resposta**: pacotes de mídia estão demorando muito tempo para chegar ao seu destino, que cria um efeito de walkie-talkie.

Para auxiliar sua investigação sobre problemas de qualidade, você pode aproveitar a [Análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Com a análise de chamada, você pode examinar uma conferência específica ou relatório de chamada detalhada dos usuários. Este relatório conterá os dados PII e é útil quando você está procurando a causa de uma falha. Depois que você sabe qual construção é afetada, ele deve ser simples rastrear usuários em que construção. 

Não se esqueça de informar a helpdesk que essas redes estão enfrentando problemas de qualidade, para que possam rapidamente triagem e responder às chamadas recebidas.

_Tabela 10 - comuns Contribuidores PSR alta_

| Remediação                              | Orientação                         |
|------------------------------------------|----------------------------------|
| **Redes**                                 | **Congestionamento**: uma rede com uso excessivo ou em provisionado pode causar problemas com a qualidade de mídia. Trabalho com a equipe de rede para determinar se as conexões de rede do usuário até a saída de internet apontam tem largura de banda suficiente para oferecer suporte a mídia. [Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) pode ajudá-lo a compreender melhor as necessidades de largura de banda da sua organização.<br><br>**Executar uma avaliação de prontidão de rede**: uma avaliação de rede fornece detalhes sobre o uso esperado de largura de banda, como lidar com largura de banda de rede e altera e redes práticas recomendadas de para equipes e Skype para negócios. Usando a tabela anterior como sua fonte, você tem uma lista de prédios ou sub-redes que são candidatos excelentes para uma avaliação.<ul><li>[Avaliação de prontidão de rede de equipes da Microsoft](3-envision-evaluate-my-environment.md#test-the-network)</li><li>[Skype para avaliação de prontidão da rede de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers/?pageState=NetworkReadiness)</li></ul><br>**Ferramenta de avaliação do Microsoft Network:** Usar essa ferramenta para um teste simples de desempenho de rede para determinar o quão bem a rede deve executar para um equipes ou Skype para chamada de negócios Online. A ferramenta ajuda você a avaliar o desempenho de uma sub-rede e validar a preparação da rede contra os [requisitos](https://aka.ms/performancerequirements)de desempenho da Microsoft.<ul><li>[Baixe a ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br> |
| **Qualidade de serviço (QoS)**  | QoS é uma ferramenta comprovada para ajudar a priorizar pacotes em uma rede de congestionamento para garantir que eles cheguem a seu destino intacto e no tempo. Considere a implementação de QoS em toda a organização para maximizar a qualidade da experiência do usuário onde a largura de banda é restrita. QoS ajudarão a solucionar problemas normalmente associados a altos níveis de perda de pacotes, e — a um grau menor — tempos de tremulação e de ida e volta.<ul><li>[Orientação de QoS de equipes da Microsoft](qos-in-teams.md)</li><li>[Skype para obter orientações de QoS de negócios](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_8)</li></ul> |
| **Wi-Fi**               | Wi-Fi pode ter um impacto significativo sobre a qualidade da chamada. Implantações Wi-Fi não duram normalmente em consideração os requisitos de rede para serviços de VoIP e, geralmente, são uma fonte de baixa qualidade. Para obter mais informações sobre como otimizar sua infraestrutura Wi-Fi, consulte [Este artigo sobre o planejamento de Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Driver wireless**: Certifique-se de que os drivers sem fio estão atualizados. Isso ajudará a atenuar qualquer experiência de usuário ruim relacionada a um driver desatualizado. Muitas organizações não incluem drivers sem fio em seus ciclos de patch e esses drivers podem ir sem patch para anos. Muitos problemas sem fio são resolvidos, garantindo que os drivers sem fio estão atualizados.<br><br>**WMM**: sem fio extensões WMM (multimídia), também conhecido como Wi-Fi Multimedia, fornece recursos básicos de QoS para redes sem fio. Redes sem fio modernos devem oferecer suporte a vários dispositivos. Esses dispositivos competem por largura de banda e podem causar problemas de qualidade para serviços de VoIP, onde estão vitais velocidade e a latência. Consulte seu fornecedor de sem fio para obter informações específicas e considere a implementação WMM em sua rede sem fio priorizar Skype para negócios e equipes de mídia.<br><br>**Densidade do ponto de acesso**: pontos de acesso podem ser muito distantes ou não em um local ideal. Para minimizar interferência potencial, coloque os pontos de acesso extra em salas de conferência e em locais que não são obstruídos por paredes ou outros objetos onde o sinal de Wi-Fi está fraco.<br><br>**2,4 GHz versus GHz 5**: 5 GHz fornece menos interferência de plano de fundo e as velocidades maiores e devem ser priorizado ao implantar VoIP por Wi-Fi. No entanto, 5 GHz não é tão forte quanto 2,4 GHz e não entrar na paredes tão facilmente. Examine seu layout de construção para determinar qual frequência você pode depender para a conexão recomendada. |
|**Dispositivo de rede** | Organizações maiores podem ter centenas de dispositivos afastadas através da rede. Trabalhar com a equipe de rede para assegurar que os dispositivos de rede do usuário para a internet são mantidos e atualizados. |
| **VPN**  | Aparelhos de VPN tradicionalmente não foram projetados para lidar com cargas de trabalho de mídia em tempo real. Algumas configurações de VPN proíbem o uso de UDP (que é o protocolo preferido para a mídia) e contam com apenas TCP. Considere a implementação de uma [solução de divisão de túnel VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) para ajudar a reduzir a VPN como uma fonte de baixa qualidade. |
| **Clientes** <br>(Skype para negócios apenas Online) | Clientes mais antigos são conhecidos por causar problemas com a mídia. Certifique-se de que os clientes estão sendo patch dentro de seis meses após o lançamento. Use [MyAdvisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de preparação de cliente e deploy [Click-to-Run](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus). |
| **Dispositivos** | O uso de [dispositivos de otimizado](https://partnersolutions.skypeforbusiness.com/solutionscatalog) pode ajudar a melhorar significativamente a experiência do usuário. Com todas as coisas sendo igual, dispositivos otimizados foram projetados para maximizar a experiência do usuário com equipes e Skype para negócios e produzir qualidade superior. Use [MyAdvisor](https://aka.ms/myadvisor) para obter orientação sobre como desenvolver uma estratégia de preparação de dispositivo. |
| **Drivers** | Aplicando o patch de rede (Ethernet Wi-Fi), áudio, vídeo e drivers USB deve ser parte de sua estratégia de gerenciamento de patches geral. Muitos problemas de qualidade são resolvidos por Atualizando drivers. |
| **Salas de reunião Wi-Fi** | É altamente recomendável que os dispositivos de sala serão conectados à rede por meio de pelo menos uma conexão de Ethernet de 1 Gbps. Dispositivos de sala de reunião geralmente incluem vários fluxos de áudio e vídeos, juntamente com o conteúdo das reuniões como compartilhamento de tela e têm requisitos de rede mais que outras equipes ou Skype para pontos de extremidade de negócios. Salas de reunião são, por definição, dispositivos pardos onde Wi-Fi, garantindo um benefício apenas durante a instalação.<br><br>As salas de reunião precisam ser tratada com atenção para garantir que a experiência usando estes dispositivos é da reunião ou superar as expectativas e cuidados especiais. Problemas de qualidade com salas de reunião geralmente vai ser escalonado rapidamente, porque eles são geralmente usados pela equipe de nível sênior.<br><br>Com todas as coisas sendo igual (, além de conveniência), Wi-Fi desempenho é geralmente menor que uma conexão com fio. Com a elevação de políticas "traga seu próprio dispositivo" e a proliferação de laptops, pontos de acesso Wi-Fi frequentemente são exagerada utilizados. Não pode ser priorizadas mídia em tempo real em redes Wi-Fi, que podem resultar em problemas de qualidade durante os horários de pico de uso. Este uso pesado pode coincidir com uma reunião onde pode haver um pequeno número de pessoas na presença, cada um com seu próprio laptop e o smartphone, todos os conectados ao mesmo ponto de acesso Wi-Fi como a reunião dispositivo de sala.<br><br>Wi-Fi só deve ser considerado como uma solução temporária, para uma instalação móvel ou quando Wi-Fi tenha sido provisionada adequadamente para dar suporte a mídia empresarial, baseado em tempo real. |


### <a name="tcp"></a>TCP

TCP é considerado um transporte failback e não o transporte principal que você deseja para a mídia em tempo real. Isso é um transporte failback é devido à natureza do TCP com informações de estado. Por exemplo, se uma chamada for feita em uma rede latente e pacotes de mídia estão atrasados, em seguida, os pacotes de alguns segundos atrás — que não são mais úteis — competem por largura de banda chegar ao destinatário, que pode tornar um pior situação ruim. Isso torna o stitch de correção de áudio e áudio Alongar, resultando em artefatos audíveis, geralmente na forma de tremulação.

Os relatórios nesta seção não fizer uma distinção entre fluxos boas e ruins. Visto que UDP é o preferido, os relatórios procuram o uso de TCP para áudio, vídeo e vídeo-based (VBSS) de compartilhamento de tela. Taxas de fluxo de baixa são fornecidas para ajudar a comparar a qualidade UDP versus qualidade TCP para que você possa se concentrar os esforços de onde o impacto é o maior. Uso TCP é principalmente causado pelas regras de firewall incompleta. Para obter mais informações sobre regras de firewall para equipes e Skype para Business Online, consulte [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips).

> [!Important]
> Ter um [arquivo de construção válido](#building-mapping) carregados é altamente recomendável para que você pode distinguir rapidamente dentro de fluxos externos ao olhar para uso TCP.

> [!Note]
> Áudio, vídeo e VBSS preferem UDP como seu transporte principal. A carga de trabalho herdada do compartilhamento de aplicativos RDP usa apenas TCP.

#### <a name="tcp-usage"></a>Uso TCP

Relatórios TCP indica o uso geral de TCP nos últimos sete meses. Todos os relatórios mais nesta seção abordará estreitando pressionada prédios específicos e sub-redes onde o TCP é usado com mais frequência. Relatórios separados estão disponíveis para conferência e fluxos de duas partes.

![Gráfico mostrando a porcentagem de fluxos de áudio que usam TCP](media/qerguide-image-audiostreamswithtcp.png)
_Figura 25 – fluxos de áudio com o uso de TCP_


##### <a name="investigation"></a>Investigação

Usando este relatório, você pode responder às seguintes perguntas:

-   Qual é o volume total de fluxos TCP para o mês atual?
-   É melhor do que o mês anterior ou de pior?
-   É a tendência de uso do TCP aumentando, steady, ou diminuindo?
-   O PSR TCP é igual ao meu PSR geral?

Se notar que a tendência de uso do TCP está aumentando ou acima de utilização monthly normal, levar o tempo de investigar usando os sub-relatórios para procurar por qualquer prédios ou redes que possam precisar de remediação. O ideal é que você deseja, no mínimo com base em TCP sessões de áudio possível na rede gerenciada.

#### <a name="tcp-vs-udp"></a>TCP versus UDP

Este relatório identifica o volume de TCP versus no último mês para áudio, vídeo e vídeo-based (VBSS) de compartilhamento de tela do relatório de uso do UDP. 

![Relatório mostrando o volume dos fluxos que usam TCP versus UDP](media/qerguide-image-tcpvsudp.png)

_Figura 26 – TCP versus UDP - conferência_

##### <a name="analysis"></a>Análise

Embora você deseja o uso TCP ao ser tão baixa quanto possível, talvez você veja um pouco de uso TCP em uma implantação do contrário íntegro. TCP por si só não contribuem para uma chamada de baixa, portanto taxas de fluxo são fornecidas para ajudar a identificar se o uso TCP é um colaborador baixa qualidade. 

#### <a name="tcp-investigations"></a>Investigações TCP

Nos modelos de CQD fornecidos, navegue até os fluxos TCP por relatórios de criação e a sub-rede, usando as redes gerenciadas ou a todas as redes do modelo. Para fins de investigar o uso TCP, o processo é o mesmo, portanto focaremos a discussão sobre conferência.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado é recomendado para que você pode distinguir rapidamente dentro de fluxos externos ao olhar para uso TCP. 

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.                                  |

![Uso TCP Construindo e sub-rede](media/qerguide-image-tcpstreams.png)

_Figura 27 – TCP fluxos, criando - e sub-rede conferência_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você tiver recebido um alerta de diagnóstico "tráfego UDP está sendo limitado, que faz com que a qualidade de chamadas ruins" concentrar os esforços de remediação TCP nessas sub-redes pela primeira vez. O alerta identificou sub-redes onde o uso de TCP negativamente está afetando a qualidade da chamada.

##### <a name="remediation"></a>Remediação

Este relatório identifica prédios específicos e sub-redes que estão contribuindo para o volume de uso do TCP. Um relatório adicional também está incluído para identificar o IP de retransmissão Microsoft que foi usado na chamada para ajudar a isolar ausentes regras de firewall. Concentre os esforços de remediação nesses prédios que têm o maior volume de fluxos TCP para maximizar o impacto.

A causa mais comum de uso do TCP está faltando regras de exceção no firewalls ou proxies. Voltaremos falando proxies na próxima seção, portanto por enquanto concentrar os esforços nos firewalls. Usando o edifício ou sub-rede fornecido, você pode determinar o firewall que precisa ser atualizado.


_A tabela 11 - diretrizes de remediação de fluxos de TCP Construindo e sub-rede_

| Remediação        | Orientação     |
|--------------------|--------------------------------------|
| Configurar o firewall | Verifique se os [endereços e portas de IP do Office 365](https://aka.ms/o365ips) são excluídos do seu firewall. Para problemas relacionados à mídia TCP, enfatizar os esforços iniciais nos tópicos a seguir:<ul><li>Verifique se o cliente mídia sub-redes 13.107.64.0/18 e 52.112.0.0/14 em suas regras de firewall.</li><li>As portas UDP 3478 – 3481 são as portas de mídia necessária e devem ser abertas, caso contrário, o cliente falhará volta para a porta TCP 443.</li></ul> |
| Verifique se             | Use a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para verificar se há problemas com a conectividade às portas e endereços IP do Office 365 específicos do edifício afetado ou sub-rede.    |

### <a name="http-proxy"></a>Proxy HTTP

Os proxies HTTP não é o caminho preferido para estabelecer sessões de mídia, para uma infinidade de motivos. Muitas contêm recursos de inspeção de pacotes profunda que pode impedir conexões ao serviço sejam concluídas e introduzir interrupções causadas. Além disso, quase todos os proxies forçam TCP em vez de permitindo UDP, que é recomendado para melhor qualidade de áudio.

Sempre, recomendamos que você configure o cliente para conectar-se diretamente para equipes e Skype para serviços corporativos. Isso é especialmente importante para o tráfego de mídia-based.


> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado facilita adequadamente distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy. 


#### <a name="http-proxy-usage"></a>Uso de proxy HTTP

O relatório de fluxo de proxy HTTP nesta seção do modelo é muito semelhante os relatórios TCP. Ele não parece estar em estejam de chamadas ruins ou BOM, mas se a chamada é conectada por HTTP.

![Relatório de fluxos de áudio que usam o HTTP](media/qerguide-image-audiostreamswithhttp.png)

_Figura 28 – fluxos de áudio com o uso de Proxy HTTP_

##### <a name="analysis"></a>Análise

Você deseja ver como os fluxos de mídia HTTP pouca possível. Se você tiver fluxos atravessando seu proxy, consulte sua equipe da rede para garantir que as exclusões adequadas estão no local para que os clientes são roteamento diretamente para equipes ou Skype para sub-redes de mídia Business Online.

Se você tiver apenas um proxy de internet em sua organização, verifique as adequadas [URLs do Office 365 e exclusões de intervalo de endereços IP](https://aka.ms/o365ips). Se mais de um proxy de internet está configurado em sua organização, use o HTTP sub-recursos relatado para isolar qual construção ou sub-rede é afetado.

Para organizações que não é possível ignorar o proxy, certifique-se que o Skype para o cliente de negócios está configurado para entrar em corretamente quando ela está localizada atrás de um proxy, conforme descrito no artigo [Skype para negócios deve usar servidor proxy para entrar em vez de tentar direta conexão](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Investigações de proxy HTTP

Este relatório identifica prédios específicos e sub-redes que estão contribuindo para o uso do HTTP.

> [!IMPORTANT]
> Ter um válido [construção arquivo](#building-mapping) carregado facilita adequadamente distinguir dentro de fluxos de áudio externos ao analisar o uso de proxy.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.

![Relatório de uso do Proxy HTTP, criando e sub-rede](media/qerguide-image-httpproxyusage.png)

_Figura 29 – sub-rede e uso de Proxy HTTP, criando_

##### <a name="remediation"></a>Remediação

É [recomendável](/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) que você sempre desviar proxies para Skype para equipes, especialmente tráfego de mídia e de negócios. Proxies não fizer Skype para negócios mais seguro, porque seu tráfego já está criptografado. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Problemas como essas resultará em uma experiência negativa com áudio, vídeo e compartilhamento de tela, onde fluxos em tempo real são essenciais.

A causa mais comum de uso do HTTP está faltando regras de exceção de proxies. Usando o edifício ou sub-rede fornecida, você pode determinar rapidamente qual proxy precisa ser configurado para a mídia do desvio.

Verifique se os [FQDNs do Office 365](https://aka.ms/o365ips) de necessários estão na lista branca em seu proxy.

Para obter mais informações sobre como usar proxies com Skype para equipes e Business Online, consulte [Este artigo](/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online).

## <a name="endpoint-investigations"></a>Investigações de ponto de extremidade

Esta seção se concentra nas tarefas de relatórios em versões do cliente e o uso de dispositivos de certificados. Relatórios estão disponíveis para uso para versões do cliente, tipo de cliente, dispositivos de captura e drivers (microfone), os dispositivos de captura de vídeo e versões de fornecedor e driver Wi-Fi de estrutura de tópicos.

> [!NOTE]
> Nem todos os relatórios incluídos nos modelos são abordados neste guia; No entanto, os métodos de investigação explicado abaixo ainda se aplicam. Consulte a descrição do relatório individual para obter mais informações.

### <a name="client-versions"></a>Versões do cliente

Os relatórios neste espaço focalizar identificando Skype para versões do cliente de negócios em uso e seu volume relativo no ambiente.

> [!IMPORTANT]
> Atualmente, os clientes de equipes são distribuídos e atualizados automaticamente por meio da rede de entrega conteúdo do Windows Azure e serão mantidos atualizados pelo serviço. Atividades de investigação e preparação de cliente não se aplicam às equipes.

> [!Important]
> A menos que você excluir dados de participantes federados, esses relatórios incluirá telemetria de cliente de pontos de extremidade federados. Para excluir os pontos de extremidade federados, você deve adicionar um [filtro de consulta](#query-filters) para a segunda ID do inquilino definida como [ID do inquilino](#tenant-id)da sua organização. Como alternativa, você pode usar um [filtro de URL](#url-filter) para excluir telemetria participantes federada.

> [!NOTE]
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.

![Relatório de dispositivos e clientes](media/qerguide-image-clientversionreport.png)

_Figura 30 - relatório da versão de cliente_

#### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você tiver recebido um diagnóstico alerta "conhecidos mal executando versões do cliente estão em uso", focalizar atualizar esses clientes pela primeira vez. O alerta identificou que esses clientes negativamente estão afetando a qualidade da chamada. Você pode usar o relatório de dispositivos & cliente (mostrado acima) para ajudar a garantir que os clientes que têm problemas conhecidos não estão sendo atualizados.

#### <a name="remediation"></a>Remediação

Uma parte importante de acionadoras experiências de usuário de alta qualidade é garantir que clientes gerenciados estiverem executando versões atualizadas do Skype para a empresa, além de garantir o suporte de áudio, vídeo, rede e drivers USB estão atualizados. Isso oferece vários benefícios, entre eles: 

-   É mais fácil gerenciar algumas versões versus muitas versões.
-   Ele fornece um nível de consistência da experiência.
-   Ele facilita a solucionar problemas de qualidade de chamada e usabilidade.
-   A Microsoft dá continuamente aperfeiçoamentos gerais e as otimizações em todo o produto. Garantir que os usuários recebam essas atualizações reduz os riscos de executar um problema que já foi resolvido.

Limitar sua implantação para as versões do cliente que são menos de seis meses, melhorar a experiência geral do usuário e melhorar a capacidade, reduzindo o número de versões que precisam ser suportados.

Se você estiver usando somente Office Click-to-Run, você estará automaticamente dentro da janela de seis meses. Nenhuma ação adicional será necessária.

Se você tiver uma mistura de Click-to-Run e pacotes do installer (MSI), você pode usar o relatório para verificar se os clientes MSI estão sendo atualizados regularmente. Se você observar que os clientes são atrasado, trabalhar com a equipe responsável pelo gerenciamento de atualizações do Office e garantir que eles estiver aprovando e Implantando patches de cliente regularmente.

Também é importante considerar e certifique-se de que a rede, vídeo, USB e drivers de áudio estão sendo corrigido também. Pode ser fácil ignore esses drivers e não incluí-las em sua estratégia de gerenciamento de patch.

Números de versão do Skype para negócios podem ser encontrados por meio de links a seguir:

-   [Informações sobre atualizações para o Office ProPlus versões](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Histórico de atualização do Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Skype para downloads de negócios e atualizações](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivos

Para fazer uso de relatório do dispositivo de microfone, precisamos entender o conceito da pontuação média de opinião (MOS). MOS é a medida padrão ouro para medir a qualidade de áudio perceptivelmente. Ele é representado como uma classificação de inteiro de 0 a 5.

A base de todas as medidas de qualidade de voz é como uma pessoa percebe a qualidade de voz. Como ela é afetada pela percepção humana, é naturalmente subjetiva. Existem várias metodologias diferentes para testar subjetiva. A maioria das medidas de qualidade de voz são baseados em uma escala de classificação (ACR) categorização absoluta.

Em um teste subjetivo ACR, um número significativo de estatística de pessoas classificar seu qualidade da experiência em uma escala de 1 (ruim) a 5 (excelente). A média das pontuações é o MOS. O MOS resultante depende do intervalo de experiências que foram expostos ao grupo e ao tipo de experiência sendo classificada como.

Porque ele é impraticável para conduzir testes subjetivas de qualidade de voz para um sistema de comunicação em tempo real, o Microsoft Teams e Skype para negócios geram valores de MOS usando algoritmos avançados objetivamente prever os resultados de um teste subjetiva.

O conjunto disponível de MOS e métricas associadas fornecem um modo de exibição para a qualidade da experiência de ser entregue aos usuários por um dispositivo de áudio. 

Fornecendo aos usuários com dispositivos certificados para equipes e Skype for Business, você reduz a probabilidade de encontrando experiências negativas devido ao próprio dispositivo (que é mais provável, por exemplo, com microfones e alto-falantes laptop internas). Para obter mais informações, consulte estes artigos sobre o [programa de certificação](/SkypeForBusiness/certification/overview) e o [Catálogo de soluções de parceiro](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Os relatórios de dispositivo são usados para avaliar o uso do dispositivo por volume e MOS pontuação (apenas áudio) e podem ser encontrado nos modelos acompanha em clientes e dispositivos. 

> [!IMPORTANT]
> A menos que você excluir dados de participantes federados, esses relatórios incluirá telemetria de cliente de pontos de extremidade federados. Para excluir os pontos de extremidade federados, você deve adicionar um filtro de consulta para a **Segunda ID do inquilino** definida como [ID do inquilino](#tenant-id)da sua organização. Como alternativa, você pode usar um [filtro de URL](#url-filter) para excluir telemetria participantes federada.

> [!NOTE] 
> Certifique-se de ajuste o filtro de mês ano ao mês atual. Selecione **Editar**e ajustar o **Mês ano** para salvar o novo mês padrão.

> [!Note]
> Você poderá observar quando visualizem esse relatório que você veja o mesmo dispositivo relatado várias vezes. Isso acontece devido à maneira como o dispositivo é informado de serem reportados para CQD. Diferenças de hardware e de localidade do sistema operacional causam diferenças em como os dados do dispositivo são relatados.

![Relatório de dispositivos (microfone)](media/qerguide-image-devicesmicrophone.png)

_Figura 31 - relatam de dispositivos (microfone)_

##### <a name="diagnostic-alert"></a>Alerta de diagnóstico

Se você tiver recebido um alerta de diagnóstico enfocam "drivers de áudio estão causando quedas de chamada," correção esses drivers pela primeira vez. O alerta identificou que drivers ruim conhecidos estão fazendo com que as chamadas para descartar e negativamente estão afetando a confiabilidade de chamada. Você pode usar o relatório de Drivers de microfone (mostrado acima), que se encontra na seção do cliente e dispositivos, para ajudá-lo com o processo.

##### <a name="remediation"></a>Remediação

Normalmente, você precisará descobrir e a fase de dispositivos não certificados e substituí-los com os dispositivos de certificados. Algumas considerações ao revisar os relatórios do dispositivo incluem:

-   São os dispositivos em uso certificado para equipes e Skype para os negócios? 
-   Você pode identificar os usuários de um dispositivo específico por meio de [Análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Verifique para garantir que eles têm os drivers de dispositivo mais recentes e que seu dispositivo não está conectado por meio de um hub USB ou estação de encaixe. 
-   Quantos diferentes versões dos vários drivers estão em uso? São eles sendo corrigidos regularmente? Garantir que áudio, vídeo e drivers Wi-Fi estão sendo corrigidos regularmente ajudarão eliminar essas como uma fonte de problemas de qualidade e facilite o experiência do usuário mais previsíveis e consistentes.

##### <a name="audio"></a>Áudio

A próxima tarefa é determinar o uso geral de [dispositivos de áudio de certificado](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). É recomendável que pelo menos de 80 por cento de todos os fluxos de áudio de usar um dispositivo de áudio certificado. Isso é realizado melhor ao exportar o relatório de dispositivos de microfone para o Excel calcular o uso de dispositivos de certificados ou aprovados. As organizações geralmente manter uma lista de todos os dispositivos aprovados, para que filtragem e classificação dos dados devem ser simples.

##### <a name="video"></a>Vídeo

Drivers de vídeo são importante para manter atualizado também. Garantir que as placas de vídeo estão sendo corrigidas regularmente ajudará a excluir drivers de vídeo como uma fonte de baixa qualidade de fluxos de vídeo. Usar o [certificado para dispositivos de vídeo](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) ajudará a garantir uma experiência de usuário tranquila e de alta qualidade. Dispositivos de vídeos que suportam a codificação nativa do h. 264 preferidos, para reduzir o uso da CPU durante a conferência de vídeo.

##### <a name="wi-fi"></a>Wi-Fi

Drivers de Wi-Fi também precisam ser corrigido em uma cadência regular também e devem ser incluídos na sua estratégia de gerenciamento de patch. Muitos problemas de qualidade podem ser corrigidos mantendo drivers de Wi-Fi atualizadas. Para obter mais informações sobre como otimizar sua infraestrutura Wi-Fi, consulte [Este artigo sobre o planejamento de Wi-Fi](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>Apêndice 

### <a name="office-365-network-connectivity-principles"></a>Princípios de conectividade de rede do Office 365

Antes de começar a planejar sua rede para conectividade de rede do Office 365, é importante entender os princípios de conectividade para gerenciar o tráfego de Office 365 de forma segura e obter o melhor desempenho possível. O artigo a seguir o ajudarão a entender as orientações mais recentes para otimizar com segurança de conectividade de rede do Office 365:

[Princípios de conectividade de rede do Office 365](https://aka.ms/pnc)

### <a name="planning-for-wi-fi"></a>Planejamento para Wi-Fi

A abordagem da Microsoft para qualidade de unidade e agilidade para as redes sem fio vem com três partes: planejamento de ponta a ponta, práticas recomendadas no implantação e as operações e manutenção proativa. Este resumo da solução o orienta durante esse processo para garantir uma Skype sem fio de classe empresarial para a experiência de negócios:

[Garantindo que um Skype sem fio de classe empresarial para a experiência de negócios](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Guia de rede do Lync

Para obter mais informações em equipes e Skype para conceitos de rede de negócios e o raciocínio por trás de sua importância a qualidade, o [Lync Server 2013 Networking Guide](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) é aplicável.

### <a name="network-performance-requirements"></a>Requisitos de desempenho de rede

A qualidade de mídia em tempo real (áudio, vídeo e compartilhamento de aplicativos) sobre IP significativamente é afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter melhor equipes ou Skype para qualidade de mídia de negócios, sua rede deve atender aos seguintes métricas de desempenho de rede.

_A tabela 12 - requisitos de desempenho de rede_

| Métrica                            | Cliente para o Microsoft Edge           | Edge do cliente para o Microsoft Edge    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latência (unidirecional)                 | \<50 ms                            | \<30 ms                            |
| Latência (tempo de resposta, ou tempo de ida e volta) | \<100 ms                           | \<60 ms                            |
| Perda de pacote de intermitência                 | \<10% durante qualquer intervalo de 200 ms   | \<1% durante qualquer intervalo de 200 ms    |
| Perda de pacote                       | \<1% durante qualquer intervalo de 15 segundos    | \<0,1% durante qualquer intervalo de 15 segundos  |
| Tremulação entre chegadas de pacote       | \<30 ms durante qualquer intervalo de 15 segundos | \<15 ms durante qualquer intervalo de 15 segundos |
| Novo pedido de pacotes                    | \<% de 0,05 pacotes de fora de ordem       | \<pacotes de fora de ordem 0,01%      |

Para obter mais informações, consulte [Este artigo sobre o desempenho de rede e qualidade de mídia](https://aka.ms/performancerequirements) para equipes e Skype para negócios Online.

### <a name="other-resources"></a>Outros recursos

#### <a name="building-data-file"></a>Criando o arquivo de dados

-   [Ativando e usando o painel de controle de qualidade de chamada para Teams da Microsoft e Skype para Business Online](turning-on-and-using-call-quality-dashboard.md)

#### <a name="cqd-training"></a>Treinamento de CQD

-   <https://aka.ms/sof-cqd>

-   Guia de [Introdução ao CQD](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) e workshop

-   [Dimensões e mensurações disponíveis no Painel de Qualidade de Chamadas](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Treinamento de análise de chamada

-   [Apresentando a análise de chamada](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurar a análise de chamada](set-up-call-analytics.md)

-   [Qual é a diferença entre a Análise de Chamada e o Painel de Qualidade de Chamadas?](difference-between-call-analytics-and-call-quality-dashboard.md)

-   [Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

### <a name="call-analytics-support"></a>Suporte de análise de chamada

-   Comunidade: [Skype para o programa de visualização de negócios](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

-   Para obter suporte, entrar em nosso portal de visualização [www.skypepreview.com](http://www.skypepreview.com), selecione **um problema de relatório**e usar a opção **Criar novo Bug** para relatar algum problema. Observe que os engenheiros de suporte estão disponíveis para oferecer suporte de segunda à sexta-feira, entre os horários de 6 horas e a hora do Leste 9 PM (Estados Unidos). Solicitações fora essas horas serão priorizadas do dia seguinte.

### <a name="devices"></a>Dispositivos

-   [Skype para soluções de negócios pessoais periféricos & PCs de catálogo](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Relatórios de locatário

-   [Pacote de conteúdo de adoção do Office 365](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Análise de uso do Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Relatórios do Skype for Business Online](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Relatórios de Teams da Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
