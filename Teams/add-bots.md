---
title: Adicionar bots para canais e chats privados no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: Aprenda a adicionar bots no Microsoft Teams para chats pessoais, chats em grupo e canais, além de carregar seus próprios bots para esses mesmos tipos de chats e canais.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f5f031b01837980897f2c1f8ad5d306e056257b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239053"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>Adicione bots para chats pessoais, chats em grupo e canais no Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados. Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams. Os bots do Teams são baseados no [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). Os bots desenvolvidos usando essa estrutura podem ser facilmente habilitados para o Teams. Para saber mais, confira [Gerenciar configurações do Microsoft Teams para sua organização](enable-features-office-365.md).

Atualmente, o Teams tem suporte para bots em chats pessoais, chats em grupo e canais dentro de uma equipe. Os administradores podem controlar se o uso de bots é permitido ou proibido dentro do locatário do Office 365.<span id="_T-Bot" class="anchor"></span>

Os bots desenvolvidos pela comunidade podem ser utilizados no Teams. A funcionalidade de bot e a capacidade de carregar aplicativos personalizados (também conhecidos como sideload) devem estar habilitados no nível do locatário para que os bots personalizados sejam funcionais. Os bots podem ser usados para chats pessoais, chats em grupo e canais. Para os canais, proprietários e membros de equipes podem adicionar bots.

Para obter mais informações, consulte [Aplicativos e serviços](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).

> [!IMPORTANT]
> Não é recomendável adicionar um bot por GUID para outros fins que não o de teste. Isso limita seriamente a funcionalidade de um bot. Os bots no uso de produção devem ser adicionados ao Teams como parte de um aplicativo. Confira [Criar um bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) e [Testar e depurar seu bot do Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Criar bots personalizados para o Microsoft Teams
--------------------------------------

Você pode facilmente criar um bot que se integre nos seus aplicativos LOB usando o Microsoft Bot Framework. Confira [Criar e testar um bot para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber como você pode desenvolver e publicar seus próprios bots.

Quando você cria um bot e o registra com o Bot Framework, pode optar por publicá-lo. Se você não o publicar, o bot permanecerá privado. Você também pode exigir que seus usuários façam login antes de usar o bot. A exigência de login assegura que apenas os funcionários da sua organização possam acessar o bot, mesmo que o ID do aplicativo do bot se torne conhecido. Veja [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) no GitHub para ver um exemplo de código de como autenticar os usuários no seu diretório ativo usando bots.

Os bots podem ser testados usando o [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) antes que sejam implantados no seu Teams.

<a name="upload-your-bot-for-personal-chat"></a>Carregar seu bot no chat pessoal
---------------------------------------

1. Depois de criar seu bot, acesse **Configurações de aplicativo** do bot que você desenvolveu e, em seguida, abaixo de **Configurações de aplicativo**, copie o valor da configuração **MicrosoftAppId**.![Captura de tela da página de Configurações de aplicativo de um bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  No Teams, no painel de **Chat**, selecione o **ícone Adicionar chat**. Em **Para**, cole a **ID do aplicativo da Microsoft** do seu bot. ![Captura de tela de um painel de chat com a ID do aplicativo Microsoft realçada](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. A ID do aplicativo determina o **nome do bot**, depois você poderá iniciar uma conversa de chat com esse bot.

<a name="upload-your-bot-for-group-chats-or-channels"></a>Carregar seu bot para chats de grupo ou canais
-----------------------------------

Se você quiser compartilhar o bot com seus colegas, veja como adicioná-lo a chats em grupo ou a canais de diferentes equipes:

1. Depois de [criar um pacote de aplicativos para seu bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), abra o Teams e navegue até a equipe na qual você carregará o bot.
2. Adicione o **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, aplicativo para o Teams.
3. No App Studio, selecione a guia **Editor de manifesto**. ![Captura de tela da guia Editor de manifesto.](media/Adding_Bot_To_Teams.png)
4. Para adicionar seu bot, em Funcionalidades, selecione o bot e escolha Adicionar um bot existente. Depois, escolha um bot existente ou insira a ID de um bot existente.
![Mostra a seleção do bot que você já criou.](media/Select_Existing_Bot.png)
5. Navegue até o local do pacote de aplicativos, selecione-o e clique em **Abrir**.
6. Selecione o nome do seu bot. (Não se esqueça de marcar a caixa de seleção **Chat em grupo** ou **Equipe** na seção do escopo).
7. Selecione **Testar e distribuir**.
8. Selecione o chat de grupo ou a equipe a que você deseja conectar o bot.

    O bot estará disponível em seu chat de grupo o equipe no Teams.
