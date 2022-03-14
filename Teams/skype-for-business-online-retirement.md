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
ms.openlocfilehash: 6c18871756c8081b7013666d98d1599cfec4117f
ms.sourcegitcommit: b635f3765498ae23f535a33fa9ffea5068eecb14
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2022
ms.locfileid: "63463734"
---
# <a name="skype-for-business-online-retirement"></a>Desativação do Skype for Business Online

Em 31 de julho de 2021, a Microsoft reformou Skype for Business Online. Essa aposentadoria foi anunciada em julho de 2019 para dar aos clientes dois anos de antecedência aviso para planejar suas atualizações para Microsoft Teams. Teams é o aplicativo principal para comunicação e colaboração no Microsoft 365. Com Skype for Business Online sendo retirada, a Microsoft deseja garantir que os clientes tenham as informações e recursos necessários para planejar e executar uma atualização bem-sucedida para Teams.  O Skype de consumidor não é afetado por essa aposentadoria.

## <a name="why-is-skype-for-business-online-retiring"></a>Por que o Skype for Business Online está se retirando?

Desde sua introdução, Skype for Business Online tem sido uma ferramenta valiosa para milhões de pessoas em todo o mundo. Combinando mensagens instantâneas, chamada e vídeo, o Skype for Business Online estabeleceu novas possibilidades para comunicações comerciais. Teams é o próximo capítulo nessa visão. 

Os recursos de Microsoft Teams vão além dos Skype for Business Online. Inovação e desenvolvimento de plataformas em andamento significa Teams usuários se beneficiam de desempenho, funcionalidade, flexibilidade e segurança mais ricos. Combinando os seguintes recursos em uma única experiência, Teams permite novas maneiras de trabalhar:

- Chat
- Vídeo
- Chamadas
- Colaboração de documentos
- Integração de aplicativos

Teams é mais do que uma atualização para Skype for Business Online. É uma ferramenta poderosa que permite que escolas e organizações se tornem mais ágeis e melhorem a eficiência dos principais fluxos de trabalho. Saiba mais sobre os benefícios da Teams no white paper forrester, [The Total Economic Impact™ of Microsoft Teams](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams.pdf?rtc=1).

Para obter mais informações sobre a Skype for Business online, consulte Perguntas frequentes — Atualizando de Skype for Business [para Microsoft Teams](FAQ-journey.yml).

## <a name="organizations-with-skype-for-business-online"></a>Organizações com Skype for Business Online

A Microsoft está fornecendo um processo de atualização assistido para ajudar as organizações a mover os usuários restantes Skype for Business Online para Teams Somente. Teams está disponível na maioria dos planos Microsoft 365 Business e Enterprise e os investimentos de licenciamento existentes são encaminhados para Teams. Os recursos que atualmente são cargas de trabalho premium no Skype for Business Online continuarão a ser cargas de trabalho premium no Microsoft Teams. Por exemplo, se você comprou Audioconferência autônoma ou como parte do E5 com Skype for Business, a Audioconferência será habilitada em Teams.

## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organizações com implantações locais de Skype for Business Server

A aposentadoria do Skype for Business Online não afeta o suporte para implantações locais do Skype for Business Server e do Lync Server 2013. No entanto, os clientes híbridos com uma combinação de usuários locais e online devem atualizar todos os *usuários online* . Esses usuários online devem ser atribuídos Teams modo Somente usando o TeamsUpgradePolicy. A Microsoft está fornecendo atualizações assistidas para ajudar a automatizar a atualização dos usuários Skype for Business Online restantes para Teams modo Somente. As organizações híbridas não precisam *mover seus* usuários locais Skype for Business para a nuvem como resultado dessa aposentadoria. A Microsoft dá suporte total a organizações híbridas com uma combinação de Teams usuários e usuários locais Skype for Business usuários. Os clientes com implantações híbridas do Skype for Business Server ou do Lync Server 2013 devem revisar Implicações da próxima aposentadoria do [Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>O que esperar após a aposentadoria

Não é mais possível que os usuários que estão na nuvem sejam atribuídos a um modo diferente do TeamsOnly. Isso significa:
 - Ao licenciar novos usuários (exceto os usuários que estão no Skype for Business Server locais), os usuários são atribuídos automaticamente ao modo TeamsOnly, independentemente da política global do TeamsUpgradePolicy do locatário.
 - Em organizações híbridas, ao mover usuários locais para a nuvem, os usuários são atribuídos automaticamente ao modo TeamsOnly (regarldess `MoveToTeams` de se a opção foi especificada em `Move-CsUser`.)
 - Os usuários que estão em casa na nuvem (por exemplo, não  usam um servidor local Skype for Business) não podem ser atribuídos a um modo diferente do Teams Only.

Os clientes podem ter partes restantes de sua população de usuários que estão no Skype for Business Online e que ainda não foram atribuídas Teams modo Somente.  Os clientes devem atribuir Teams modo Somente a esses usuários assim que possível.  Além disso, a Microsoft fornecerá atualizações assistidas para usuários Skype for Business Online que não estão Teams modo Somente.  A experiência de atualização assistida depende se sua organização é uma organização online pura ou uma organização com usuários Skype for Business locais.  Para obter mais informações, consulte [Atualizações assistidas do Skype for Business Online para Microsoft Teams](upgrade-assisted.md).

Depois que a atualização assistida for concluída, todos os *usuários online* estarão Teams modo Somente. Os usuários no Teams somente recebem chats e chamadas de entrada no Teams e também agendam reuniões no Teams. Eles não podem iniciar chats, chamadas ou agendar reuniões no Skype for Business Online.  No entanto, Teams usuários podem participar Skype for Business reuniões que já têm ou recebem no futuro. Por fim, todos os usuários que estão no local permanecem no local e não serão Teams *Somente.*


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Como a Microsoft está ajudando os clientes a atualizar para Teams

Recomendamos que você comece sua atualização do Skype for Business Online para Teams hoje.

Aproveite os recursos disponíveis para ajudar a planejar sua implantação Teams e atualização do Skype for Business:

- [Teams documentação de implantação e atualização](upgrade-start-here.md) – Diretrizes técnicas gratuitas para administradores de IT.

- [Teams workshops](./upgrade-workshops-landing-page.yml) de planejamento de atualização – workshops gratuitos de planejamento interativo de atualização, onde você receberá orientações, práticas recomendadas e recursos projetados para ajudá-lo a planejar e implementar sua atualização para Teams.

- [Atualizações assistidas do Skype for Business Online para o Microsoft Teams](upgrade-assisted.md) – programa automatizado que o ajuda a atualizar usuários do Skype for Business Online para Teams.

- [FastTrack para Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams de implantação disponíveis para planos de qualificação.

- [Teams treinamento ao vivo](./instructor-led-training-teams-landing-page.yml) – aulas de treinamento online gratuitas projetadas para fazer sua organização funcionar com Teams.

- [Teams Chalk Talks](./chalk-talks-landing-page.yml) – workshops online gratuitos para profissionais de IT e tomadores de decisão que descrevem as práticas recomendadas para cenários principais no Teams.

- [Parceiros da Microsoft](https://www.microsoft.com/solution-providers/home) – os provedores de soluções da Microsoft podem ajudá-lo a tirar proveito total do Teams.

- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Teams notícias sobre novos recursos, recursos de adoção e uso, Teams dispositivos e integração com outros aplicativos de negócios.

Se você for um cliente Skype for Business Online atual, comece a planejar sua atualização para Teams hoje. Estamos animados para que você experimente seus poderosos recursos de comunicação e colaboração, e estamos comprometidos em ajudar ao longo do caminho.




