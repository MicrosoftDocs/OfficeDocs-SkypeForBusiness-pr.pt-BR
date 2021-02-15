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

Os conectores mantêm sua equipe atualizada, fornecendo atualizações de serviço e conteúdo usados com frequência diretamente em um canal. Com conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como Trello, Wunderlist, GitHub e Serviços do Azure DevOps no fluxo de chat em sua equipe.

Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores, se as permissões da equipe permitirem, e todos os membros da equipe são notificados das atividades desse serviço. Os conectores continuarão a funcionar mesmo após o membro que inicialmente tiver configurado o conector. Qualquer membro da equipe com as permissões para adicionar\remover pode modificar a configuração de conectores por outros membros.

Os conectores do Microsoft 365 podem ser usados com os grupos do Microsoft Teams e do Microsoft 365, facilitando a sincronização de todos os membros e recebendo informações relevantes rapidamente. O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas. No entanto, vale a pena notar que desabilitar conectores para o grupo do Microsoft 365 do que uma equipe depende desabilitará a capacidade de criar conectores para essa equipe também.

<a name="add-a-connector-to-a-channel"></a>Adicionar um conector a um canal
----------------------------

Atualmente, você pode adicionar conectores usando clientes da área de trabalho e da Web do Microsoft Teams. No entanto, as informações postadas por esses conectores podem ser visualizadas em **todos os clientes, incluindo** dispositivos móveis.

1. Para adicionar um conector a um canal, clique nas **reellipses (...),** à direita de um nome de canal e, em seguida, clique em **Conectores.**

    > [!div class="mx-imgBorder"]
    > ![Captura de tela da interface do Teams com a opção Conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Você pode selecionar entre uma variedade de conectores disponíveis e clicar em **Adicionar.**

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
> **Notificação de atualização da URL do Conector**
>
> Os conectores do Teams estão em transição para uma nova URL para melhorar a segurança. Durante o decorrer dessa transição, você receberá determinadas notificações para atualizar o conector configurado para usar a nova URL. É altamente recomendável que você atualize o conector imediatamente para evitar qualquer interrupção nos serviços do conector. As etapas a seguir devem ser seguidas para atualizar a URL:
> 1. Na página de configuração de conectores, uma mensagem "Atenção Necessária" será exibida no botão "Gerenciar" para as conexões que precisam ser atualizadas.
> ![Captura de tela da mensagem "Atenção Necessária".](media/Teams_Attention_Required_message.png)
> 2. Para conectores web connectors de entrada, os usuários podem recriar a conexão simplesmente selecionando Atualizar URL e usando a **URL** recém-gerada da Web.
> ![Captura de tela do botão "Atualizar URL".](media/Teams_update_URL_button.png)
> 3. Para outros tipos de conector, o usuário precisaria remover o conector e recriar a configuração do conector.
> 4. Você verá a mensagem "A URL está atualizada" depois que a URL for atualizada com êxito.
> ![Captura de tela da mensagem "A URL está atualizada".](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>Desenvolvimento de conectores personalizados
----------------------------

Você também pode criar conectores personalizados, bem como web widgets de entrada e saída. Para obter mais informações, consulte nossa [documentação do desenvolvedor](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
