---
title: Reunião primeiro – Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Saiba mais sobre Reuniões Primeiro, onde os usuários podem criar suas reuniões no Teams, enquanto continuam a usar o Skype for Business para chat, chamadas e presença.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4e4eba45e7f6719b1fb3427ebd169b69a1e86c9
ms.sourcegitcommit: 4e648c3dd71d9c38cbcb81fab9e8cb9d241fe79c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871072"
---
# <a name="meetings-first"></a>Meetings First

"Reuniões Primeiro" é direcionado e otimizado para organizações do Skype for Business Server com o Enterprise Voice local que querem começar a usar reuniões do Teams o mais rapidamente possível. Para essas organizações, o Meetings First é uma alternativa ao uso do modo **Ilhas** que prioriza a experiência de reuniões do Teams.

## <a name="what-is-meetings-first"></a>O que é Reuniões Primeiro?

A primeira reunião é baseada no modo de coexistência **SfBWithTeamsCollabAndMeetings.** A primeira reunião não é um produto ou um recurso — é uma configuração que usa recursos e recursos do Teams e do Skype for Business para fornecer uma experiência de coexistência personalizada exclusiva.

Em Reuniões Primeiro, os usuários criam suas reuniões no Teams, enquanto continuam a usar o Skype for Business para chat, chamadas e presença. Não há sobreposição de modalidades entre o Teams e o Skype for Business. O chat, as chamadas e a presença estão no Skype for Business e desligados no Teams. Isso permite cenários exclusivos "melhores juntos" entre o Skype for Business e o Teams, que aprimoram a experiência do usuário durante a coexistência, bem como cenários de interoperabilidade com usuários somente do **Teams.**

![Captura de tela do cenário melhor juntos com o Teams e o Skype for Business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> As Reuniões Primeiro são uma melhor combinação para organizações que não têm nem poucos usuários de chat do Teams ativos. Os usuários de chat do Active Teams não devem ser alternáveis para o modo Primeiro de Reuniões, pois perderiam a capacidade de conversar no Teams e acessar seu histórico de chats. Em vez disso,  esses usuários devem ser acodados no modo Ilhas, e as Reuniões Primeiro só são concedidas aos usuários que ainda não estão ativos no chat no Teams.

## <a name="who-should-consider-meetings-first"></a>Quem deve considerar Reuniões Primeiro?

As Reuniões Primeiro foram projetadas para as organizações que usam o Skype for Business Server com o Enterprise Voice que querem acelerar a movimentação para reuniões do Teams, especialmente aquelas com forte disciplina de TE que querem um caminho de atualização gerenciado e determinístico para o Teams.

Para organizações complexas ou de grande porte, as migrações de voz normalmente são realizadas localmente e podem levar muito tempo, potencialmente vários anos, resultando em cenários de coexistência estendida. Se essa coexistência  estiver no modo Ilhas, os usuários sempre terão a opção de duas soluções de reunião (Skype for Business e Teams), o que pode resultar em situações confusas ou suboptílcas. Ao contrário das migrações de voz, as migrações de reuniões geralmente podem ser concluídas em toda a empresa em um curto período de tempo. As organizações que querem mudar completamente para reuniões do Teams o mais rápido possível (e sem esperar a conclusão da migração de voz) devem considerar Reuniões Primeiro.

As Reuniões Primeiro podem não ser úteis para organizações que não têm usuários do Enterprise Voice. Essas organizações só poderão atualizar para o **Teams** assim que conseguir adotar reuniões do Teams. Eles devem considerar ignorar Reuniões Primeiro.

Além disso, a primeira reunião é útil para as organizações cujo escopo é uma solução de reunião de jogo puro, por exemplo, quando uma RFP "somente reuniões" está sendo emitida.

## <a name="capabilities-in-meetings-first"></a>Recursos em Reuniões Primeiro

A Reunião Primeiro reúne os seguintes recursos:

- [Provisione um usuário do Skype for Business Server (local)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) com a [Audioconferência do Teams.](tutorial-audio-conferencing.yml)
- [Serviço de Migração](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)de Reuniões: as reuniões organizadas pelo usuário serão migradas para a nuvem e convertidas em reuniões do Teams à medida que o usuário for promovido para Reuniões Primeiro (requer o Exchange Online).
- Experiência do usuário simplificada no Teams, centralizada em reuniões e equipes e canais do Teams (que, opcionalmente, podem ficar ocultos usando a política permissões [do aplicativo);](teams-app-permission-policies.md) [Os chats privados, as](teams-client-experience-and-conformance-to-coexistence-modes.md) chamada e a autoexecução do Teams não são expostos em Reuniões Primeiro, permitindo que a implantação e o esforço de adoção se concentrem totalmente nas reuniões.
- Experiência de [reunião do Teams Superior.](tutorial-meetings-in-teams.yml)
- "Better Together" entre o Teams e o Skype for Business: 
  - Espera automática: quando estiver em uma reunião no Teams, entrar em uma chamada no Skype for Business colocará a reunião do Teams em espera e vice-versa. Isso impede que os usuários tenha suas chamadas privadas controladas pelos participantes das reuniões.
    ![Captura de tela do cenário melhor juntos com o Teams e o Skype for Business](media/meetings-first-better-together-hold.png)
  - Reconciliação de presença: a atividade no Teams é refletida na presença do usuário, que é a presença do Skype for Business, uma vez que o chat e as chamadas estão no Skype for Business. Especificamente, quando os primeiros usuários de Reuniões estão em uma reunião do Teams, sua presença será atualizada para refletir isso. Quando eles apresentarem a tela, sua presença será atualizada para mostrar Não Incomodar (com base em suas configurações no Skype for Business).
  - Reconciliação de controle HID do dispositivo USB (também disponível no Mac): os controles HID são honorários pelo Teams durante as reuniões do Teams e pelo Skype for Business em todas as outras circunstâncias.
  - A menos que mencionado de outra forma, os recursos Better Together exigem clientes recentes da área de trabalho do Windows no momento.

## <a name="prerequisites-for-meetings-first"></a>Pré-requisitos para Reuniões Primeiro

Os únicos requisitos rígidos para Reuniões Primeiro são os mesmos que os requisitos do Teams com o Active Directory local e uma implantação local do Skype for Business:

- [Pré-requisitos gerais para o Teams,](upgrade-plan-journey-prerequisites.md)incluindo
- [Identidade e autenticação no Teams](identify-models-authentication.md) e
- [Configure o Azure Active Directory para Teams e o Skype for Business.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)

Uma [topologia](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) híbrida do Skype for Business não é necessária, mas é recomendável. Alguns recursos, como o Serviço de Migração de Reuniões e a interoperabilidade, dependem dessa topologia.

O Meetings First é suportado com qualquer versão do Skype for Business Server (e conhecido por trabalhar com o Lync Server sem suporte). Ele é suportado com qualquer cliente do Skype for Business com suporte, mas os recursos Better Together exigem um cliente recente.

Depois que esses requisitos são atendidos (e não anteriores), os usuários podem ser licenciados para o [Microsoft 365 ou o Office 365 e o Teams.](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)

Para a melhor experiência de Primeira Reunião, os usuários devem estar habilitados para o [Exchange Online,](exchange-teams-interact.md) [o SharePoint Online](sharepoint-onedrive-interact.md)e o OneDrive for Business e a criação de grupos do Microsoft 365. As Reuniões Primeiro são suportadas para usuários cuja caixa de correio está no Exchange local ou que não têm o SharePoint Online ou o OneDrive For Business, ou a criação de grupos do Microsoft 365. No entanto, sua experiência será menos completa. Em particular, para as organizações que usam o Exchange Server local, pode haver (dependendo da versão do Exchange Server) algumas limitações para criar e exibir reuniões do cliente Teams, bem como com relação aos recursos de conformidade.

No mínimo, os usuários devem ser [licenciados para o Teams.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) Além disso, eles podem ser licenciados para [Audioconferência,](set-up-audio-conferencing-in-teams.md)se necessário.

Recomendamos conceder [o **modo SfBOnly** **ou SfBWithTeamsCollab**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como padrão de locatário no momento em que você licencia os usuários. Isso garante que os usuários não comecem a  usar o Teams por conta própria no modo de Ilhas padrão antes de você estar pronto para iniciar Reuniões Primeiro.

As Reuniões Primeiro são suportadas em clientes completos da área de trabalho (Windows e Mac), em clientes de navegador e em clientes móveis. Ele também é compatível com salas [do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/room-systems/) O Better Together requer o cliente completo da área de trabalho.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Preparar-se para reuniões do Teams em Reuniões Primeiro

Para que os usuários tenham a melhor experiência possível em reuniões do Teams, você deve:

- Siga as etapas em [Reuniões e conferências do Microsoft Teams,](deploy-meetings-microsoft-teams-landing-page.md)em particular.
- [Avalie seu ambiente.](3-envision-evaluate-my-environment.md)
- [Prepare a rede da sua organização para o Microsoft Teams.](prepare-network.md)
- Atualize suas salas [](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)de reunião com dispositivos e soluções de sala de reunião compatíveis do Teams ou use o [Cloud Video Interop](cloud-video-interop.md) para o Microsoft Teams para habilitar suas salas e dispositivos de terceiros existentes para ingressar em reuniões do Teams.
- Equipe seus usuários com dispositivos [de áudio e vídeo USB certificados.](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- Prepare-se [para impulsionar a conscientização e a adoção para reuniões do Teams.](adopt-microsoft-teams-landing-page.md)
- [Planeje o gerenciamento de serviços.](4-envision-plan-my-service-management.md)
- Familiarize-se com os relatórios rich Call Analytics para [solucionar problemas de baixa qualidade de chamada.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Você pode considerar executar um piloto de produção de escala moderada pronto neste estágio.

## <a name="configure-users-for-meetings-first"></a>Configurar usuários para Reuniões Primeiro

Depois de licenciar os usuários e preparar sua organização para reuniões do Teams, é hora de habilitar os usuários para reuniões primeiro. Facilitamos isso: uma única configuração fará tudo isso!

Todos os recursos e experiências do usuário em [](teams-client-experience-and-conformance-to-coexistence-modes.md) Reuniões Primeiro, incluindo a configuração do cliente do Teams e a conformidade automática da experiência do usuário, o Serviço de Migração de Reuniões e os recursos Better Together, são configurados concedendo ao usuário (ou grupo de usuários ou padrão de locatário) o modo de [coexistência SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) no Centro de administração do [Microsoft Teams](manage-teams-in-modern-portal.md) ou usando [o PowerShell.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

![Captura de tela das configurações de administração para habilitar Reuniões Primeiro](media/teams-meeting-admin-settings.png)

Opcionalmente, você deve ocultar o aplicativo Teams e Canais da navegação à esquerda do cliente do Teams dos usuários para focar ainda mais sua experiência em reuniões, que podem ser realizadas usando a política de Permissão do [Aplicativo.](teams-app-permission-policies.md)

## <a name="reporting-and-call-analytics"></a>Relatórios e Análise de Chamada

Relatórios e Análises de Chamada para reuniões do Teams em Reuniões Primeiro permanecem inalterados do que estão em outros modos.

## <a name="related-links"></a>Links relacionados

Depois de revisar este artigo, talvez você queira consultar Escolher sua jornada de [atualização,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)as diretrizes de migração e [interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)e a [Coexistência](coexistence-chat-calls-presence.md) com o Skype for Business para obter mais detalhes.


