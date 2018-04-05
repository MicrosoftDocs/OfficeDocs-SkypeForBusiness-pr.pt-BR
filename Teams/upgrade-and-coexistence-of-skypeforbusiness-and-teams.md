---
title: Jornada de atualização e coexistência do Skype para Teams da Microsoft e de negócios
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/04/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Detalhes do Skype para opções de coexistência de negócios e Teams da Microsoft e modos de viagens atualização às equipes do Skype for Business com cenários de exemplo.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46967004ec571e593ea3f73e213c3d0e5b801f86
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="upgrade-journey-and-coexistence-of-skype-for-business-and-microsoft-teams"></a>Jornada de atualização e coexistência do Skype para Teams da Microsoft e de negócios

Como um Skype existente para o cliente de negócios, sua transição completa para equipes pode levar algum tempo. No entanto, você pode começar a perceber o valor de equipes hoje em dia, permitindo que os usuários usem equipes junto com Skype para negócios. Visto que há algumas funcionalidades podem sobreposição entre os dois aplicativos, recomendamos que você examine os modos de atualização disponíveis para ajudar a determinar qual caminho é certo para sua organização. Por exemplo, você pode optar por habilitar todas as cargas de trabalho em ambas as soluções sem interoperabilidade. Ou, talvez você decida gerenciar a experiência do usuário, pelo gradualmente introduzindo recursos de equipes ou pelo direcionamento de grupos de usuários para selecionar recursos, até que a sua organização estiver pronta para atualizar todos para equipes.

Assim como acontece com qualquer implantação, recomendamos que você para [testar seu plano pretendido](pilot-essentials.md) com um grupo selecionado de usuários antes de implantá equipes em sua organização ampla. Lembre-se de que pode ser destrutivos para usuários introduzindo nova tecnologia. Demore para avaliar a preparação do usuário e implementar um plano de treinamento para impedir que os usuários a tomar conhecimento e acelerar sua aceitação de equipes e de comunicação. 

> [!IMPORTANT]
> Skype para a jornada de atualização está evoluindo rapidamente as equipes de negócios. Este artigo o ajudarão a entender a atualização de equipes próxima, mas ele não inclui instruções de atualização de ponta a ponta. Uma atualização bem-sucedida do Skype para negócios incluirá as atividades de preparação focados técnico e do usuário. Estamos trabalhando nesta orientação agora e podemos vai ser publicá-lo em breve.
 
## <a name="upgrade-and-coexistence-modes-defined"></a>Modos de atualização e coexistência definidos
Para ajudar a orientar seu processo de tomada de decisão, familiarize-se com os vários modos, conceitos e terminologia relevante para atualização do Skype for Business para equipes.

### <a name="skype-for-business-with-teams-collaborationndashonly-mode"></a>Skype for Business com colaboração de equipes&ndash;somente modo

Neste modo, equipes é configurado para suportar o equipes e conversas com base no canais somente com bate-papos privadas, chamadas e reuniões desabilitadas.

Esse modo é uma ótima maneira de introduzir equipes em seu ambiente enquanto você continuar alavancar o investimento existente em Skype para negócios. 

### <a name="skype-for-business-with-teams-collaboration-and-meetings-mode"></a>Skype for Business com o modo de reuniões e colaboração de equipes
Junto com usando equipes para equipes e baseada no canais de conversas neste modo, os usuários iniciam usando equipes para agendar e conduzir suas reuniões. Bate-papos privadas e voz e chamadas de vídeo, permanecem no Skype para negócios.

Se sua organização precisa os recursos que equipes fornece para reuniões, mas business precisa exigem que você mantenha enterprise recursos de voz no Skype for Business, você pode configurar equipes para oferecer Skype for Business com reuniões e colaboração de equipes recursos para toda sua organização (ou algumas partes dele).

### <a name="islands-mode"></a>Modo de ilhas
Esse é o modo padrão. Você pode usá-lo para implantar as equipes independentemente Skype para negócios. 

Neste modo, equipes usuários podem imediatamente usar equipes com todos os seus recursos com outros usuários de equipes, enquanto outros usuários possam continuar usando o Skype para negócios e mantenha-se produtivo sem impacto sobre como estejam usando Skype para negócios hoje.

> [!NOTE]
> Modo de ilhas vem com unidirecional interoperabilidade temporária que permite a interoperabilidade de bate-papo de equipes para Skype para negócios quando as seguintes condições forem atendidas:
> - O usuário equipes é hospedado em e habilitado para, Skype para Business Online.
> - O Skype para o usuário de negócios nunca usou equipes (ou não está licenciado para equipes).
>
> Esse modo é útil quando você deseja que os usuários que estão usando principalmente o equipes para se conectar com outros usuários na organização que ainda estão usando Skype para negócios apenas.
>
> Depois que os usuários que anteriormente usado apenas Skype para negócios começarem a usar as equipes, todos os seus chats de outros usuários equipes chegará em equipes. Isso alterna a esses usuários para o modo de ilhas. A partir desse momento, eles devem manter executando equipes para garantir que elas permanecem conectadas com os outros usuários equipes na organização.

### <a name="teams-only-mode"></a>Modo somente equipes
Neste modo atualizados, o Skype para o cliente de negócios não fornece mais operação básica desse recurso, indicadores de presença, bate-papo, chamada ou capacidades de reunião. Os usuários que trabalham no modo atualizado devem usar equipes como seu ferramenta principal de comunicação e colaboração.

Os usuários que estão prontos para uso equipes como sua principal ferramenta de comunicação e colaboração podem ser atualizados como usuários somente equipes.

Um usuário atualizado só pode usar o Skype para o cliente de negócios para ingressar Skype existente para reuniões de negócios ou reuniões em Skype para negócios organizados por usuários não atualizado ou parceiros externos. Um usuário atualizado pode continuar a se comunicar com outros usuários na organização que ainda estejam usando Skype para negócios usando os recursos de interoperabilidade entre equipes e Skype para negócios.

### <a name="skype-for-businessndashonly-mode"></a>Skype para negócios&ndash;somente modo
Os usuários que precisam ficar em Skype para negócios podem ser configurado como Skype para negócios&ndash;somente os usuários. Os usuários configurados neste modo serão impedidos de usando equipes e serão capazes de se comunicarem com usuários somente equipes, usando os recursos de interoperabilidade entre equipes e Skype para negócios.

## <a name="upgrade-and-coexistence-building-blocks"></a>Blocos de construção de atualização e coexistência
Para preparar formalmente a sua organização para sua jornada para equipes, você precisa começar a planejar os cenários de atualização que eventualmente permitirá que sua organização adotará totalmente equipes como suas comunicações exclusiva e solução de colaboração.

Quando alguns dos seus usuários estiver prontos para usar apenas as equipes de suas comunicações diárias e colaboração necessidades, você poderá começar a atualizar esses usuários às equipes habilitando o modo somente equipes para eles.

Se não for viável para toda a organização mover para equipes, você pode iniciar adotando totalmente equipes como uma solução de colaboração de grupo primeiro enquanto mantém Skype para negócios como solução de comunicação unificada da sua organização. Outra opção é iniciar movendo reuniões para equipes além apresentando os recursos de colaboração do grupo de equipes, mantendo o restante dos recursos de comunicação unificada no Skype para negócios.

![Uma captura de tela da atualização blocos de construção do Skype for Business para equipes, consistindo Skype for Business com colaboração de equipes&ndash;modo exclusivo, Skype for Business com colaboração de equipes e modo de reuniões, modo Ilhas, modo somente equipes e Skype para Business&ndash;somente modo.](media/upgrade_and_coexistence_building_block.png)

A tabela a seguir compara os modos de atualização e coexistência.

|Modo  |Situação  |Metas de curto prazo  |Vantagens  |Advertências  |
|---------|---------|---------|---------|---------|
|Skype for Business com apenas a colaboração de equipes |Skype para implantação de negócios com requisitos que ainda não forem atendidas por equipes (por exemplo, conformidade avançados)<br><br>Necessidade de longo prazo de e/ou compromisso em Skype para negócios|Iniciar a adoção de equipes rapidamente, concentrando-se pela primeira vez em colaboração de grupo<br><br> Deseja manter todas as cargas de trabalho de comunicação unificada em Skype for Business para agora|Não há recursos sobreposição entre equipes e Skype para negócios<br><br>Mensagens instantâneas e bate-papo residirão em Skype para negócios (vinculados à chamada)<br><br>|
|Skype for Business com reuniões e colaboração de equipes |Skype para implantação de negócios com o uso significativo do enterprise voice e requisitos que ainda não forem atendidos por equipes chamar<br><br>Necessidade de longo prazo de e/ou compromisso em Skype para negócios<br><br>Pode estar usando um serviço de reunião de terceiros|Iniciar a adoção de equipes rapidamente, ultrapassando a colaboração de grupo<br><br>Melhorar a experiência de reuniões dos usuários|Não há recursos de sobreposição<br><br>Reuniões de alto valor em equipes (WebRTC, gravações de reuniões de nuvem e assim por diante)|Mensagens instantâneas e bate-papo residirão em Skype para negócios (vinculados à chamada)|
|Ilhas |Skype menor ou mais simples para implantação de negócios<br><br>Capacidade e a disposição para gerenciar alguma complexidade a curto prazo para mover para equipes mais rapidamente |Vá para a experiência de equipes completa mais depressa possível<br><br>Conduzir uma prova de conceito (PoC) de equipes |Simples de operar, sem interoperabilidade<br><br>Melhor experiência de equipes inicial para todos os recursos |Requer a comunicação do usuário bom para evitar confusões e para o uso da unidade em direção de equipes<br><br>Estratégia de saída requer que os usuários totalmente adotaram equipes pelo tempo Skype para negócios é desativado|
|Somente as equipes |Precisam de alguns usuários permaneçam em Skype para negócios<br><br>Você está atualizando seu Skype para usuários corporativos Online para equipes enquanto mantém Skype for Business usuários locais no Skype para Business Server<br><br>Você talvez já tenha implantado usuários no modo de ilhas e esteja pronto para retirar Skype for Business para grupos de usuários |Reduzir custos de variáveis no Skype para negócios (as operações do servidor local, contrato de terceirização e assim por diante)<br><br>Vá para a experiência de equipes completa assim que possível, para pelo menos alguns usuários|Limita a confusão do usuário, fornecendo apenas um cliente para trabalhar com|Interoperabilidade suporta apenas o bate-papo básica e chamadas entre equipes e Skype para negócios|
|Skype para negócios apenas |Precisam de alguns usuários permaneçam em Skype para negócios<br><br>|Limita a confusão do usuário, fornecendo apenas um cliente para trabalhar com|Continuar a atender aos requisitos de negócios que atualmente só podem ser atendidos por Skype para negócios|Interoperabilidade suporta apenas o bate-papo básica e chamadas entre equipes e Skype para negócios|

> [!NOTE]
> Para ajudá-lo a permitir que cada um dos modos descritos acima, nós iremos publicá um guia de início rápido sobre como executar sua jornada do Skype para negócios às equipes quando as diretivas estão disponíveis em um momento posterior. Não perca!

## <a name="upgrade-journeys"></a>Atualização de viagens
Você pode levar várias abordagens para atualização do Skype para a empresa, seja online ou no local, às equipes:
- Em uma simple jornada de atualização, você primeiro implante equipes em Skype for Business com colaboração de equipes&ndash;apenas como parte da avaliação e adoção antecipada e, em seguida, implementar somente equipes modo com o objetivo de retirada eventualmente Skype para negócios do ambiente para todos os usuários na organização.
- Uma jornada de atualização gradual oferece um modo de atualização específico a um grupo específico de usuários (também chamado de um *cohort*), dependendo de suas comunicações e requisitos de colaboração. Ao longo do tempo, toda a organização pode convergem em usando apenas o equipes e eventualmente substituir Skype para negócios. No entanto, se sua organização tem atraentes razões de negócios para manter Skype para negócios — como uma dependência em uma solução baseada no Unified Communications Managed API UCMA que integra-se com aplicativos de linha de negócios ou uma solução de parede ética disponível no momento para Skype para negócios apenas — você pode atualizar a maioria dos usuários para o modo somente equipes enquanto mantém Skype para usuários comerciais em um do Skype para modos de negócios de uma parte de sua população de usuários.

> [!IMPORTANT]
> Para ambos os tipos de atualização jornada, se sua organização está atualmente um Skype Business local apenas para implantação, será necessário começar a planejar, implementar Skype para híbrido de negócios antes de atualizar seus usuários para o modo somente equipes. Isso também ajuda a facilitar a interoperabilidade com equipes.
> Use [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para orientar sua Skype para a implementação híbrida de negócios.

> [!NOTE]
> Modo somente equipes exige que os usuários que fazem parte do colaboradores ser hospedados no Skype para Business Online e uma relação de híbrido entre seu Skype para implantação no local de negócios e seu Skype para locatário Business Online é necessária para facilitar a atualização e interoperabilidade entre equipes e Skype para negócios. A mudança para Skype para Business Online deve ser concluída para usuários que fazem parte dos colaboradores antes que eles estão atualizados para o modo somente equipes. Planejar a Skype para Business Server 2019 e também uma atualização cumulativa futura do Skype para negócios 2015 do servidor simplificar a mecânica da atualização de usuários locais para equipes Gerenciando a migração para o Skype para Business Online e atualizando os usuários para equipes somente modo em uma única etapa.

Seja qual for o journey que você escolher, Microsoft aqui é oferecer suporte a você pelo processo de atualização. De requisitos técnicos para recursos de preparação do usuário, podemos dividirá as diretrizes e práticas recomendadas para ajudar a garantir uma transição bem-sucedida do Skype para negócios às equipes. Orientação detalhada de atualização será estar pronto em breve, portanto, verifique novamente para obter mais informações.

### <a name="simple-upgrade-journey"></a>Simple jornada de atualização
A jornada simple de atualização é ilustrada no diagrama a seguir.

![Uma captura de tela da atualização jornada simple. Todos os usuários inicialmente usar equipes em Skype for Business com colaboração de equipes&ndash;somente modo, então a transição para o modo somente equipes, com o estado final do toda a organização atualizado para equipes.](media/upgrade_and_coexistence_simple_upgrade_journey.png)

Equipes é implantada para todos os usuários na organização e configurado em Skype for Business com colaboração de equipes&ndash;somente modo. Quando sua organização determina que equipes está pronta para atender a todas as suas comunicações e necessidades de colaboração, todos os usuários são atualizados para o modo somente equipes. Nesse momento, Skype for Business pode ser retirado do ambiente.

### <a name="gradual-upgrade-journey"></a>Jornada de atualização gradual
Um exemplo de uma jornada de atualização gradual é ilustrado no diagrama a seguir.

![A jornada de atualização gradual, colaboradores de usuários inicialmente usam equipes em uma variedade de modos de atualização, lado a lado com Skype para negócios. Transição alguns colaboradores para o modo somente equipes, enquanto um grupo de usuários permanece com Skype for Business com colaboração de equipes e modo de reuniões.](media/upgrade_and_coexistence_gradual_upgrade_journey.png)

Usando os modos de atualização diferentes para diferentes grupos de usuários ou colaboradores, equipes é implantado na organização. Por exemplo, um grupo de usuários que pode ser habilitado para o modo de ilhas, outro habilitado para Skype for Business com colaboração de equipes e o modo de reuniões, enquanto um terceiro grupo de usuários inicialmente pode ser habilitado para Skype for Business com colaboração de equipes&ndash;somente modo.

Ao longo do tempo, os grupos de usuários podem ser atualizados para o modo somente equipes, seguido do resto da organização. Eventualmente, toda a organização será pronta para retirar Skype para negócios e usar apenas as equipes para comunicação e colaboração, ou — se os requisitos de negócios determinam que Skype para negócios ser retidos por um grupo específico — a maioria dos usuários no organização pode usar apenas as equipes. <br><br>
<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul> Qual jornada de atualização é adequada para os requisitos de negócios da sua organização?<br><br></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul> Identificando seu modelo de implantação atual, use a cenários de caso e considerações fundamentais para sua organização informará a jornada para equipes que é mais adequada para sua organização.<br><br></ul></td></tr>
</table>

## <a name="upgrade-scenarios"></a>Cenários de atualização
Com base nas atualização de viagens descritas anteriormente neste artigo, a seguinte orientação prescritiva é fornecida para Skype específica para modelos de implantação de negócios pode mapear para o seu modelo de implantação atual. 

|Modelo de implantação  |Ponto de partida  |Considerações  |Jornada  |
|---------|---------|---------|---------|
|Skype para negócios Online – somente com a chamada de planos |Inquilino do Office 365 com o Azure Connect da AD, SharePoint Online, o Exchange Online e Skype para negócios Online<br><br> Sistema telefônico com chamar planos implementada usando Skype para Business Online para todos os usuários |Todos os usuários aproveitar headsets certificados<br><br> Reuniões exigem internos e anônimos VoIP os participantes externos<br><br> Mensagens inclui contatos internos e externos |**Mapa de mensagens**: o recurso de Federação destinado para lançamento T2 de 2018<br><br> **Mapa de reuniões**: recursos desejados já estão disponíveis<br><br> **Chamar o mapa**: recursos desejados já estão disponíveis<br><br> Blocos de construção:<ul><li> Skype for Business com colaboração de equipes&ndash;somente modo</li><li> Modo somente equipes</li></ul>|
|Skype para negócios Online com o conector de nuvem Edition (CCE) |Inquilino do Office 365 com o Azure Connect da AD, SharePoint Online, o Exchange Online e Skype para negócios Online<br><br> Sistema telefônico com voz híbrida via CCE implementado usando Skype para negócios Online em vários locais do office<br><br> 1.000 usuários estiver usando somente cargas de mensagens e voz|80% da população usuário aproveita o sistema telefônico com voz híbrida via CCE<br><br> Todas as mensagens está contido dentro da empresa<br><br> Reuniões não estão sendo usados no momento, mas não há interesse em Habilitar conferência de áudio no futuro|**Mapa de mensagens**: recursos que você deseja estão disponíveis<br><br> **Mapa de reuniões**: requisitos do futuro podem ser atendidos<br><br> **Chamar o mapa**: direcionar circulação ao recurso de equipes destinado para lançamento T2 de 2018 <br><br> Blocos de construção:<ul><li> Skype for Business com o modo de reuniões e colaboração de equipes</li><li> Modo somente equipes</li></ul> |
|Skype para o híbrido de negócios |Inquilino do Office 365 com o Azure Connect da AD, SharePoint Online, o Exchange Online e Skype para negócios Online<br><br> Skype para negócios 2015 de servidor implantada e híbrido é configurado com Skype para Business Online|Um número de usuários exige a capacidade de gravar reuniões<br><br> Há 10 salas de conferência, aproveitando atualmente v2 de sistemas de sala do Skype<br><br> A organização quer tirar proveito das equipes como uma ferramenta de colaboração mais depressa possível|**Mapa de mensagens**: recursos que você deseja estão disponíveis<br><br> **Mapa de reuniões**: gravação de reunião, o recurso de dispositivos de sala destinado para lançamento T2 de 2018 da reunião em nuvem<br><br> **Chamar o mapa**: recursos que você deseja estão disponíveis<br><br> Blocos de construção:<ul><li>Skype for Business com colaboração de equipes&ndash;somente modo</li><li> Skype for Business com o modo de reuniões e colaboração de equipes</li><li>Modo de ilhas</li><li>Modo somente equipes</li></ul> |
|Skype para Business Server (no local) |Inquilino do Office 365 com o Azure Connect da AD e o Exchange Online<br><br> SharePoint e Skype para negócios são implantados no local|Completo do enterprise voice do conjunto de recursos (Skype para Business Server 2015) atualmente em uso<br><br> Central de contato implantado<br><br> Reuniões são conduzidas com usuários federados internos e externos, usando VoIP e conferência discada<br><br> Mensagens com usuários internos e externos|Implantar o SharePoint Online<br><br> Configurar Skype para o híbrido de negócios (domínio dividido)<br><br>**Mapa de mensagens**: o recurso de Federação destinado para lançamento T2 de 2018<br><br> **Mapa de reuniões**: federados participação da reunião, recurso de lobby PSTN destinado para lançamento T2 de 2018<br><br> **Chamar o mapa**: recurso destinado para lançamento T4 de 2018 em diante<br><br>Blocos de construção:<ul><li>Modo de ilhas (piloto)</li><li>Skype for Business com colaboração de equipes&ndash;somente modo</li><li>Skype for Business com o modo de reuniões e colaboração de equipes</li><li>Modo somente equipes e Skype para negócios&ndash;somente modo</li></ul><br>Investigar a atualização para o Skype para Business Server 2019|

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul> Qual cenário de atualização é aplicável a sua organização?<br><br></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul> Decida o cronograma da jornada de atualização da sua organização com base em mensagens, reuniões e chamando os requisitos de negócios.<br><br> Decida o trabalho adicional necessário para concluir sua jornada de atualização.<br><br></ul></td></tr>
</table>

## <a name="see-also"></a>Consulte também
[Gerenciar equipes durante a transição para o novo Teams da Microsoft e Skype para Business Admin Center](manage-teams-skypeforbusiness-admin-center.md)
