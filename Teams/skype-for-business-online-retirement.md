---
title: Desativação do Skype for Business Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Saiba mais sobre o plano de Skype for Business Online e como a Microsoft está ajudando os clientes a migrar para Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783900"
---
# <a name="skype-for-business-online-retirement"></a>Desativação do Skype for Business Online

Em 31 de julho de 2021, a Microsoft reformou Skype for Business Online. Essa aposentadoria foi anunciada em julho de 2019 para dar aos clientes dois anos de antecedência aviso para planejar suas atualizações para Microsoft Teams. Teams é o aplicativo principal para comunicação e colaboração no Microsoft 365. Com Skype for Business Online sendo retirada, a Microsoft deseja garantir que os clientes tenham as informações e recursos necessários para planejar e executar uma atualização bem-sucedida para Teams.  O Skype de consumidor não é afetado por essa aposentadoria. Para saber mais sobre por Skype for Business Online foi Skype for Business, consulte Perguntas frequentes— Atualizando de Skype for Business [para Microsoft Teams](FAQ-journey.yml).

A Microsoft começará a descomissionar a infraestrutura Skype for Business Online em ou após 30 de junho de 2022. Este artigo contém orientações para organizações com usuários do TeamsOnly que foram atualizados de qualquer versão do Skype for Business.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organizações com implantações locais de Skype for Business Server

A aposentadoria do Skype for Business Online não afeta o suporte para implantações locais do Skype for Business Server e do Lync Server 2013. No entanto, os clientes híbridos com uma combinação de usuários locais e online devem atualizar todos os *usuários online* . Todos os usuários online devem ser atribuídos ao modo TeamsOnly usando o TeamsUpgradePolicy. A Microsoft está fornecendo atualizações assistidas para ajudar a automatizar a atualização dos usuários Skype for Business Online restantes para o modo TeamsOnly. As organizações híbridas não precisam mover *seus* usuários locais Skype for Business para a nuvem como resultado dessa aposentadoria. A Microsoft dá suporte total a organizações híbridas com uma combinação de usuários do TeamsOnly e usuários Skype for Business locais. Os clientes com implantações híbridas do Skype for Business Server ou do Lync Server 2013 devem revisar a Aposentadoria [do Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>O que esperar após a aposentadoria

Não é mais possível que os usuários que estão na nuvem sejam atribuídos a um modo diferente do TeamsOnly. Isso significa:

 - Ao licenciar novos usuários que não estão no Skype for Business Server local, os usuários são atribuídos automaticamente ao modo TeamsOnly, independentemente da política global do TeamsUpgradePolicy do locatário.
 - Em organizações híbridas, ao mover usuários locais para a nuvem, os usuários são atribuídos automaticamente ao modo TeamsOnly `MoveToTeams` , independentemente de a opção ter sido especificada em `Move-CsUser`.
 - Os usuários que estão na nuvem não podem ser atribuídos a um modo diferente do TeamsOnly. Os usuários em casa online *não* usam Skype for Business servidor local.

Os clientes podem ter usuários restantes que estão no Skype for Business Online e que ainda não estão atribuídos ao modo TeamsOnly. Os clientes devem atribuir o modo TeamsOnly a esses usuários assim que possível. A Microsoft fornecerá atualizações assistidas para usuários Skype for Business Online que não estão no modo TeamsOnly. A experiência de atualização assistida depende se sua organização é uma organização online pura ou uma organização com usuários Skype for Business locais. Para obter mais informações, consulte [Atualizações assistidas do Skype for Business Online para Microsoft Teams](upgrade-assisted.md).

Depois que a atualização assistida for concluída, todos os *usuários online* estarão no modo TeamsOnly. Os usuários no modo TeamsOnly recebem chats e chamadas de entrada no Teams e também agendam reuniões em Teams. Eles não podem iniciar chats, chamadas ou agendar reuniões no Skype for Business Online.  No entanto, os usuários do TeamsOnly podem participar Skype for Business reuniões que já têm ou recebem no futuro. Por fim, todos os usuários que estão no local permanecem no local e não serão *feitos teamsOnly*.

## <a name="actions-to-take-before-june-30-2022"></a>Ações a tomar antes de 30 de junho de 2022
Agora que Skype for Business Online foi desativada, a Microsoft começará a descomissionar a infraestrutura de suporte até 30 de junho de 2022.  Para qualquer organização com usuários do TeamsOnly que foram atualizados de qualquer versão do Skype for Business, você precisa tomar medidas se uma dessas situações se aplicar:

- Se você tiver usuários do TeamsOnly que previoulsy tiveram contatos no Skype for Business e que ainda não  entraram no Teams desde que foram atualizados.
- Se você tiver algum usuário do TeamsOnly que ainda tenha Skype for Business online que eles organizaram antes de ser atualizado para o TeamsOnly.

Se uma dessas situações se aplicar à sua organização, você deverá tomar medidas até 30 de junho de 2022, conforme descrito abaixo:

 - Skype for Business Contatos Online: depois que um usuário tiver sido atualizado para o modo TeamsOnly, na primeira vez que o usuário entrar no Teams, quaisquer contatos **existentes** na conta do Skype for Business Online desse usuário serão migrados para o Teams. Depois que a Microsoft remover a infraestrutura do Skype for Business Online, você não poderá mais migrar contatos para usuários que ainda não fizeram logo Teams *.* Para migrar contatos do Skype for Business para o Teams, a Microsoft recomenda que todos os usuários que anteriormente Skype for Business tivessem feito logoff para Teams pelo menos uma vez antes de 30 de junho de 2022.

 - **Skype for Business Online:** depois que uma organização é atualizada para o TeamsOnly, os usuários criam todas as novas reuniões como Teams reuniões. Em alguns casos, os usuários do TeamsOnly ainda podem ter reuniões Skype for Business Online que organizaram anteriormente. Atualmente, os usuários do TeamsOnly atualizados e todos os participantes convidados podem participar dessas reuniões Skype for Business Online usando seu cliente Skype for Business cliente. Depois que a Microsoft remover a infraestrutura do Skype for Business Online para um determinado usuário do TeamsOnly, no entanto, quaisquer reuniões Skype for Business Online restantes organizadas por esse usuário não existirão mais. O organizador e os participantes não poderão participar dessas reuniões. Se os usuários nas organizações teamsOnly têm qualquer reunião Skype for Business Online restantes que organizaram, a Microsoft recomenda reagendar essas reuniões como Teams reuniões. Como alternativa, os administradores podem usar o Serviço de Migração de [Reunião](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) para converter essas reuniões em Teams reuniões. Em ambos os casos, conclua essas ações até 30 de junho de 2022.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Como a Microsoft está ajudando os clientes a atualizar para Teams

Recomendamos que você comece sua atualização do Skype for Business Online para Teams hoje. Aproveite os recursos disponíveis para ajudar a planejar sua implantação Teams e atualização do Skype for Business:

- [Teams documentação de implantação e atualização](upgrade-start-here.md) – Diretrizes técnicas gratuitas para administradores de IT.

- [Teams workshops](./upgrade-workshops-landing-page.yml) de planejamento de atualização – workshops gratuitos de planejamento interativo de atualização, onde você receberá orientações, práticas recomendadas e recursos projetados para ajudá-lo a planejar e implementar sua atualização para Teams.

- [Atualizações assistidas do Skype for Business Online para o Microsoft Teams](upgrade-assisted.md) – programa automatizado que o ajuda a atualizar usuários do Skype for Business Online para Teams.

- [FastTrack para Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams de implantação disponíveis para planos de qualificação.

- [Teams treinamento ao vivo](./instructor-led-training-teams-landing-page.yml) – aulas de treinamento online gratuitas projetadas para fazer sua organização funcionar com Teams.

- [Teams Chalk Talks](./chalk-talks-landing-page.yml) – workshops online gratuitos para profissionais de IT e tomadores de decisão que descrevem as práticas recomendadas para cenários principais no Teams.

- [Parceiros da Microsoft](https://www.microsoft.com/solution-providers/home) – os provedores de soluções da Microsoft podem ajudá-lo a tirar proveito total do Teams.

- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Teams notícias sobre novos recursos, recursos de adoção e uso, Teams dispositivos e integração com outros aplicativos de negócios.

Se você for um cliente Skype for Business Online atual, comece a planejar sua atualização para Teams hoje. Estamos animados para que você experimente seus poderosos recursos de comunicação e colaboração, e estamos comprometidos em ajudar ao longo do caminho.  Para obter mais informações sobre a Skype for Business online, consulte Perguntas frequentes— Atualizando de Skype for Business [para Microsoft Teams](FAQ-journey.yml).





