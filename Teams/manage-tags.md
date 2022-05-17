---
title: Gerenciar marcas no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 0fa615f2bbcdd7965777925b2413717779ad4a7a
ms.sourcegitcommit: 54cb804e6e8338f2d09499e53416e6d55ef1cc40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2022
ms.locfileid: "65442007"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gerenciar marcas no Microsoft Teams

## <a name="overview"></a>Visão Geral

As marcas Microsoft Teams permitem que os usuários se conectem com rapidez e facilidade com um subconjunto de pessoas em uma equipe. Você pode criar e atribuir marcas personalizadas para categorizar pessoas com base em atributos, como função, projeto, habilidade ou local. Ou, as marcas podem ser atribuídas automaticamente às pessoas com base em suas informações de agendamento e deslocamento no aplicativo [Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts). Depois que uma marca é adicionada a um ou vários membros da equipe, ela pode ser usada no @mentions por qualquer pessoa na equipe em uma postagem de canal ou para iniciar uma conversa somente com as pessoas que recebem essa marca.

Conforme mencionado anteriormente, há dois tipos de marcas no Teams.

- **Marcas personalizadas**: os proprietários da equipe e os membros da equipe (se o recurso estiver habilitado para eles) podem criar e atribuir marcas manualmente às pessoas. Por exemplo, uma marca "Designer" ou "Radiologista" alcançará esses conjuntos de pessoas em uma equipe sem precisar digitar seus nomes.
- **Marcação por turno**: com esse recurso, as pessoas recebem automaticamente marcas que correspondem ao nome do grupo de turnos e agendamento no aplicativo [Turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) Teams. Por exemplo, a marca "EngineerOnCall" atinge todos os engenheiros agendados no Turnos para trabalhar no momento em que a marca é usada em uma postagem de chat ou canal. Com a marcação por turno, Teams o trabalho de adivinhação de saber o nome da equipe no turno quando os usuários precisam retransmitir rapidamente as informações. A marcação por turno também pode ser apoiada pelos principais sistemas de gerenciamento de força de trabalho, como JDA, Kronos e AMiON, integrando-os com Shifts no Teams. Para saber mais sobre como configurar esse recurso, consulte [Configurar a marcação por turno](#set-up-tagging-by-shift).

> [!NOTE]
> Não há suporte para marcas em canais privados ou compartilhados.  

## <a name="how-tags-work"></a>Como as marcas funcionam

Uma marca pode ser adicionada manualmente ou atribuída automaticamente a uma pessoa em uma equipe específica. Em seguida, ele pode ser usado @mentions na linha Para em  um chat ou em uma postagem em qualquer canal padrão da equipe. Aqui estão alguns exemplos de como as marcas podem ser usadas Teams:

- Um gerente de loja posta um comunicado em um canal para notificar todos os caixas.
- Um administrador do hospital envia uma mensagem para todos os radiologistas em um canal.
- Um gerente de marketing inicia um chat em grupo com todos os designers.
- Uma enfermeira envia uma mensagem para todos os telemetria de chamada. (em breve)
- Um engenheiro de sistema posta um comunicado em um canal para notificar todos os engenheiros de campo no turno. (em breve)

Quando uma marca é @mentioned em uma conversa de canal, os membros da equipe associados à marca serão notificados, assim como qualquer outro @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gerenciar marcas personalizadas para sua organização

Como administrador, você pode controlar como as marcas são usadas em sua organização no Microsoft Teams de administração. No momento, você não pode usar o PowerShell para gerenciar marcas.

![Captura de tela das configurações de marcação no Microsoft Teams de administração.](media/manage-tags-admin-settings.png)

Uma equipe pode ter até 100 marcas, até 200 membros da equipe podem ser atribuídos a uma marca e até 25 marcas na mesma equipe podem ser atribuídas a um único usuário. 

### <a name="set-who-can-add-custom-tags"></a>Definir quem pode adicionar marcas personalizadas

Por padrão, os proprietários da equipe podem adicionar marcas personalizadas. Você pode alterar essa configuração para permitir que os proprietários da equipe e os membros da equipe criem, editem, excluam e gerenciem marcas ou você pode desativar marcas para sua organização.

1. No painel de navegação à esquerda do Microsoft Teams de administração, clique **Teams** >  **Teams configurações**.
2. Em **Marcação**, ao lado **de Marcas são gerenciadas**, selecione uma das seguintes opções:

    - **Proprietários e membros da equipe**: permitir que proprietários e membros da equipe gerenciem marcas.
    - **Proprietários da equipe**: permitir que os proprietários da equipe gerenciem marcas.
    - **Desabilitado**: desative as marcas.

### <a name="configure-custom-tags-settings"></a>Definir configurações de marcas personalizadas

Você pode definir as seguintes configurações de marcas para controlar como as marcas personalizadas são usadas em toda a organização.

1. No painel de navegação à esquerda do Microsoft Teams de administração, clique **Teams** >  **Teams configurações**.
2. Em **Marcação**, defina o seguinte, dependendo das necessidades da sua organização.

    - Permitir que os proprietários da equipe substituam quem pode gerenciar **marcas: quando** você ativa essa configuração, os proprietários da equipe podem definir se os membros da equipe podem criar e  gerenciar marcas dentro de uma equipe e o valor das Marcas é gerenciado pela configuração como o valor padrão para cada equipe. Se você desativar essa configuração, as **Marcas serão gerenciadas pela** configuração não poderão ser alteradas por equipe.
    - **Marcas padrão sugeridas**: use isso para adicionar um conjunto de marcas padrão. Você pode adicionar até 25 marcas e cada marca pode conter um máximo de 25 caracteres. Os proprietários e membros da equipe (se o recurso estiver habilitado para eles) podem usar essas sugestões, adicioná-los ou criar um novo conjunto de marcas.
    - **Permitir que marcas personalizadas sejam criadas**: ative essa configuração para permitir que as pessoas adicionem marcas diferentes das marcas padrão sugeridas que você definiu. Se isso estiver desativado, as pessoas só poderão usar as marcas padrão sugeridas. Se você desativar isso, certifique-se de adicionar uma ou mais marcas padrão.

## <a name="manage-custom-tags-settings-for-a-team"></a>Gerenciar configurações de marcas personalizadas para uma equipe

Se você ativou a  opção Permitir que os proprietários da equipe substituam quem pode gerenciar a configuração de marcas no centro de administração do Microsoft Teams, os proprietários da equipe poderão definir se os membros podem adicionar marcas no nível da equipe. Para fazer isso, na guia **Configurações** para uma equipe, vá para **Marcas** e escolha quem pode adicionar marcas.

![Captura de tela da configuração de marcas no nível da equipe.](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usar marcas

Veja como adicionar marcas personalizadas e como configurar a marcação por turno (se você estiver usando o aplicativo Shifts no Teams). Para saber mais, confira [Usando marcas no Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Criar e atribuir marcas personalizadas

Para criar e atribuir marcas personalizadas, **selecione Teams** no lado esquerdo do aplicativo e, em seguida, localize sua equipe na lista. Selecione **mais 1 opções e**, em seguida, escolha **Gerenciar marcas**. Aqui, você pode criar marcas e atribuí-las às pessoas da sua equipe.

![Captura de tela de como aplicar marcas no Teams cliente.](media/manage-tags-teams.png)

Para excluir uma marca, selecione **1 Mais opções** ao lado da marca e, em seguida, **selecione Excluir marca**.

### <a name="set-up-tagging-by-shift"></a>Configurar a marcação por turno

A marcação por turno permite que os usuários alcancem as pessoas no turno em tempo real. Teams atribui automaticamente aos usuários marcas correspondentes ao nome do grupo de turnos e agendamento do aplicativo Shifts, permitindo mensagens dinâmicas baseadas em função. As notificações são enviadas somente para as pessoas que estão de turno no momento em que uma marca é usada para iniciar um chat ou em uma postagem de canal. 

1. No Teams, vá para o [aplicativo Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Crie [grupos de turnos](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) e nomeie-os após um atributo, como uma função. Por exemplo, EngineerOnCall. O nome do grupo de turnos será o nome da marca.
3. [Preencha um agendamento](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) atribuindo turnos aos membros de suas equipes. Quando terminar, no canto superior direito do aplicativo Shifts, selecione **Compartilhar com a equipe**.
4. Aguarde 15 minutos para que os turnos agendados preencham o serviço de marcação.
5. Use a marca em qualquer lugar em que você usa marcas Teams.

## <a name="related-topics"></a>Tópicos relacionados

[Usando marcas no Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gerenciar o aplicativo Shifts para sua organização no Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentação da Ajuda do Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
