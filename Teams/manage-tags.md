---
title: Gerenciar marcas em Microsoft Teams
author: cichur
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar como as marcas são usadas em sua organização em Microsoft Teams.
ms.openlocfilehash: 8c623c4240466c7f7a6d11194e03e9717e302089
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771740"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gerenciar marcas em Microsoft Teams

## <a name="overview"></a>Visão geral

As marcas Microsoft Teams permitem que os usuários se conectem rapidamente e facilmente com um subconjunto de pessoas em uma equipe. Você pode criar e atribuir marcas personalizadas para categorizar pessoas com base em atributos, como função, projeto, habilidade ou local. Ou, as marcas podem ser atribuídas automaticamente às pessoas com base em suas informações de agendamento e turno no aplicativo [Shifts.](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) Depois que uma marca é adicionada a um ou vários membros da equipe, ela pode ser usada no @mentions por qualquer pessoa na equipe em uma postagem de canal ou para iniciar uma conversa somente com as pessoas que são atribuídas a essa marca.

Como mencionado anteriormente, há dois tipos de marcas Teams.

- **Marcas personalizadas**: Proprietários de equipe e membros da equipe (se o recurso estiver habilitado para eles) podem criar e atribuir marcas manualmente às pessoas. Por exemplo, uma marca "Designer" ou "Radiologist" alcançará esses conjuntos de pessoas em uma equipe sem precisar digitar seus nomes.
- **Marcação por turno**: com esse recurso, as pessoas são atribuídas automaticamente marcas que corresponderem ao nome do grupo de turnos e agendamento no aplicativo [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) no Teams. Por exemplo, a marca "EngineerOnCall" atinge todos os engenheiros agendados em Shifts para trabalhar no momento em que a marca é usada em uma postagem de chat ou canal. Com a marcação por turno, Teams faz a suposição de saber o nome da equipe de turno quando os usuários precisam retransmitir rapidamente as informações. A marcação por turno também pode ser respaldada pelos principais sistemas de gerenciamento de força de trabalho, como JDA, Kronos e AMiON, integrando-os com Shifts em Teams. Para saber mais sobre como configurar esse recurso, consulte [Configurar marcação por turno](#set-up-tagging-by-shift).

> [!NOTE]
> As marcas ainda não são suportadas em canais privados. As marcas não estão disponíveis em organizações do Departamento de Defesa (DoD). 

## <a name="how-tags-work"></a>Como as marcas funcionam

Uma marca pode ser adicionada manualmente ou atribuída automaticamente a uma pessoa em uma equipe específica. Em seguida, ele pode ser usado @mentions na linha **Para** em um chat ou em uma postagem em qualquer canal padrão da equipe. Veja alguns exemplos de como as marcas podem ser usadas em Teams:

- Um gerente de loja posta um comunicado em um canal para notificar todos os caixas.
- Um administrador de hospital envia uma mensagem para todos os radiologistas em um canal.
- Um gerente de marketing inicia um chat em grupo com todos os designers.
- Uma ama envia uma mensagem para todos os cardiologistas de chamada. (em breve)
- Um engenheiro de sistema posta um comunicado em um canal para notificar todos os engenheiros de campo no turno. (em breve)

Quando uma marca é @mentioned em uma conversa de canal, os membros da equipe associados à marca serão notificados, assim como qualquer outra @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gerenciar marcas personalizadas para sua organização

Como administrador, você pode controlar como as marcas são usadas em sua organização no Microsoft Teams de administração. Atualmente, você não pode usar o PowerShell para gerenciar marcas.

![Captura de tela das configurações de marcação no Microsoft Teams de administração.](media/manage-tags-admin-settings.png)

Uma equipe pode ter até 100 marcas, até 100 membros da equipe podem ser atribuídos a uma marca e até 25 marcas podem ser atribuídas a um único usuário. 

### <a name="set-who-can-add-custom-tags"></a>Definir quem pode adicionar marcas personalizadas

Por padrão, os proprietários de equipe podem adicionar marcas personalizadas. Você pode alterar essa configuração para permitir que os proprietários da equipe e os membros da equipe criem, editem, excluam e gerenciem marcas ou podem desativar as marcas da sua organização.

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Configurações** em toda a  >  **organização Teams configurações**.
2. Em **Marcação**, ao lado de **Marcas são gerenciados por**, selecione uma das seguintes opções:

    - **Proprietários e membros da equipe**: Permitir que proprietários e membros da equipe gerenciem marcas.
    - **Proprietários de** equipe : Permitir que os proprietários da equipe gerenciem marcas.
    - **Desabilitado:** desative as marcas.

### <a name="configure-custom-tags-settings"></a>Configurar configurações de marcas personalizadas

Você pode definir as seguintes configurações de marcas para controlar como as marcas personalizadas são usadas em toda a sua organização.

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Configurações** em toda a  >  **organização Teams configurações**.
2. Em **Marcação**, de definir o seguinte, dependendo das necessidades da sua organização.

    - Permitir **que** os proprietários de equipe substituam quem pode gerenciar marcas : Quando você ativar essa configuração, os proprietários da equipe podem definir se os membros da equipe podem criar e gerenciar marcas em uma equipe e o valor das **Marcas** são gerenciados por definição é o valor padrão para cada equipe. Se você desativar essa configuração, as **Marcas serão gerenciadas por** configuração não poderão ser alteradas por equipe.
    - **Marcas padrão sugeridas**: Use isso para adicionar um conjunto de marcas padrão. Você pode adicionar até 25 marcas e cada marca pode conter no máximo 25 caracteres. Os proprietários e membros da equipe (se o recurso estiver habilitado para eles) podem usar essas sugestões, adicioná-las ou criar um novo conjunto de marcas.
    - **Permitir que marcas personalizadas sejam criadas**: acione essa configuração para permitir que as pessoas adicionem marcas que não sejam as marcas padrão sugeridas que você definiu. Se isso estiver desligado, as pessoas só poderão usar as marcas padrão sugeridas. Se você desativar isso, certifique-se de adicionar uma ou mais marcas padrão.

## <a name="manage-custom-tags-settings-for-a-team"></a>Gerenciar configurações de marcas personalizadas para uma equipe

Se você acionou a configuração Permitir que os proprietários de equipe substituam quem pode gerenciar marcas no centro de administração Microsoft Teams, os proprietários da equipe poderão definir se os membros podem adicionar marcas no nível da equipe.  Para fazer isso, **na** guia Configurações uma equipe, vá para **Marcas** e escolha quem pode adicionar marcas.

![Captura de tela da configuração de marcas no nível da equipe.](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usar marcas

Veja como adicionar marcas personalizadas e como configurar a marcação por turno (se você estiver usando o aplicativo Shifts no Teams). Para saber mais, confira [Usando marcas em Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Criar e atribuir marcas personalizadas

Para criar e atribuir marcas personalizadas, selecione **Teams** no lado esquerdo do aplicativo e encontre sua equipe na lista. Selecione **̇ ̇ ̇ Mais opções** e, em seguida, escolha Gerenciar **marcas**. Aqui, você pode criar marcas e atribuí-las a pessoas em sua equipe.

![Captura de tela de como aplicar marcas no cliente Teams .](media/manage-tags-teams.png)

Para excluir uma marca, selecione **̇ ̇ ̇ mais opções** ao lado da marca e selecione Excluir **marca**.

### <a name="set-up-tagging-by-shift"></a>Configurar a marcação por turno

A marcação por turno permite que os usuários alcancem as pessoas no turno em tempo real. Teams atribui automaticamente aos usuários marcas correspondentes ao nome do grupo de turnos e agendamento do aplicativo Shifts, habilitando mensagens dinâmicas baseadas em função. As notificações são enviadas somente para as pessoas que estão de turno no momento em que uma marca é usada para iniciar um chat ou em uma postagem de canal. 

1. Em Teams, vá para o aplicativo [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Crie [grupos de turnos](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) e nomee-os após um atributo, como uma função. Por exemplo, EngineerOnCall. O nome do grupo de turnos será o nome da marca.
3. [Preencha um cronograma atribuindo](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) turnos aos membros de suas equipes. Quando terminar, no canto superior direito do aplicativo Shifts, selecione **Compartilhar com a equipe**.
4. Aguarde 15 minutos para que os turnos agendados preencham o serviço de marcação.
5. Use a marca em qualquer lugar que você use marcas Teams.

## <a name="related-topics"></a>Tópicos relacionados

[Usando marcas em Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gerenciar o aplicativo Shifts para sua organização no Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentação da Ajuda de Turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
