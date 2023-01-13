---
title: Configurar reuniões do Teams com três camadas de proteção
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
- m365solution-overview
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Saiba como configurar reuniões do Teams para obter uma melhor segurança usando três camadas de proteção, equilibrando a segurança com facilidade de colaboração.
ms.openlocfilehash: 607c4d484df714fd4fba736ffd618aafdbab67d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800135"
---
# <a name="configure-teams-meetings-with-three-tiers-of-protection"></a>Configurar reuniões do Teams com três camadas de proteção

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Os artigos desta série fornecem opções para usar os recursos de conformidade disponíveis no Teams e no Microsoft 365 para criar um ambiente de reunião que atenda aos seus requisitos de conformidade. Examinaremos as opções disponíveis com rótulos e modelos de confidencialidade e como você pode usá-las junto com outras configurações de administrador do Teams.

> [!Note]
> As configurações de reunião em rótulos de confidencialidade e modelos de reunião personalizados exigem Teams Premium.

Este artigo define quatro configurações diferentes, começando com uma configuração de linha de base para reuniões que não têm requisitos de conformidade específicos. Cada configuração adicional representa um avanço significativo na proteção à medida que as opções de reunião se tornam mais restritas. As configurações deste artigo fornecem exemplos de como configurar a proteção para reuniões com diferentes níveis de confidencialidade. Use esses exemplos para entender o que é possível e modificar as configurações específicas conforme necessário para sua organização.

Discutiremos essas três configurações:

- Proteção de linha de base

- Proteção confidencial

- Proteção altamente confidencial

Além disso, discutiremos uma variação da configuração altamente sensível projetada para apresentações que têm interação mínima dos participantes.

## <a name="three-tiers-at-a-glance"></a>Três camadas de relance

A tabela a seguir resume as configurações de cada camada. Use essas configurações como recomendações de ponto de partida e ajuste as configurações para atender às necessidades da sua organização. Dependendo das suas necessidades de conformidade, talvez você não precise de todas as camadas.

|&nbsp;|Base|Sensível|Altamente sensível|Apresentação altamente sensível|
|:-----|:-----|:-----|:-----|:-----|
|Permitir câmera para participantes|**Ativado**|**Ativado**|**Ativado**|**Desativado**|
|Permitir microfone para participantes|**Ativado**|**Ativado**|**Ativado**|**Desativado**|
|Aplicar uma marca d'água ao feed de vídeo de todos|**Desativado**|**Desativado**|**Ativado**|**Ativado**|
|Aplicar uma marca d'água ao conteúdo compartilhado|**Desativado**|**Desativado**|**Ativado**|**Ativado**|
|Criptografia de ponta a ponta|**Desativado**|**Desativado**|**Ativado**|**Ativado**|
|Gerenciar o que os participantes veem|**Desativado**|**Ativado**|**Ativado**|**Ativado**|
|Chat de reunião|**Ativado**|**Ativado**|**Somente em reunião**|**Desativado**|
|Pessoas discagem pode ignorar o lobby|**Desativado**|**Desativado**|**Desativado**|**Desativado**|
|Impedir a cópia do conteúdo do chat na área de transferência|**Desativado**|**Desativado**|**Ativado**|**Ativado**|
|Gravar automaticamente|**Desativado**|**Desativado**|**Desativado**|**Desativado**|
|Quem pode ignorar o lobby|**Pessoas na minha organização, pessoas em domínios confiáveis e convidados**|**Pessoas eu convido**|**Só eu e os co-organizadores**|**Só eu e os co-organizadores**|
|Quem pode apresentar|**Pessoas na minha organização e convidados**|**Pessoas na minha organização e convidados**|**Apenas organizadores e co-organizadores**|**Apenas organizadores e co-organizadores**|
|Quem pode gravar|**Organizadores e apresentadores**|**Organizadores e co-organizadores**|Desabilitado devido à marca d'água|Desabilitado devido à marca d'água|

Detalhes sobre como configurar cada camada são abordados em:

- [Configurar reuniões do Teams com proteção de linha de base](configure-meetings-baseline-protection.md)
- [Configurar reuniões do Teams com proteção para dados confidenciais](configure-meetings-sensitive-protection.md)
- [Configurar reuniões do Teams com proteção para dados altamente confidenciais](configure-meetings-highly-sensitive-protection.md)

## <a name="managing-compliance-with-sensitivity-labels-and-meeting-templates"></a>Gerenciando a conformidade com rótulos de confidencialidade e modelos de reunião

Os modelos de reunião e os rótulos de confidencialidade têm a capacidade de impor determinadas configurações de reunião. A maioria das configurações pode ser imposta como ativada ou desativada ou pode ficar desfigurada para que o organizador da reunião possa defini-las.

> [!Important]
> Alguns recursos são [controlados por políticas de administrador](meeting-templates-sensitivity-labels-policies.md#policies-labels-templates-and-meetings-settings) e devem ser habilitados para que possam ser controlados por modelos de reunião e rótulos de confidencialidade.

Algumas configurações só estão disponíveis em rótulos de confidencialidade e algumas estão disponíveis apenas em modelos. Vários estão disponíveis em ambos:

- Chat
- Criptografia de ponta a ponta
- Configurações de lobby
- Gravação de reunião
- Watermarking

Rótulos e modelos de confidencialidade podem ser usados juntos para ajudá-lo a atender às suas necessidades de conformidade. Para obter mais informações, consulte [Usar modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos](meeting-templates-sensitivity-labels-policies.md).

## <a name="meeting-chat"></a>Chat de reunião

O chat de reunião pode ser uma parte importante da colaboração durante uma reunião. No entanto, talvez você queira restringir o chat de reunião em determinados tipos de reuniões para evitar que informações confidenciais sejam compartilhadas lá.

Como administrador, você pode controlar o chat de reunião das seguintes maneiras:

- **A política de reunião de administrador do Teams** (por usuário ou grupo) pode ser usada para permitir chat, permitir chat para todos, exceto participantes anônimos, ou desativar o chat.
- **A configuração do rótulo de confidencialidade** (por reunião) pode impor que o chat esteja ativado ou desativado ou permitido somente durante a reunião. Essa configuração pode ficar inconfigurada para ser controlada por um modelo ou pelo organizador da reunião.
- **A configuração do modelo** de reunião (por reunião) pode impor que o chat esteja ativado ou desativado ou permitido somente durante a reunião. Essa configuração pode ficar inconfigurada para ser controlada pelo organizador da reunião.

Para as três camadas de proteção, permitimos conversar para reuniões de linha de base e confidenciais e restringi-la em reuniões altamente sensíveis somente na reunião.

Para obter mais informações, consulte [Gerenciar chat para reuniões confidenciais do Teams](manage-chat-sensitive-meetings.md).

## <a name="meeting-recordings"></a>Gravações de reunião

Como administrador, você pode controlar as gravações de reunião das seguintes maneiras:

- A política de reunião de administrador de **gravação na nuvem** (por usuário ou grupo)
- As **Reuniões expiram automaticamente** (exclusão de gravação) política de reunião de administrador (por usuário ou grupo)
- A configuração **Quem pode gravar** em rótulos de confidencialidade e modelos de reunião (por reunião)
- A configuração **record automaticamente** em rótulos de confidencialidade e modelos de reunião (por reunião)

Se sua organização ou determinadas pessoas ou grupos dentro dela nunca puder gravar reuniões, você poderá desativar o recurso usando a política de reunião de administrador de **gravação na nuvem** .

Se houver determinados tipos de reuniões que devem ser sempre gravados, você poderá impor a configuração **Record automaticamente** usando um modelo de reunião ou um rótulo de confidencialidade.

Nas três camadas discutidas aqui, a gravação está desabilitada em reuniões altamente sensíveis porque estamos usando criptografia de ponta a ponta e marcas d'água em conteúdo compartilhado e vídeo. Se você precisar registrar reuniões altamente confidenciais, certifique-se de não impor marcas d'água ou criptografia de ponta a ponta com o rótulo de confidencialidade. Os organizadores da reunião ainda podem usar criptografia de ponta a ponta e aplicar marcas d'água se uma determinada reunião não estiver sendo registrada.

Para obter mais informações sobre como gerenciar opções de gravação de reunião, consulte [Gerenciar opções de gravação de reunião do Microsoft Teams para reuniões confidenciais](manage-meeting-recording-options.md).

Para obter informações sobre a gravação baseada em política de reuniões para conformidade, consulte [Introdução à gravação baseada em política do Teams para chamadas & reuniões](teams-recording-policy.md).

## <a name="meeting-with-guests-and-external-participants"></a>Reunião com convidados e participantes externos

Há três tipos de participantes externos que podem participar de reuniões:

- Participantes de domínios confiáveis
- Convidados
- Participantes anônimos

Participantes de domínios confiáveis ingressam em reuniões por meio do recurso [de acesso externo](manage-external-access.md) . Você pode controlar quais domínios, se houver, sua organização deseja confiar. (Essa configuração também afeta 1:1 e o chat em grupo com pessoas nesses domínios.)

Se [o acesso de convidado do Teams](guest-access.md) estiver habilitado para sua organização, os convidados poderão participar de reuniões. As configurações de acesso ao convidado também podem ser usadas para controlar o modo de compartilhamento de tela dos convidados, incluindo desabilitar o compartilhamento de tela. (O acesso de convidado também é usado para convidar convidados para equipes.)

Se os **usuários Anônimos puderem ingressar em uma configuração** de administrador do Teams de reunião estiver ativada, os participantes anônimos poderão participar de reuniões.

Embora você possa desativar completamente a junção anônima sem afetar recursos que não sejam reuniões, o acesso de convidados e domínios confiáveis são usados em cenários fora das reuniões. Se você quiser restringir o acesso à reunião a esses participantes, mas precisar deixar os recursos ativados por outros motivos, você deve usar o lobby.

## <a name="lobby-options"></a>Opções de lobby

O lobby da reunião permite que os organizadores da reunião vetem os participantes antes de permitir que eles entrem na reunião. Dependendo do tipo de reunião e seus requisitos de conformidade, você pode querer permitir que todos os participantes ignorem o lobby e participem da reunião diretamente, ou mantenham certos tipos de participantes no lobby até que eles sejam admitidos por um organizador da reunião. Se você quiser impedir que certos tipos de pessoas - como convidados - participem de reuniões, você pode tê-los passando pelo lobby e, em seguida, o organizador da reunião pode negar-lhes a admissão.

Para a camada de linha de base, permitimos que todos, exceto participantes anônimos, ignorem o lobby. Para reuniões confidenciais, permitimos que apenas pessoas com um convite de reunião ignorem o lobby. Para reuniões altamente sensíveis, exigimos que os organizadores admitam cada participante.

Como administrador, você pode controlar o lobby das seguintes maneiras:

- A política **de reunião do administrador de pessoas automaticamente** (por usuário ou grupo)
- Os **usuários do Dial-in podem ignorar a** política de reunião de administrador do lobby (por usuário ou grupo)
- O **Quem pode ignorar a configuração do lobby** em rótulos de confidencialidade e modelos de reunião (por reunião)
- O **Pessoas discagem pode ignorar a** política de reunião de administrador do lobby (por usuário ou grupo) ou em rótulos de confidencialidade e modelos de reunião (por reunião)

Essas configurações também estão disponíveis para o organizador da reunião, a menos que tenham sido bloqueadas por um rótulo ou modelo de confidencialidade.


Enquanto a política de administrador define um padrão, você precisa de um modelo ou rótulo para impor


Se você estiver em um setor altamente regulamentado e precisar admitir manualmente cada participante em todas as reuniões da sua organização, poderá configurar o lobby usando políticas de reunião de administrador no centro de administração do Teams. Se sua organização tiver diferentes tipos de reuniões com requisitos de lobby diferentes, recomendamos usar modelos de reunião ou rótulos de confidencialidade para configurar essas configurações.

Para obter mais informações, consulte [Configurar o lobby de reuniões do Microsoft Teams para reuniões confidenciais](configure-lobby-sensitive-meetings.md)

## <a name="related-topics"></a>Tópicos relacionados

[Ilustrações da nuvem da Microsoft para arquitetos empresariais](/microsoft-365/solutions/cloud-architecture-models)

[Usar rótulos de confidencialidade para proteger itens de calendário, reuniões do Teams e chat](/microsoft-365/compliance/sensitivity-labels-meetings)
