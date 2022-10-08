---
title: Reuniões Primeiro – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Saiba mais sobre o Meetings First, em que os usuários podem criar sua reunião no Teams, enquanto continuam a usar Skype for Business para chat, chamada e presença.
ms.localizationpriority: medium
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
ms.openlocfilehash: 88be8ef1e43cc9d17fb541f6c56186959aeeb8a4
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999336"
---
# <a name="meetings-first"></a>Meetings First

O "Meetings First" é direcionado e otimizado para Skype for Business Server organizações com Enterprise Voice locais que desejam começar a usar reuniões do Teams o mais rápido possível. Para essas organizações, o Meetings First é uma alternativa ao uso **do modo Ilhas** que prioriza a experiência de reuniões do Teams.

## <a name="what-is-meetings-first"></a>O que é o Meetings First?

Meetings First é baseado no modo de coexistência **SfBWithTeamsCollabAndMeetings** . O Meetings First não é um produto ou um recurso, é uma configuração que usa recursos e recursos do Teams e do Skype for Business para fornecer uma experiência de coexistência personalizada exclusivamente.

No Meetings First, os usuários criam sua reunião no Teams, enquanto continuam a usar Skype for Business para chat, chamada e presença. Não há sobreposição de modalidades entre o Teams e o Skype for Business. Chat, chamada e presença estão ativados Skype for Business e desativados no Teams. Essa configuração permite cenários exclusivos "melhores juntos" entre o Skype for Business e o Teams que aprimoram a experiência do usuário durante a coexistência, bem como cenários de interoperabilidade somente com usuários do **Teams**.

![Captura de tela do melhor cenário em conjunto com o Teams e o Skype for Business.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> O Meetings First é uma correspondência melhor para organizações que não têm nem poucos usuários de chat do Teams ativos. Os usuários de chat do Teams ativos não devem ser alternados para o modo Reuniões Primeiro, pois perderiam a capacidade de conversar no Teams e acessar seu histórico de chat. Esses usuários devem ser avôs no modo **Ilhas** , e o Meetings First só é concedido aos usuários que ainda não estão ativos no chat no Teams.

## <a name="who-should-consider-meetings-first"></a>Quem deve considerar o Meetings First?

O Meetings First é para organizações que usam Skype for Business Server com Enterprise Voice que desejam acelerar sua mudança para as reuniões do Teams. O Meetings First é especialmente para organizações com uma disciplina de TI forte que desejam um caminho de atualização gerenciado para o Teams.

Para organizações complexas ou grandes, as migrações de voz normalmente são feitas site a site e podem levar muito tempo, potencialmente vários anos, resultando em cenários de coexistência estendidos. Se essa coexistência estiver no modo **Ilhas**, os usuários sempre terão a opção de duas soluções de reunião (Skype for Business e Teams), o que pode resultar em situações confusas ou abaixo do ideal. Ao contrário das migrações de voz, as migrações de reuniões geralmente podem ser concluídas em toda a empresa em um curto período de tempo. As organizações que desejam mudar completamente para reuniões do Teams o mais rápido possível (e sem esperar que a migração de voz seja concluída) devem considerar as Reuniões Primeiro.

O Meetings First pode não ser útil para organizações que não têm Enterprise Voice usuários. Essas organizações devem ser capazes de atualizar para o **Teams somente** assim que forem capazes de adotar reuniões do Teams. Eles devem considerar ignorar o Meetings First.

Além disso, o Meetings First é útil para organizações cujo escopo é uma solução de reunião pura, por exemplo, quando uma RFP "somente reuniões" está sendo emitida.

## <a name="capabilities-in-meetings-first"></a>Funcionalidades nas Reuniões Primeiro

O Meeting First reúne os seguintes recursos:

- [Provisione Skype for Business Server usuário (local) com](./tutorial-audio-conferencing.yml?tutorial-step=3) a [Audioconferência do Teams](tutorial-audio-conferencing.yml).
- [Serviço de Migração](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) de Reuniões: as reuniões organizadas pelo usuário serão migradas para a nuvem e convertidas em reuniões do Teams à medida que o usuário for promovido para o Meetings First (requer Exchange Online).
- Experiência do usuário simplificada no Teams, centralizada em reuniões e equipes e canais do Teams (que podem ser ocultos usando a política [de Permissões de Aplicativo](teams-app-permission-policies.md)). [Chat privado do Teams, chamadas e autoatendimento](teams-client-experience-and-conformance-to-coexistence-modes.md) não são expostos nas Reuniões Primeiro, permitindo que a implantação e o esforço de adoção se concentrem em reuniões.
- Experiência superior [de reunião do Teams](tutorial-meetings-in-teams.yml).
- "Melhor juntos" entre o Teams e Skype for Business: 
  - Retenção automática: quando estiver em uma reunião no Teams, receber uma chamada no Skype for Business colocará a reunião do Teams em espera e vice-versa. Isso impede que os usuários tenha suas chamadas privadas ouvidas pelos participantes das reuniões.
    ![Captura de tela do melhor cenário em conjunto com o Teams e o Skype for Business.](media/meetings-first-better-together-hold.png)
  - Reconciliação de presença: a atividade no Teams é refletida na presença do usuário, que é a Skype for Business, pois o chat e a chamada estão em Skype for Business. Especificamente, quando os usuários do Meetings First estão em uma reunião do Teams, sua presença será atualizada para refletir isso. Quando apresentarem a tela, sua presença será atualizada para mostrar Não Incomodar (com base nas configurações no Skype for Business).
  - Reconciliação de controle HID do dispositivo USB (também disponível no Mac): os controles HID são respeitados pelo Teams durante as reuniões do Teams e por Skype for Business em todas as outras circunstâncias.
  - A menos que mencionado de outra forma, os recursos Better Together exigem clientes recentes da área de trabalho do Windows no momento.

## <a name="prerequisites-for-meetings-first"></a>Pré-requisitos para reuniões primeiro

Os únicos requisitos rígidos para o Meetings First são os mesmos que os requisitos para o Teams com Active Directory local e uma Skype for Business implantação local:

- [Pré-requisitos gerais para o Teams](upgrade-plan-journey-prerequisites.md), incluindo
- [Identidade e autenticação no Teams](identify-models-authentication.md) e
- [Configure o Azure Active Directory para Teams e Skype for Business](/skypeforbusiness/hybrid/configure-azure-ad-connect).

Uma [Skype for Business topologia](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) híbrida não é necessária, mas é recomendável. Alguns recursos, como o Serviço de Migração de Reuniões e a interoperabilidade, dependem dessa topologia.

O Meetings First é compatível com qualquer versão do Skype for Business Server (e conhecido por trabalhar com o Lync Server sem mais suporte). Ele tem suporte com qualquer cliente Skype for Business suporte, no entanto, as funcionalidades Better Together exigem um cliente recente.

Depois que esses requisitos forem atendidos (e não anteriores), os usuários poderão ser licenciados para [o Microsoft 365 ou o Office 365 e o Teams](/office365/enterprise/assign-licenses-to-user-accounts).

Para obter a melhor experiência do Meetings First, os usuários devem ser habilitados para [Exchange Online](exchange-teams-interact.md), [SharePoint Online e OneDrive for Business](sharepoint-onedrive-interact.md) e criação de grupos do Microsoft 365. O Meetings First é compatível com usuários cuja caixa de correio está no Exchange local, ou que não têm o SharePoint Online, o OneDrive For Business ou a criação de grupos do Microsoft 365. No entanto, sua experiência será menos completa. Para organizações que usam o Exchange Server local, pode haver (dependendo da versão do Exchange Server) algumas limitações para criar e exibir reuniões do cliente teams e algumas limitações em relação aos recursos de conformidade.

No mínimo, os usuários devem ser [licenciados para o Teams](/microsoft-365/admin/manage/assign-licenses-to-users). Além disso, eles podem ser licenciados para [Audioconferência](set-up-audio-conferencing-in-teams.md), se necessário.

Recomendamos que [você **conceda o modo SfBOnly** ou **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como o padrão de locatário no momento em que você licencia os usuários. Essa configuração garante que os usuários não comecem a usar o Teams por conta própria no modo de **Ilhas** padrão antes de iniciar o Meetings First.

O Meetings First tem suporte em clientes completos da área de trabalho (Windows e Mac), em clientes de navegador e em clientes móveis. Ele também é compatível com [Salas do Microsoft Teams](/microsoftteams/room-systems/). O Better Together requer o cliente de área de trabalho completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Preparar-se para reuniões do Teams em Reuniões Primeiro

Para que os usuários tenham a melhor experiência possível em reuniões do Teams, você deve:

- Siga as etapas em [Reuniões e conferências do Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md), em particular.
- [Avalie seu ambiente](3-envision-evaluate-my-environment.md).
- [Prepare a rede da sua organização para o Microsoft Teams](prepare-network.md).
- Atualize suas salas de reunião com [](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)soluções e dispositivos de sala de reunião compatíveis com o Teams ou use a Interoperabilidade de Vídeo na Nuvem para [o Microsoft Teams](cloud-video-interop.md) para permitir que suas salas e dispositivos de terceiros existentes participem de reuniões do Teams.
- Equipar seus usuários com [dispositivos de áudio e vídeo USB certificados](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).
- Prepare-se [para promover a conscientização e a adoção para reuniões do Teams](adopt-microsoft-teams-landing-page.md).
- [Planeje o gerenciamento de serviços](4-envision-plan-my-service-management.md).
- Familiarize-se com os relatórios avançados do Call Analytics para [solucionar problemas de baixa qualidade de chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Você pode considerar a execução de um piloto pronto para produção de escala moderada neste estágio.

## <a name="configure-users-for-meetings-first"></a>Configurar usuários para o Meetings First

Depois de licenciar seus usuários e preparar sua organização para reuniões do Teams, é hora de habilitar os usuários para o Meetings First. Facilitamos: uma configuração fará tudo.

Todos os recursos e experiências do usuário nas Reuniões Primeiro , incluindo a configuração [](teams-client-experience-and-conformance-to-coexistence-modes.md) do cliente do Teams e a conformidade automática da experiência do usuário, do Serviço de Migração de Reuniões e dos recursos Better Together, são configurados concedendo ao usuário (ou grupo de usuários ou padrão de locatário) o modo de [coexistência SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) no centro de administração do [Microsoft Teams](manage-teams-in-modern-portal.md) ou usando o [PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Captura de tela das configurações de administrador para habilitar o Meetings First.](media/teams-meeting-admin-settings.png)

Se você quiser ocultar o aplicativo Teams e Canais da navegação à esquerda do cliente do Teams dos usuários para concentrar ainda mais sua experiência em reuniões, use a política de Configuração [de Aplicativos](teams-app-setup-policies.md).

## <a name="reporting-and-call-analytics"></a>Análise de Relatórios e Chamadas

Relatórios e Análise de Chamadas para reuniões do Teams em Reuniões Primeiro não são alterados do que estão em outros modos.

## <a name="related-links"></a>Links relacionados

Para obter mais informações, consulte [Escolher](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) seu percurso de atualização, diretrizes de [migração e interoperabilidade](migration-interop-guidance-for-teams-with-skype.md) e [coexistência](coexistence-chat-calls-presence.md) com Skype for Business para obter mais detalhes.
