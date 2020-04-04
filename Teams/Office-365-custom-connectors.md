---
title: Usar o Office 365 e conectores personalizados
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 6726507b0dd6c0ca0067bf19a3f9a2c37f727c53
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136501"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Usar o Office 365 e conectores personalizados no Microsoft Teams
=======================================================

Os conectores mantêm sua equipe em dia fornecendo conteúdo usado com frequência e atualizações de serviço diretamente em um canal. Com os conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e serviços do DevOps do Azure dentro do fluxo de chat de sua equipe.

Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores, se as permissões da equipe permitirem, e todos os membros da equipe forem notificados sobre as atividades desse serviço. Os conectores continuarão a funcionar mesmo após o membro que, inicialmente, configurar o conector. Qualquer membro da equipe com as permissões para adicionar à instalação pode modificar os conectores por outros membros.

Os conectores do Office 365 podem ser usados com o Microsoft Teams e com os grupos do Office 365, facilitando para todos os membros manter a sincronia e receber informações relevantes rapidamente. O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas. No entanto, vale a pena observar que a desabilitação de conectores para o grupo do Office 365 em que uma equipe depende da capacidade de criar conectores para essa equipe também será desativada.

<a name="add-a-connector-to-a-channel"></a>Adicionar um conector a um canal
----------------------------

No momento, você pode adicionar conectores usando clientes da Web e de área de trabalho do Microsoft Teams. No entanto, as informações postadas por esses conectores podem ser vistas em **todos os clientes** , inclusive móvel.

1. Para adicionar um conector a um canal, clique nas **reticências (...)** à direita de um nome de canal e, em seguida, clique em **conectores**.

    ![Captura de tela da interface do teams com a opção conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Você pode selecionar uma variedade de conectores disponíveis e, em seguida, clicar em **Adicionar**.

    ![Captura de tela da caixa de diálogo conectores mostrando os conectores disponíveis.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Preencha as informações necessárias do conector selecionado e clique em **Salvar**. Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.

    ![Captura de tela da página de configuração do conector RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Os dados fornecidos pelo conector são publicados automaticamente no canal.

    ![Captura de tela da interface do Teams mostrando uma conversa em um canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Desenvolvimento de conectores personalizados
----------------------------

Você também pode criar conectores personalizados, bem como WebHooks de entrada e saída. Para obter mais informações, consulte nossa [documentação do desenvolvedor](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
