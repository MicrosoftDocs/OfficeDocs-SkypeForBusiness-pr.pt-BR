---
title: Microsoft Teams atualizar do Skype for Business | Modos de coexistência
author: lsomi
ms.author: lsomi
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen, bjwhalen
description: Detalhes do Skype para opções de coexistência de negócios e Teams da Microsoft e modos de viagens atualização às equipes do Skype for Business com cenários de exemplo.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 22bd17ffbb29695f69aa4eff8581821a882f1614
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30649192"
---
![Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação] (media/upgrade-banner-deployment.png "Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação")

Este artigo faz parte do estágio de implantação e a implementação da sua jornada de atualização. Antes de continuar, confirme que você tiver concluído as seguintes atividades:

- [Inscrito seus participantes do projeto](upgrade-enlist-stakeholders.md)
- [Definido o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Escolher sua atualização jornada Skype for Business para equipes

Como um Skype existente para o cliente de negócios, sua transição completa para equipes pode levar algum tempo. No entanto, você pode começar a perceber o valor de equipes hoje em dia, permitindo que os usuários usem equipes junto com Skype para negócios. Visto que há algumas funcionalidades podem sobreposição entre os dois aplicativos, recomendamos que você revise a coexistência disponível e atualizar modos para ajudar a determinar qual caminho é certo para sua organização. Por exemplo, você pode optar por habilitar todas as cargas de trabalho em ambas as soluções sem interoperabilidade. Ou, talvez você decida gerenciar a experiência do usuário, pelo gradualmente introduzindo recursos de equipes ou pelo direcionamento de grupos de usuários para selecionar recursos, até que a sua organização estiver pronta para atualizar todos para equipes. Use o resultado de seu piloto para ajudar a avaliar a jornada atualização direita para a sua organização.

> [!IMPORTANT]
> Este artigo descreve os vários modos que permitem que você gerencie quais modalidades no Skype para negócios e equipes estão disponíveis para os usuários. Assim como acontece com qualquer implantação, recomendamos que você para [testar seu plano pretendido](pilot-essentials.md) com um grupo selecionado de usuários antes da atualização de sua organização para equipes. Lembre-se de que pode ser destrutivos para usuários introduzindo nova tecnologia. Demore para avaliar a preparação do usuário e implementar um plano de treinamento antes da implementação de qualquer um dos modos descritos neste documento e de comunicação.

## <a name="upgrade-journey-building-blocks"></a>Blocos de construção jornada de atualização

Para preparar formalmente a sua organização para sua jornada para equipes, você precisa começar a planejar os cenários de atualização que eventualmente permitirá que sua organização adotará totalmente equipes como suas comunicações exclusiva e solução de colaboração.

Para ajudar a orientar seu processo de tomada de decisão, familiarize-se com os vários modos, conceitos e terminologia relevante para atualização do Skype for Business para equipes. Para obter mais informações, consulte [as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](https://aka.ms/SkypeToTeams-Coexist)

Quando alguns dos seus usuários estiver prontos para usar apenas as equipes de suas comunicações diárias e colaboração necessidades, você poderá começar a atualizar esses usuários às equipes habilitando o modo **Equipes apenas** para eles.

Se não for viável para toda a organização mover para equipes, você pode iniciar com piloto equipes junto com Skype for Business no modo de coexistência **Ilhas** . Conforme os modos de coexistência adicionais, (isto é, **Skype for Business com colaboração de equipes** e **Skype for Business com reuniões e colaboração de equipes**) são disponibilizados progressivamente totalmente nos próximos meses, você também pode iniciar pelo totalmente adotando equipes como uma solução de colaboração de grupo primeiro enquanto mantém Skype para negócios como solução de comunicação unificada da sua organização. Que é o caminho recomendado da Microsoft para clientes que usam o Skype para clientes e servidor de negócios (local ou híbrida) com complexidade significativa cuja trajetória às equipes incluirá um período de coexistência longo.

![Uma captura de tela da atualização blocos de construção do Skype for Business para equipes, consistindo Skype for Business com colaboração de equipes&ndash;modo exclusivo, Skype for Business com colaboração de equipes e modo de reuniões, modo Ilhas, modo somente equipes e Skype para Business&ndash;somente modo.](media/upgrade_journeys_building_block.png)

A tabela a seguir compara os modos de coexistência e atualização.

|Modo |Situação |Uso recomendado |Vantagens |Advertências |
|---|---|---|---|---|
|Ilhas |Skype menor ou mais simples para implantação de negócios<br><br>Capacidade e a disposição para gerenciar alguma complexidade a curto prazo para mover para equipes mais rapidamente |Vá para a experiência de equipes completa mais depressa possível<br><br>Conduzir uma prova de conceito (PoC) de equipes<br><br>Caminho de atualização recomendado para organizações que adotado Skype para Business Online |Simples para operar<br><br>Experiência de equipes mais sofisticada inicial para todos os recursos |Requer a comunicação do usuário bom para evitar confusões e para o uso da unidade em direção de equipes<br><br>Estratégia de saída requer que os usuários totalmente adotaram equipes antes de iniciar a atualização para equipes somente fase<br><br>Não há interoperabilidade para usuários no modo de ilhas; também nenhum federação de equipes quando Skype do usuário para a conta comercial é hospedado no local|
|Skype for Business com colaboração de equipes |Skype para implantação de negócios com requisitos que ainda não forem atendidas por equipes (por exemplo, conformidade avançados)<br><br>Necessidade de longo prazo de e/ou compromisso em Skype para negócios|Iniciar a adoção de equipes rapidamente, concentrando-se pela primeira vez em colaboração de grupo<br><br>Deseja manter todas as cargas de trabalho de comunicação unificada em Skype for Business para agora<br><br>Uso como ponto de partida para a organização iniciar sua jornada no local (ou híbrida) recomendado Skype para negócios|Não há recursos sobreposição entre equipes e Skype para negócios<br><br>Mensagens instantâneas de bate-papo e agendamento de reuniões residirá no Skype para negócios (vinculados à chamada)<br><br>Interoperabilidade com usuários em equipes somente|
|Skype for Business com reuniões e colaboração de equipes |Skype para implantação de negócios com o uso significativo do enterprise voice e requisitos que ainda não forem atendidos por equipes chamar<br><br>Necessidade de longo prazo de e/ou compromisso em Skype para negócios<br><br>Pode estar usando um serviço de reunião de terceiros|Iniciar a adoção de equipes rapidamente, ultrapassando a colaboração de grupo<br><br>Melhorar a experiência de reuniões dos usuários<br><br>Uso recomendado para em organizações locais querer tirar proveito das reuniões de equipes antes de ser pronto para atualizar totalmente (geralmente devido ao Enterprise Voice no local). |Não há recursos de sobreposição<br><br>Reuniões superiores em equipes. Plataforma de mapa, eu e cruzado de recursos, a qualidade e a confiabilidade<br><br>Experiências de "Melhor juntos" entre equipes e Skype para negócios<br><br>Usuários de interoperabilidade em equipes apenas.|Mensagens instantâneas e bate-papo residirão em Skype para negócios (vinculados à chamada)|
|Somente as equipes |Precisam de alguns usuários permaneçam em Skype para negócios<br><br>Você está atualizando seu Skype para usuários corporativos Online para equipes enquanto mantém Skype for Business usuários locais no Skype para Business Server<br><br>Você talvez já tenha implantado usuários no modo de ilhas e esteja pronto para retirar Skype for Business para grupos de usuários |Reduzir custos de variáveis no Skype para negócios (as operações do servidor local, contrato de terceirização e assim por diante)<br><br>Vá para a experiência de equipes completa assim que possível, para pelo menos alguns usuários|Limita a confusão do usuário, fornecendo apenas um cliente para trabalhar com a interoperabilidade com usuários em Skype para negócios apenas, Skype para negócios com colaboração de equipes, Skype for Business com reuniões e colaboração de equipes|Interoperabilidade suporta apenas o bate-papo básica e chamar entre Skype para equipes e de negócios e escalonamento de interoperabilidade cenários para o compartilhamento da área de trabalho e bate-papo com vários participante e chamadas|
|Skype para negócios apenas |Precisam de alguns usuários permaneçam em Skype para negócios<br><br>|Limita a confusão do usuário, fornecendo apenas um cliente para trabalhar com<br><br>Usuário ainda pode participar de reuniões de equipes, a que eles são convidados|Continuar a atender aos requisitos de negócios que atualmente só podem ser atendidos por Skype para negócios<br><br>Interoperabilidade com usuários em equipes somente|Interoperabilidade suporta apenas o bate-papo básica e chamar entre Skype para equipes e de negócios e escalonamento de interoperabilidade cenários para o compartilhamento da área de trabalho e bate-papo com vários participante e chamadas|

## <a name="upgrade-journeys"></a>Atualização de viagens

Você pode levar várias abordagens para atualização do Skype para a empresa, seja online ou no local, às equipes:

- Em uma jornada atualização direta, você primeiro implante equipes junto com Skype for Business no modo de **Ilhas** como parte da avaliação e adoção antecipada e depois atualize seus usuários para o modo **Equipes somente** com o objetivo de retirada rapidamente Skype para negócios do ambiente para todos os usuários na organização. Isso é a jornada recomendada para clientes do Skype Business online, a menos que sejam preocupado com que seus usuários vai ser confundidos com ter duas ferramentas para conduzir a mesma ação (bate-papo, chamada, agendamento de reunião).
- Uma jornada de atualização gradual oferece um coexistência específica e o modo de atualização para um grupo específico de usuários (também chamado de um *cohort*), dependendo de suas comunicações e requisitos de colaboração. Ao longo do tempo, toda a organização pode convergem no usando apenas equipes e eventualmente substituir Skype para negócios. No entanto, se sua organização tem atraentes razões de negócios para manter Skype para negócios — como uma dependência em uma solução baseada no Unified Communications Managed API UCMA que integra-se com aplicativos de linha de negócios ou uma solução de parede ética disponível no momento para Skype para negócios apenas ou uma implantação do Enterprise Voice complexa que levará tempo para atualizar para **Equipes apenas**— você pode atualizar uma parte dos usuários para o modo de **Equipes apenas** enquanto mantém Skype para usuários comerciais em um do modos de coexistência para uma parte da sua população de usuários. Jornada de atualização gradual é clientes abordagem recomendada para o local (e híbrida) começando com Skype for Business com o modo de coexistência de colaboração de equipes e mover a partir daí para o modo de equipes somente quando atendidos requisito para os usuários (possivelmente até o Skype for Business com o modo de coexistência de reuniões e colaboração de equipes).

> [!IMPORTANT]
> Para ambos os tipos de atualização jornada, se sua organização está atualmente um Skype Business local apenas para implantação, será necessário começar a planejar, implementar Skype para híbrido de negócios antes de atualizar seus usuários para o modo **Somente equipes** . Isso também ajuda a facilitar a interoperabilidade com equipes.
>
> Use [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para orientar sua Skype para a implementação híbrida de negócios.

> [!NOTE]
> **Equipes somente** modo exige que os usuários que fazem parte do colaboradores ser hospedados no Skype para Business Online e uma relação de híbrido entre seu Skype para implantação no local de negócios e seu Skype para locatário Business Online é necessária para facilitar a interoperabilidade entre equipes e Skype para negócios. A mudança para Skype para Business Online deve ser concluída para usuários que fazem parte dos colaboradores antes que eles estão atualizados para **Equipes apenas** o modo. Skype para Business Server 2019 e Skype para negócios 2015 de servidor com atualização CU8 podem simplificar a mecânica da atualização de usuários locais para equipes Gerenciando a migração para o Skype para Business Online e atualizando os usuários para o modo **Equipes somente** em uma única etapa .

### <a name="direct-upgrade-journey"></a>Direta jornada de atualização

A jornada de atualização direta é ilustrada no diagrama a seguir.

![Uma captura de tela da jornada atualização direta. Todos os usuários inicialmente usam equipes no modo de ilhas e fazer a transição para o modo somente equipes, com o estado final do toda a organização atualizado para equipes.](media/upgrade_journey_direct_upgrade.png)

As equipes é implantada para todos os usuários na organização e configurado no modo de **Ilhas** . Quando sua organização determina que equipes está pronta para atender a todas as suas comunicações e colaboração precisa, notificar os usuários e atualizá-los para **Equipes somente** modo. Nesse momento, Skype for Business pode ser retirado do ambiente.

### <a name="gradual-upgrade-journey"></a>Jornada de atualização gradual

Um exemplo de uma jornada de atualização gradual é ilustrado no diagrama a seguir.

![Na jornada de atualização gradual, colaboradores de usuários inicialmente usam equipes no modo de ilhas para avaliação e, em seguida, em uma variedade de modos de atualização para a adoção antecipada, lado a lado com Skype para negócios. Transição alguns colaboradores para o modo somente equipes, enquanto um grupo de usuários permanece com Skype for Business com colaboração de equipes e modo de reuniões.](media/upgrade_journey_gradual_upgrade.png)

Equipes é implantado na organização no modo de **Ilhas** para avaliação e mova para coexistência diferente e atualizar modos para diferentes grupos de usuários. Por exemplo, um grupo de usuários que pode ser habilitado para o modo de **Ilhas** , outro habilitados para o modo de **Skype for Business com reuniões e colaboração de equipes** , enquanto um terceiro grupo de usuários inicialmente pode ser habilitado para **Skype for Business com equipes colaboração apenas** modo.

Ao longo do tempo, os grupos de usuários podem ser atualizados para **Equipes somente** modo, seguido do resto da organização. Eventualmente, toda a organização será pronta para retirar Skype para negócios e usar apenas as equipes para comunicação e colaboração, ou — se os requisitos de negócios determinam que Skype para negócios ser retidos por um grupo específico — a maioria dos usuários no organização pode usar apenas as equipes. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Ponto de decisão</td><td><ul> Qual jornada de atualização é adequada para os requisitos de negócios da sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próxima etapa</td><td><ul> Identificando seu modelo de implantação atual, use a cenários de caso e considerações fundamentais para sua organização informará a jornada para equipes que é mais adequada para sua organização.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Ponto de decisão</td><td><ul> Qual cenário de atualização é aplicável a sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul> Decida o cronograma da jornada de atualização da sua organização com base em mensagens, reuniões e chamando os requisitos de negócios.<br><br> Decida o trabalho adicional necessário para concluir sua jornada de atualização.<br><br></ul></td></tr>
</table>

Depois que você tiver escolhido a jornada recomendada de atualização da sua organização, [execute a atualização para equipes](https://aka.ms/SkypeToTeams-Upgrade).
