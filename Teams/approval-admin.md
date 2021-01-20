---
title: Aprovações na disponibilidade de aplicativos no Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Saiba mais sobre a disponibilidade de aplicativos de aprovação no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909515"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="19109-103">Aprovação do aplicativo aprovações de equipe</span><span class="sxs-lookup"><span data-stu-id="19109-103">Teams Approvals app availability</span></span>

<span data-ttu-id="19109-104">O aplicativo aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="19109-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="19109-105">O aplicativo aprovações fornece uma maneira simples de trazer auditoria, conformidade, responsabilidade e fluxos de trabalho para aprovações estruturadas e não estruturadas no Teams.</span><span class="sxs-lookup"><span data-stu-id="19109-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![mostra o aplicativo aprovações](media/approvals-selection.png)

<span data-ttu-id="19109-107">Os usuários podem fixar o aplicativo aprovações para salvá-lo na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="19109-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![mostra o aplicativo aprovações com a opção PIN](media/approvalApp-pin.png)

<span data-ttu-id="19109-109">A primeira aprovação criada a partir do aplicativo aprovações irá disparar o provisionamento da solução de aprovação no ambiente padrão de serviços de dados comuns (CDS).</span><span class="sxs-lookup"><span data-stu-id="19109-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="19109-110">As aprovações criadas do aplicativo aprovações serão armazenadas no ambiente de CDS padrão.</span><span class="sxs-lookup"><span data-stu-id="19109-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="19109-111">Este artigo descreve os requisitos e funções do aplicativo aprovações.</span><span class="sxs-lookup"><span data-stu-id="19109-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="19109-112">Permissões e licenças necessárias</span><span class="sxs-lookup"><span data-stu-id="19109-112">Required permissions and licenses</span></span>

<span data-ttu-id="19109-113">Para usar o aplicativo aprovações, você precisa de permissão para os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="19109-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="19109-114">Permissões para criar um banco de dados do Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="19109-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="19109-115">Uma conta no [Flow.Microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="19109-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="19109-116">Função de administrador no ambiente de destino.</span><span class="sxs-lookup"><span data-stu-id="19109-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="19109-117">Licença para [automatização de energia](https://docs.microsoft.com/power-automate/get-started-approvals), um Office 365 ou um Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="19109-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="19109-118">Armazenamento com CDS</span><span class="sxs-lookup"><span data-stu-id="19109-118">Storage with CDS</span></span>

<span data-ttu-id="19109-119">O modelo de dados comuns (MDL) é o idioma de dados compartilhados usados por aplicativos analíticos e comerciais nos CDS.</span><span class="sxs-lookup"><span data-stu-id="19109-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="19109-120">Ele consiste em um conjunto de esquemas de dados extensíveis e padronizados publicados pela Microsoft e por nossos parceiros que permitem a consistência de dados e seu significado entre aplicativos e processos de negócios.</span><span class="sxs-lookup"><span data-stu-id="19109-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="19109-121">Saiba mais sobre o [modelo de dados comum da plataforma de alimentação da Microsoft](https://docs.microsoft.com/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="19109-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="19109-122">Saiba mais sobre o [fluxo de trabalho de aprovação](https://docs.microsoft.com/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="19109-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="19109-123">Permissões do aplicativo equipes de aprovações</span><span class="sxs-lookup"><span data-stu-id="19109-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="19109-124">O aplicativo de equipes de aprovação permite que você acesse os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="19109-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="19109-125">Receba mensagens e dados fornecidos a ele.</span><span class="sxs-lookup"><span data-stu-id="19109-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="19109-126">Envie mensagens e notificações para você.</span><span class="sxs-lookup"><span data-stu-id="19109-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="19109-127">Renderizar aplicativos pessoais e caixas de diálogo sem um cabeçalho fornecido pelo Teams.</span><span class="sxs-lookup"><span data-stu-id="19109-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="19109-128">Acesse suas informações de perfil, como seu nome, endereço de e-mail, nome da empresa e idioma preferencial.</span><span class="sxs-lookup"><span data-stu-id="19109-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="19109-129">Receber mensagens e dados que os membros da equipe fornecem a ele em um canal.</span><span class="sxs-lookup"><span data-stu-id="19109-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="19109-130">Envie mensagens e notificações em um canal.</span><span class="sxs-lookup"><span data-stu-id="19109-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="19109-131">Acesse as informações da sua equipe:</span><span class="sxs-lookup"><span data-stu-id="19109-131">Access your team's information:</span></span>
  - <span data-ttu-id="19109-132">nome da equipe</span><span class="sxs-lookup"><span data-stu-id="19109-132">team name</span></span>
  - <span data-ttu-id="19109-133">lista de canais</span><span class="sxs-lookup"><span data-stu-id="19109-133">channel list</span></span>
  - <span data-ttu-id="19109-134">lista (nomes e endereços de email dos membros da equipe).</span><span class="sxs-lookup"><span data-stu-id="19109-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="19109-135">Use as informações da equipe para contatá-los.</span><span class="sxs-lookup"><span data-stu-id="19109-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="19109-136">Desabilitar o aplicativo aprovações</span><span class="sxs-lookup"><span data-stu-id="19109-136">Disable the Approvals app</span></span>

<span data-ttu-id="19109-137">O aplicativo aprovações está disponível por padrão.</span><span class="sxs-lookup"><span data-stu-id="19109-137">The Approvals app is available by default.</span></span> <span data-ttu-id="19109-138">Você pode desabilitar o aplicativo no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="19109-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="19109-139">Entre no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="19109-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="19109-140">Expanda **aplicativos do teams** e selecione **gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="19109-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="19109-141">Procure o aplicativo aprovações.</span><span class="sxs-lookup"><span data-stu-id="19109-141">Search for the Approvals app.</span></span>

![mostra a navegação do centro de administração com aplicativos do teams > gerenciar aplicativos realçados](media/manage-approval-apps.png)

  4. <span data-ttu-id="19109-143">Selecione aprovações.</span><span class="sxs-lookup"><span data-stu-id="19109-143">Select Approvals.</span></span>

  5. <span data-ttu-id="19109-144">Selecione o botão de alternância para desabilitar o aplicativo para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="19109-144">Select the toggle to disable the app for your organization.</span></span>

![mostra os detalhes do aplicativo aprovações](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="19109-146">Política de retenção</span><span class="sxs-lookup"><span data-stu-id="19109-146">Retention policy</span></span>

<span data-ttu-id="19109-147">As aprovações criadas do aplicativo aprovações são armazenadas no ambiente de CDS padrão, que não dá suporte a backups no momento.</span><span class="sxs-lookup"><span data-stu-id="19109-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="19109-148">Saiba mais sobre como [fazer backup e restaurar ambientes- \| documentos da Microsoft para plataforma de energia](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="19109-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="19109-149">Auditoria</span><span class="sxs-lookup"><span data-stu-id="19109-149">Auditing</span></span>

<span data-ttu-id="19109-150">O aplicativo aprovações registra eventos de auditoria no centro de conformidade e segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19109-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="19109-151">Você pode exibir o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="19109-151">You can view the audit log.</span></span>

1. <span data-ttu-id="19109-152">Vá para o site de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19109-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="19109-153">Selecione a seção **auditoria** .</span><span class="sxs-lookup"><span data-stu-id="19109-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="19109-154">Procure atividades em **atividades de aprovação do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="19109-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="19109-155">Você pode pesquisar as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="19109-155">You can search for the following activities:</span></span>

- <span data-ttu-id="19109-156">Criar nova solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="19109-156">Create new approval request</span></span>

- <span data-ttu-id="19109-157">Exibir detalhes da solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="19109-157">View approval request details</span></span>

- <span data-ttu-id="19109-158">Solicitação de aprovação aprovada</span><span class="sxs-lookup"><span data-stu-id="19109-158">Approved approval request</span></span>

- <span data-ttu-id="19109-159">Solicitação de aprovação rejeitada</span><span class="sxs-lookup"><span data-stu-id="19109-159">Rejected approval request</span></span>

- <span data-ttu-id="19109-160">Solicitação de aprovação cancelada</span><span class="sxs-lookup"><span data-stu-id="19109-160">Canceled approval request</span></span>

- <span data-ttu-id="19109-161">Solicitação de aprovação compartilhada</span><span class="sxs-lookup"><span data-stu-id="19109-161">Shared approval request</span></span>

- <span data-ttu-id="19109-162">Arquivo anexado à solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="19109-162">File attached to approval request</span></span>

- <span data-ttu-id="19109-163">Solicitação de aprovação reatribuída</span><span class="sxs-lookup"><span data-stu-id="19109-163">Reassigned approval request</span></span>

- <span data-ttu-id="19109-164">Assinatura e-assinatura para solicitação de aprovação adicionada</span><span class="sxs-lookup"><span data-stu-id="19109-164">Added e-signature to approval request</span></span>

<span data-ttu-id="19109-165">Para ter acesso a mais aprovações de auditoria dentro do fluxo, habilite e configure a auditoria no ambiente padrão para a aprovação de entidades de aprovação primária, solicitação de aprovação e resposta de aprovação.</span><span class="sxs-lookup"><span data-stu-id="19109-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="19109-166">As operações criar, atualizar e excluir são eventos auditáveis para registros de aprovação.</span><span class="sxs-lookup"><span data-stu-id="19109-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="19109-167">Saiba mais sobre [a auditoria de dados e atividades do usuário para segurança e conformidade- \| Microsoft docs para plataforma de energia](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="19109-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="19109-168">A auditoria pode ser personalizada ainda mais no [centro de conformidade e segurança do Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="19109-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="19109-169">Para usar os relatórios pré-configurados, entre em segurança e conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19109-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="19109-170">Selecione **pesquisar & investigação**.</span><span class="sxs-lookup"><span data-stu-id="19109-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="19109-171">Pesquisar no log de auditoria e selecionar a guia **atividades do Dynamics 365** .</span><span class="sxs-lookup"><span data-stu-id="19109-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="19109-172">Saiba mais sobre [o Microsoft dataverso e os aplicativos controlados por modelo-plataforma de energia](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="19109-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="19109-173">Segurança</span><span class="sxs-lookup"><span data-stu-id="19109-173">Security</span></span>

<span data-ttu-id="19109-174">No aplicativo aprovações do Teams, os usuários têm acesso para criar novas aprovações e exibir aprovações que enviaram e receberam.</span><span class="sxs-lookup"><span data-stu-id="19109-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="19109-175">Os usuários não terão acesso às aprovações criadas por outras pessoas, a menos que elas sejam um Respondente ou um visualizador da solicitação.</span><span class="sxs-lookup"><span data-stu-id="19109-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="19109-176">Um usuário receberá uma função de visualizador de uma solicitação se eles fizerem parte do chat ou do canal em que a aprovação foi criada.</span><span class="sxs-lookup"><span data-stu-id="19109-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="19109-177">Elas não terão a capacidade de atuar na solicitação se não estivessem dadas essa função quando a aprovação foi criada.</span><span class="sxs-lookup"><span data-stu-id="19109-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
