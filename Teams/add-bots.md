---
title: Adicionar bots para bate-papos privados e canais no Microsoft Teams
author: LolaJacobsen, DamienDoumer
ms.author: lolaj, Damien
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: Saiba como adicionar bots no Microsoft Teams para bate-papos privados e canais, criar bots personalizados e carregue seu próprio bot para bate-papo privado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6987c14973443e62f0be69f9872c4e248ddb026b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548841"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Adicionar bots para bate-papos privados e canais no Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados. Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams. Os bots do Microsoft Teams são baseados no [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). Os bots desenvolvidos usando essa estrutura podem ser facilmente habilitados para o Microsoft Teams. Para saber mais, confira [Gerenciar configurações do Microsoft Teams para sua organização](enable-features-office-365.md).

No momento, o Microsoft Teams suporta bots em bate-papos privados e canais dentro de uma equipe. Os administradores podem controlar se o uso de bots é permitido ou proibido dentro do locatário do Office 365.<span id="_T-Bot" class="anchor"></span>

Os bots desenvolvidos pela comunidade podem ser utilizados no Microsoft Teams. A funcionalidade do bot e o carregamento lateral do bot devem ser ativados em nível de locatário para que os bots personalizados sejam funcionais. Os bots podem ser usados em bate-papos privados ou em canais. Para os canais, proprietários e membros de equipes podem adicionar bots.

Para obter mais informações, consulte a seção "Usando bots" em [Aplicativos e serviços](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b). 

> [!IMPORTANT]
> Não é recomendável adicionar um bot por GUID para qualquer coisa além de fins de teste. Isso limita severamente a funcionalidade de um bot. Os bots no uso da produção devem ser adicionados ao Teams como parte de um aplicativo. Consulte [criar um bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) e [testar e depurar o Microsoft Teams bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Criar bots personalizados para o Microsoft Teams
--------------------------------------

Você pode facilmente criar um bot que se integre nos seus aplicativos LOB usando o Microsoft Bot Framework. Consulte a orientação de [Criar e testar um bot para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber como você pode desenvolver e publicar seus próprios bots.

Quando você cria um bot e o registra com o Bot Framework, pode optar por publicá-lo. Se você não o publicar, o bot permanecerá privado. Você também pode exigir que seus usuários façam login antes de usar o bot. A exigência de login assegura que apenas os funcionários da sua organização possam acessar o bot, mesmo que o ID do aplicativo do bot se torne conhecido. Veja [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) no GitHub para ver um exemplo de código de como autenticar os usuários no seu diretório ativo usando bots.

Os bots podem ser testados usando o [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) antes que sejam implantados no seu Teams.

<a name="side-load-your-own-bot-for-private-chat"></a>Carregue o seu próprio bot para bate-papos privados
---------------------------------------

1. Depois de criar o bot, vá para as **configurações do aplicativo** do bot que você desenvolveu e, em **configurações do aplicativo**, copie o valor da configuração **MicrosoftAppId** . ![Captura de tela da página de configurações do aplicativo para um bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  No Microsoft Teams, no painel de **Bate-papo**, selecione o **ícone Adicionar bate-papo**. Em **Para**, cole a **ID do Aplicativo da Microsoft** de seu bot. ![Captura de tela de um painel de chat com a ID do aplicativo da Microsoft realçada](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  O ID do aplicativo determina o **nome do bot,** e então você poderá iniciar uma conversa de bate-papo com esse bot.

<a name="side-load-your-bot-for-channels"></a>Carregar o bot para canais
-----------------------------------

Se você quiser compartilhar seu bot com seus colegas, veja como adicioná-lo a canais de diferentes equipes:

1. Depois de [criar um pacote do aplicativo para o seu bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), abra o Teams e navegue até a equipe na qual você está carregando o bot.
2. Adicione o app **[Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, App ao Microsoft Teams.
3. No app Studio, selecione a guia **Editor** de manifesto ![. captura de tela da guia Editor de manifesto.](media/Adding_Bot_To_Teams.png)
4. Para adicionar seu bot, em recursos, selecione bot e escolha Adicionar um bot existente e, em seguida, você terá a opção de escolher um bot existente de um drop ou inserir a ID de um dos seus bots existentes.
![Mostra a seleção do bot que você já criou.](media/Select_Existing_Bot.png)
5. Navegue até o local do pacote do aplicativo, selecione-o e clique em **abrir**.
6. Selecione o nome do seu bot (não se esqueça de marcar a caixa de seleção "equipe" na seção escopo)
7. Selecione a opção testar e distribuir.
8. Selecione a equipe à qual deseja conectar o bot na caixa de diálogo que aparece na caixa de diálogo que aparece.

Com isso, seu bot estará disponível na equipe da equipe da Microsoft.
