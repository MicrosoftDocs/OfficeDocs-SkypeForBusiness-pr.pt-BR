---
title: Gerenciar o Teams com políticas
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Saiba mais sobre as políticas do Teams.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: acaa1280e00ad2e86a49c2bbd8e7f4464bd0c0e7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268756"
---
# <a name="manage-teams-with-policies"></a>Gerenciar o Teams com políticas

As políticas são uma parte importante do gerenciamento do Teams. Use este artigo para navegar sobre como usar políticas para beneficiar sua organização.

## <a name="what-you-use-policies-for"></a>Para o que você usa políticas

As políticas são usadas para realizar muitas tarefas em sua organização em diferentes áreas, como mensagens, reuniões e aplicativos. Algumas das coisas que você pode fazer incluem permitir que os usuários agendem reuniões em um canal do Teams, permitindo que os usuários editem mensagens enviadas e controlando se os usuários podem fixar aplicativos na barra de aplicativos do Teams.

## <a name="how-to-assign-policies"></a>Como atribuir políticas

As políticas podem ser atribuídas de várias maneiras diferentes, dependendo do que sua organização está tentando realizar. Você pode fazer e exibir atribuições no centro de administração do Teams.

:::image type="content" source="media/group-policy-assignment.png" alt-text="Captura de tela da atribuição de política de grupo do Teams." lightbox="media/group-policy-assignment.png":::

Saiba mais sobre como atribuir políticas [aqui](policy-assignment-overview.md).

> [!NOTE]
> Para cancelar a atribuição de políticas, você pode remover atribuições em massa para todos os usuários atribuídos diretamente a uma política. Para saber mais, leia [Cancelar a atribuição de políticas em massa](assign-policies-users-and-groups.md#unassign-policies-in-bulk).

## <a name="how-to-manage-policies"></a>Como gerenciar políticas

As políticas são gerenciadas com o centro de administração do Microsoft Teams ou [usando o PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Por exemplo, uma política de configuração de aplicativo pode permitir que os usuários carreguem aplicativos personalizados, instalem aplicativos em nome de seus usuários e fixem aplicativos na barra de aplicativos do Teams. Essas políticas são configuradas no centro de administração do Teams.

:::image type="content" source="media/app-setup-policy.png" alt-text="Captura de tela da política de configuração do aplicativo." lightbox="media/app-setup-policy.png":::

Além disso, uma política de reunião pode ser usada para controlar as configurações de áudio e vídeo em reuniões do Teams, como transcrições, gravações de nuvem e áudio/vídeo IP.

:::image type="content" source="media/engineering-meeting-policy.png" alt-text="Captura de tela da política de reunião." lightbox="media/engineering-meeting-policy.png":::

### <a name="teams-for-education"></a>Teams para o ensino

Você também pode usar o [assistente Teams para Educação política](easy-policy-setup-edu.md) para configurar e gerenciar facilmente políticas para seu ambiente de aprendizado.

:::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Captura de tela do Teams para Educação de política." lightbox="media/easy-policy-setup-quick-setup.png":::

## <a name="types-of-policies"></a>Tipos de políticas

As políticas a seguir podem ser gerenciadas com o Microsoft Teams.

Tipo de política | Descrição
------------|------------
[Pacotes de política](manage-policy-packages.md) | Um pacote de políticas no Microsoft Teams é uma coleção de políticas e configurações predefinidas que você pode atribuir a usuários que têm funções semelhantes em sua organização.
[Políticas de reunião](meeting-policies-overview.md) | Uma política de reunião é usada para controlar os recursos que estão disponíveis para os participantes da reunião para reuniões agendadas pelos usuários em sua organização. As políticas de reunião incluem os tópicos a seguir.<br> - Políticas de áudio e vídeo<br> - Políticas de compartilhamento de conteúdo e tela<br> - Participantes, convidados e políticas de acesso<br> – Políticas gerais
[Políticas de voz e chamada](voice-and-calling-policies.md)| As políticas de voz e chamada gerenciam essas configurações por meio de equipes como chamadas de emergência, roteamento de chamadas e ID do chamador.
[Políticas de aplicativo](app-policies.md)| As políticas de aplicativo são usadas para controlar aplicativos no Microsoft Teams. Os administradores podem permitir ou bloquear quais aplicativos os usuários podem instalar, fixar aplicativos na barra de aplicativos do Teams de um usuário e instalar o aplicativo em nome de seus usuários.
[Políticas de mensagens](messaging-policies-in-teams.md)| As políticas de mensagens controlam a disponibilidade de recursos de chat e canal.

## <a name="related-topics"></a>Tópicos relacionados

* [Atribuir políticas no Teams – introdução](policy-assignment-overview.md)
* [Gerenciar políticas de comentários no Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gerenciar políticas de equipes no Microsoft Teams](teams-policies.md)
* [Prepare-se para eventos ao vivo no Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams para Educação políticas e pacotes de políticas](policy-packages-edu.md)