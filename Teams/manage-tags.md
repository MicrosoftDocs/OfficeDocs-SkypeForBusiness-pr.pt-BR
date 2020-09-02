---
title: Gerenciar marcas no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar como as marcas são usadas em sua organização no Microsoft Teams.
ms.openlocfilehash: 9295d03aecb6c0bc6a4f667214869fe698d4eaab
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324006"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gerenciar marcas no Microsoft Teams

> [!NOTE]
> Um dos recursos descritos neste artigo, **marcação por turno**, ainda não foi lançado. Ele foi anunciado e estará disponível em breve.Se você for um administrador, poderá descobrir quando este recurso será lançado no centro de mensagens (no centro de administração do [Microsoft 365](https://portal.office.com/adminportal/home)). Para manter-se atualizado sobre os recursos futuros do Teams, consulte o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Visão geral

As marcas no Microsoft Teams permitem que os usuários se conectem de forma rápida e fácil com um subconjunto de pessoas de uma equipe. Você pode criar e atribuir marcas personalizadas para categorizar as pessoas com base em atributos, como função, projeto, habilidade ou local. Ou, as marcas podem ser atribuídas automaticamente às pessoas com base em suas informações de cronograma e turno no [aplicativo turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (em breve). Depois que uma marca é adicionada a um ou vários membros da equipe, ela pode ser usada no @mentions por qualquer pessoa da equipe em uma postagem de canal ou para iniciar uma conversa apenas com as pessoas que receberam essa marca.

Conforme mencionado anteriormente, há dois tipos de marcas no Teams.

- **Marcas personalizadas**: os proprietários da equipe e os membros da equipe (se o recurso estiver habilitado para eles) podem criar e atribuir marcas manualmente a pessoas. Por exemplo, uma marca "designer" ou "radiologist" vai chegar a esses conjuntos de pessoas em uma equipe sem ter que digitar seus nomes.
- **Marcando por turno (em** breve): com esse recurso, as pessoas recebem automaticamente marcas que correspondem ao cronograma e ao nome do grupo de turno no [aplicativo turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) do teams. Por exemplo, a marca "EngineerOnCall" atinge todos os engenheiros agendados em turnos para trabalhar no momento em que a marca é usada em uma postagem de canal ou chat. Com a marcação por turno, o Microsoft Teams usa a adivinhação de saber o nome do pessoal do usuário no turno quando os usuários precisam retransmitir informações rapidamente. A marcação por turno também pode ser apoiada pelos principais sistemas de gerenciamento de força de equipe, como o JDA, o Kronos e o AMiON, integrando-os com turnos no Teams. Para saber mais sobre como configurar esse recurso, consulte [Configurar marcação por turno](#set-up-tagging-by-shift-coming-soon).

> [!NOTE]
> Marcas ainda não são suportadas em canais privados. As marcas ainda não estão disponíveis nas organizações da Comunidade do governo dos EUA (GCC), GCC alto ou departamento de defesa (DoD).

## <a name="how-tags-work"></a>Como as marcas funcionam

Uma marca pode ser adicionada manualmente ou atribuída automaticamente a uma pessoa em uma equipe específica. Ele pode ser usado em @mentions na linha **para** em um chat ou em uma postagem em qualquer canal padrão da equipe. Veja a seguir alguns exemplos de como as marcas podem ser usadas no Teams:

- Um gerente de loja publica um anúncio em um canal para notificar todos os caixas.
- Um administrador do hospital envia uma mensagem para todos os radiologists de um canal.
- Um gerente de marketing inicia um chat em grupo com todos os designers.
- Um enfermeira envia uma mensagem para todos os CARDIOLOGISTS on-Call. (em breve)
- Um engenheiro de sistema envia um comunicado a um canal para notificar todos os engenheiros de campo no turno. (em breve)

Quando uma marca é @mentioned em uma conversa de canal, os membros da equipe associados à marca serão notificados, assim como qualquer outro @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gerenciar marcas personalizadas para sua organização

Como administrador, você pode controlar como as marcas são usadas em toda a organização no centro de administração do Microsoft Teams.

![Captura de tela das configurações de marcação no centro de administração do Microsoft Teams](media/manage-tags-admin-settings.png)

Uma equipe pode ter até 100 marcas, até 100 os membros da equipe podem ser atribuídos a uma marca e até 25 marcas podem ser atribuídas a um único usuário. 

### <a name="set-who-can-add-custom-tags"></a>Definir quem pode adicionar marcas personalizadas

Por padrão, os proprietários da equipe podem adicionar marcas personalizadas. Você pode alterar essa configuração para permitir que os proprietários da equipe e os membros da equipe criem, editem, excluam e gerenciem marcas ou você pode desativar as marcas da sua organização.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em configurações da equipe de **configurações de toda a organização**  >  **Teams settings**.
2. Em **marcação**, ao lado de **marcas são gerenciados por**, selecione uma das seguintes opções:

    - **Proprietários e membros da equipe**: permitir que os proprietários e membros da equipe gerenciem as etiquetas.
    - **Proprietários da equipe**: permitir que os proprietários de equipe gerenciem as etiquetas.
    - **Disabled**: desativar marcas.

### <a name="configure-custom-tags-settings"></a>Definir configurações de marcas personalizadas

Você pode definir as seguintes configurações de marcas para controlar como as marcas personalizadas são usadas em toda a sua organização.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em configurações da equipe de **configurações de toda a organização**  >  **Teams settings**.
2. Em **marcação**, defina o seguinte, dependendo das necessidades da sua organização.

    - **Permitir que os proprietários de equipe substituam quem pode gerenciar as etiquetas**: quando você ativa essa configuração, os proprietários da equipe podem definir se os membros da equipe podem criar e gerenciar marcas em uma equipe e o valor das **marcas são gerenciados por** configuração é o valor padrão para cada equipe. Se você desativar essa configuração, as **marcas são gerenciadas pela** configuração não podem ser alteradas por equipe.
    - **Marcas padrão sugeridas**: Use isto para adicionar um conjunto de marcas padrão. Você pode adicionar até 25 marcas e cada marca pode conter no máximo 25 caracteres. Os proprietários e membros da equipe (se o recurso estiver habilitado para eles) podem usar essas sugestões, adicionar a eles ou criar um novo conjunto de marcas.
    - **Deixe as marcas personalizadas serem criadas**: Ative essa configuração para permitir que as pessoas adicionem marcas diferentes das marcas padrão sugeridas que você definiu. Se estiver desativado, as pessoas só poderão usar as marcas padrão sugeridas. Se você desativar essa opção, certifique-se de adicionar uma ou mais marcas padrão.

## <a name="manage-custom-tags-settings-for-a-team"></a>Gerenciar configurações de marcas personalizadas para uma equipe

Se você ativou a configuração **deixar que os proprietários da equipe substituam quem pode gerenciar marcas** no centro de administração do Microsoft Teams, os proprietários da equipe podem definir se os membros podem adicionar marcas no nível da equipe. Para fazer isso, na guia **configurações** de uma equipe, vá até **marcas**e escolha quem pode adicionar marcas.

![Captura de tela da configuração marcas no nível da equipe](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usar marcas

Veja como adicionar marcas personalizadas e como configurar a marcação por Shift (se você estiver usando o aplicativo turnos no Teams). Para saber mais, confira [usando marcas no Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Criar e atribuir marcas personalizadas

Para criar e atribuir marcas personalizadas, selecione **equipes** no lado esquerdo do aplicativo e localize sua equipe na lista. Selecione **mais opções**e, em seguida, escolha **gerenciar marcas**. Aqui, você pode criar marcas e atribuí-las às pessoas de sua equipe.

![Captura de tela de como aplicar marcas no cliente do teams ](media/manage-tags-teams.png)

Para excluir uma marca, remova todos os membros da equipe associados à marca.

### <a name="set-up-tagging-by-shift-coming-soon"></a>Configurar marcação por turno (disponível em breve)

1. No Teams, vá para o [aplicativo turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Criar [grupos de turnos](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) e nomeá-los após um atributo, como uma função. Por exemplo, EngineerOnCall. O nome do grupo Shift será o nome da marca.
3. [Preencha um cronograma](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) atribuindo turnos a membros de suas equipes. Quando tiver terminado, no canto superior direito do aplicativo turnos, selecione **compartilhar com a equipe**.
4. Espere 15 minutos para que os turnos programados preencham o serviço de marcação.
5. Use a marca em qualquer lugar em que você usar as marcas no Teams.

A marcação por turno permite que os usuários acessem as pessoas em tempo real. As notificações são enviadas somente para as pessoas que estão no turno no momento em que uma marca é usada para iniciar um chat ou em uma postagem de canal.

## <a name="related-topics"></a>Tópicos relacionados

[Usando marcas no Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gerenciar o aplicativo Shifts para sua organização no Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentação de ajuda de turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
