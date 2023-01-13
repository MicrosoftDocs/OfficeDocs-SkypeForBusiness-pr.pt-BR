---
title: Configurar o lobby de reuniões do Microsoft Teams para reuniões confidenciais
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Saiba como configurar o lobby de reuniões do Teams para aprimorar a segurança de reuniões confidenciais usando políticas de administrador, rótulos de confidencialidade e modelos de reunião.
ms.openlocfilehash: 1905bc337f0260e86b2351da5015b8e1ba641bf4
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800151"
---
# <a name="configure-the-microsoft-teams-meeting-lobby-for-sensitive-meetings"></a>Configurar o lobby de reuniões do Microsoft Teams para reuniões confidenciais

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

O lobby da reunião é uma ferramenta que você pode usar para garantir que pessoas inadequadas não sejam admitidas em reuniões. Ao manter diferentes tipos de participantes no lobby, os organizadores da reunião podem vetá-los e garantir que seja apropriado que eles participem da reunião.

Por padrão, as pessoas em sua organização e [convidados](guest-access.md) são admitidos em reuniões diretamente e participantes de domínios confiáveis e participantes anônimos devem esperar no lobby para serem admitidos por um organizador da reunião. Os organizadores da reunião podem alterar essa configuração padrão para cada reunião que eles criam.

O lobby e outras configurações relacionadas podem ser controlados pelo Administrador do Teams usando políticas de reunião, modelos de reunião e rótulos de confidencialidade para personalizar a experiência para diferentes usuários e diferentes tipos de reuniões.

A tabela a seguir lista os recursos que você pode usar para ajudar a gerenciar a experiência de lobby para sua organização e onde configurá-los.

|Configuração|Administração política|Rótulo de confidencialidade|Modelo|Organizador da reunião|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Anunciar quando os chamadores discados ingressarem ou saírem|Não|Não|Sim|Sim|
|Usuários anônimos e chamadores discadas podem iniciar uma reunião|Sim|Não|Não|Não|
|Usuários anônimos podem participar de uma reunião|Sim|Não|Não|Não|
|Pessoas discagem pode ignorar o lobby|Sim|Sim|Sim|Sim|
|Quem pode ignorar o lobby|Sim|Sim|Sim|Sim|

Para obter informações sobre como usar modelos e rótulos de confidencialidade para configurar as configurações de reunião, confira [Visão geral dos modelos de reunião personalizados no Microsoft Teams](custom-meeting-templates-overview.md) e [Use rótulos de confidencialidade para proteger itens de calendário, reuniões do Teams e chat](/microsoft-365/compliance/sensitivity-labels-meetings).

> [!Note]
> As configurações de reunião em rótulos de confidencialidade e modelos de reunião personalizados exigem Teams Premium.

## <a name="lobby-settings-for-different-types-of-meetings"></a>Configurações de lobby para diferentes tipos de reuniões

As seguintes configurações estão disponíveis para quem pode ignorar o lobby:

- Todos
- Pessoas da minha organização e organizações confiáveis
- Pessoas na minha organização e convidados
- Pessoas da minha organização
- Pessoas que foram convidados
- Organizadores e co-organizadores

Embora o organizador da reunião normalmente escolha qual configuração usar para cada reunião, você pode impor uma configuração específica usando um modelo de reunião ou um rótulo de confidencialidade.

Se sua organização exigir que determinados tipos de reuniões não sejam atendidos por pessoas fora da organização, considere um modelo de reunião que só permita que pessoas em sua organização ignorem o lobby. Isso garante que pessoas de fora da organização que foram acidentalmente convidadas ou enviadas um link de reunião não possam participar da reunião diretamente.

Se sua organização tiver reuniões em que informações altamente confidenciais sejam compartilhadas e você precisar ter certeza de que apenas determinadas pessoas comparecem, considere usar um modelo de reunião ou um rótulo de confidencialidade que permita apenas que os organizadores da reunião ignorem o lobby. Isso garante que os organizadores possam examinar cada participante de entrada para garantir que eles devem estar na reunião. Isso também impede que a reunião comece até que um organizador ingresse.

Para reuniões confidenciais em geral, considere usar a opção **Pessoas que foram convidados**. Isso garante que as pessoas que não têm um convite de reunião (incluindo convites encaminhados) passem pelo lobby. (O organizador da reunião também pode impedir o encaminhamento quando eles criam a reunião.)

Para obter informações sobre como usar modelos de reunião e rótulos de confidencialidade juntos, consulte [Usar modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos para reuniões confidenciais](meeting-templates-sensitivity-labels-policies.md).

### <a name="attendees-calling-in-by-phone"></a>Participantes chamando por telefone

Por padrão, os participantes que estão discando por telefone passam pelo lobby. Os administradores podem alterar esse padrão com os **usuários do Dial-in podem ignorar a** política de reunião de administrador do lobby. Se você quiser impor que essa configuração esteja ativada ou desativada, você deve usar um modelo de reunião ou um rótulo de confidencialidade.

Se houver circunstâncias em que você deseja permitir que os chamadores ignorem o lobby, os organizadores da reunião podem controlar essa configuração ou você pode impor isso por meio de um modelo de reunião ou rótulo de confidencialidade.

#### <a name="join-and-leave-notifications"></a>Ingressar e deixar notificações

Os organizadores da reunião têm a opção de ter os participantes ligando por telefone anunciados quando ingressarem ou saírem de uma reunião. Se você quiser garantir que os participantes do telefone sejam anunciados para determinados tipos de reuniões, você poderá impor essa configuração com um modelo de reunião.

## <a name="meeting-with-anonymous-participants"></a>Reunião com participantes anônimos

A menos que você permita que todos ignorem o lobby, os participantes anônimos devem passar pelo lobby para participar da reunião. Em seguida, os organizadores da reunião podem decidir se esses participantes devem ser admitidos.

Se sua organização não permitir que participantes anônimos participem de reuniões, você poderá desativar os **usuários anônimos que podem ingressar em uma** configuração de reunião no centro de administração do Teams. Para obter mais informações, consulte [Gerenciar configurações de reunião no Microsoft Teams](/microsoftteams/meeting-settings-in-teams).

Se você tiver determinados grupos em sua organização - como marketing - que precisam organizar reuniões com participantes anônimos e outros - como pesquisa - que não devem, você pode usar políticas de reunião do Teams para configurar a junção de reunião anônima para diferentes grupos. (Você precisará ativar os **usuários Anônimos pode ingressar em uma** configuração de reunião mencionada acima para que isso funcione.) Para obter detalhes, confira [Configurações da política de reunião – Participantes & convidados](/microsoftteams/meeting-policies-participants-and-guests).

## <a name="related-topics"></a>Tópicos relacionados

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)

[Gerenciar reuniões externas e chat no Microsoft Teams](/microsoftteams/manage-external-access)
