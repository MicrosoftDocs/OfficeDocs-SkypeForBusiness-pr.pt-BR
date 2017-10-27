---
title: Adicionar bots para bate-papos privados e canais no Microsoft Teams | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como adicionar bots no Microsoft Teams para bate-papos privados e canais, criar bots personalizados e carregue seu próprio bot para bate-papo privado."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 905a105fba269aebb2b01cbccc1a47e7667ca341
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Adicionar bots para bate-papos privados e canais no Microsoft Teams
==========================================================

Os bots são programas automatizados configurados para responder a questões ou fornecer atualizações ou notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados. Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams. Os bots do Microsoft Teams são construídos no [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) e os bots que são desenvolvidos usando essa estrutura podem ser ativados facilmente para o Microsoft Teams.

No momento, o Microsoft Teams suporta bots em bate-papos privados e canais dentro de uma equipe. Os administradores podem controlar se o uso de bots é permitido ou proibido dentro do locatário do Office 365.<span id="_T-Bot" class="anchor"></span>

Os bots desenvolvidos e disponibilizados pela comunidade podem ser aproveitados no Microsoft Teams. A funcionalidade do bot e o carregamento lateral do bot devem ser ativados em nível de locatário para que os bots personalizados sejam funcionais. Os bots podem ser usados em bate-papos privados ou em canais. Para os canais, proprietários e membros de equipes podem adicionar bots.

<a name="add-bots-for-private-chat-and-channels"></a>Adicionar bots para bate-papos privados e canais
--------------------------------------

Existem duas formas de integrar um bot em bate-papos privados e canais:

1.  Instalar bots disponíveis publicamente para **bate-papos privados** ou **canais**. (Essa é a primeira opção.)

2.  Como alternativa, para encontrar bots, navegue até **Bate-papo**, pesquise por um **contato** e clique em **Descobrir aplicativos.**

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  Selecione com qual **Bot** você deseja ter uma conversa, conforme mostrado abaixo.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  Depois de escolher, dê **permissões** ao bot e selecione se deseja usar **bots em um bate-papo privado** ou selecione uma **Equipe** para usá-lo.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  Como alternativa, para usar um bot dentro do canal de uma equipe, basta clicar em **Visualizar equipe e bots**. Aqui, você pode descobrir mais bots.

6.  Um bot pode ser removido da equipe a qualquer momento. Basta clicar em **Visualizar equipe e bots** para ver todos os bots, e então **remover** o que desejar.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a>Criar bots personalizados para o Microsoft Teams
--------------------------------------

Você pode facilmente criar um bot que se integre nos seus aplicativos LOB usando o Microsoft Bot Framework. Consulte a orientação de [Criar e testar um bot para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber como você pode desenvolver e publicar seus próprios bots.

Quando você cria um bot e o registra com o Bot Framework, você pode optar por publicá-lo ou não. Se você não o publicar, o bot permanecerá privado. Você também pode exigir que seus usuários façam login antes de usar o bot. A exigência de login assegura que apenas os funcionários da sua organização possam acessar o bot, mesmo que o ID do aplicativo do bot se torne conhecido. Veja [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) no GitHub para ver um exemplo de código de como autenticar os usuários no seu diretório ativo usando bots.

Os bots podem ser testados usando o [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) antes que sejam implantados no seu Teams.

<a name="side-load-your-own-bot-for-private-chat"></a>Carregue o seu próprio bot para bate-papos privados
---------------------------------------

1.  Depois de criar seu bot, navegue até a página do **Painel do Bot** [](https://go.microsoft.com/fwlink/?linkid=854374) para o bot que você desenvolveu e, em **Detalhes**, copie o **ID do aplicativo da Microsoft**.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  No Microsoft Teams, no painel de **Bate-papo**, selecione o **ícone Adicionar bate-papo**. Em **Para:,** copie o **ID do aplicativo da Microsoft** do seu bot.

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  O ID do aplicativo determina o **nome do bot,** e então você poderá iniciar uma conversa de bate-papo com esse bot.
