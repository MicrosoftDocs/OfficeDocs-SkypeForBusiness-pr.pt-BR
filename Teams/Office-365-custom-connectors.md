---
title: Usar o Office 365 e conectores personalizados no Microsoft Teams | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5adef4ea4c540523a0efffcf007a516f0a4efbbc
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2017
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Usar o Office 365 e conectores personalizados no Microsoft Teams
=======================================================

Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal. Com os conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e VSTS no fluxo de bate-papo de suas equipes.

Qualquer membro da equipe pode conectar sua equipe a serviços populares em nuvem com os conectores, e todos os membros da equipe são notificados das atividades desse serviço. Se um usuário for removido de uma equipe, todos os conectores adicionados à equipe pelo usuário removido deixam de funcionar. As reuniões agendadas continuam funcionando porque estão no calendário do grupo.

Os conectores do Office 365 podem ser usados com o Microsoft Teams e com os grupos do Office 365, facilitando para todos os membros manter a sincronia e receber informações relevantes rapidamente. O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas.

No momento, os conectores podem ser adicionados usando os clientes Microsoft Teams de desktop e web. No entanto, as informações publicadas por esses conectores podem ser visualizadas usando **todos os clientes**, inclusive de celular.

1.  Para adicionar um conector a um canal, clique nas **reticências (…),** ao lado direito do nome do canal, e então clique em **Conectores.**

    ![Captura de tela da interface do Teams com o nome de um canal selecionado e a opção de Conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  Os usuários podem escolher a partir de uma grande variedade de conectores, e então clicar em **Adicionar**.

    ![Captura de tela da caixa de diálogo Conectores mostrando os conectores disponíveis para ser adicionados.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

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

    ![Captura de tela da página de configuração do conector Incoming Webhook. ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  Os aplicativos que levam dados para este canal precisam da URL do conector Webhook. É criada uma **URL exclusiva** ao criar o **Webhook**. Compartilhe essa URL com os seus desenvolvedores para que eles possam configurar seus aplicativos para pegar os dados conforme necessário.

    ![Captura de tela da URL exclusiva do Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  Quando um aplicativo externo leva dados para um conector, a mensagem é mostrada na lista de conversas do canal como uma mensagem especial chamada de mensagem do **Cartão do Conector**.

    ![Captura de tela da interface do Teams mostrando uma mensagem do Cartão do Conector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

Os desenvolvedores podem configurar seus aplicativos para criar esses cartões enviando uma solicitação HTTP com um payload JSON simples para o endereço Webhook do Microsoft Team, que é uma URL exclusiva desse endpoint fornecido pelo assistente. Solicite que os seus desenvolvedores consultem [Introdução aos Conectores do Office 365 para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783) na Rede do Desenvolvedor da Microsoft, com instruções detalhadas e exemplos de conectores. Outros recursos incluem [Conectar aplicativos aos seus grupos no Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) e [Centro de Desenvolvimento do Office – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).
