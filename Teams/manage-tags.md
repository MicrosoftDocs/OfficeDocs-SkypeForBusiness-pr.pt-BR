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
description: Saiba como gerenciar como as marcas são usadas em sua organização no Microsoft Teams.
ms.openlocfilehash: bdb4fcbdd4c4d197dcdc778b9c15130071ad37fc
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267946"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gerenciar marcas no Microsoft Teams

## <a name="overview"></a>Visão geral

As marcas no Microsoft Teams permitem que os usuários se conectem com rapidez e facilidade com um subconjunto de pessoas em uma equipe. Você pode criar e atribuir marcas personalizadas para categorizar pessoas com base em atributos, como função, projeto, habilidade ou local. Ou, as marcas podem ser atribuídas automaticamente às pessoas com base em suas informações de agendamento e deslocamento no aplicativo [Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts). Depois que uma marca é adicionada a um ou vários membros da equipe, ela pode ser usada no @mentions por qualquer pessoa na equipe em uma postagem de canal ou para notificar somente as pessoas que recebem essa marca de uma conversa

Conforme mencionado anteriormente, há dois tipos de marcas no Teams.

- **Marcas personalizadas**: os proprietários da equipe e os membros da equipe (se o recurso estiver habilitado para eles) podem criar e atribuir marcas manualmente às pessoas. Por exemplo, uma marca "Designer" ou "Radiologista" alcançará esses conjuntos de pessoas em uma equipe sem precisar digitar seus nomes.
- **Marcação por turno**: com esse recurso, as pessoas recebem automaticamente marcas que correspondem ao nome do grupo de turnos e agendamento no aplicativo [Turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) no Teams. Por exemplo, a marca "EngineerOnCall" atinge todos os engenheiros agendados no Turnos para trabalhar no momento em que a marca é usada em uma postagem de chat ou canal. Com a marcação por turno, o Teams tira a suposição de saber o nome da equipe no turno quando os usuários precisam retransmitir informações rapidamente.

> [!NOTE]
> Não há suporte para marcas em canais privados ou compartilhados.

## <a name="how-tags-work"></a>Como as marcas funcionam

Uma marca pode ser adicionada manualmente ou atribuída automaticamente a uma pessoa em uma equipe específica. Em seguida, ele pode ser usado @mentions na linha Para em  um chat ou em uma postagem em qualquer canal padrão da equipe. Aqui estão alguns exemplos de como as marcas podem ser usadas no Teams:

- Um gerente de loja posta um comunicado em um canal para notificar todos os caixas.
- Um administrador do hospital envia uma mensagem para todos os radiologistas em um canal.
- Um gerente de marketing inicia um chat em grupo com todos os designers.

Quando uma marca é @mentioned em uma conversa de canal, os membros da equipe associados à marca serão notificados, assim como qualquer outro @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gerenciar marcas personalizadas para sua organização

Como administrador, você pode controlar como as marcas são usadas em sua organização no centro de administração do Microsoft Teams. Observe que você não pode usar o PowerShell para gerenciar marcas.

:::image type="content" source="media/manage-tags-admin-settings.png" alt-text="Captura de tela das configurações de marcação no centro de administração do Microsoft Teams.":::

Uma equipe pode ter até 100 marcas, até 100 membros da equipe podem ser atribuídos a uma marca e até 25 marcas podem ser atribuídas a um único usuário.

### <a name="set-who-can-add-custom-tags"></a>Definir quem pode adicionar marcas personalizadas

Por padrão, os proprietários da equipe podem adicionar marcas personalizadas. Você pode alterar essa configuração para permitir que os proprietários da equipe e os membros da equipe criem, editem, excluam e gerenciem marcas, ou você pode desativar marcas para sua organização.

1. No painel de navegação esquerdo do centro de administração do Microsoft Teams, clique nas **configurações** **do** Teams\>.

2. Em **Marcação**, ao lado **de Marcas são gerenciadas**, selecione uma das seguintes opções:

    - **Proprietários e membros da equipe**: permitir que proprietários e membros da equipe gerenciem marcas.
    - **Proprietários da equipe**: permitir que os proprietários da equipe gerenciem marcas.
    - **Desabilitado**: desative as marcas.

### <a name="configure-custom-tags-settings"></a>Definir configurações de marcas personalizadas

Você pode definir as seguintes configurações de marcas para controlar como as marcas personalizadas são usadas em toda a organização.

1. No painel de navegação esquerdo do centro de administração do Microsoft Teams, clique nas **configurações** **do** Teams\>.

2. Em **Marcação**, defina o seguinte, dependendo das necessidades da sua organização.

    - Permitir que os proprietários da equipe substituam quem pode gerenciar **marcas: quando** você ativa essa configuração, os proprietários da equipe podem definir se os membros da equipe podem criar e  gerenciar marcas dentro de uma equipe e o valor das Marcas é gerenciado pela configuração como o valor padrão para cada equipe. Se você desativar essa configuração, as **Marcas serão gerenciadas pela** configuração não poderão ser alteradas por equipe.
    - **Marcas padrão sugeridas**: use isso para adicionar um conjunto de marcas padrão. Você pode adicionar até 25 marcas e cada marca pode conter um máximo de 25 caracteres. Os proprietários e membros da equipe (se o recurso estiver habilitado para eles) podem usar essas sugestões, adicioná-los ou criar um novo conjunto de marcas.
    - **Permitir que marcas personalizadas sejam criadas**: ative essa configuração para permitir que as pessoas adicionem marcas diferentes das marcas padrão sugeridas que você definiu. Se isso estiver desativado, as pessoas só poderão usar as marcas padrão sugeridas. Se você desativar isso, certifique-se de adicionar uma ou mais marcas padrão.

## <a name="related-topics"></a>Tópicos relacionados

[Usando marcas no Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gerenciar o aplicativo Shifts para sua organização no Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentação da Ajuda do Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
