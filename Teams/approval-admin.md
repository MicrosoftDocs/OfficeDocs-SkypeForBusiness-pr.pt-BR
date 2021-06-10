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
ms.openlocfilehash: 127fc2831e58e7ddea152c7754015a9126390ecc
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212164"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="35caf-103">Disponibilidade dos aplicativos de aprovação do Teams</span><span class="sxs-lookup"><span data-stu-id="35caf-103">Teams Approvals app availability</span></span>

<span data-ttu-id="35caf-104">O aplicativo Aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35caf-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="35caf-105">O aplicativo Aprovações oferece uma maneira simples de levar auditoria, conformidade, responsabilidade e fluxos de trabalho para Aprovações estruturadas e não estruturadas em Equipes.</span><span class="sxs-lookup"><span data-stu-id="35caf-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![mostra o aplicativo aprovações](media/approvals-selection.png)

<span data-ttu-id="35caf-107">Os usuários podem fixar o aplicativo Aprovações para salvá-lo na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="35caf-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![mostra o aplicativo aprovações com a opção de fixar](media/approvalApp-pin.png)

<span data-ttu-id="35caf-109">A primeira aprovação criada a partir do aplicativo Aprovações acionará o provisionamento da Solução de Aprovação no ambiente padrão de CDS (Serviço de Dados Comuns).</span><span class="sxs-lookup"><span data-stu-id="35caf-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="35caf-110">As aprovações criadas a partir do aplicativo Aprovações serão armazenadas no ambiente de CDS padrão.</span><span class="sxs-lookup"><span data-stu-id="35caf-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="35caf-111">Este artigo descreve os requisitos e as funções do aplicativo Aprovações.</span><span class="sxs-lookup"><span data-stu-id="35caf-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="35caf-112">Esse recurso ainda não foi lançado para usuários Nuvem da Comunidade Governamental (GCC), Nuvem da Comunidade Governamental High (GCCH) e Departamento de Defesa (DOD).</span><span class="sxs-lookup"><span data-stu-id="35caf-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="35caf-113">Permissões e licenças necessárias</span><span class="sxs-lookup"><span data-stu-id="35caf-113">Required permissions and licenses</span></span>

<span data-ttu-id="35caf-114">Para usar o aplicativo Aprovações, você precisa de permissão para os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="35caf-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="35caf-115">Permissões para criar um banco de dados de CDS da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35caf-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="35caf-116">Uma conta em [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="35caf-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="35caf-117">Função de administrador no ambiente de destino.</span><span class="sxs-lookup"><span data-stu-id="35caf-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="35caf-118">Licença para um [Power Automate](/power-automate/get-started-approvals), um Office 365 ou um Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="35caf-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

- <span data-ttu-id="35caf-119">A licença do Microsoft Forms é necessária para os usuários configurarem novos modelos de aprovação.</span><span class="sxs-lookup"><span data-stu-id="35caf-119">License for Microsoft Forms is required for users to set up new approval templates.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="35caf-120">Armazenamento com CDS</span><span class="sxs-lookup"><span data-stu-id="35caf-120">Storage with CDS</span></span>

<span data-ttu-id="35caf-121">O CDM (Modelo de Dados Comum) é a linguagem de dados compartilhada usada por aplicativos de negócios e analíticos no CDS.</span><span class="sxs-lookup"><span data-stu-id="35caf-121">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="35caf-122">Ele consiste em um conjunto de esquemas de dados extensíveis padronizados publicados pela Microsoft e por nossos parceiros que permitem a consistência dos dados e seu significado em aplicativos e processos empresariais.</span><span class="sxs-lookup"><span data-stu-id="35caf-122">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="35caf-123">Saiba mais sobre o [dados comuns do Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="35caf-123">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="35caf-124">Saiba mais sobre o fluxo [de trabalho aprovação](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="35caf-124">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

<span data-ttu-id="35caf-125">As aprovações criadas a partir de um modelo ainda armazenam dados em CDS, como título, detalhes, ID do modelo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="35caf-125">Approvals that are created from a template still store data in CDS, such as their title, details, template ID, and more.</span></span> <span data-ttu-id="35caf-126">As respostas enviadas na solicitação de aprovação são armazenadas em Formulários.</span><span class="sxs-lookup"><span data-stu-id="35caf-126">Responses that are submitted on the approval request are stored in Forms.</span></span> <span data-ttu-id="35caf-127">Saiba mais sobre  [o armazenamento de dados do Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span><span class="sxs-lookup"><span data-stu-id="35caf-127">Learn more about  [Data storage for Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span></span>

>[!Note]
><span data-ttu-id="35caf-128">Se você excluir o modelo de formulário no site do Microsoft Forms, ele quebrará seu modelo de Aprovação e os usuários não poderão iniciar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="35caf-128">If you delete the Form template on the Microsoft Forms site, it will break your Approval template and users will not be able to start the request.</span></span> <span data-ttu-id="35caf-129">Os usuários receberão um erro "CDB TableNotFound" ao tentar abrir um modelo de Aprovação que foi excluído no Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="35caf-129">Users will get an error "CDB TableNotFound" when trying to open an Approval template that has been deleted on Microsoft Forms.</span></span>

<span data-ttu-id="35caf-130">Os modelos de aprovação são armazenados no Substrate Data Armazenamento (SDS), que é uma plataforma de armazenamento compatível usada internamente apenas dentro da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35caf-130">The approval templates are stored in Substrate Data Storage (SDS), which is a compliant storage platform used internally only inside Microsoft.</span></span> <span data-ttu-id="35caf-131">Os modelos de escopo da organização são armazenados em "fragmento de locatário" do SDS, e os modelos com escopo de equipe são armazenados em "fragmentos de grupo" do SDS.</span><span class="sxs-lookup"><span data-stu-id="35caf-131">The organization-scoped templates are stored in “tenant shard” of SDS, and team-scoped templates are stored in “group shards” of SDS.</span></span> <span data-ttu-id="35caf-132">Isso significa que os modelos com escopo organizacional compartilham o mesmo tempo de vida dos modelos de locatário e de equipe compartilham o mesmo tempo de vida da equipe.</span><span class="sxs-lookup"><span data-stu-id="35caf-132">This means that the org-scoped templates share the same lifetime of the tenant and team-scoped templates share the same lifetime of the team.</span></span> <span data-ttu-id="35caf-133">Portanto, excluir permanentemente a equipe exclui os modelos relacionados.</span><span class="sxs-lookup"><span data-stu-id="35caf-133">So, permanently deleting the team deletes the related templates.</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="35caf-134">Permissões do aplicativo Aprovações do Teams</span><span class="sxs-lookup"><span data-stu-id="35caf-134">Approvals Teams app permissions</span></span>

<span data-ttu-id="35caf-135">O aplicativo Aprovações Teams permite que você acesse os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="35caf-135">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="35caf-136">Receba mensagens e dados que você fornece a ela.</span><span class="sxs-lookup"><span data-stu-id="35caf-136">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="35caf-137">Enviar mensagens e notificações.</span><span class="sxs-lookup"><span data-stu-id="35caf-137">Send you messages and notifications.</span></span>

- <span data-ttu-id="35caf-138">Renderizar aplicativos pessoais e caixas de diálogo sem um header fornecido pelo Teams.</span><span class="sxs-lookup"><span data-stu-id="35caf-138">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="35caf-139">Acesse suas informações de perfil, como nome, endereço de email, nome da empresa e idioma preferido.</span><span class="sxs-lookup"><span data-stu-id="35caf-139">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="35caf-140">Receba mensagens e dados que os membros da equipe fornecem a ela em um canal.</span><span class="sxs-lookup"><span data-stu-id="35caf-140">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="35caf-141">Enviar mensagens e notificações em um canal.</span><span class="sxs-lookup"><span data-stu-id="35caf-141">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="35caf-142">Acesse as informações da sua equipe:</span><span class="sxs-lookup"><span data-stu-id="35caf-142">Access your team's information:</span></span>
  - <span data-ttu-id="35caf-143">nome da equipe</span><span class="sxs-lookup"><span data-stu-id="35caf-143">team name</span></span>
  - <span data-ttu-id="35caf-144">lista de canais</span><span class="sxs-lookup"><span data-stu-id="35caf-144">channel list</span></span>
  - <span data-ttu-id="35caf-145">lista de lista (nomes e endereços de email dos membros da equipe).</span><span class="sxs-lookup"><span data-stu-id="35caf-145">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="35caf-146">Use as informações da equipe para contatá-los.</span><span class="sxs-lookup"><span data-stu-id="35caf-146">Use the team's information to contact them.</span></span>

<span data-ttu-id="35caf-147">Permissões do modelo de aprovação</span><span class="sxs-lookup"><span data-stu-id="35caf-147">Approval Template Permissions</span></span>

- <span data-ttu-id="35caf-148">Todos os proprietários de equipe podem criar um modelo de aprovação para equipes que eles próprios têm.</span><span class="sxs-lookup"><span data-stu-id="35caf-148">All team owners can create an approval template for teams that they own.</span></span>

- <span data-ttu-id="35caf-149">Quando um Administrador cria um modelo para toda a organização pela primeira vez, ele criará automaticamente uma nova equipe de Teams para todos os administradores do locatário, incluindo os administradores de serviço globais e de equipe.</span><span class="sxs-lookup"><span data-stu-id="35caf-149">When an Admin creates a template for their entire organization for the first time, it will automatically create a new Teams team for all admins of the tenant, including the global and Team’s service admins.</span></span> <span data-ttu-id="35caf-150">Esses administradores serão adicionados como proprietários da equipe, para que possam co-gerenciar modelos organizacionais.</span><span class="sxs-lookup"><span data-stu-id="35caf-150">These admins will be added as owners of the team, so they can co-manage organizational templates.</span></span> <span data-ttu-id="35caf-151">Os administradores novos na organização após a criação da equipe precisam ser adicionados manualmente como proprietários de equipe para que tenham as mesmas permissões para gerenciar modelos de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="35caf-151">Admins that are new to the organization after the team has been created need to be manually added as team owners so they have the same permissions to manage organization-wide templates.</span></span>

> [!Note]
> <span data-ttu-id="35caf-152">Se um administrador excluir a equipe, você terá um mês para restaurá-la no portal Azure Active Directory (AAD) para restaurar todos os dados relacionados.</span><span class="sxs-lookup"><span data-stu-id="35caf-152">If an admin deletes the team, you have one month to restore it within the Azure Active Directory (AAD) portal to restore all related data.</span></span> <span data-ttu-id="35caf-153">Após um mês ou se o administrador excluir essa equipe dentro da lixeira, você perderá todos os dados relacionados.</span><span class="sxs-lookup"><span data-stu-id="35caf-153">After one month, or if the admin deletes this team within the recycle bin, you will lose all the related data.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="35caf-154">Desabilitar o aplicativo Aprovações</span><span class="sxs-lookup"><span data-stu-id="35caf-154">Disable the Approvals app</span></span>

<span data-ttu-id="35caf-155">O aplicativo Aprovações está disponível por padrão.</span><span class="sxs-lookup"><span data-stu-id="35caf-155">The Approvals app is available by default.</span></span> <span data-ttu-id="35caf-156">Você pode desabilitar o aplicativo no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="35caf-156">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="35caf-157">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="35caf-157">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="35caf-158">Expanda **aplicativos Teams** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="35caf-158">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="35caf-159">Procure o aplicativo Aprovações.</span><span class="sxs-lookup"><span data-stu-id="35caf-159">Search for the Approvals app.</span></span>

     ![mostra a navegação do Centro de administração com Aplicativos do Teams > Gerenciar Aplicativos realçada](media/manage-approval-apps.png)

  4. <span data-ttu-id="35caf-161">Selecione Aprovações.</span><span class="sxs-lookup"><span data-stu-id="35caf-161">Select Approvals.</span></span>

  5. <span data-ttu-id="35caf-162">Selecione o alternância para desabilitar o aplicativo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="35caf-162">Select the toggle to disable the app for your organization.</span></span>

     ![mostra os detalhes do aplicativo Aprovações](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="35caf-164">Política de retenção</span><span class="sxs-lookup"><span data-stu-id="35caf-164">Retention policy</span></span>

<span data-ttu-id="35caf-165">As aprovações criadas a partir do Aplicativo Aprovações são armazenadas no ambiente de CDS padrão, que não dá suporte a backups no momento.</span><span class="sxs-lookup"><span data-stu-id="35caf-165">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="35caf-166">Saiba mais sobre como fazer [backup e restaurar ambientes - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="35caf-166">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

<span data-ttu-id="35caf-167">Os dados armazenados no Forms não serão excluídos até que os proprietários da equipe os limpem da guia **formulários** excluídos no aplicativo Web do Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="35caf-167">Data stored in Forms will not be deleted until the team owners clean it up from the **deleted forms** tab in the Microsoft Forms web app.</span></span>

## <a name="data-limitations"></a><span data-ttu-id="35caf-168">Limitações de dados</span><span class="sxs-lookup"><span data-stu-id="35caf-168">Data limitations</span></span>

<span data-ttu-id="35caf-169">Cada equipe pode conter no máximo 400 modelos de aprovações, e cada modelo pode coletar no máximo 50.000 solicitações com base na funcionalidade atual no Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="35caf-169">Each team can contain at most 400 approvals templates, and each template can collect a maximum of 50,000 requests based on the current capability in Microsoft Forms.</span></span>

## <a name="auditing"></a><span data-ttu-id="35caf-170">Auditoria</span><span class="sxs-lookup"><span data-stu-id="35caf-170">Auditing</span></span>

<span data-ttu-id="35caf-171">O aplicativo Approvals registra eventos de auditoria no Centro de Conformidade e Segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35caf-171">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="35caf-172">Você pode exibir o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="35caf-172">You can view the audit log.</span></span>

1. <span data-ttu-id="35caf-173">Vá para o Site de Conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35caf-173">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="35caf-174">Selecione a **seção** Auditoria.</span><span class="sxs-lookup"><span data-stu-id="35caf-174">Select the **Audit** section.</span></span>

3. <span data-ttu-id="35caf-175">Procure atividades em atividades em **de aprovação do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="35caf-175">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="35caf-176">Você pode procurar as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="35caf-176">You can search for the following activities:</span></span>

- <span data-ttu-id="35caf-177">Criar nova solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="35caf-177">Create new approval request</span></span>

- <span data-ttu-id="35caf-178">Exibir detalhes da solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="35caf-178">View approval request details</span></span>

- <span data-ttu-id="35caf-179">Solicitação de aprovação aprovada</span><span class="sxs-lookup"><span data-stu-id="35caf-179">Approved approval request</span></span>

- <span data-ttu-id="35caf-180">Solicitação de aprovação rejeitada</span><span class="sxs-lookup"><span data-stu-id="35caf-180">Rejected approval request</span></span>

- <span data-ttu-id="35caf-181">Solicitação de aprovação cancelada</span><span class="sxs-lookup"><span data-stu-id="35caf-181">Canceled approval request</span></span>

- <span data-ttu-id="35caf-182">Solicitação de aprovação compartilhada</span><span class="sxs-lookup"><span data-stu-id="35caf-182">Shared approval request</span></span>

- <span data-ttu-id="35caf-183">Arquivo anexado à solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="35caf-183">File attached to approval request</span></span>

- <span data-ttu-id="35caf-184">Solicitação de aprovação reatribuida</span><span class="sxs-lookup"><span data-stu-id="35caf-184">Reassigned approval request</span></span>

- <span data-ttu-id="35caf-185">Assinatura eletrônica adicionada à solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="35caf-185">Added e-signature to approval request</span></span>

- <span data-ttu-id="35caf-186">Detalhes da solicitação de assinatura eletrônica exibida</span><span class="sxs-lookup"><span data-stu-id="35caf-186">Viewed e-signature request details</span></span>

- <span data-ttu-id="35caf-187">Solicitação de assinatura eletrônica revisada</span><span class="sxs-lookup"><span data-stu-id="35caf-187">Reviewed e-signature request</span></span>

- <span data-ttu-id="35caf-188">Solicitação de assinatura eletrônica cancelada</span><span class="sxs-lookup"><span data-stu-id="35caf-188">Canceled e-signature request</span></span>

- <span data-ttu-id="35caf-189">Criar um novo modelo</span><span class="sxs-lookup"><span data-stu-id="35caf-189">Create a new template</span></span>

- <span data-ttu-id="35caf-190">Editar um modelo existente</span><span class="sxs-lookup"><span data-stu-id="35caf-190">Edit an existing template</span></span>

- <span data-ttu-id="35caf-191">Habilitar/desabilitar um modelo</span><span class="sxs-lookup"><span data-stu-id="35caf-191">Enable/disable a template</span></span>

- <span data-ttu-id="35caf-192">Modelo exibido</span><span class="sxs-lookup"><span data-stu-id="35caf-192">Viewed template</span></span>

<span data-ttu-id="35caf-193">Para obter acesso a mais aprovações de auditoria no Flow, habilita e configure a auditoria no ambiente padrão para as entidades de aprovação principais Aprovação, Solicitação de Aprovação e Resposta de Aprovação.</span><span class="sxs-lookup"><span data-stu-id="35caf-193">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="35caf-194">Operações de criação, atualização e exclusão são eventos auditáveis para registros de Aprovação.</span><span class="sxs-lookup"><span data-stu-id="35caf-194">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="35caf-195">Saiba mais sobre [dados de Auditoria e atividade do usuário para segurança e conformidade - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="35caf-195">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="35caf-196">A auditoria pode ser personalizada ainda mais no [de Conformidade e Segurança do Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="35caf-196">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="35caf-197">Para usar os relatórios pré-configurados, entre em Segurança e Conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35caf-197">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="35caf-198">Selecione **pesquisa e investigação**.</span><span class="sxs-lookup"><span data-stu-id="35caf-198">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="35caf-199">Pesquise no log de Auditoria e selecione **atividades do Dynamics 365** dados.</span><span class="sxs-lookup"><span data-stu-id="35caf-199">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="35caf-200">Saiba mais sobre [registro em log de atividades de aplicativos orientados por modelos e dados de aplicativos do Microsoft Dataverse - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="35caf-200">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="35caf-201">Segurança</span><span class="sxs-lookup"><span data-stu-id="35caf-201">Security</span></span>

<span data-ttu-id="35caf-202">No aplicativo Aprovações de Equipes, os usuários têm acesso para criar novas Aprovações e exibir Aprovações que enviaram e receberam.</span><span class="sxs-lookup"><span data-stu-id="35caf-202">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="35caf-203">Os usuários não terão acesso às Aprovações criadas por outras pessoas, a menos que sejam respondentes ou visualizadores da solicitação.</span><span class="sxs-lookup"><span data-stu-id="35caf-203">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="35caf-204">Um usuário terá uma função de visualizador de uma solicitação se ele for parte do chat ou canal no qual a aprovação foi criada.</span><span class="sxs-lookup"><span data-stu-id="35caf-204">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="35caf-205">Ela não terá a capacidade de tomar medidas na solicitação caso não tenha sido concedida essa função quando a aprovação foi criada.</span><span class="sxs-lookup"><span data-stu-id="35caf-205">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="35caf-206">Aprova a integração de assinatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="35caf-206">Approvals e-signature integration</span></span>

<span data-ttu-id="35caf-207">As aprovações de assinatura eletrônica criadas a partir do aplicativo Aprovações são armazenadas no ambiente de nuvem do provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="35caf-207">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="35caf-208">Para obter mais informações sobre o armazenamento em torno do contrato de assinatura eletrônica, consulte a documentação de armazenamento do provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="35caf-208">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="35caf-209">Para usar o recurso de assinatura eletrônica do aplicativo Aprovações, você precisa dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="35caf-209">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="35caf-210">Licença para o provedor de assinatura eletrônica específico que você está escolhendo usar.</span><span class="sxs-lookup"><span data-stu-id="35caf-210">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="35caf-211">Para obter uma licença para sua organização, você precisará acessar o site do provedor.</span><span class="sxs-lookup"><span data-stu-id="35caf-211">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="35caf-212">Para a funcionalidade de assinatura eletrônica Aprovações, parceiros de assinatura de terceiros aparecerão no aplicativo Teams Aprovações por padrão.</span><span class="sxs-lookup"><span data-stu-id="35caf-212">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="35caf-213">Você pode desabilitar provedores de assinatura eletrônica específicos acessando as configurações do aplicativo no Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="35caf-213">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="35caf-214">No centro Teams de administração, em Gerenciar **aplicativos,** selecione o aplicativo Aprovações e escolha **Configurações**. </span><span class="sxs-lookup"><span data-stu-id="35caf-214">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="35caf-215">Cada provedor de assinatura eletrônica tem uma alternância ao lado dele que está na posição on (à direita) por padrão.</span><span class="sxs-lookup"><span data-stu-id="35caf-215">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="35caf-216">Deslize a alternância para a esquerda para desabilitar um provedor de assinatura eletrônica específico.</span><span class="sxs-lookup"><span data-stu-id="35caf-216">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="35caf-217">Se um administrador Teams desabilitar um provedor, os usuários finais não verão o provedor ao criar uma aprovação.</span><span class="sxs-lookup"><span data-stu-id="35caf-217">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="35caf-218">Os usuários finais também não poderão exibir quaisquer solicitações de assinatura eletrônica que foram feitas com esse provedor.</span><span class="sxs-lookup"><span data-stu-id="35caf-218">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="35caf-219">Aprovações de assinatura eletrônica criadas a partir do Aplicativo de Aprovações são armazenadas na nuvem do provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="35caf-219">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="35caf-220">Portanto, você precisará acessar o site do provedor para exportar quaisquer dados sobre assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="35caf-220">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="35caf-221">Consulte a documentação do provedor sobre exportação e retenção desses contratos.</span><span class="sxs-lookup"><span data-stu-id="35caf-221">Refer to the provider's documentation about export and retention of these agreements.</span></span>
