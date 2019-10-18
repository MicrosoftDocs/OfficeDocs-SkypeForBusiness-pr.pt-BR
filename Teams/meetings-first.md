---
title: Microsoft Teams | Reuniões primeiro
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: Saiba mais sobre reuniões primeiro, onde os usuários podem criar uma reunião no Microsoft Teams, enquanto continuam a usar o Skype for Business para chat, chamadas e presença.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3207a7e7f460cb2941dd4c46df2a215df7997ed4
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564901"
---
# <a name="meetings-first"></a>Meetings First

"Reuniões primeiro" tem como alvo e são otimizadas para organizações do Skype for Business Server com Enterprise Voice no local que desejam começar a usar reuniões do Team o mais rápido possível. Para essas organizações, as reuniões primeiro são uma alternativa para usar o modo de **ilhas** que prioriza a experiência de reuniões do teams.

## <a name="what-is-meetings-first"></a>O que é reunião primeiro?

As reuniões primeiro se baseiam no modo de coexistência de **SfBWithTeamsCollabAndMeetings** . As reuniões primeiro não são um produto ou um recurso — é uma configuração que aproveita recursos e recursos do Teams e do Skype for Business para fornecer uma experiência de coexistência adaptada exclusivamente.

Em reuniões primeiro, os usuários criam sua reunião no Microsoft Teams, ao mesmo tempo em que continuam a usar o Skype for Business para chat, chamadas e presença. Não há sobreposição de modalidades entre o Teams e o Skype for Business. Chat, chamadas e presença são ativadas no Skype for Business e no Teams. Isso permite cenários exclusivos "melhor juntos" entre o Skype for Business e as equipes que melhoram a experiência do usuário durante a coexistência, bem como cenários de interoperabilidade com usuários do Microsoft **Teams** .

![Captura de tela do cenário melhor em conjunto com o Microsoft Teams e o Skype for Business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> As reuniões primeiro são uma melhor combinação para organizações que têm um ou poucos usuários de chat de equipes ativas. Os usuários de chat de equipes ativas não devem ser trocados para o modo de reuniões de primeira mão, pois perderão a capacidade de conversar com o Microsoft Teams e acessar seu histórico de chats. Esses usuários devem ser preenchidos no modo de **ilhas** em vez disso, e as reuniões são concedidas primeiro somente aos usuários que ainda não estão ativos no chat no Microsoft Teams.

## <a name="who-should-consider-meetings-first"></a>Quem deve considerar as reuniões primeiro?

As reuniões primeiro foram projetadas para organizações que usam o Skype for Business Server com Enterprise Voice que desejam acelerar a mudança para reuniões de equipes, especialmente aquelas com disciplina de ti forte que queira um caminho de atualização determinístico e gerenciado para o Teams.

Para organizações complexas ou grandes, as migrações de voz geralmente são feitas de acordo com cada site e podem levar muito tempo, possivelmente vários anos, resultando em cenários de coexistência estendidos. Se essa coexistência estiver no modo de **ilhas** , os usuários terão sempre a opção de duas soluções de reunião (Skype for Business e Teams), o que pode resultar em situações confusas ou subótimas. Ao contrário das migrações de voz, as migrações de reuniões geralmente podem ser concluídas em toda a empresa em um curto período de tempo. As organizações que desejam alternar completamente para reuniões de equipe o mais rápido possível (e sem esperar que a migração de voz sejam concluídas) devem considerar as reuniões primeiro.

As reuniões primeiro podem não ser úteis para organizações que não tenham usuários de voz empresarial. Essas organizações podem ser capazes de atualizar para o Microsoft **Teams somente** assim que puderem adotar reuniões de equipe. Eles devem considerar ignorar reuniões primeiro.

Além disso, as reuniões primeiro são úteis para organizações cujo escopo é uma solução de reunião simples, por exemplo, quando uma RFP de "somente reuniões" está sendo emitido.

## <a name="capabilities-in-meetings-first"></a>Recursos em reuniões primeiro

Em primeiro lugar, a reunião traz os seguintes recursos:

- [Provisionar um usuário do Skype for Business Server (local)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) com [conferência de áudio do teams](tutorial-audio-conferencing.yml).
- [Serviço de migração de reuniões](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): as reuniões organizadas pelo usuário serão migradas para a nuvem e convertidas em reuniões do Team, pois o usuário será promovido para reuniões primeiro (requer o Exchange Online).
- Experiência do usuário simplificada no Microsoft Teams, centralizado em reuniões de equipes e equipes e canais (que, opcionalmente, podem ser ocultados usando a [política de permissões do aplicativo](teams-app-permission-policies.md)); As [equipes de chat, chamada e autopresença particulares do teams](teams-client-experience-and-conformance-to-coexistence-modes.md) não são expostas em reuniões primeiro, permitindo que a implantação e o esforço de adoção se destaquem totalmente em reuniões.
- [Experiência de reunião de equipes](tutorial-meetings-in-teams.yml)superiores.
- "Melhor juntos" entre o Teams e o Skype for Business: 
  - Retenção automática: quando estiver em uma reunião no Microsoft Teams, entrar em uma chamada no Skype for Business colocará a reunião do Microsoft Teams em espera e vice-versa. Isso impede que os usuários tenham suas chamadas privadas ensaiadas pelos participantes da reunião.
    ![Captura de tela do cenário melhor em conjunto com o Microsoft Teams e o Skype for Business](media/meetings-first-better-together-hold.png)
  - Reconciliação de presença: a atividade no Teams é refletida na presença do usuário, que é a presença do Skype for Business, pois o chat e as chamadas estão no Skype for Business. Especificamente, quando as reuniões dos primeiros usuários estiverem em uma reunião do Teams, sua presença será atualizada para refletir isso. Quando apresentarem sua tela, a presença deles será atualizada para mostrar não incomodar (com base nas configurações do Skype for Business).
  - Reconciliação de controle HID de dispositivo USB (também disponível no Mac): os controles HID são atendidos pelo Teams enquanto em reuniões do Teams e pelo Skype for Business em todas as outras circunstâncias.
  - A menos que seja mencionado em contrário, os recursos mais avançados exigem clientes da área de trabalho do Windows recentes no momento.

## <a name="prerequisites-for-meetings-first"></a>Pré-requisitos para reuniões primeiro

As únicas exigências de reuniões primeiro são iguais às do teams com o Active Directory local e uma implantação local do Skype for Business:

- [Pré-requisitos gerais para equipes](upgrade-plan-journey-prerequisites.md), incluindo
- [Identidade e autenticação no Teams](identify-models-authentication.md) e
- [Configurar o Azure Active Directory para Teams e o Skype for Business](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect).

Não é necessária uma [topologia híbrida do Skype for Business](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) , mas é recomendável. Alguns recursos, como o serviço de migração de reuniões e interoperabilidade dependem dessa topologia.

As reuniões primeiro são compatíveis com qualquer versão do Skype for Business Server (e conhecidas para funcionar com o Lync Server sem suporte). Ele é compatível com qualquer cliente Skype for Business compatível, mas melhor recurso juntos exige um cliente recente.

Depois que esses requisitos são atendidos (e não antes), os usuários podem ser [licenciados para o Office 365 e Teams](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts).

Para a melhor experiência da melhor reunião, os usuários devem ser habilitados para o [Exchange Online](exchange-teams-interact.md), o [SharePoint Online e o onedrive for Business](sharepoint-onedrive-interact.md), e a criação de grupos do Office 365. As reuniões primeiro são compatíveis com os usuários cuja caixa de correio está no Exchange local ou que não têm o SharePoint Online ou o OneDrive for Business, ou a criação de grupos do Office 365. No entanto, sua experiência será menos completa. Em particular, para organizações que usam o Exchange Server local, pode haver (dependendo da versão do Exchange Server) algumas limitações para criar e exibir reuniões do cliente do Teams, bem como com relação aos recursos de conformidade.

No mínimo, os usuários devem ser [licenciados para equipes](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide). Além disso, eles podem ser licenciados para [conferências de áudio](set-up-audio-conferencing-in-teams.md), se necessário.

Recomendamos que você [conceda o **SfBOnly** ou o modo **SfBWithTeamsCollab** ](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) como padrão do locatário no momento em que licenciasse os usuários. Isso garante que os usuários não comecem a usar o Microsoft Teams no modo de **ilhas** padrão antes de você estar pronto para iniciar reuniões primeiro.

As reuniões primeiro têm suporte em clientes de área de trabalho completos (Windows e Mac), em clientes de navegador e em clientes móveis. Ele também é compatível com as [salas do Microsoft Teams](https://docs.microsoft.com/microsoftteams/room-systems/). Melhor juntos requer o cliente de área de trabalho completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Preparar-se primeiro para reuniões do teams em reuniões

Para os usuários terem a melhor experiência possível em reuniões do Teams, você deve:

- Siga as etapas em [reuniões e conferências do Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md), em particular.
- [Avalie seu ambiente](3-envision-evaluate-my-environment.md).
- [Prepare a rede da sua organização para o Microsoft Teams](prepare-network.md).
- Atualize suas salas de reunião com as [soluções e dispositivos da sala de reunião](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)habilitados para o Microsoft Teams ou use a [interoperabilidade de vídeo em nuvem para Microsoft Teams](cloud-video-interop.md) para permitir que seus dispositivos e salas de terceiros participem de reuniões de equipe.
- Equipar seus usuários com [dispositivos de áudio e vídeo USB certificados](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).
- Prepare-se para a [conscientização da unidade e a adoção de reuniões do teams](adopt-microsoft-teams-landing-page.md).
- [Planejar o gerenciamento de serviços](4-envision-plan-my-service-management.md).
- Familiarize-se com os avançados relatórios de análise de chamadas para [solucionar problemas com a qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Você pode considerar a execução de um piloto de preparação da produção de escala moderada neste estágio.

## <a name="configure-users-for-meetings-first"></a>Configurar usuários para reuniões primeiro

Depois de licenciar seus usuários e preparar sua organização para reuniões do Teams, é hora de habilitar seus usuários para reuniões primeiro. Ficou mais fácil: uma única configuração fará tudo isso!

Todos os recursos e experiências do usuário em reuniões primeiro, incluindo a configuração do cliente do Teams e a [conformidade automática](teams-client-experience-and-conformance-to-coexistence-modes.md) da experiência do usuário, o serviço de migração de reuniões e recursos aprimorados juntos, são configurados por meio da concessão do usuário (ou grupo de usuários ou padrão locatário) o [modo de coexistência de SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) no centro de administração do [Microsoft Teams](manage-teams-in-modern-portal.md) ou usando o [PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Captura de tela das configurações do administrador para habilitar as reuniões primeiro](media/teams-meeting-admin-settings.png)

Opcionalmente, se você quiser ocultar o aplicativo equipes e canais da navegação à esquerda do cliente de equipes de seus usuários para concentrar ainda mais sua experiência em reuniões, isso pode ser feito usando a [política de permissão do aplicativo](teams-app-permission-policies.md).

## <a name="reporting-and-call-analytics"></a>Relatórios e análises de chamadas

O relatório e a análise de chamadas para reuniões de equipe em reuniões primeiro não são alterados do que estão em outros modos.

## <a name="related-links"></a>Links relacionados

Depois de revisar este artigo, talvez você queira consultar [escolher a sua viagem de atualização, a](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)orientação de [migração e interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)e [a coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter mais detalhes.


