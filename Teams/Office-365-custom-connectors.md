---
title: Usar Microsoft 365 e conectores personalizados
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Os conectores mantêm sua equipe atualizada com conteúdo e atualizações de serviços que você usa frequentemente diretamente em um canal.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e42ef850c089633a6c9145935d6e70a92cdb6801
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442687"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Use Microsoft 365 conectores personalizados e Microsoft Teams

Os conectores mantêm sua equipe atual, fornecendo atualizações de conteúdo e serviço usados com frequência diretamente em um canal. Com conectores, Microsoft Teams usuários podem receber atualizações de serviços populares, como Trello, Wunderlist, GitHub e Azure DevOps Services no fluxo de chat em sua equipe.

Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores se as permissões de equipe permitirem e todos os membros da equipe são notificados das atividades desse serviço. Os conectores continuarão a funcionar mesmo depois que o membro que tiver configurado inicialmente o conector tiver sido deixado. Qualquer membro da equipe com as permissões para adicionar\remover pode modificar a configuração de conectores por outros membros.

Microsoft 365 conectores podem ser usados com grupos de Microsoft Teams e Microsoft 365, facilitando que todos os membros fiquem em sincronia e recebam informações relevantes rapidamente. O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas. No entanto, vale a pena notar que desabilitar conectores para o grupo Microsoft 365 que uma equipe depende desabilitará a capacidade de criar conectores para essa equipe também.

> [!NOTE]
> Os conectores são desabilitados por padrão nos ambientes de Community (GCC) do Governo. Se você precisar habilita-los, desmarque os parâmetros ConnectorsEnabled ou ConnectorsEnabledForTeams para $true com o cmdlet SetOrganizationConfig. Você precisa se conectar ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).

## <a name="add-a-connector-to-a-channel"></a>Adicionar um conector a um canal

Atualmente, você pode adicionar conectores usando Microsoft Teams da área de trabalho e da Web. No entanto, as informações postadas por esses conectores podem ser exibidas em **todos os clientes,** incluindo móveis.

1. Para adicionar um conector a um canal, clique nas **releições (...),** à direita de um nome de canal e clique em **Conectores**.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da interface Teams com a opção Conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Você pode selecionar entre vários conectores disponíveis e, em seguida, clique em **Adicionar**.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da caixa de diálogo Conectores mostrando os conectores disponíveis.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Preencha as informações necessárias do conector selecionado e clique em **Salvar**. Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da página de configuração do conector RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Os dados fornecidos pelo conector são publicados automaticamente no canal.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da interface do Teams mostrando uma conversa em um canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **Notificação de atualização da URL do conector**
>
> Os Teams conectores estão fazendo a transição para uma nova URL para melhorar a segurança. Durante o curso dessa transição, você receberá determinadas notificações para atualizar seu conector configurado para usar a nova URL. É altamente recomendável que você atualize seu conector imediatamente para evitar qualquer interrupção nos serviços do conector. As etapas a seguir precisam ser seguidas para atualizar a URL:
>
> 1. Na página de configuração de conectores, uma mensagem "Atenção Necessária" será exibida no botão "Gerenciar" para as conexões que precisam ser atualizadas.
> ![Captura de tela da mensagem "Atenção Necessária".](media/Teams_Attention_Required_message.png)
> 2. Para conectores de webhook de entrada, os usuários podem recriar a conexão simplesmente selecionando **Atualizar URL** e usando a URL de webhook recém-gerada.
> ![Captura de tela do botão "Atualizar URL".](media/Teams_update_URL_button.png)
> 3. Para outros tipos de conector, o usuário precisaria remover o conector e recriar a configuração do conector.
> 4. Você verá uma mensagem "A URL está atualizada" depois que a URL tiver sido atualizada com êxito.
> ![Captura de tela da mensagem "URL está atualizada".](media/Teams_URL_up_to_date.png)

## <a name="develop-custom-connectors"></a>Desenvolvimento de conectores personalizados

Você também pode criar conectores personalizados, bem como webhooks de entrada e de saída. Para obter mais informações, consulte nossa [documentação do desenvolvedor](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
