---
title: Gerenciar Teams com políticas
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Incline-se Teams políticas.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a08e48a37b90a7d8a99053d01a844c3451314e00
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605587"
---
# <a name="manage-teams-with-policies"></a>Gerenciar Teams com políticas

As políticas são uma parte importante do gerenciamento Teams. Use este artigo para navegar sobre como usar políticas para beneficiar sua organização.

## <a name="what-you-use-policies-for"></a>Para o que você usa políticas

As políticas são usadas para realizar muitas tarefas em sua organização em diferentes áreas, como mensagens, reuniões e aplicativos. Algumas das coisas que você pode fazer incluem permitir que os usuários agendem reuniões em um canal de equipe, permitindo que os usuários editem mensagens enviadas e controlando se os usuários podem fixar aplicativos na barra Teams aplicativos.

## <a name="how-to-assign-policies"></a>Como atribuir políticas

As políticas podem ser atribuídas de várias maneiras diferentes, dependendo do que sua organização está tentando realizar. Você pode fazer e exibir atribuições no Teams de administração.

![Captura de tela da atribuição de política de grupo.](media/group-policy-assignment.png)

Saiba mais sobre como atribuir políticas [aqui](policy-assignment-overview.md).

## <a name="how-to-manage-policies"></a>Como gerenciar políticas

As políticas são gerenciadas com o centro de administração Microsoft Teams ou [usando o PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).

Por exemplo, uma política de configuração de aplicativo pode permitir que os usuários carreguem aplicativos personalizados, instalem aplicativos em nome de seus usuários e fixem aplicativos na barra Teams aplicativos. Essas políticas são configuradas no Teams de administração.

![Captura de tela da política de configuração do aplicativo.](media/app-setup-policy.png)

Além disso, uma política de reunião pode ser usada para controlar configurações de áudio e vídeo em reuniões Teams como transcrições, gravações de nuvem e áudio/vídeo IP.

![Captura de tela da política de reunião.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams para o ensino

Você também pode usar o assistente [de Teams para Educação de](easy-policy-setup-edu.md) política para configurar e gerenciar facilmente políticas para seu ambiente de aprendizagem.

![Captura de tela do Teams para Educação de política.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>Tipos de políticas

As políticas a seguir podem ser gerenciadas com Microsoft Teams.

Tipo de política | Descrição
------------|------------
[Pacotes de política](manage-policy-packages.md) | Um pacote de política no Microsoft Teams é uma coleção de políticas e configurações predefinidas que você pode atribuir aos usuários que têm funções semelhantes em sua organização.
[Políticas de reunião](meeting-policies-overview.md) | Uma política de reunião é usada para controlar os recursos que estão disponíveis para os participantes da reunião para reuniões agendadas pelos usuários em sua organização. As políticas de reunião incluem os tópicos a seguir.<br> - Políticas de áudio e vídeo<br> - Políticas de compartilhamento de conteúdo e tela<br> - Participantes, convidados e políticas de acesso<br> - Políticas gerais
[Políticas de voz e chamada](voice-and-calling-policies.md)| As políticas de voz e chamada gerenciam essas configurações por meio de equipes como chamadas de emergência, roteamento de chamadas e ID do chamador.
[Políticas de aplicativo](app-policies.md)| As políticas de aplicativos são usadas para controlar aplicativos Microsoft Teams. Os administradores podem permitir ou bloquear quais aplicativos os usuários podem instalar, fixar aplicativos na barra Teams de aplicativos do usuário e instalar o aplicativo em nome de seus usuários.
[Políticas de mensagens](messaging-policies-in-teams.md)| As políticas de mensagens controlam a disponibilidade de recursos de chat e canal.

## <a name="related-topics"></a>Tópicos relacionados

* [Atribuir políticas em Teams - iniciando](policy-assignment-overview.md)
* [Gerenciar políticas de comentários em Microsoft Teams](manage-feedback-policies-in-teams.md)
* [Gerenciar políticas de equipes em Microsoft Teams](teams-policies.md)
* [Prepare-se para eventos ao vivo no Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md)
* [Teams para Educação políticas e pacotes de política](policy-packages-edu.md)