---
title: Disponibilidade do aplicativo Aprovações no Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Saiba mais sobre a disponibilidade do aplicativo Aprovações no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e03ad5c562f7fd31599bbb86f08e411dfa4b415
ms.sourcegitcommit: fb87d64c6f98041a1da50cf4ef6ff54cdc8d1d29
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902565"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="e84cb-103">Disponibilidade dos aplicativos de aprovação do Teams</span><span class="sxs-lookup"><span data-stu-id="e84cb-103">Teams Approvals app availability</span></span>

<span data-ttu-id="e84cb-104">O aplicativo Aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e84cb-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="e84cb-105">O aplicativo Aprovações oferece uma maneira simples de levar auditoria, conformidade, responsabilidade e fluxos de trabalho para Aprovações estruturadas e não estruturadas em Equipes.</span><span class="sxs-lookup"><span data-stu-id="e84cb-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![mostra o aplicativo aprovações](media/approvals-selection.png)

<span data-ttu-id="e84cb-107">Os usuários podem fixar o aplicativo Aprovações para salvá-lo na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="e84cb-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![mostra o aplicativo aprovações com a opção de fixar](media/approvalApp-pin.png)

<span data-ttu-id="e84cb-109">A primeira aprovação criada a partir do aplicativo Aprovações acionará o provisionamento da Solução de Aprovação no ambiente padrão de CDS (Serviço de Dados Comuns).</span><span class="sxs-lookup"><span data-stu-id="e84cb-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="e84cb-110">As aprovações criadas a partir do aplicativo Aprovações serão armazenadas no ambiente de CDS padrão.</span><span class="sxs-lookup"><span data-stu-id="e84cb-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="e84cb-111">Este artigo descreve os requisitos e as funções do aplicativo Aprovações.</span><span class="sxs-lookup"><span data-stu-id="e84cb-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="e84cb-112">Esse recurso ainda não foi lançado para usuários do Government Community Cloud (GCC), Government Community Cloud High (GCCH) e Department of Defense (DOD).</span><span class="sxs-lookup"><span data-stu-id="e84cb-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="e84cb-113">Permissões e licenças necessárias</span><span class="sxs-lookup"><span data-stu-id="e84cb-113">Required permissions and licenses</span></span>

<span data-ttu-id="e84cb-114">Para usar o aplicativo Aprovações, você precisa de permissão para os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="e84cb-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="e84cb-115">Permissões para criar um banco de dados de CDS da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e84cb-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="e84cb-116">Uma conta em [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="e84cb-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="e84cb-117">Função de administrador no ambiente de destino.</span><span class="sxs-lookup"><span data-stu-id="e84cb-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="e84cb-118">Licença para um [Power Automate](/power-automate/get-started-approvals), um Office 365 ou um Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e84cb-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="e84cb-119">Armazenamento com CDS</span><span class="sxs-lookup"><span data-stu-id="e84cb-119">Storage with CDS</span></span>

<span data-ttu-id="e84cb-120">O CDM (Modelo de Dados Comum) é a linguagem de dados compartilhada usada por aplicativos de negócios e analíticos no CDS.</span><span class="sxs-lookup"><span data-stu-id="e84cb-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="e84cb-121">Ele consiste em um conjunto de esquemas de dados padronizados e extensíveis publicados pela Microsoft e por nossos parceiros, que permite a consistência dos dados e seu significado entre aplicativos e processos comerciais.</span><span class="sxs-lookup"><span data-stu-id="e84cb-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners, that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="e84cb-122">Saiba mais sobre o [dados comuns do Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="e84cb-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="e84cb-123">Saiba mais sobre o fluxo [de trabalho aprovação](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="e84cb-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="e84cb-124">Permissões do aplicativo Aprovações do Teams</span><span class="sxs-lookup"><span data-stu-id="e84cb-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="e84cb-125">O aplicativo Aprovações Teams permite que você acesse os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="e84cb-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="e84cb-126">Receba mensagens e dados que você fornece a ela.</span><span class="sxs-lookup"><span data-stu-id="e84cb-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="e84cb-127">Enviar mensagens e notificações.</span><span class="sxs-lookup"><span data-stu-id="e84cb-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="e84cb-128">Renderizar aplicativos pessoais e caixas de diálogo sem um header fornecido pelo Teams.</span><span class="sxs-lookup"><span data-stu-id="e84cb-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="e84cb-129">Acesse suas informações de perfil, como nome, endereço de email, nome da empresa e idioma preferido.</span><span class="sxs-lookup"><span data-stu-id="e84cb-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="e84cb-130">Receba mensagens e dados que os membros da equipe fornecem a ela em um canal.</span><span class="sxs-lookup"><span data-stu-id="e84cb-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="e84cb-131">Enviar mensagens e notificações em um canal.</span><span class="sxs-lookup"><span data-stu-id="e84cb-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="e84cb-132">Acesse as informações da sua equipe:</span><span class="sxs-lookup"><span data-stu-id="e84cb-132">Access your team's information:</span></span>
  - <span data-ttu-id="e84cb-133">nome da equipe</span><span class="sxs-lookup"><span data-stu-id="e84cb-133">team name</span></span>
  - <span data-ttu-id="e84cb-134">lista de canais</span><span class="sxs-lookup"><span data-stu-id="e84cb-134">channel list</span></span>
  - <span data-ttu-id="e84cb-135">lista de lista (nomes e endereços de email dos membros da equipe).</span><span class="sxs-lookup"><span data-stu-id="e84cb-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="e84cb-136">Use as informações da equipe para contatá-los.</span><span class="sxs-lookup"><span data-stu-id="e84cb-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="e84cb-137">Desabilitar o aplicativo Aprovações</span><span class="sxs-lookup"><span data-stu-id="e84cb-137">Disable the Approvals app</span></span>

<span data-ttu-id="e84cb-138">O aplicativo Aprovações está disponível por padrão.</span><span class="sxs-lookup"><span data-stu-id="e84cb-138">The Approvals app is available by default.</span></span> <span data-ttu-id="e84cb-139">Você pode desabilitar o aplicativo no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="e84cb-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="e84cb-140">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="e84cb-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="e84cb-141">Expanda **aplicativos Teams** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="e84cb-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="e84cb-142">Procure o aplicativo Aprovações.</span><span class="sxs-lookup"><span data-stu-id="e84cb-142">Search for the Approvals app.</span></span>

![mostra a navegação do Centro de administração com Aplicativos do Teams > Gerenciar Aplicativos realçada](media/manage-approval-apps.png)

  4. <span data-ttu-id="e84cb-144">Selecione Aprovações.</span><span class="sxs-lookup"><span data-stu-id="e84cb-144">Select Approvals.</span></span>

  5. <span data-ttu-id="e84cb-145">Selecione o alternância para desabilitar o aplicativo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e84cb-145">Select the toggle to disable the app for your organization.</span></span>

![mostra os detalhes do aplicativo Aprovações](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="e84cb-147">Política de retenção</span><span class="sxs-lookup"><span data-stu-id="e84cb-147">Retention policy</span></span>

<span data-ttu-id="e84cb-148">As aprovações criadas a partir do Aplicativo Aprovações são armazenadas no ambiente de CDS padrão, que não dá suporte a backups no momento.</span><span class="sxs-lookup"><span data-stu-id="e84cb-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="e84cb-149">Saiba mais sobre como fazer [backup e restaurar ambientes - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="e84cb-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="e84cb-150">Auditoria</span><span class="sxs-lookup"><span data-stu-id="e84cb-150">Auditing</span></span>

<span data-ttu-id="e84cb-151">O aplicativo Approvals registra eventos de auditoria no Centro de Conformidade e Segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e84cb-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="e84cb-152">Você pode exibir o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="e84cb-152">You can view the audit log.</span></span>

1. <span data-ttu-id="e84cb-153">Vá para o Site de Conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e84cb-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="e84cb-154">Selecione a **seção** Auditoria.</span><span class="sxs-lookup"><span data-stu-id="e84cb-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="e84cb-155">Procure atividades em atividades em **de aprovação do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="e84cb-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="e84cb-156">Você pode procurar as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="e84cb-156">You can search for the following activities:</span></span>

- <span data-ttu-id="e84cb-157">Criar nova solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="e84cb-157">Create new approval request</span></span>

- <span data-ttu-id="e84cb-158">Exibir detalhes da solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="e84cb-158">View approval request details</span></span>

- <span data-ttu-id="e84cb-159">Solicitação de aprovação aprovada</span><span class="sxs-lookup"><span data-stu-id="e84cb-159">Approved approval request</span></span>

- <span data-ttu-id="e84cb-160">Solicitação de aprovação rejeitada</span><span class="sxs-lookup"><span data-stu-id="e84cb-160">Rejected approval request</span></span>

- <span data-ttu-id="e84cb-161">Solicitação de aprovação cancelada</span><span class="sxs-lookup"><span data-stu-id="e84cb-161">Canceled approval request</span></span>

- <span data-ttu-id="e84cb-162">Solicitação de aprovação compartilhada</span><span class="sxs-lookup"><span data-stu-id="e84cb-162">Shared approval request</span></span>

- <span data-ttu-id="e84cb-163">Arquivo anexado à solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="e84cb-163">File attached to approval request</span></span>

- <span data-ttu-id="e84cb-164">Solicitação de aprovação reatribuida</span><span class="sxs-lookup"><span data-stu-id="e84cb-164">Reassigned approval request</span></span>

- <span data-ttu-id="e84cb-165">Assinatura eletrônica adicionada à solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="e84cb-165">Added e-signature to approval request</span></span>

<span data-ttu-id="e84cb-166">Para obter acesso a mais aprovações de auditoria no Flow, habilita e configure a auditoria no ambiente padrão para as entidades de aprovação principais Aprovação, Solicitação de Aprovação e Resposta de Aprovação.</span><span class="sxs-lookup"><span data-stu-id="e84cb-166">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="e84cb-167">Operações de criação, atualização e exclusão são eventos auditáveis para registros de Aprovação.</span><span class="sxs-lookup"><span data-stu-id="e84cb-167">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="e84cb-168">Saiba mais sobre [dados de Auditoria e atividade do usuário para segurança e conformidade - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="e84cb-168">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="e84cb-169">A auditoria pode ser personalizada ainda mais no [de Conformidade e Segurança do Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="e84cb-169">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="e84cb-170">Para usar os relatórios pré-configurados, entre em Segurança e Conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e84cb-170">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="e84cb-171">Selecione **pesquisa e investigação**.</span><span class="sxs-lookup"><span data-stu-id="e84cb-171">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="e84cb-172">Pesquise no log de Auditoria e selecione **atividades do Dynamics 365** dados.</span><span class="sxs-lookup"><span data-stu-id="e84cb-172">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="e84cb-173">Saiba mais sobre [registro em log de atividades de aplicativos orientados por modelos e dados de aplicativos do Microsoft Dataverse - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="e84cb-173">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="e84cb-174">Segurança</span><span class="sxs-lookup"><span data-stu-id="e84cb-174">Security</span></span>

<span data-ttu-id="e84cb-175">No aplicativo Aprovações de Equipes, os usuários têm acesso para criar novas Aprovações e exibir Aprovações que enviaram e receberam.</span><span class="sxs-lookup"><span data-stu-id="e84cb-175">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="e84cb-176">Os usuários não terão acesso às Aprovações criadas por outras pessoas, a menos que sejam respondentes ou visualizadores da solicitação.</span><span class="sxs-lookup"><span data-stu-id="e84cb-176">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="e84cb-177">Um usuário terá uma função de visualizador de uma solicitação se ele for parte do chat ou canal no qual a aprovação foi criada.</span><span class="sxs-lookup"><span data-stu-id="e84cb-177">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="e84cb-178">Ela não terá a capacidade de tomar medidas na solicitação caso não tenha sido concedida essa função quando a aprovação foi criada.</span><span class="sxs-lookup"><span data-stu-id="e84cb-178">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>