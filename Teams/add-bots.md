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
ms.openlocfilehash: a4e921ea668fc59b520fdb068355db82bfe24481
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298520"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Adicionar bots para bate-papos privados e canais no Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados. Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams. Os bots do Microsoft Teams são baseados no [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). Os bots desenvolvidos usando essa estrutura podem ser facilmente habilitados para o Microsoft Teams. Para saber mais, confira [Gerenciar configurações do Microsoft Teams para sua organização](enable-features-office-365.md).

No momento, o Microsoft Teams suporta bots em bate-papos privados e canais dentro de uma equipe. Os administradores podem controlar se o uso de bots é permitido ou proibido dentro do locatário do Office 365.<span id="_T-Bot" class="anchor"></span>

Os bots desenvolvidos pela comunidade podem ser utilizados no Microsoft Teams. A funcionalidade do bot e o carregamento lateral do bot devem ser ativados em nível de locatário para que os bots personalizados sejam funcionais. Os bots podem ser usados em bate-papos privados ou em canais. Para os canais, proprietários e membros de equipes podem adicionar bots.

Para obter mais informações, consulte a seção "Usando bots" em [Aplicativos e serviços](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b). 




<a name="create-custom-bots-for-microsoft-teams"></a>Criar bots personalizados para o Microsoft Teams
--------------------------------------

Você pode facilmente criar um bot que se integre nos seus aplicativos LOB usando o Microsoft Bot Framework. Consulte a orientação de [Criar e testar um bot para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber como você pode desenvolver e publicar seus próprios bots.

Quando você cria um bot e o registra com o Bot Framework, pode optar por publicá-lo. Se você não o publicar, o bot permanecerá privado. Você também pode exigir que seus usuários façam login antes de usar o bot. A exigência de login assegura que apenas os funcionários da sua organização possam acessar o bot, mesmo que o ID do aplicativo do bot se torne conhecido. Veja [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) no GitHub para ver um exemplo de código de como autenticar os usuários no seu diretório ativo usando bots.

Os bots podem ser testados usando o [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) antes que sejam implantados no seu Teams.

<a name="side-load-your-own-bot-for-private-chat"></a>Carregue o seu próprio bot para bate-papos privados
---------------------------------------

1. Depois de criar sua bot, vá para as **Configurações do aplicativo** para o bot que você desenvolvido, em seguida, em **configurações de aplicativo**, copie o valor da configuração **MicrosoftAppId** . ![Página de captura de tela das configurações de aplicativo para um bot com a ID de aplicativo Microsoft realçado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)



2.  No Microsoft Teams, no painel de **Bate-papo**, selecione o **ícone Adicionar bate-papo**. Em **Para**, cole a **ID do Aplicativo da Microsoft** de seu bot. ![Captura de tela de um painel de chat com o ícone para Adicionar chat e a linha Para com a ID do Aplicativo da Microsoft destacada.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  O ID do aplicativo determina o **nome do bot,** e então você poderá iniciar uma conversa de bate-papo com esse bot.

<a name="side-load-your-bot-for-channels"></a>No lado do seu bot de canais de carga
-----------------------------------

Se você deseja compartilhar seu bot com seus colegas, aqui está como adicioná-lo a canais de equipes diferentes:

1. Após ter [criado um pacote de aplicativos para o seu bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), abra o equipes e navegue para a equipe nos quais você vai ser lado carregamento o bot.
2. Adicione o **[Studio de aplicativo](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app às equipes da Microsoft.
3. No App Studio, selecione o **Editor de manifesto** na guia ![captura de tela do guia Editor de manifesto.](media/Adding_Bot_To_Teams.png)
4. Para adicionar sua bot, em recursos, selecione bot e optar por adicionar um bot existente, então você terá a opção para escolher um bot existente de um depósito ou insira a Id de um dos seus bots existentes.
![Selecione seu bot já criado.](media/Select_Existing_Bot.png)
5. Navegue até o local do seu pacote de aplicativos, selecioná-la e, em seguida, clique em **Abrir**.
6. Selecione o nome do seu bot (não se esqueça de marcar a caixa de seleção "Equipe" na seção escopo)
7. Selecione o teste e distribua a opção.
8. Selecione a equipe do qual você deseja se conectar seu bot na caixa de diálogo que é exibida.

Com isso, o seu bot será disponíveis na equipe do Team seu Microsoft.
