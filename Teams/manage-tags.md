---
title: Gerenciar marcas no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Aprenda a gerenciar como as marcas são usadas em sua organização no Microsoft Teams.
ms.openlocfilehash: 56a2daf53c362accec8059b11fba400547a7b6ff
ms.sourcegitcommit: b535a70df5bc842f597889582df3eb86371f8139
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2022
ms.locfileid: "68869556"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gerenciar marcas no Microsoft Teams

As marcas no Microsoft Teams permitem que os usuários se conectem rapidamente e facilmente com um subconjunto de pessoas em uma equipe. Você pode criar e atribuir marcas personalizadas para categorizar pessoas com base em atributos, como função, projeto, habilidade ou local. Ou, as marcas podem ser atribuídas automaticamente às pessoas com base em suas informações de agendamento e turno no [aplicativo Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6). Depois que uma marca é adicionada a um ou vários membros da equipe, ela pode ser usada em @mentions por qualquer pessoa na equipe em uma postagem de canal para notificar apenas as pessoas que recebem essa marca de uma conversa.

Se você é proprietário de uma equipe e deseja gerenciar marcas em sua equipe, confira [Usando marcas no Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

Como mencionado anteriormente, há dois tipos de marcas no Teams.

- **Marcas personalizadas: proprietários** de equipe e membros da equipe (se tiverem as permissões) podem criar e atribuir marcas manualmente às pessoas. Por exemplo, uma marca "Designer" ou "Radiologista" alcançará esses conjuntos de pessoas em uma equipe sem precisar digitar seus nomes.
- **Marcação por turno**: com esse recurso, as pessoas recebem automaticamente marcas que correspondem à agenda e ao nome do grupo de [turnos no aplicativo Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_usetags) no Teams. Por exemplo, a marca "EngineerOnCall" atinge todos os engenheiros agendados em Turnos para trabalhar no momento em que a marca é usada em um chat ou postagem de canal. Com a marcação por turno, o Teams tira a adivinhação de saber o nome da equipe de turno quando os usuários precisam retransmitir informações rapidamente.

> [!NOTE]
> Não há suporte para marcas em canais privados ou compartilhados.

## <a name="how-tags-work"></a>Como as marcas funcionam

Uma marca pode ser adicionada manualmente (marca personalizada) ou atribuída automaticamente a uma pessoa em uma equipe específica (configurando Shifts no aplicativo Shifts). Em seguida, a marca pode ser usada em @mentions na linha **To** em um chat ou em uma postagem em qualquer canal padrão da equipe. Aqui estão alguns exemplos de como as marcas podem ser usadas no Teams:

- Um gerente da loja publica um comunicado em um canal para notificar todos os caixas.
- Um administrador do hospital envia uma mensagem a todos os radiologistas em um canal.
- Um gerente de marketing inicia um chat em grupo com todos os designers.
- Uma enfermeira envia uma mensagem a todos os cardiologistas de plantão.
- Um engenheiro do sistema posta um anúncio em um canal para notificar todos os engenheiros de campo em turno.

Quando uma marca é @mentioned em uma conversa de canal, os membros da equipe associados à marca serão notificados, assim como qualquer outro @mention.

## <a name="manage-tags-for-your-organization"></a>Gerenciar marcas para sua organização

Como administrador, você pode controlar como as marcas são usadas em toda a sua organização no centro de administração do Microsoft Teams. Observe que você não pode usar o PowerShell para gerenciar marcas.

:::image type="content" source="media/manage-tags-admin-settings-shifts.png" alt-text="Captura de tela das configurações de marcação no centro de administração do Microsoft Teams.":::

Uma equipe pode ter até 100 marcas, até 200 membros da equipe podem ser atribuídos a uma marca e até 25 marcas na mesma equipe serão atribuídas a um único usuário.

### <a name="set-who-can-manage-tags"></a>Definir quem pode gerenciar marcas

Por padrão, os proprietários da equipe podem criar, editar e excluir marcas. Você pode alterar a configuração **Quem pode gerenciar marcas** para permitir que proprietários de equipe e membros da equipe gerenciem marcas ou desative marcas para sua organização.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Configurações do** **Teams** \> Teams.

2. Em **Marcação**, ao lado de **Quem pode gerenciar marcas**, selecione uma das seguintes opções:

    - **Proprietários e membros da equipe**: permitir que proprietários e membros da equipe gerenciem marcas.
    - **Proprietários de equipe**: permitir que os proprietários de equipe gerenciem marcas.
    - **Não habilitado**: Desative marcas.

### <a name="configure-tagging-settings"></a>Configurar configurações de marcação

Você pode configurar as seguintes configurações de marcas para controlar como as marcas são usadas em toda a sua organização.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Configurações do** **Teams** \> Teams.

2. Em **Marcação**, defina o seguinte, dependendo das necessidades da sua organização.

    - **Os proprietários da equipe podem alterar quem pode gerenciar marcas**: quando você ativa essa configuração, os proprietários da equipe podem definir se os membros da equipe podem criar e gerenciar marcas dentro de uma equipe e o valor da configuração **Quem pode gerenciar marcas** é o valor padrão para cada equipe. Se você desativar essa configuração, a configuração **Quem pode gerenciar marcas** não poderá ser alterada por equipe.
    - **Marcas sugeridas**: use isso para adicionar um conjunto de marcas padrão. Você pode adicionar até 25 marcas e cada marca pode conter um máximo de 25 caracteres. Os proprietários e membros da equipe (se o recurso estiver habilitado para eles) poderão usar essas sugestões, adicionar a elas ou criar um novo conjunto de marcas.
    - **Marcas personalizadas**: ative essa configuração para permitir que as pessoas adicionem marcas diferentes das marcas padrão sugeridas que você definiu. Se isso estiver desativado, as pessoas só poderão usar as marcas padrão sugeridas. Se você desativar isso, certifique-se de adicionar uma ou mais marcas padrão.
    - **O aplicativo Shifts pode aplicar marcas**: ative essa configuração para permitir que o aplicativo Shifts atribua automaticamente marcas a pessoas que estão em turno em tempo real. Essas marcas corresponderão à agenda e ao nome do grupo de um usuário em Shifts. As notificações são enviadas somente para aquelas pessoas que estão em turno no momento em que a marca é usada em um chat ou postagem de canal.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o aplicativo Shifts](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentação de ajuda de turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
