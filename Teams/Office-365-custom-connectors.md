---
title: Usar o Office 365 e conectores personalizados no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8235ce9eb950df0c04ab41949500a640376e612
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245204"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Usar o Office 365 e conectores personalizados no Microsoft Teams
=======================================================

Os conectores mantêm sua equipe em dia fornecendo conteúdo usado com frequência e atualizações de serviço diretamente em um canal. Com os conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e serviços do DevOps do Azure dentro do fluxo de chat de sua equipe.

Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores, se as permissões da equipe permitirem, e todos os membros da equipe forem notificados sobre as atividades desse serviço. Os conectores continuarão a funcionar mesmo após o membro que, inicialmente, configurar o conector. Qualquer membro da equipe com as permissões para adicionar à instalação pode modificar os conectores por outros membros.

Os conectores do Office 365 podem ser usados com o Microsoft Teams e com os grupos do Office 365, facilitando para todos os membros manter a sincronia e receber informações relevantes rapidamente. O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas. No entanto, vale a pena observar que a desabilitação de conectores para o grupo do Office 365 em que uma equipe depende da capacidade de criar conectores para essa equipe também será desativada.

<a name="add-a-connector-to-a-channel"></a>Adicionar um conector a um canal
----------------------------

No momento, você pode adicionar conectores usando clientes da Web e de área de trabalho do Microsoft Teams. No entanto, as informações postadas por esses conectores podem ser vistas em **todos os clientes** , inclusive móvel.

1. Para adicionar um conector a um canal, clique nas **reticências (...)** à direita de um nome de canal e, em seguida ****, clique em conectores.

    ![Captura de tela da interface do teams com a opção conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Você pode selecionar uma variedade de conectores disponíveis e, em seguida, clicar em **Adicionar**.

    ![Captura de tela da caixa de diálogo conectores mostrando os conectores disponíveis.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Preencha as informações necessárias do conector selecionado e clique em **Salvar**. Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.

    ![Captura de tela da página de configuração do conector RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Os dados fornecidos pelo conector são publicados automaticamente no canal.

    ![Captura de tela da interface do Teams mostrando uma conversa em um canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Desenvolvimento de conectores personalizados
-----------------------------

É muito fácil desenvolver conectores personalizados que podem ser integrados a seus aplicativos de linha de negócios (LOB). Você pode usar o conector de webhook de **entrada** interno para criar um ponto de extremidade para um canal que obtém dados de qualquer aplicativo usando métodos post http.

1. E o **Incoming Webhook** como qualquer outro conector.

    ![Captura de tela da opção de adicionar o conector Incoming Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. Para criar um Webhook, especifique um **nome**, atualize a imagem do Webhook, se necessário, e clique em **Criar**.

    ![Captura de tela da página de configuração do conector de webhook de entrada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. Os aplicativos que empurram dados para esse canal exigem a URL do conector do webhook. Uma URL exclusiva é criada quando você cria o webhook. Compartilhe esta URL com seus desenvolvedores, para que eles possam configurar seus aplicativos para enviar dados por push, conforme necessário.

    ![Captura de tela da URL exclusiva do Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. Quando um aplicativo externo leva dados para um conector, a mensagem é mostrada na lista de conversas do canal como uma mensagem especial chamada de mensagem do **Cartão do Conector**.

    ![Captura de tela da interface do Teams mostrando uma mensagem do Cartão do Conector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     Os desenvolvedores podem configurar seus aplicativos para criar esses cartões enviando uma solicitação HTTP com uma carga JSON simples para o endereço do webhook de uma equipe, que é uma URL exclusiva desse ponto de extremidade fornecida pelo assistente. Faça com que seus desenvolvedores consultem [introdução aos conectores do Office 365 para Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), na Microsoft Developer Network, que tenha instruções detalhadas e exemplos de conector. Outros recursos incluem [Conectar aplicativos aos seus grupos no Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) e [Centro de Desenvolvimento do Office – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).
