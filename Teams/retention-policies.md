---
title: Políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Saiba como as políticas de retenção e como gerenciá-las no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6adaee32648a6ec522098d90fd3c90ff161ef00e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838191"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="cc20e-103">Políticas de retenção no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc20e-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="cc20e-104">As conversas de equipes são persistentes e mantidas para sempre por padrão.</span><span class="sxs-lookup"><span data-stu-id="cc20e-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="cc20e-105">Com a introdução de políticas de retenção, os administradores podem configurar as políticas de retenção (preservação e exclusão) no centro de conformidade do & de segurança para mensagens de chat e de canal de equipe.</span><span class="sxs-lookup"><span data-stu-id="cc20e-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="cc20e-106">Isso ajuda as organizações a reter dados para conformidade (especificamente, política de preservação) para um período específico ou livrar-se de dados (ou seja, política de exclusão) se for considerado um passivo após um período específico.</span><span class="sxs-lookup"><span data-stu-id="cc20e-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="cc20e-107">As políticas de retenção de equipe garantem que, quando você exclui dados, ele é removido de todos os locais de armazenamento de dados permanentes do serviço Teams.</span><span class="sxs-lookup"><span data-stu-id="cc20e-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="cc20e-108">Ainda não damos suporte à configuração para a retenção de mensagens de canal privado.</span><span class="sxs-lookup"><span data-stu-id="cc20e-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="cc20e-109">A retenção de arquivos compartilhados em canais privados tem suporte.</span><span class="sxs-lookup"><span data-stu-id="cc20e-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="cc20e-110">Para gerenciar as políticas de retenção do Teams, use as configurações e cmdlets no centro de conformidade do Office 365 Security & em**retenção**de **governança** > de informações.</span><span class="sxs-lookup"><span data-stu-id="cc20e-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="cc20e-111">As políticas de retenção de equipes oferecem suporte:</span><span class="sxs-lookup"><span data-stu-id="cc20e-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="cc20e-112">Preservação: manter os dados do teams por uma duração especificada e, em seguida, não fazer nada</span><span class="sxs-lookup"><span data-stu-id="cc20e-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="cc20e-113">Preservação e excluir: manter os dados do teams por uma duração especificada e excluir</span><span class="sxs-lookup"><span data-stu-id="cc20e-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="cc20e-114">Exclusão: excluir dados de equipes após uma duração especificada</span><span class="sxs-lookup"><span data-stu-id="cc20e-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="cc20e-115">As políticas de retenção do teams ainda não dão suporte:</span><span class="sxs-lookup"><span data-stu-id="cc20e-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="cc20e-116">Políticas avançadas de retenção não se aplicam a locais de mensagens de canal de chat e equipe do teams</span><span class="sxs-lookup"><span data-stu-id="cc20e-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>

<span data-ttu-id="cc20e-117">Os administradores podem configurar políticas de retenção separadas para chats privados do Teams (1:1 ou 1: muitos chats) e mensagens de canal de equipe.</span><span class="sxs-lookup"><span data-stu-id="cc20e-117">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="cc20e-118">Em muitos casos, as organizações consideram dados de chat privados como uma obrigação mais passiva do que as mensagens de canal, que normalmente são mais conversas relacionadas ao projeto.</span><span class="sxs-lookup"><span data-stu-id="cc20e-118">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="cc20e-119">Configure essas políticas no centro de conformidade & segurança,**retenção**de **governança** > de informações.</span><span class="sxs-lookup"><span data-stu-id="cc20e-119">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="cc20e-120">Ative mensagens de canal e **chats de equipe** do **Teams** e, em seguida, defina as políticas de retenção para esses locais (também mostrado no diagrama abaixo).</span><span class="sxs-lookup"><span data-stu-id="cc20e-120">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="cc20e-121">Ao ativar **as mensagens de canal do teams**, você pode especificar as equipes às quais essa política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="cc20e-121">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="cc20e-122">Por exemplo, para Teams X, Y e Z, o administrador pode definir as políticas de exclusão para 1 ano (selecionando essas equipes individualmente) e aplicar uma política de exclusão de 3 anos ao restante das equipes.</span><span class="sxs-lookup"><span data-stu-id="cc20e-122">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="cc20e-123">Você pode fazer o mesmo para **chats de equipe** selecionando usuários específicos e aplicando políticas exclusivas de retenção.</span><span class="sxs-lookup"><span data-stu-id="cc20e-123">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="cc20e-125">Os locais de mensagens de canal de equipe e os chats de equipe só abordam as conversas de equipe armazenadas nas caixas de correio do Exchange Online (caixas de correio de grupo e de usuário).</span><span class="sxs-lookup"><span data-stu-id="cc20e-125">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="cc20e-126">As mensagens são excluídas de todos os locais de armazenamento pertinentes, ou seja, as caixas de correio, substrato e serviço de chat.</span><span class="sxs-lookup"><span data-stu-id="cc20e-126">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="cc20e-127">Para gerenciar políticas de retenção para arquivos do Teams, que são armazenados no OneDrive for Business e no SharePoint, use as políticas de retenção.</span><span class="sxs-lookup"><span data-stu-id="cc20e-127">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="cc20e-128">Por design, as políticas de exclusão para arquivos do teams são configuradas por locais do SharePoint Online e do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cc20e-128">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="cc20e-129">Como resultado, é possível que uma política possa excluir um arquivo referenciado em uma mensagem de chat ou um canal de equipe antes de as mensagens serem excluídas.</span><span class="sxs-lookup"><span data-stu-id="cc20e-129">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="cc20e-130">Nesse caso, o arquivo ainda será exibido na mensagem do Teams, mas, se você clicar no arquivo, receberá um erro "arquivo não encontrado" (isso também pode acontecer na ausência de uma política, se alguém excluir manualmente um arquivo do SharePoint Online ou do OneDrive for Business).</span><span class="sxs-lookup"><span data-stu-id="cc20e-130">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="cc20e-131">Para obter informações detalhadas sobre a configuração de políticas de retenção do Office 365, leia [visão geral das políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="cc20e-131">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
