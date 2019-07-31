---
title: Atualização do Microsoft Teams do Skype for Business | Modos, coexistência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen, bjwhalen
description: Detalhes das opções e modos de coexistência do Skype for Business e do Microsoft Teams e de upgrade para o Teams do Skype for Business com cenários de exemplo.
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
ms.openlocfilehash: d662dfd98aa4706d32a7e9ba3bec06d5e32ae975
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934395"
---
![Atualize o diagrama de viagem, enfatizando implantação e implementação] (media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")

Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Listamos os participantes do projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendemos a coexistência e interoperabilidade do Skype for Business e do teams](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Escolher a jornada da atualização do Skype for Business para o Teams

Como cliente existente do Skype for Business, sua transição completa para o Microsoft Teams pode levar algum tempo. No entanto, você pode começar a concretizar o valor do teams hoje, permitindo que seus usuários usem o Microsoft Teams juntamente com o Skype for Business. Como há alguns recursos sobrepostos entre os dois aplicativos, recomendamos que você revise os modos de coexistência e atualização disponíveis para ajudar a determinar qual caminho é ideal para a sua organização. Por exemplo, você pode optar por habilitar todas as cargas de trabalho em ambas as soluções sem interoperabilidade. Ou, você pode decidir gerenciar a experiência do usuário, introduzindo gradualmente os recursos do teams ou direcionando grupos de usuários para obter recursos de seleção, até que a sua organização esteja pronta para fazer a atualização de todos para o Microsoft Teams. Use o resultado do seu piloto para ajudar a avaliar a jornada de atualização certa para a sua organização.

> [!IMPORTANT]
> O Skype for Business online será desativado em 31 de julho de 2021, após o qual ele não estará mais acessível ou compatível. Para maximizar a concretização de benefícios e garantir que sua organização tenha tempo adequado para implementar a sua atualização, recomendamos que você comece sua jornada ao Microsoft Teams hoje mesmo.

Este artigo descreve os vários modos que permitem que você gerencie quais modalidades do Skype for Business e do teams estão disponíveis para seus usuários. Assim como em qualquer implantação, recomendamos que você denomine [o plano pretendido](pilot-essentials.md) com um grupo de usuários selecionado antes de atualizar sua organização para o Teams. Lembre-se de que introduzir nova tecnologia pode causar interrupções para os usuários. Reserve algum tempo para avaliar a prontidão do usuário e implementar um plano de comunicação e treinamento antes de implementar qualquer um dos modos descritos aqui.

> [!TIP]
> Junte-se aos workshops interativos e ativos nos quais compartilharemos orientação, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação da atualização.
>
>Ingresse no [plano da sessão de atualização](https://aka.ms/SkypeToTeamsPlanning) primeiro para começar.


## <a name="upgrade-journey-building-blocks"></a>Atualizar blocos de construção de viagem

Para preparar formalmente sua organização para o seu Journey to Teams, você precisa começar a planejar os cenários de atualização que, eventualmente, permitirão que sua organização adote o Teams como sua única solução de comunicação e colaboração.

Para ajudar a orientar seu processo de tomada de decisões, familiarize-se com os vários modos, conceitos e terminologia relevantes para a atualização do Skype for Business para o Teams. Para obter mais informações, consulte [Microsoft Teams e coexistência e interoperabilidade do Skype for Business](https://aka.ms/SkypeToTeams-Coexist)

Quando alguns dos seus usuários estão prontos para usar apenas as equipes de suas necessidades cotidianas de comunicação e colaboração, você pode começar a atualizar esses usuários para o Microsoft Teams, habilitando o modo **somente Teams** para eles.

Se não for possível que toda a sua organização se movimente para o Teams, você pode começar por meio de equipes piloto juntamente com o Skype for Business no modo de coexistência de **ilhas** . Como os modos de coexistência adicionais, (isto é, o **Skype for Business com colaboração** do Teams e o **Skype for Business com Teams e reuniões**do Microsoft Teams) estão se tornando cada vez mais disponíveis nos próximos meses, você também pode começar por todos os detalhes adotar equipes como uma solução de colaboração em grupo primeiro, mantendo o Skype for Business como a solução de comunicação unificada da sua organização. Esse é o caminho recomendado pela Microsoft para clientes que usam o Skype for Business Server (local ou híbrido) e clientes com complexidade significativa, cuja trajetória para as equipes incluirá um período de coexistência longo.

![Captura de tela de atualizar blocos de construção do Skype for Business para] o Teams (media/upgrade_journeys_building_block.png "Uma captura de tela de atualização de blocos de construção do Skype for Business para o Teams, que consiste no&ndash;Skype for Business com modo de colaboração do Microsoft Teams, o Skype for Business com o Microsoft Teams e o modo de reunião, modo de ilhas, modo somente para equipes e Skype para Modo&ndash;somente para empresas.")

A tabela a seguir compara os modos de coexistência e atualização.

|Modo |Problema |Uso recomendado |Vantagens |Limitações |
|---|---|---|---|---|
|McDonald |Implantação do Skype for Business menor ou mais simples<br><br>Capacidade e disposição para gerenciar uma complexidade de curto prazo para mover-se para as equipes com mais rapidez |Vá para toda a experiência da equipe o mais rápido possível<br><br>Conduzir uma prova de conceito (VDC) de equipes<br><br>Caminho de atualização recomendado para organizações que adotaram o Skype for Business Online |Simples de operar<br><br>Experiência mais rica em equipes mais avançadas para todos os recursos |Requer uma boa comunicação entre o usuário para evitar confusão e direcionar o uso para o Microsoft Teams<br><br>A estratégia de saída exige que os usuários tenham equipes totalmente adotadas antes de iniciar a atualização para a fase apenas do Microsoft Teams<br><br>Não há interoperabilidade para usuários no modo ilhas. também não é possível fazer uma Federação do teams quando a conta do Skype for Business do usuário é hospedada no local|
|Skype for Business com colaboração em equipe |Implantação do Skype for Business com requisitos que ainda não foram atendidos pelas equipes (por exemplo, conformidade avançada)<br><br>Necessidade a longo prazo e/ou compromisso com o Skype for Business|Iniciar a adoção do teams rapidamente, com foco em colaboração em grupo primeiro<br><br>Deseja manter todas as cargas de trabalho de comunicação unificada no Skype for Business por enquanto<br><br>Recomendamos o uso como ponto de partida para a organização iniciar sua jornada no Skype for Business local (ou híbrido)|Sem recursos sobrepostos entre o Teams e o Skype for Business<br><br>O chat de mensagens instantâneas e o agendamento de reuniões residem no Skype for Business (vinculado a chamadas)<br><br>Interoperabilidade com usuários somente no Teams|
|Skype for Business com colaboração e reuniões do teams |Implantação do Skype for Business com uso significativo de Enterprise Voice e requisitos que ainda não foram atendidos pelas chamadas de equipe<br><br>Necessidade a longo prazo e/ou compromisso com o Skype for Business<br><br>Pode estar usando um serviço de reunião de terceiros|Iniciar a adoção do teams rapidamente, indo além da colaboração em grupo<br><br>Melhorar a experiência de reuniões dos usuários<br><br>Uso recomendado para organizações locais que desejam tirar proveito das reuniões do teams antes de estarem prontas para a atualização completa (geralmente devido ao Enterprise Voice local). |Sem recursos sobrepostos<br><br>Reuniões superiores no Teams. Recursos de orientação, UX e plataforma cruzada, qualidade e confiabilidade<br><br>Experiências "melhor juntas" entre o Skype for Business e o Teams<br><br>Interoperabilidade entre usuários somente no Microsoft Teams.|Mensagens instantâneas e chats residirão no Skype for Business (vinculado a chamadas)|
|Somente equipes |Teams only é o destino final para todos os usuários, eventualmente.<br><br>Alguns usuários precisam ficar no Skype for Business<br><br>Você está fazendo a atualização dos usuários do Skype for Business online para o Microsoft Teams e, ao mesmo tempo, mantém os usuários locais do Skype for Business no Skype for Business Server<br><br>Talvez você já tenha implantado usuários no modo de ilhas e esteja pronto para desativar o Skype for Business para grupos de usuários |Reduzir os custos variáveis no Skype for Business (operações do servidor local, contrato de terceirização e assim por diante)<br><br>Vá para toda a experiência da equipe o mais rápido possível, para pelo menos alguns usuários|Limita a confusão do usuário fornecendo apenas um cliente para trabalhar com interoperabilidade com usuários no Skype for Business apenas, Skype for Business com colaboração do Teams, Skype for Business com colaboração e reuniões do teams|A interoperabilidade só oferece suporte a chat e chamadas básicas entre o Skype for Business e o Teams e cenários de escalonamento para interoperabilidade para compartilhamento de área de trabalho e chat e chamadas de vários participantes|
|Somente Skype for Business |Alguns usuários precisam ficar no Skype for Business<br><br>|Limita a confusão do usuário fornecendo apenas um cliente com o qual trabalhar<br><br>O usuário ainda pode participar de reuniões de equipes para as quais eles são convidados|Continuar a atender às necessidades de negócios que atualmente só podem ser atendidas pelo Skype for Business<br><br>Interoperabilidade com usuários somente no Teams|A interoperabilidade só oferece suporte a chat e chamadas básicas entre o Skype for Business e o Teams e cenários de escalonamento para interoperabilidade para compartilhamento de área de trabalho e chat e chamadas de vários participantes|

> [!TIP]
> Para ajudar a identificar o modo de atualização recomendado com base nos recursos que você deseja habilitar no Teams enquanto o Skype for Business ainda está em uso, use o [Assistente de atualização do Skype to Teams](https://aka.ms/SkypeToTeamsWizard).

## <a name="upgrade-journeys"></a>Atualizar viagens

Você pode usar várias abordagens para fazer a atualização do Skype for Business, online ou local, para o Teams:

- Em uma jornada de atualização direta, primeiro você implanta o Microsoft Teams juntamente com o Skype for Business no modo de **ilhas** como parte da avaliação e da adoção antecipada e, em seguida, atualiza seus usuários para o modo **somente Teams** , com o objetivo de desativar rapidamente o Skype for Business do ambiente para todos os usuários da organização. Esta é a jornada recomendada para os clientes do Skype Business Online, a menos que seus usuários se preocupem com ter duas ferramentas para conduzir a mesma ação (chat, chamadas, agendamento de reuniões).
- Uma viagem de atualização gradual fornece um modo de coexistência e atualização específico para um grupo específico de usuários (também chamado de *cohort*), dependendo de suas necessidades de comunicação e colaboração. Com o passar do tempo, toda a organização pode convergir para usar somente o Microsoft Teams e, eventualmente, substituir o Skype for Business. No entanto, se a sua organização tiver motivos comerciais atraentes para manter o Skype for Business, como uma dependência em uma solução baseada em UCMA (Unified Communication Managed API) que se integre com aplicativos de linha de negócios ou uma solução de parede ética atualmente disponível somente para o Skype for Business, ou uma implantação de voz complexa para a empresa que levará **** algum tempo para fazer a atualização para o Microsoft Teams, você pode atualizar uma parte do usuário para o modo **somente de equipe** , mantendo os usuários do Skype for Business em um dos modos de coexistência para uma parte da população do usuário. Viagem de atualização gradual é a abordagem recomendada para clientes locais (e híbridos) que começam com o Skype for Business com o modo de coexistência de equipes do Teams e movendo-se do modo somente Teams quando o requisito para os usuários foram atendidos (possivelmente por meio do Skype for Business com colaboração nas equipes e modo de coexistência de reuniões).

> [!IMPORTANT]
> Para os dois tipos de jornada de atualização, se a sua organização for atualmente uma implantação do Skype for Business local, você precisará começar a planejar a implementação do Skype for Business híbrido antes de atualizar os usuários para o modo **somente Teams** . Isso também ajudará a facilitar a interoperabilidade com o Teams.

> [!NOTE]
> O modo **somente para equipes** requer que os usuários que fazem parte do cohorts sejam hospedados no Skype for Business Online e uma relação híbrida entre a implantação local do Skype for Business e o locatário do Skype for Business online seja necessária para facilitar o interoperabilidade entre o Skype for Business e o Teams. A mudança para o Skype for Business online deve ser concluída para os usuários que fazem parte do cohorts antes de serem atualizados para o modo **somente Teams** . O Skype for Business Server 2019 e o Skype for Business Server 2015 com CU8 Update podem simplificar a mecânica de atualização de usuários locais para o Microsoft Teams ao gerenciar a migração para o Skype for Business Online **** e para atualizar o modo de usuários para o Microsoft Teams em uma etapa .

### <a name="direct-upgrade-journey"></a>Viagem de atualização direta

A jornada da atualização direta é ilustrada no diagrama a seguir.

![Uma captura de tela da jornada de atualização direta] (media/upgrade_journey_direct_upgrade.png "Uma captura de tela da jornada de atualização direta. Todos os usuários usam inicialmente o Teams no modo de ilhas e, em seguida, transformando-se no modo somente Teams, com o estado final de toda a organização atualizado para o Microsoft Teams.")

O Teams é implantado para todos os usuários na organização e configurados no modo de **ilhas** . Quando sua organização determina que o Microsoft Teams está pronto para atender a todas as suas necessidades de comunicação e colaboração, notifique os usuários e atualize-os para o modo **somente Teams** . Nesse ponto, o Skype for Business pode ser desativado no ambiente.

### <a name="gradual-upgrade-journey"></a>Viagem de atualização gradual

Um exemplo de uma viagem de atualização gradual é ilustrado no diagrama a seguir.

![Exemplo ilustrado da jornada de atualização gradual] (media/upgrade_journey_gradual_upgrade.png "Na jornada da atualização gradual, a cohorts de usuários inicialmente usa equipes no modo ilhas para avaliação e, em seguida, em diversos modos de atualização para adoção antecipada, lado a lado com o Skype for Business. Alguns cohorts a transição para o modo somente de equipes, enquanto um grupo de usuários permanece com o Skype for Business com o modo de colaboração e reuniões do teams.")

O Teams é implantado na organização no modo de **ilhas** para avaliação e, em seguida, move para diferentes modos de atualização e de atualização para diferentes grupos de usuários. Por exemplo, um grupo de usuários pode ser habilitado para o modo de **ilhas** , outro habilitado para o **Skype for Business com o modo de colaboração e reuniões** do Teams, enquanto um terceiro grupo de usuários pode ser habilitado inicialmente para o **Skype for Business com Teams modo somente colaboração** .

Ao longo do tempo, os grupos de usuários podem ser atualizados para o modo **somente** do Teams, seguido do restante da organização. Por fim, a organização inteira estará pronta para desativar o Skype for Business e usar somente equipes para comunicações e colaboração, ou, se os requisitos de negócios exigirem que o Skype for Business seja retido para um grupo específico, a maioria dos usuários do a organização pode usar apenas o Microsoft Teams. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul> Qual viagem de atualização é adequada para as necessidades comerciais da sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Próxima etapa</td><td><ul> Identificar seu modelo de implantação atual, cenários de uso, e as principais considerações para a sua organização informarão ao Journey to Teams mais adequados para a sua organização.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul> Qual cenário de atualização é aplicável à sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul> Decida a linha do tempo da viagem de atualização de sua organização com base nas solicitações de mensagens, reuniões e chamadas para empresas.<br><br> Decida o trabalho adicional necessário para concluir a viagem de atualização.<br><br></ul></td></tr>
</table>

Depois de escolher a melhor viagem de atualização para sua organização, [realize a atualização para](https://aka.ms/SkypeToTeams-Upgrade)o Microsoft Teams.
