---
title: Adicionar bots para bate-papos privados e canais no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: lucarras
description: Saiba como adicionar bots no Microsoft Teams para bate-papos privados e canais, criar bots personalizados e carregue seu próprio bot para bate-papo privado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ff6cf5af3a1a2129ee22ae0ff51ac4216ccaefe
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013357"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Adicionar bots para bate-papos privados e canais no Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados. Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams. Os bots do Microsoft Teams são baseados no [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). Os bots desenvolvidos usando essa estrutura podem ser facilmente habilitados para o Microsoft Teams. Para obter mais informações, consulte [os recursos de gerenciar equipes da Microsoft em sua organização do Office 365](enable-features-office-365.md).

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
