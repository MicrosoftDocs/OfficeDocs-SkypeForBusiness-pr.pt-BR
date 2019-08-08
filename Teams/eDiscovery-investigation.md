---
title: Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Saiba o que fazer quando precisar executar uma Descoberta Eletrônica, como quando precisar enviar todas as informações armazenadas eletronicamente para procedimentos judiciais.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6831ec2cef16e65e2fd8dd722d436c12b7548a5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236355"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="f3428-103">Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3428-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="f3428-104">Grandes empresas muitas vezes são expostas a grandes procedimentos legais de penalidade que exigem o envio de todas as ESI (informações armazenadas eletronicamente).</span><span class="sxs-lookup"><span data-stu-id="f3428-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="f3428-105">Todas as equipes 1:1 ou chats em grupo são registradas nas caixas de correio dos respectivos usuários e todas as mensagens de canal são registradas na caixa de correio do grupo que representa a equipe.</span><span class="sxs-lookup"><span data-stu-id="f3428-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="f3428-106">Os arquivos carregados são cobertos pela funcionalidade de Descoberta Eletrônica para SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="f3428-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="f3428-107">Para conduzir uma investigação de descoberta eletrônica com o conteúdo do Microsoft Teams, examine [a](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) etapa 1 neste link.</span><span class="sxs-lookup"><span data-stu-id="f3428-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="f3428-108">Os dados do Microsoft Teams serão exibidos como mensagens instantâneas ou conversas na saída de exportação do Excel para descoberta eletrônica, e você poderá montar o. PST no Outlook para exibir essas mensagens postar na exportação.</span><span class="sxs-lookup"><span data-stu-id="f3428-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="f3428-109">Ao montar o .PST para a equipe, observe que todas as conversas serão mantidas na pasta Bate-papo em Equipe no Histórico de Conversas.</span><span class="sxs-lookup"><span data-stu-id="f3428-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="f3428-110">O título da mensagem corresponde à Equipe a ao Canal.</span><span class="sxs-lookup"><span data-stu-id="f3428-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="f3428-111">Ao analisar a imagem abaixo, você pode ver essa mensagem que Bob enviou ao canal Projeto 7 da equipe de Especificações de Fabricação.</span><span class="sxs-lookup"><span data-stu-id="f3428-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Captura de tela de uma pasta de chat de equipe na caixa de correio de um usuário no Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="f3428-113">Para ver bate-papos privados na Caixa de Correio de um usuário, eles também estão localizados dentro da pasta Bate-papo em Equipe no Histórico de Conversas.</span><span class="sxs-lookup"><span data-stu-id="f3428-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="f3428-114">Descoberta eletrônica de chats convidados para convidados</span><span class="sxs-lookup"><span data-stu-id="f3428-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="f3428-115">Sem uma caixa de correio, chats convidados para convidados (chats 1xN em que não há usuários locatários domésticos) não seriam indexados e, consequentemente, não seriam incluídos na descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="f3428-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="f3428-116">Para facilitar a descoberta eletrônica para chats convidados a convidados, uma caixa de correio baseada em nuvem (ou uma caixa de correio fantasma) é criada para armazenar os dados do 1xN.</span><span class="sxs-lookup"><span data-stu-id="f3428-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="f3428-117">Depois que os dados de chat de equipe são armazenados na caixa de correio baseada em nuvem, eles são indexados para pesquisa de conteúdo de descoberta eletrônica e conformidade.</span><span class="sxs-lookup"><span data-stu-id="f3428-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="f3428-118">A ilustração a seguir mostra como a descoberta eletrônica funciona para chats convidados a convidados em que não há uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="f3428-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![convidado para convidado-chats com e sem caixa de correio](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
