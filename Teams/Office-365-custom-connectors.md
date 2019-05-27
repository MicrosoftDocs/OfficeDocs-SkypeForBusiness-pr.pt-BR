---
title: Usar o Office 365 e conectores personalizados no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2167022e3187924f5283ab5bee3a6b220595fd64
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432852"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Usar o Office 365 e conectores personalizados no Microsoft Teams
=======================================================

Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal. Com os conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e serviços do DevOps do Azure dentro do fluxo de chat de sua equipe.

Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores, se as permissões da equipe permitirem, e todos os membros da equipe forem notificados sobre as atividades desse serviço. Os conectores continuarão a funcionar mesmo após o membro que, inicialmente, configurar o conector. Qualquer membro da equipe com as permissões para adicionar à instalação pode modificar os conectores por outros membros.

Os conectores do Office 365 podem ser usados com o Microsoft Teams e com os grupos do Office 365, facilitando para todos os membros manter a sincronia e receber informações relevantes rapidamente. O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas. No entanto, vale a pena observar que a desabilitação de conectores para o grupo do Office 365 em que uma equipe depende da capacidade de criar conectores para essa equipe também será desativada.

No momento, os conectores podem ser adicionados usando os clientes Microsoft Teams de desktop e web. No entanto, as informações publicadas por esses conectores podem ser visualizadas usando **todos os clientes**, inclusive de celular.

1.  Para adicionar um conector a um canal, clique nas **reticências (…),** ao lado direito do nome do canal, e então clique em **Conectores.**

    ![Captura de tela da interface do teams com a opção conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  Os usuários podem escolher a partir de uma grande variedade de conectores, e então clicar em **Adicionar**.

    ![Captura de tela da caixa de diálogo conectores mostrando os conectores disponíveis.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  Preencha as informações necessárias do conector selecionado e clique em **Salvar**. Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.

    ![Captura de tela da página de configuração do conector RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  Os dados fornecidos pelo conector são publicados automaticamente no canal.

    ![Captura de tela da interface do Teams mostrando uma conversa em um canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Desenvolvimento de conectores personalizados
-----------------------------

Desenvolver conectores personalizados que podem se integrar aos seus aplicativos Line-of-Business (LOB) é muito fácil. Você pode usar o conector interno **Incoming Webhook** para criar um endpoint para um canal que pega dados de qualquer aplicativo usando métodos de publicação HTTP.

1.  E o **Incoming Webhook** como qualquer outro conector.

    ![Captura de tela da opção de adicionar o conector Incoming Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  Para criar um Webhook, especifique um **nome**, atualize a imagem do Webhook, se necessário, e clique em **Criar**.

    ![Captura de tela da página de configuração do conector de webhook de entrada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  Os aplicativos que levam dados para este canal precisam da URL do conector Webhook. É criada uma **URL exclusiva** ao criar o **Webhook**. Compartilhe essa URL com os seus desenvolvedores para que eles possam configurar seus aplicativos para pegar os dados conforme necessário.

    ![Captura de tela da URL exclusiva do Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  Quando um aplicativo externo leva dados para um conector, a mensagem é mostrada na lista de conversas do canal como uma mensagem especial chamada de mensagem do **Cartão do Conector**.

    ![Captura de tela da interface do Teams mostrando uma mensagem do Cartão do Conector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

Os desenvolvedores podem configurar seus aplicativos para criar esses cartões enviando uma solicitação HTTP com um payload JSON simples para o endereço Webhook do Microsoft Team, que é uma URL exclusiva desse endpoint fornecido pelo assistente. Solicite que os seus desenvolvedores consultem [Introdução aos Conectores do Office 365 para o Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors) na Rede do Desenvolvedor da Microsoft, com instruções detalhadas e exemplos de conectores. Outros recursos incluem [Conectar aplicativos aos seus grupos no Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) e [Centro de Desenvolvimento do Office – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).
