---
title: Usar o Microsoft 365 e conectores personalizados
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
description: Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076413"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Usar o Microsoft 365 e conectores personalizados no Microsoft Teams
=======================================================

Os conectores mantêm sua equipe em dia fornecendo conteúdo usado com frequência e atualizações de serviço diretamente em um canal. Com os conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como o Trello, o Wunderlist, o GitHub e os serviços do DevOps do Azure dentro do fluxo de chat de sua equipe.

Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores, se as permissões da equipe permitirem, e todos os membros da equipe forem notificados sobre as atividades desse serviço. Os conectores continuarão a funcionar mesmo após o membro que, inicialmente, configurar o conector. Qualquer membro da equipe com as permissões para adicionar à instalação pode modificar os conectores por outros membros.

Os conectores do Microsoft 365 podem ser usados com os grupos do Microsoft Teams e do Microsoft 365, tornando mais fácil para todos os membros ficarem sincronizados e receber informações relevantes rapidamente. O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas. No entanto, é importante observar que a desabilitação de conectores para o grupo do Microsoft 365 em que uma equipe depende da capacidade de criar conectores para essa equipe também será desabilitada.

<a name="add-a-connector-to-a-channel"></a>Adicionar um conector a um canal
----------------------------

No momento, você pode adicionar conectores usando clientes da Web e de área de trabalho do Microsoft Teams. No entanto, as informações postadas por esses conectores podem ser vistas em **todos os clientes** , inclusive móvel.

1. Para adicionar um conector a um canal, clique nas **reticências (...)** à direita de um nome de canal e, em seguida, clique em **conectores**.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da interface do teams com a opção conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Você pode selecionar uma variedade de conectores disponíveis e, em seguida, clicar em **Adicionar**.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da caixa de diálogo conectores mostrando os conectores disponíveis.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Preencha as informações necessárias do conector selecionado e clique em **Salvar**. Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da página de configuração do conector RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Os dados fornecidos pelo conector são publicados automaticamente no canal.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da interface do Teams mostrando uma conversa em um canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **Notificação de atualização de URL do conector**
>
> Os conectores do teams estão migrando para uma nova URL para melhorar a segurança. Durante o curso dessa transição, você receberá determinadas notificações para atualizar seu conector configurado para usar a nova URL. É altamente recomendável que você atualize seu conector imediatamente para evitar qualquer interrupção nos serviços de conector. As etapas a seguir devem ser seguidas para atualizar a URL:
> 1. Na página de configuração de conectores, será exibida uma mensagem de "atenção necessária" no botão "gerenciar" das conexões que precisam ser atualizadas.
> ![Captura de tela da mensagem "atenção necessária".](media/Teams_Attention_Required_message.png)
> 2. Para conectores de webhook de entrada, os usuários podem recriar a conexão simplesmente selecionando **Atualizar URL** e usando a URL do webhook recém gerada.
> ![Captura de tela do botão "atualizar URL".](media/Teams_update_URL_button.png)
> 3. Para outros tipos de conector, o usuário precisaria remover o conector e recriar a configuração do conector.
> 4. Você verá uma mensagem "URL está atualizada" depois que a URL for atualizada com êxito.
> ![Captura de tela da mensagem "URL atualizada".](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>Desenvolvimento de conectores personalizados
----------------------------

Você também pode criar conectores personalizados, bem como WebHooks de entrada e saída. Para obter mais informações, consulte nossa [documentação do desenvolvedor](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
