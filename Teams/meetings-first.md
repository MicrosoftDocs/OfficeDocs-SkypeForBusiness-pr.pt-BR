---
title: Reunião Primeiro - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Saiba mais sobre Reuniões Primeiro, onde os usuários podem criar sua reunião no Teams, enquanto continuam a usar o Skype for Business para chat, chamada e presença.
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
ms.openlocfilehash: b691a9d722a82e68384f8937479c5f71d3f4c11d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096165"
---
# <a name="meetings-first"></a>Meetings First

"Reuniões Primeiro" é direcionado e otimizado para organizações do Skype for Business Server com Enterprise Voice locais que querem começar a usar reuniões do Teams o mais rapidamente possível. Para essas organizações, o Meetings First é uma alternativa ao uso do modo **Ilhas** que prioriza a experiência de reuniões do Teams.

## <a name="what-is-meetings-first"></a>O que é Reuniões Primeiro?

Reuniões Primeiro se baseia no modo de coexistência **SfBWithTeamsCollabAndMeetings.** Reuniões Primeiro não é um produto ou um recurso, é uma configuração que usa recursos e recursos do Teams e do Skype for Business para fornecer uma experiência de coexistência personalizada exclusivamente.

Em Reuniões Primeiro, os usuários criam sua reunião no Teams, enquanto continuam a usar o Skype for Business para chat, chamadas e presença. Não há sobreposição de modalidades entre o Teams e o Skype for Business. Chat, chamadas e presença estão no Skype for Business e desligados no Teams. Isso permite cenários exclusivos "melhor juntos" entre o Skype for Business e o Teams que aprimoram a experiência do usuário durante a coexistência, bem como cenários de interoperabilidade com usuários somente do **Teams.**

![Captura de tela do cenário melhor em conjunto com o Teams e o Skype for Business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Reuniões Primeiro é uma melhor combinação para organizações que não têm nem poucos usuários de chat do Teams ativos. Os usuários de chat do Active Teams não devem ser trocados para o modo Reuniões Primeiro, pois eles perderiam a capacidade de conversar no Teams e de acessar seu histórico de chat. Em vez disso,  esses usuários devem ser acossados no modo Ilhas, e as Reuniões Primeiro só são concedidas aos usuários que ainda não estão ativos no chat no Teams.

## <a name="who-should-consider-meetings-first"></a>Quem deve considerar Reuniões Primeiro?

As Reuniões Primeiro foram projetadas para organizações que usam o Skype for Business Server com Enterprise Voice que querem acelerar sua movimentação para reuniões do Teams, especialmente aquelas com forte disciplina de IT que querem um caminho de atualização gerenciado e determinístico para o Teams.

Para organizações complexas ou grandes, as migrações de voz geralmente são feitas site a site e podem levar muito tempo, potencialmente vários anos, resultando em cenários de coexistência estendidos. Se essa coexistência estiver no modo **Ilhas,** os usuários sempre terão a opção de duas soluções de reunião (Skype for Business e Teams), o que pode resultar em situações confusas ou suboptimais. Ao contrário das migrações de voz, as migrações de reuniões geralmente podem ser concluídas em toda a empresa em um curto período de tempo. As organizações que querem mudar completamente para reuniões do Teams o mais rapidamente possível (e sem esperar a conclusão da migração de voz) devem considerar Reuniões Primeiro.

As Reuniões Primeiro podem não ser úteis para organizações que não têm Enterprise Voice usuários. Essas organizações devem ser capazes de atualizar para o **Teams apenas** assim que eles podem adotar reuniões do Teams. Eles devem considerar ignorar reuniões primeiro.

Além disso, Reuniões Primeiro é útil para organizações cujo escopo é uma solução de reunião pura, por exemplo, quando um RFP "somente reuniões" está sendo emitido.

## <a name="capabilities-in-meetings-first"></a>Recursos em reuniões primeiro

A Reunião Primeiro reúne os seguintes recursos:

- [Provisionar um usuário do Skype for Business Server (local)](./tutorial-audio-conferencing.yml?tutorial-step=3) com a [Audioconferência do Teams.](tutorial-audio-conferencing.yml)
- [Serviço de Migração](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)de Reuniões : reuniões organizadas pelo usuário serão migradas para a nuvem e convertidas em reuniões do Teams à medida que o usuário for promovido para Reuniões Primeiro (exige o Exchange Online).
- Experiência do usuário simplificada no Teams, centralizada em reuniões e equipes e canais do Teams (que, opcionalmente, podem ser [ocultos](teams-app-permission-policies.md)usando a política permissões do aplicativo ); [O chat privado, a chamada](teams-client-experience-and-conformance-to-coexistence-modes.md) e a auto-presença do Teams não são expostos em Reuniões Primeiro, permitindo que o esforço de implantação e adoção se concentre totalmente nas reuniões.
- Experiência [de reunião do Teams Superior](tutorial-meetings-in-teams.yml).
- "Melhor juntos" entre o Teams e o Skype for Business: 
  - Espera automática: quando em uma reunião no Teams, entrar em uma chamada no Skype for Business colocará a reunião do Teams em espera e vice-versa. Isso impede que os usuários tenha suas chamadas privadas ouvidas pelos participantes das reuniões.
    ![Captura de tela do cenário melhor em conjunto com o Teams e o Skype for Business](media/meetings-first-better-together-hold.png)
  - Reconciliação de presença: a atividade no Teams é refletida na presença do usuário, que é a presença do Skype for Business, já que o chat e a chamada estão no Skype for Business. Especificamente, quando os primeiros usuários de reuniões estão em uma reunião do Teams, sua presença será atualizada para refletir isso. Quando eles apresentarem sua tela, sua presença será atualizada para mostrar Não Incomodar (com base em suas configurações no Skype for Business).
  - Reconciliação de controle HID do dispositivo USB (também disponível no Mac): os controles HID são honrados pelo Teams durante as reuniões do Teams e pelo Skype for Business em todas as outras circunstâncias.
  - A menos que mencionado de outra forma, os recursos Better Together exigem clientes recentes da área de trabalho do Windows no momento.

## <a name="prerequisites-for-meetings-first"></a>Pré-requisitos para reuniões primeiro

Os únicos requisitos rígidos para Reuniões Primeiro são os mesmos dos requisitos para o Teams com o Active Directory local e uma implantação local do Skype for Business:

- [Pré-requisitos gerais para o Teams](upgrade-plan-journey-prerequisites.md), incluindo
- [Identidade e autenticação no Teams](identify-models-authentication.md) e
- [Configurar o Azure Active Directory para o Teams e o Skype for Business.](/skypeforbusiness/hybrid/configure-azure-ad-connect)

Uma [topologia híbrida](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) do Skype for Business não é necessária, mas é recomendada. Alguns recursos, como o Serviço de Migração de Reuniões e interoperabilidade, dependem dessa topologia.

As Reuniões Primeiro são suportadas com qualquer versão do Skype for Business Server (e conhecida por trabalhar com o Lync Server sem mais suporte). Ele é suportado com qualquer cliente do Skype for Business com suporte, no entanto, os recursos Better Together exigem um cliente recente.

Depois que esses requisitos são atendidos (e não anteriores), os usuários podem ser licenciados para [o Microsoft 365 ou Office 365 e o Teams.](/office365/enterprise/assign-licenses-to-user-accounts)

Para a melhor experiência de reuniões, os usuários devem estar habilitados para [Exchange Online,](exchange-teams-interact.md) [SharePoint Online e OneDrive for Business](sharepoint-onedrive-interact.md)e criação de grupo do Microsoft 365. As Reuniões Primeiro são suportadas para usuários cuja caixa de correio está no Exchange local, ou que não têm o SharePoint Online ou o OneDrive For Business, ou a criação de grupos do Microsoft 365. No entanto, sua experiência será menos completa. Em particular, para organizações que usam o Exchange Server local, pode haver (dependendo da versão do Exchange Server) algumas limitações para criar e exibir reuniões do cliente teams, bem como em relação aos recursos de conformidade.

No mínimo, os usuários devem ser [licenciados para o Teams](/microsoft-365/admin/manage/assign-licenses-to-users). Além disso, eles podem ser licenciados para [Audioconferência](set-up-audio-conferencing-in-teams.md), se necessário.

Recomendamos que [você conceda o modo **SfBOnly** ou **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como padrão de locatário no momento em que licenciar os usuários. Isso garante que os usuários não comecem a  usar o Teams por conta própria no modo padrão ilhas antes de você estar pronto para iniciar reuniões primeiro.

As Reuniões Primeiro são suportadas em clientes de área de trabalho completa (Windows e Mac), em clientes do navegador e em clientes móveis. Ele também é compatível com salas [do Microsoft Teams.](/microsoftteams/room-systems/) O Better Together requer o cliente de área de trabalho completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Preparar-se para reuniões do Teams em Reuniões Primeiro

Para que os usuários tenham a melhor experiência possível nas reuniões do Teams, você deve:

- Siga as etapas em [Reuniões e conferências do Microsoft Teams,](deploy-meetings-microsoft-teams-landing-page.md)em particular.
- [Avalie seu ambiente](3-envision-evaluate-my-environment.md).
- [Preparar a rede da sua organização para o Microsoft Teams.](prepare-network.md)
- Atualize suas salas de reunião com dispositivos e soluções de sala de reunião capazes do Teams [ou](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)use a Cloud [Video Interop](cloud-video-interop.md) para o Microsoft Teams para permitir que suas salas e dispositivos de terceiros existentes participem de reuniões do Teams.
- Equipar seus usuários com [dispositivos de áudio e vídeo USB certificados.](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)
- Prepare-se [para impulsionar a conscientização e a adoção para reuniões do Teams.](adopt-microsoft-teams-landing-page.md)
- [Planeje seu gerenciamento de serviço](4-envision-plan-my-service-management.md).
- Familiarize-se com os relatórios rich Call Analytics para [solucionar problemas de qualidade de chamada ruim.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Você pode considerar executar um piloto pronto para produção em escala moderada neste estágio.

## <a name="configure-users-for-meetings-first"></a>Configurar usuários para reuniões primeiro

Depois de licenciar seus usuários e preparar sua organização para reuniões do Teams, é hora de habilitar seus usuários para reuniões primeiro. Facilitamos a tarefa: uma única configuração fará tudo isso!

Todos os recursos e experiências do usuário em [](teams-client-experience-and-conformance-to-coexistence-modes.md) Reuniões Primeiro, incluindo a configuração do cliente do Teams e a conformidade automática da experiência do usuário, o Serviço de Migração de Reuniões e os recursos de Melhor Avaliação, são configurados concedendo ao usuário (ou grupo de usuários ou locatário padrão) o modo de [coexistência SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) no centro de administração do [Microsoft Teams](manage-teams-in-modern-portal.md) ou usando [o PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Captura de tela das configurações de administrador para habilitar reuniões primeiro](media/teams-meeting-admin-settings.png)

Opcionalmente, você deve ocultar o aplicativo Teams e Channels da navegação à esquerda do cliente do Teams de seus usuários para concentrar ainda mais sua experiência em reuniões, que podem ser alcançadas usando a política de Permissão do Aplicativo [.](teams-app-permission-policies.md)

## <a name="reporting-and-call-analytics"></a>Análise de relatórios e de chamada

Relatórios e análises de chamada para reuniões do Teams em Reuniões Primeiro não são alterados do que estão em outros modos.

## <a name="related-links"></a>Links relacionados

Depois de revisar este artigo, talvez você queira consultar [Escolher](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)sua jornada de atualização, diretrizes de migração e [interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)e [Coexistência](coexistence-chat-calls-presence.md) com o Skype for Business para obter mais detalhes.