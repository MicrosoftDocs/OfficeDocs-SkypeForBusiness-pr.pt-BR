---
title: Desativação do Skype for Business Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Saiba mais sobre o plano de desativação do Skype for Business Online e como a Microsoft está ajudando os clientes a migrar para o Teams.
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
ms.openlocfilehash: 3c973daf4dc90a6de734c1c76aa352e7a7eeac28
ms.sourcegitcommit: fc1787ad74a8c454f750a294def188b532cbadd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67854387"
---
# <a name="skype-for-business-online-retirement"></a>Desativação do Skype for Business Online

Em 31 de julho de 2021, a Microsoft desativou o Skype for Business Online. Essa desativação foi anunciada em julho de 2019 para dar aos clientes um aviso prévio de dois anos para planejar suas atualizações para o Microsoft Teams. O Teams é o aplicativo principal para comunicação e colaboração no Microsoft 365. Com Skype for Business Online sendo desativado, a Microsoft deseja garantir que os clientes tenham as informações e os recursos necessários para planejar e executar uma atualização bem-sucedida para o Teams.  O serviço de consumidor do Skype não é afetado por essa desativação. Para obter informações sobre por que Skype for Business Online foi desativado, consulte perguntas frequentes – Atualizando do [Skype for Business para o Microsoft Teams](FAQ-journey.yml).

A Microsoft começará a desativar a infraestrutura Skype for Business Online em ou após 30 de junho de 2022. Além disso, a partir de outubro de 2022, a Microsoft começará a desativar aspectos dessa infraestrutura específicos para organizações híbridas. Este artigo contém diretrizes para organizações com usuários do TeamsOnly que foram atualizados de qualquer versão do Skype for Business.

> [!Important]
> A desativação do Skype for Business Online não afeta o suporte para implantações locais do **Skype for Business Server e do Lync Server 2013**. No entanto, os clientes *híbridos com* uma combinação de usuários hospedados online e locais devem atualizar todos os usuários *online* para serem TeamsOnly. Todos os usuários online devem receber o modo TeamsOnly usando TeamsUpgradePolicy. Além disso, a Microsoft está fornecendo atualizações assistidas para ajudar a automatizar a atualização dos usuários Skype for Business Online restantes para o modo TeamsOnly. As organizações híbridas não precisam mover seus *usuários locais Skype for Business* para a nuvem como resultado dessa desativação. *A Microsoft dá suporte total a organizações híbridas* com uma combinação de usuários do TeamsOnly e usuários Skype for Business locais. Os clientes com implantações híbridas do Skype for Business Server ou do Lync Server 2013 devem examinar as implicações da desativação [do Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity.md#implications-of-the-upcoming-retirement-of-skype-for-business-online).


## <a name="what-to-expect-post-retirement"></a>O que esperar após a aposentadoria

Não é mais possível que os usuários hospedados na nuvem sejam atribuídos a um modo diferente do TeamsOnly. Isso significa:

 - Ao licenciar novos usuários que não estão hospedados no Skype for Business Server local, os usuários recebem automaticamente o modo TeamsOnly, independentemente da política global do teamsUpgradePolicy do locatário.
 - Em organizações híbridas, ao mover usuários hospedados localmente para a nuvem, os usuários recebem automaticamente o modo TeamsOnly `MoveToTeams` , independentemente de a opção ter sido especificada em `Move-CsUser`.
 - Os usuários hospedados na nuvem não podem receber um modo diferente do TeamsOnly. Os usuários hospedados online *não* usam Skype for Business servidor local.

Todos os clientes que tiverem usuários restantes hospedados no Skype for Business Online, mas ainda não tiverem o modo TeamsOnly atribuído, deverão atribuir o modo TeamsOnly a esses usuários assim que possível. Além disso, a Microsoft fornecerá atualizações assistidas para Skype for Business online que não estão no modo TeamsOnly. A experiência de atualização assistida depende se sua organização é uma organização online pura ou uma organização com usuários Skype for Business locais. Para obter mais informações, consulte [Atualizações assistidas do Skype for Business Online para o Microsoft Teams](upgrade-assisted.md). Após a conclusão da atualização assistida, todos os *usuários online* estarão no modo TeamsOnly. *Todos os usuários hospedados localmente permanecem no local e não serão disponibilizados no TeamsOnly*.

Os usuários no modo TeamsOnly recebem chats e chamadas de entrada no Teams e também agendam reuniões no Teams. Eles não podem iniciar chats ou chamadas ou agendar reuniões no Skype for Business Online. Os usuários do TeamsOnly podem Skype for Business reuniões que já têm ou recebem no futuro. No entanto, depois que a Microsoft remover a infraestrutura do Skype for Business Online para um determinado usuário do TeamsOnly, os usuários do TeamsOnly só poderão ingressar Skype for Business reuniões anonimamente.  A partir de 30 de junho de 2022, os usuários recém-criados do TeamsOnly não serão mais provisionados com a infraestrutura do Skype for Business Online, portanto, se forem convidados para uma reunião do Skype for Business, eles precisarão ingressar anonimamente. Da mesma forma, os usuários movidos do local para o Teams somente em organizações híbridas não serão mais provisionados com a infraestrutura do Skype for Business Online a partir de outubro de 2022. Se esses usuários forem convidados para uma reunião Skype for Business, eles também precisarão ingressar anonimamente.


## <a name="guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Diretrizes para organizações com implantações locais de Skype for Business Server

 - Ao criar novos usuários em seu ambiente do Active Directory local, se esses usuários serão sincronizados com o Azure AD e você pretende licenciá-los para o Teams, antes de atribuir a licença a esses *usuários, primeiro* você deve habilita-los em seu Skype for Business **e verifique se a alteração foi sincronizada com a nuvem por meio Azure AD conexão**.  Você pode verificar se a alteração foi totalmente sincronizada com a nuvem usando Get-CsOnlineUser. A alteração será sincronizada se HostingProvider= "SRV:" do usuário.  Não deve ser "sipfed.online.lync.com".   

 - Lembre-se de que os usuários do TeamsOnly precisarão ingressar anonimamente em reuniões do Skype for Business depois que a Microsoft remover a infraestrutura herdada do Skype for Business Online para organizações híbridas, a partir de outubro de 2022.  Para obter detalhes, consulte [o que esperar após a desativação](#what-to-expect-post-retirement). Como alternativa, você pode garantir que as reuniões agendadas por todos os usuários (seja localmente ou somente no Teams) em sua organização sejam reuniões do Teams, o que permite o ingresso na reunião autenticada para qualquer usuário na organização (sujeito à configuração de política). Para fazer isso, execute as seguintes ações:
   - Para todos os usuários atribuídos Skype for Business **somente** ou Skype for Business com modos de Colaboração do **Teams**, altere o modo de coexistência para Skype for Business colaboração e reuniões do **Teams**.  Esse modo oferece a mesma funcionalidade que as outras duas, exceto que novas reuniões agendadas pelo usuário serão reuniões do Teams em vez de Skype for Business reuniões. Quando você atribui esse modo diretamente a um usuário (em vez de no nível do locatário), ele também converterá automaticamente todas as reuniões do Skype for Business em reuniões do Teams organizadas por esse usuário.
   - Para usuários que estão no modo Ilhas, você pode exigir que eles sempre agendem reuniões no Teams atribuindo a eles uma instância do TeamsMeetingPolicy com PreferredMeetingProviderForIslandsMode=Teams. 
   - Para garantir que todas as reuniões existentes do Skype for Business sejam convertidas em reuniões do Teams (por exemplo, se você tiver usuários do Islands), você pode usar o Start-CsExMeetingMigration para disparar o [](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#trigger-meeting-migration-manually-via-powershell-cmdlet) Serviço de Migração de Reunião para converter as reuniões de um usuário no Teams.

- Para garantir que todos os contatos do Skype for Business Server sejam migrados corretamente para o Teams quando um usuário for movido do local para o TeamsOnly, verifique se os usuários migrados entrarão no Teams dentro de 30 dias após a migração do local. Esse é um requisito temporário, pois a Microsoft faz a transição do Teams para longe da infraestrutura Skype for Business Online herdada.

## <a name="actions-to-take-before-june-30-2022"></a>Ações a serem executadas antes de 30 de junho de 2022
Agora que Skype for Business Online foi desativado, a Microsoft começará a encerrar a infraestrutura de suporte até 30 de junho de 2022.  Para qualquer organização com usuários do TeamsOnly que foram atualizados de qualquer versão do Skype for Business, você precisará tomar medidas se qualquer uma dessas situações se aplicar:

- Se você tiver usuários do TeamsOnly que tinham contatos no Skype for Business e que ainda não entraram no Teams  desde que foram atualizados.
- Se você tiver algum usuário do TeamsOnly que ainda tenha Skype for Business online que eles organizaram antes de serem atualizados para o TeamsOnly.

Se qualquer uma dessas situações se aplicar à sua organização, você deverá tomar medidas até 30 de junho de 2022, conforme descrito abaixo:

 - **Skype for Business Online:** depois que um usuário tiver sido atualizado para o modo TeamsOnly, na primeira vez que o usuário fizer logon no Teams, todos os contatos existentes na conta do Skype for Business Online desse usuário serão migrados para o Teams. Depois que a Microsoft remover o Skype for Business Online, você não poderá mais migrar contatos para usuários que ainda não se conectaram *ao Teams.* Para migrar contatos do Skype for Business para o Teams, a Microsoft recomenda que todos os usuários que anteriormente tinham Skype for Business feito logon no Teams pelo menos uma vez antes de 30 de junho de 2022.

 - **Skype for Business Online: depois que** uma organização é atualizada para o TeamsOnly, os usuários criam todas as novas reuniões como reuniões do Teams. Em alguns casos, os usuários do TeamsOnly ainda podem ter Skype for Business online que organizaram anteriormente. Atualmente, os usuários atualizados do TeamsOnly e todos os participantes convidados podem ingressar nessas reuniões do Skype for Business Online usando seu Skype for Business cliente. No entanto, depois que a Microsoft remover a infraestrutura do Skype for Business Online para um determinado usuário do TeamsOnly, esse usuário só poderá ingressar em reuniões do Skype for Business anonimamente, e as reuniões restantes  do Skype for Business Online organizadas por esse usuário não existirão mais. O organizador e os participantes não poderão participar dessas reuniões. Se os usuários nas organizações teamsOnly tiverem quaisquer reuniões Skype for Business Online restantes que organizaram, a Microsoft recomenda reagendar essas reuniões como reuniões do Teams. Como alternativa, os administradores podem usar o Serviço de Migração [de Reunião](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) para converter essas reuniões em reuniões do Teams. Em ambos os casos, conclua essas ações até 30 de junho de 2022.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Como a Microsoft está ajudando os clientes a atualizar para o Teams

É altamente recomendável que você comece sua atualização do Skype for Business Online para o Teams hoje mesmo. Aproveite os recursos disponíveis para ajudar a planejar a implantação e a atualização do Teams Skype for Business:

- [Documentação de implantação e atualização do Teams](upgrade-start-here.md) – Diretrizes técnicas gratuitas para administradores de TI.

- Workshops de planejamento de atualização do Teams – workshops gratuitos de planejamento de atualização interativa, em que você receberá diretrizes, práticas recomendadas e recursos [projetados](./upgrade-workshops-landing-page.yml) para ajudá-lo a planejar e implementar sua atualização para o Teams.

- [Atualizações assistidas do Skype for Business Online para o Microsoft Teams](upgrade-assisted.md) – Programa automatizado que ajuda você a atualizar Skype for Business Online para o Teams.

- [FastTrack para Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Assistência de implantação do Teams disponível para planos de qualificação.

- [Treinamento ao vivo do Teams](./instructor-led-training-teams-landing-page.yml) – classes de treinamento online gratuitas projetadas para fazer sua organização funcionar com o Teams.

- [Teams Giz Talks](./chalk-talks-landing-page.yml) – workshops online gratuitos para profissionais de TI e tomadores de decisão que descrevem as práticas recomendadas para cenários principais no Teams.

- [Parceiros da Microsoft](https://www.microsoft.com/solution-providers/home) – os provedores de soluções da Microsoft podem ajudá-lo a aproveitar ao máximo o Teams.

- [Blog do Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Notícias do Teams sobre novos recursos, recursos de adoção e uso, dispositivos do Teams e integração com outros aplicativos de negócios.

Se você for um cliente atual do Skype for Business Online, comece a planejar sua atualização para o Teams hoje mesmo. Estamos animados para que você experimente seus poderosos recursos de comunicação e colaboração e estamos comprometidos em ajudar ao longo do caminho.  Para obter mais informações sobre a desativação Skype for Business Online, consulte perguntas [frequentes– Atualizando do Skype for Business para o Microsoft Teams](FAQ-journey.yml).





