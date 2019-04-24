---
title: Políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
description: Saiba mais sobre como as políticas de retenção e como gerenciá-los em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3c253569f642a8833d9bfad6677fe1a17624447
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205116"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="2f838-103">Políticas de retenção no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f838-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="2f838-104">As equipes conversas são persistentes e retido para sempre por padrão.</span><span class="sxs-lookup"><span data-stu-id="2f838-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="2f838-105">Com a introdução das políticas de retenção, admins pode configurar políticas de retenção (preservação e exclusão) no & a segurança Centro de conformidade para mensagens de chat e canal de equipes.</span><span class="sxs-lookup"><span data-stu-id="2f838-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="2f838-106">Isso ajuda as organizações a reter dados para fins de conformidade (isto é, a diretiva de preservação) por um período específico ou se livrar de dados (ou seja, a política de exclusão), se ele é considerado um passivo após um período específico.</span><span class="sxs-lookup"><span data-stu-id="2f838-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="2f838-107">Políticas de retenção de equipes Certifique-se de que, quando você exclui dados, ele será removido de todos os locais de armazenamento de dados permanentes no serviço equipes.</span><span class="sxs-lookup"><span data-stu-id="2f838-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span> 

<span data-ttu-id="2f838-108">Para gerenciar políticas de retenção de equipes, use as configurações e os cmdlets no & de segurança do Office 365 Centro de conformidade em um **Governança dados** > **retenção**.</span><span class="sxs-lookup"><span data-stu-id="2f838-108">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Data Governance** > **Retention**.</span></span>

<span data-ttu-id="2f838-109">Políticas de retenção de equipes têm suporte para:</span><span class="sxs-lookup"><span data-stu-id="2f838-109">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="2f838-110">Preservação: Manter dados de equipes por um período especificado e, em seguida, eu não fizer nada</span><span class="sxs-lookup"><span data-stu-id="2f838-110">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="2f838-111">Preservação e, em seguida, excluir: manter dados de equipes por um período especificado e excluir</span><span class="sxs-lookup"><span data-stu-id="2f838-111">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="2f838-112">Exclusão: Excluir dados de equipes após um período especificado</span><span class="sxs-lookup"><span data-stu-id="2f838-112">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="2f838-113">Políticas de retenção de equipes ainda não suportam:</span><span class="sxs-lookup"><span data-stu-id="2f838-113">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="2f838-114">Políticas de retenção avançada não se aplicam ao chat de equipes e locais de mensagem de canal de equipes</span><span class="sxs-lookup"><span data-stu-id="2f838-114">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="2f838-115">Duração de menos de 30 dias</span><span class="sxs-lookup"><span data-stu-id="2f838-115">Duration of fewer than 30 days</span></span>

<span data-ttu-id="2f838-116">Administradores podem configurar políticas de retenção separados para mensagens de canal de equipes e chats privadas de equipes (1:1 ou 1: muitos chats).</span><span class="sxs-lookup"><span data-stu-id="2f838-116">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="2f838-117">Em muitos casos, as organizações considerar os dados de bate-papo privado como mais de uma obrigação de mensagens de canal, que geralmente são mais conversas relacionados ao projeto.</span><span class="sxs-lookup"><span data-stu-id="2f838-117">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="2f838-118">Configurar essas diretivas de segurança & Centro de conformidade, **governança de dados** > **retenção**.</span><span class="sxs-lookup"><span data-stu-id="2f838-118">Set up these policies in the Security & Compliance Center, **Data governance** > **Retention**.</span></span> <span data-ttu-id="2f838-119">Ative **equipes mensagens de canal** e **equipes de bate-papos** e, em seguida, definir políticas de retenção desses locais (também é mostradas no diagrama a seguir).</span><span class="sxs-lookup"><span data-stu-id="2f838-119">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="2f838-120">Quando você ativa **as mensagens de canal de equipes**, você pode especificar as equipes ao qual esta política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="2f838-120">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="2f838-121">Por exemplo, para as equipes X, Y e Z, o administrador pode definir as políticas de exclusão por 1 ano (selecionando essas equipes individualmente) e aplicar uma política de exclusão de 3 anos para o restante das equipes.</span><span class="sxs-lookup"><span data-stu-id="2f838-121">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="2f838-122">Você pode fazer a mesma coisa por **equipes chats** selecionando usuários específicos e aplicar políticas de retenção exclusivo.</span><span class="sxs-lookup"><span data-stu-id="2f838-122">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="2f838-124">Os locais de mensagem do canal de equipes e os locais de chats de equipes apenas endereços as conversas de equipes armazenadas em caixas de correio Exchange Online (caixas de correio grupo e usuário).</span><span class="sxs-lookup"><span data-stu-id="2f838-124">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="2f838-125">As mensagens são excluídas de todos os locais de armazenamento relevantes, notadamente as caixas de correio, substrate e serviço de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="2f838-125">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="2f838-126">Para gerenciar políticas de retenção para arquivos de equipes, que são armazenados no OneDrive para negócios e do SharePoint, use suas políticas de retenção.</span><span class="sxs-lookup"><span data-stu-id="2f838-126">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="2f838-127">Por design, as políticas de exclusão para arquivos de equipes são configuradas por meio do SharePoint Online e OneDrive para locais de negócios.</span><span class="sxs-lookup"><span data-stu-id="2f838-127">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="2f838-128">Como resultado, é possível que uma política foi possível excluir um arquivo referenciado em uma mensagem de bate-papo ou canal de equipes antes que essas mensagens são excluídas.</span><span class="sxs-lookup"><span data-stu-id="2f838-128">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="2f838-129">Nesse caso, o arquivo ainda serão exibidas na mensagem de equipes, mas se você clicar no arquivo, você receberá um erro "Arquivo não encontrado" (Isso também pode acontecer na ausência de uma política, se alguém manualmente exclui um arquivo do SharePoint Online ou do OneDrive for Business).</span><span class="sxs-lookup"><span data-stu-id="2f838-129">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="2f838-130">Para obter informações detalhadas sobre como configurar as políticas de retenção para o Office 365, leia a [Visão geral das políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="2f838-130">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
