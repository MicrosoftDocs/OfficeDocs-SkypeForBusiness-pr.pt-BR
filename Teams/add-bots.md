---
title: Adicionar bots para bate-papos privados e canais no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: Saiba como adicionar bots no Microsoft Teams para chats pessoais, chats em grupo e canais e carregar seus próprios bots para chats pessoais, grupos chats e canais.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5f7ef2d548031528aa41b9fdb75831fe46d36d
ms.sourcegitcommit: c13bd343c3f3d14c7b8ff710ac5a4fec17ab88b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "34859685"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>Adicionar bots para chats pessoais, chats em grupo e canais no Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados. Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams. Os bots para equipes são criados na [estrutura Microsoft bot](https://go.microsoft.com/fwlink/?linkid=854370). Os bots desenvolvidos usando essa estrutura podem ser habilitados facilmente para Teams. Para saber mais, confira [Gerenciar configurações do Microsoft Teams para sua organização](enable-features-office-365.md).

Atualmente, o Teams oferece suporte para bots em chats pessoais, chats em grupo e canais dentro de uma equipe. Os administradores podem controlar se o uso de bots é permitido ou proibido dentro do locatário do Office 365.<span id="_T-Bot" class="anchor"></span>

Os bots desenvolvidos pela Comunidade podem ser aproveitados dentro do teams. A funcionalidade do bot e a capacidade de carregar aplicativos personalizados (também conhecidos como Sideload) devem estar habilitadas no nível do locatário para que os bots personalizados sejam funcionais. Os bots podem ser usados em chats pessoais, chats em grupo e canais. Para os canais, proprietários e membros de equipes podem adicionar bots.

Para obter mais informações, consulte [aplicativos e serviços](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).

> [!IMPORTANT]
> Não é recomendável adicionar um bot por GUID para qualquer coisa além de fins de teste. Isso limita severamente a funcionalidade de um bot. Os bots no uso da produção devem ser adicionados ao Teams como parte de um aplicativo. Consulte [criar um bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) e [testar e depurar o Microsoft Teams bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Criar bots personalizados para o Microsoft Teams
--------------------------------------

Você pode facilmente criar um bot que se integre nos seus aplicativos LOB usando o Microsoft Bot Framework. Consulte o guia [criando e testando um bot para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber como você pode desenvolver e publicar seus próprios bots.

Quando você cria um bot e o registra com o Bot Framework, pode optar por publicá-lo. Se você não o publicar, o bot permanecerá privado. Você também pode exigir que seus usuários façam login antes de usar o bot. A exigência de login assegura que apenas os funcionários da sua organização possam acessar o bot, mesmo que o ID do aplicativo do bot se torne conhecido. Veja [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) no GitHub para ver um exemplo de código de como autenticar os usuários no seu diretório ativo usando bots.

Os bots podem ser testados usando o [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) antes que sejam implantados no seu Teams.

<a name="upload-your-bot-for-personal-chat"></a>Carregar o bot para chat pessoal
---------------------------------------

1. Depois de criar o bot, vá para as **configurações do aplicativo** do bot que você desenvolveu e, em **configurações do aplicativo**, copie o valor da configuração **MicrosoftAppId** . ![Captura de tela da página de configurações do aplicativo para um bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  No Teams, no painel de **chat** , selecione o **ícone Adicionar chat**. Em **para**, Cole a ID do **aplicativo Microsoft**do bot. ![Captura de tela de um painel de chat com a ID do aplicativo da Microsoft realçada](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. A ID do aplicativo será resolvida para o **nome do bot** e você poderá iniciar uma conversa de chat com esse bot.

<a name="upload-your-bot-for-group-chats-or-channels"></a>Carregar o bot para chats de grupo ou canais
-----------------------------------

Se você quiser compartilhar seu bot com seus colegas, veja como adicioná-lo a chats de grupo ou canais de diferentes equipes:

1. Depois [de criar um pacote do aplicativo para o seu bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), abra o Teams e navegue até a equipe na qual você carregará o bot.
2. Adicione o app **[Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, App ao Teams.
3. No app Studio, selecione a guia **Editor** de manifesto ![. captura de tela da guia Editor de manifesto.](media/Adding_Bot_To_Teams.png)
4. Para adicionar seu bot, em recursos, selecione o bot e escolha Adicionar um bot existente. Em seguida, escolha um bot existente ou digite a ID de um bot existente.
![Mostra a seleção do bot que você já criou.](media/Select_Existing_Bot.png)
5. Navegue até o local do pacote do aplicativo, selecione-o e clique em **abrir**.
6. Selecione o nome do seu bot. (Não se esqueça de selecionar a caixa de seleção **chat em grupo** ou **equipe** na seção escopo).
7. Selecione **testar e distribuir**.
8. Selecione o chat do grupo ou a equipe à qual você deseja conectar o bot.

    Seu bot estará disponível em seu chat em grupo ou equipe no Microsoft Teams.
