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
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129790"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="398ab-103">Disponibilidade dos aplicativos de aprovação do Teams</span><span class="sxs-lookup"><span data-stu-id="398ab-103">Teams Approvals app availability</span></span>

<span data-ttu-id="398ab-104">O aplicativo Aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="398ab-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="398ab-105">O aplicativo Aprovações oferece uma maneira simples de levar auditoria, conformidade, responsabilidade e fluxos de trabalho para Aprovações estruturadas e não estruturadas em Equipes.</span><span class="sxs-lookup"><span data-stu-id="398ab-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![mostra o aplicativo aprovações](media/approvals-selection.png)

<span data-ttu-id="398ab-107">Os usuários podem fixar o aplicativo Aprovações para salvá-lo na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="398ab-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![mostra o aplicativo aprovações com a opção de fixar](media/approvalApp-pin.png)

<span data-ttu-id="398ab-109">A primeira aprovação criada a partir do aplicativo Aprovações acionará o provisionamento da Solução de Aprovação no ambiente padrão de CDS (Serviço de Dados Comuns).</span><span class="sxs-lookup"><span data-stu-id="398ab-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="398ab-110">As aprovações criadas a partir do aplicativo Aprovações serão armazenadas no ambiente de CDS padrão.</span><span class="sxs-lookup"><span data-stu-id="398ab-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="398ab-111">Este artigo descreve os requisitos e as funções do aplicativo Aprovações.</span><span class="sxs-lookup"><span data-stu-id="398ab-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="398ab-112">Esse recurso ainda não foi lançado para usuários Nuvem da Comunidade Governamental (GCC), Nuvem da Comunidade Governamental High (GCCH) e Departamento de Defesa (DOD).</span><span class="sxs-lookup"><span data-stu-id="398ab-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="398ab-113">Permissões e licenças necessárias</span><span class="sxs-lookup"><span data-stu-id="398ab-113">Required permissions and licenses</span></span>

<span data-ttu-id="398ab-114">Para usar o aplicativo Aprovações, você precisa de permissão para os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="398ab-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="398ab-115">Permissões para criar um banco de dados de CDS da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="398ab-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="398ab-116">Uma conta em [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="398ab-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="398ab-117">Função de administrador no ambiente de destino.</span><span class="sxs-lookup"><span data-stu-id="398ab-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="398ab-118">Licença para um [Power Automate](/power-automate/get-started-approvals), um Office 365 ou um Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="398ab-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="398ab-119">Armazenamento com CDS</span><span class="sxs-lookup"><span data-stu-id="398ab-119">Storage with CDS</span></span>

<span data-ttu-id="398ab-120">O CDM (Modelo de Dados Comum) é a linguagem de dados compartilhada usada por aplicativos de negócios e analíticos no CDS.</span><span class="sxs-lookup"><span data-stu-id="398ab-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="398ab-121">Ele consiste em um conjunto de esquemas de dados extensíveis padronizados publicados pela Microsoft e por nossos parceiros que permitem a consistência dos dados e seu significado em aplicativos e processos empresariais.</span><span class="sxs-lookup"><span data-stu-id="398ab-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="398ab-122">Saiba mais sobre o [dados comuns do Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="398ab-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="398ab-123">Saiba mais sobre o fluxo [de trabalho aprovação](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="398ab-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="398ab-124">Permissões do aplicativo Aprovações do Teams</span><span class="sxs-lookup"><span data-stu-id="398ab-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="398ab-125">O aplicativo Aprovações Teams permite que você acesse os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="398ab-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="398ab-126">Receba mensagens e dados que você fornece a ela.</span><span class="sxs-lookup"><span data-stu-id="398ab-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="398ab-127">Enviar mensagens e notificações.</span><span class="sxs-lookup"><span data-stu-id="398ab-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="398ab-128">Renderizar aplicativos pessoais e caixas de diálogo sem um header fornecido pelo Teams.</span><span class="sxs-lookup"><span data-stu-id="398ab-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="398ab-129">Acesse suas informações de perfil, como nome, endereço de email, nome da empresa e idioma preferido.</span><span class="sxs-lookup"><span data-stu-id="398ab-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="398ab-130">Receba mensagens e dados que os membros da equipe fornecem a ela em um canal.</span><span class="sxs-lookup"><span data-stu-id="398ab-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="398ab-131">Enviar mensagens e notificações em um canal.</span><span class="sxs-lookup"><span data-stu-id="398ab-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="398ab-132">Acesse as informações da sua equipe:</span><span class="sxs-lookup"><span data-stu-id="398ab-132">Access your team's information:</span></span>
  - <span data-ttu-id="398ab-133">nome da equipe</span><span class="sxs-lookup"><span data-stu-id="398ab-133">team name</span></span>
  - <span data-ttu-id="398ab-134">lista de canais</span><span class="sxs-lookup"><span data-stu-id="398ab-134">channel list</span></span>
  - <span data-ttu-id="398ab-135">lista de lista (nomes e endereços de email dos membros da equipe).</span><span class="sxs-lookup"><span data-stu-id="398ab-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="398ab-136">Use as informações da equipe para contatá-los.</span><span class="sxs-lookup"><span data-stu-id="398ab-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="398ab-137">Desabilitar o aplicativo Aprovações</span><span class="sxs-lookup"><span data-stu-id="398ab-137">Disable the Approvals app</span></span>

<span data-ttu-id="398ab-138">O aplicativo Aprovações está disponível por padrão.</span><span class="sxs-lookup"><span data-stu-id="398ab-138">The Approvals app is available by default.</span></span> <span data-ttu-id="398ab-139">Você pode desabilitar o aplicativo no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="398ab-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="398ab-140">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="398ab-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="398ab-141">Expanda **aplicativos Teams** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="398ab-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="398ab-142">Procure o aplicativo Aprovações.</span><span class="sxs-lookup"><span data-stu-id="398ab-142">Search for the Approvals app.</span></span>

     ![mostra a navegação do Centro de administração com Aplicativos do Teams > Gerenciar Aplicativos realçada](media/manage-approval-apps.png)

  4. <span data-ttu-id="398ab-144">Selecione Aprovações.</span><span class="sxs-lookup"><span data-stu-id="398ab-144">Select Approvals.</span></span>

  5. <span data-ttu-id="398ab-145">Selecione o alternância para desabilitar o aplicativo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="398ab-145">Select the toggle to disable the app for your organization.</span></span>

     ![mostra os detalhes do aplicativo Aprovações](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="398ab-147">Política de retenção</span><span class="sxs-lookup"><span data-stu-id="398ab-147">Retention policy</span></span>

<span data-ttu-id="398ab-148">As aprovações criadas a partir do Aplicativo Aprovações são armazenadas no ambiente de CDS padrão, que não dá suporte a backups no momento.</span><span class="sxs-lookup"><span data-stu-id="398ab-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="398ab-149">Saiba mais sobre como fazer [backup e restaurar ambientes - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="398ab-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="398ab-150">Auditoria</span><span class="sxs-lookup"><span data-stu-id="398ab-150">Auditing</span></span>

<span data-ttu-id="398ab-151">O aplicativo Approvals registra eventos de auditoria no Centro de Conformidade e Segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="398ab-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="398ab-152">Você pode exibir o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="398ab-152">You can view the audit log.</span></span>

1. <span data-ttu-id="398ab-153">Vá para o Site de Conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="398ab-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="398ab-154">Selecione a **seção** Auditoria.</span><span class="sxs-lookup"><span data-stu-id="398ab-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="398ab-155">Procure atividades em atividades em **de aprovação do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="398ab-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="398ab-156">Você pode procurar as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="398ab-156">You can search for the following activities:</span></span>

- <span data-ttu-id="398ab-157">Criar nova solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="398ab-157">Create new approval request</span></span>

- <span data-ttu-id="398ab-158">Exibir detalhes da solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="398ab-158">View approval request details</span></span>

- <span data-ttu-id="398ab-159">Solicitação de aprovação aprovada</span><span class="sxs-lookup"><span data-stu-id="398ab-159">Approved approval request</span></span>

- <span data-ttu-id="398ab-160">Solicitação de aprovação rejeitada</span><span class="sxs-lookup"><span data-stu-id="398ab-160">Rejected approval request</span></span>

- <span data-ttu-id="398ab-161">Solicitação de aprovação cancelada</span><span class="sxs-lookup"><span data-stu-id="398ab-161">Canceled approval request</span></span>

- <span data-ttu-id="398ab-162">Solicitação de aprovação compartilhada</span><span class="sxs-lookup"><span data-stu-id="398ab-162">Shared approval request</span></span>

- <span data-ttu-id="398ab-163">Arquivo anexado à solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="398ab-163">File attached to approval request</span></span>

- <span data-ttu-id="398ab-164">Solicitação de aprovação reatribuida</span><span class="sxs-lookup"><span data-stu-id="398ab-164">Reassigned approval request</span></span>

- <span data-ttu-id="398ab-165">Assinatura eletrônica adicionada à solicitação de aprovação</span><span class="sxs-lookup"><span data-stu-id="398ab-165">Added e-signature to approval request</span></span>

- <span data-ttu-id="398ab-166">Detalhes da solicitação de assinatura eletrônica exibida</span><span class="sxs-lookup"><span data-stu-id="398ab-166">Viewed e-signature request details</span></span>

- <span data-ttu-id="398ab-167">Solicitação de assinatura eletrônica revisada</span><span class="sxs-lookup"><span data-stu-id="398ab-167">Reviewed e-signature request</span></span>

- <span data-ttu-id="398ab-168">Solicitação de assinatura eletrônica cancelada</span><span class="sxs-lookup"><span data-stu-id="398ab-168">Canceled e-signature request</span></span>

<span data-ttu-id="398ab-169">Para obter acesso a mais aprovações de auditoria no Flow, habilita e configure a auditoria no ambiente padrão para as entidades de aprovação principais Aprovação, Solicitação de Aprovação e Resposta de Aprovação.</span><span class="sxs-lookup"><span data-stu-id="398ab-169">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="398ab-170">Operações de criação, atualização e exclusão são eventos auditáveis para registros de Aprovação.</span><span class="sxs-lookup"><span data-stu-id="398ab-170">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="398ab-171">Saiba mais sobre [dados de Auditoria e atividade do usuário para segurança e conformidade - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="398ab-171">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="398ab-172">A auditoria pode ser personalizada ainda mais no [de Conformidade e Segurança do Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="398ab-172">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="398ab-173">Para usar os relatórios pré-configurados, entre em Segurança e Conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="398ab-173">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="398ab-174">Selecione **pesquisa e investigação**.</span><span class="sxs-lookup"><span data-stu-id="398ab-174">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="398ab-175">Pesquise no log de Auditoria e selecione **atividades do Dynamics 365** dados.</span><span class="sxs-lookup"><span data-stu-id="398ab-175">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="398ab-176">Saiba mais sobre [registro em log de atividades de aplicativos orientados por modelos e dados de aplicativos do Microsoft Dataverse - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="398ab-176">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="398ab-177">Segurança</span><span class="sxs-lookup"><span data-stu-id="398ab-177">Security</span></span>

<span data-ttu-id="398ab-178">No aplicativo Aprovações de Equipes, os usuários têm acesso para criar novas Aprovações e exibir Aprovações que enviaram e receberam.</span><span class="sxs-lookup"><span data-stu-id="398ab-178">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="398ab-179">Os usuários não terão acesso às Aprovações criadas por outras pessoas, a menos que sejam respondentes ou visualizadores da solicitação.</span><span class="sxs-lookup"><span data-stu-id="398ab-179">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="398ab-180">Um usuário terá uma função de visualizador de uma solicitação se ele for parte do chat ou canal no qual a aprovação foi criada.</span><span class="sxs-lookup"><span data-stu-id="398ab-180">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="398ab-181">Ela não terá a capacidade de tomar medidas na solicitação caso não tenha sido concedida essa função quando a aprovação foi criada.</span><span class="sxs-lookup"><span data-stu-id="398ab-181">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="398ab-182">Aprova a integração de assinatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="398ab-182">Approvals e-signature integration</span></span>

<span data-ttu-id="398ab-183">As aprovações de assinatura eletrônica criadas a partir do aplicativo Aprovações são armazenadas no ambiente de nuvem do provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="398ab-183">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="398ab-184">Para obter mais informações sobre o armazenamento em torno do contrato de assinatura eletrônica, consulte a documentação de armazenamento do provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="398ab-184">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="398ab-185">Para usar o recurso de assinatura eletrônica do aplicativo Aprovações, você precisa dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="398ab-185">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="398ab-186">Licença para o provedor de assinatura eletrônica específico que você está escolhendo usar.</span><span class="sxs-lookup"><span data-stu-id="398ab-186">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="398ab-187">Para obter uma licença para sua organização, você precisará acessar o site do provedor.</span><span class="sxs-lookup"><span data-stu-id="398ab-187">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="398ab-188">Para a funcionalidade de assinatura eletrônica Aprovações, parceiros de assinatura de terceiros aparecerão no aplicativo Teams Aprovações por padrão.</span><span class="sxs-lookup"><span data-stu-id="398ab-188">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="398ab-189">Você pode desabilitar provedores de assinatura eletrônica específicos acessando as configurações do aplicativo no Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="398ab-189">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="398ab-190">No centro Teams de administração, em Gerenciar **aplicativos,** selecione o aplicativo Aprovações e escolha **Configurações**. </span><span class="sxs-lookup"><span data-stu-id="398ab-190">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="398ab-191">Cada provedor de assinatura eletrônica tem uma alternância ao lado dele que está na posição on (à direita) por padrão.</span><span class="sxs-lookup"><span data-stu-id="398ab-191">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="398ab-192">Deslize a alternância para a esquerda para desabilitar um provedor de assinatura eletrônica específico.</span><span class="sxs-lookup"><span data-stu-id="398ab-192">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="398ab-193">Se um administrador Teams desabilitar um provedor, os usuários finais não verão o provedor ao criar uma aprovação.</span><span class="sxs-lookup"><span data-stu-id="398ab-193">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="398ab-194">Os usuários finais também não poderão exibir quaisquer solicitações de assinatura eletrônica que foram feitas com esse provedor.</span><span class="sxs-lookup"><span data-stu-id="398ab-194">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="398ab-195">Aprovações de assinatura eletrônica criadas a partir do Aplicativo de Aprovações são armazenadas na nuvem do provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="398ab-195">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="398ab-196">Portanto, você precisará acessar o site do provedor para exportar quaisquer dados sobre assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="398ab-196">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="398ab-197">Consulte a documentação do provedor sobre exportação e retenção desses contratos.</span><span class="sxs-lookup"><span data-stu-id="398ab-197">Refer to the provider's documentation about export and retention of these agreements.</span></span>
