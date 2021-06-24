---
title: Configurar uma conta Microsoft 365 Business Voice de recursos
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Saiba como configurar uma conta de recurso Microsoft 365 Business Voice para uso com os atendentes automáticos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: df5001b6f757b407e96a473d302c79d837af957c
ms.sourcegitcommit: 38fa37d83704200911866cf017566fcb128ea2fe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105163"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="d1605-103">Etapa 4: Configurar uma conta de recurso do Business Voice</span><span class="sxs-lookup"><span data-stu-id="d1605-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="d1605-104">As contas de recursos não são atribuídas a nenhum usuário específico.</span><span class="sxs-lookup"><span data-stu-id="d1605-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="d1605-105">Em vez disso, as contas de recurso, que usam uma licença de usuário virtual gratuita, são usadas por dispositivos e serviços em Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1605-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="d1605-106">Em Microsoft Teams, contas de recursos são atribuídas a números de telefone e são associadas a atendimentos automáticos e filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="d1605-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="d1605-107">Ao associar contas de recursos a atendimentos automáticos e filas de chamadas, você pode adicionar um ou mais números de telefone gratuitos ou de chamada gratuita a eles.</span><span class="sxs-lookup"><span data-stu-id="d1605-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="d1605-108">Por exemplo, você pode associar uma conta de recurso a um número de chamada a um atendimento automático para chamadores locais.</span><span class="sxs-lookup"><span data-stu-id="d1605-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="d1605-109">Para chamadas de longa distância, você pode associar outra conta de recurso a um número de chamada gratuita ao mesmo atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="d1605-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="d1605-110">As seções deste artigo mostram como configurar uma conta de recurso e atribuir um número de telefone a ela.</span><span class="sxs-lookup"><span data-stu-id="d1605-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="d1605-111">Mais tarde, você associará a conta de recurso a um atendente automático.</span><span class="sxs-lookup"><span data-stu-id="d1605-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

<span data-ttu-id="d1605-112">O vídeo a seguir mostra como concluir essas etapas no Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="d1605-112">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYG]

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="d1605-113">Obter licenças de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="d1605-113">Obtain virtual user licenses</span></span>

<span data-ttu-id="d1605-114">As contas de recursos exigem uma licença para trabalhar com os atendimentos automáticos e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="d1605-114">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="d1605-115">Você pode usar uma licença de *Microsoft 365 Sistema de Telefonia - Usuário Virtual.*</span><span class="sxs-lookup"><span data-stu-id="d1605-115">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="d1605-116">Você só deverá executar as etapas a seguir se tiver se inscreveu para um período de avaliação do Business Voice.</span><span class="sxs-lookup"><span data-stu-id="d1605-116">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="d1605-117">Se você comprou licenças do Business Voice, as licenças virtuais já devem ser aplicadas à sua conta.</span><span class="sxs-lookup"><span data-stu-id="d1605-117">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="d1605-118">Para ver se você já tem licenças virtuais, entre Microsoft 365 usando uma conta com permissões de administrador global.</span><span class="sxs-lookup"><span data-stu-id="d1605-118">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="d1605-119">Em seguida, vá para Cobrança > [Seus produtos](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span><span class="sxs-lookup"><span data-stu-id="d1605-119">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="d1605-120">Se você tiver licenças virtuais, elas aparecerão como Microsoft 365 Sistema de Telefonia **- Usuário Virtual**.</span><span class="sxs-lookup"><span data-stu-id="d1605-120">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="d1605-121">Abra o Centro de administração do Microsoft 365 e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever para Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d1605-121">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="d1605-122">No painel de navegação esquerdo, vá para <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank"> **Cobrança**  >  **Serviços**</a>de Compra  >  **Complementos**  >  **Consulte todos os produtos complementos**.</span><span class="sxs-lookup"><span data-stu-id="d1605-122">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="d1605-123">Role até o final para encontrar a licença **Microsoft 365 Sistema de Telefonia – Usuário Virtual.**</span><span class="sxs-lookup"><span data-stu-id="d1605-123">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="d1605-124">Selecione **Detalhes** **e,** em seguida, Comprar .</span><span class="sxs-lookup"><span data-stu-id="d1605-124">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="d1605-125">Na página de compra de licença, selecione o número de licenças de usuário virtual que você deseja.</span><span class="sxs-lookup"><span data-stu-id="d1605-125">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="d1605-126">Você precisa de uma licença virtual para cada atendimento automático e fila de chamada que planeja configurar.</span><span class="sxs-lookup"><span data-stu-id="d1605-126">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="d1605-127">Recomendamos selecionar pelo menos cinco licenças para que você possa facilmente configurar mais atendimentos automáticos e filas de chamada no futuro sem precisar comprar mais licenças imediatamente.</span><span class="sxs-lookup"><span data-stu-id="d1605-127">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="d1605-128">**Desmarque Atribuir automaticamente a todos os seus usuários sem licenças**.</span><span class="sxs-lookup"><span data-stu-id="d1605-128">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="d1605-129">Selecione **Check-out agora**.</span><span class="sxs-lookup"><span data-stu-id="d1605-129">Select **Check out now**.</span></span>
7. <span data-ttu-id="d1605-130">Confirme seu pedido, selecione **Próximo** e, em **seguida, Coloque o pedido**.</span><span class="sxs-lookup"><span data-stu-id="d1605-130">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="d1605-131">Lembre-se de que você ainda deve  **Comprar** a licença mesmo que ela tenha um custo zero.</span><span class="sxs-lookup"><span data-stu-id="d1605-131">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="d1605-132">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="d1605-132">Create a resource account</span></span>

<span data-ttu-id="d1605-133">Depois de receber sua Microsoft 365 Sistema de Telefonia *- Licença de Usuário Virtual,* você pode criar sua conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="d1605-133">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Captura de tela da interface do usuário adicionar conta de recurso](../media/resource-account-add.png)

1. <span data-ttu-id="d1605-135">Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever no Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d1605-135">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="d1605-136">No painel de navegação esquerdo, vá para Configurações de toda a organização Contas <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **de recursos.**</a></span><span class="sxs-lookup"><span data-stu-id="d1605-136">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="d1605-137">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d1605-137">Select **Add**.</span></span>
4. <span data-ttu-id="d1605-138">No painel **Adicionar conta de** recurso, preencha Nome **de** exibição e, em seguida, Nome de **usuário**.</span><span class="sxs-lookup"><span data-stu-id="d1605-138">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="d1605-139">Escolha um nome de exibição descritivo, como "Atendimento automático de linha principal" para descrever a finalidade da conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="d1605-139">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="d1605-140">Em **Tipo de conta de recurso,** selecione Atendimento **automático**.</span><span class="sxs-lookup"><span data-stu-id="d1605-140">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="d1605-141">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d1605-141">Select **Save**.</span></span>

![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="d1605-143">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="d1605-143">Assign a license</span></span>

<span data-ttu-id="d1605-144">Depois de criar sua conta de recurso, você precisará atribuir uma Microsoft 365 Sistema de Telefonia *- licença* de usuário virtual *ou* Sistema de Telefonia licença.</span><span class="sxs-lookup"><span data-stu-id="d1605-144">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Captura de tela da interface do usuário atribuir licenças no Centro de administração do Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="d1605-146">Abra o Centro de administração do Microsoft 365 e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever para Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d1605-146">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="d1605-147">No painel de navegação esquerdo, vá para <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **Usuários**  >  **Usuários ativos.**</a></span><span class="sxs-lookup"><span data-stu-id="d1605-147">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="d1605-148">Selecione sua conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="d1605-148">Select your resource account.</span></span>
1. <span data-ttu-id="d1605-149">Na guia **Licenças e Aplicativos,** em **Licenças,** selecione **Microsoft 365 Sistema de Telefonia - Usuário Virtual**.</span><span class="sxs-lookup"><span data-stu-id="d1605-149">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="d1605-150">Selecione **Salvar alterações** e, em **seguida, Fechar**.</span><span class="sxs-lookup"><span data-stu-id="d1605-150">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="d1605-151">Atribuir um número de serviço</span><span class="sxs-lookup"><span data-stu-id="d1605-151">Assign a service number</span></span>

![Captura de tela da interface do usuário atribuir número de serviço](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="d1605-153">Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever no Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="d1605-153">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="d1605-154">No painel de navegação esquerdo, vá para Configurações de toda a organização Contas <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **de recursos.**</a></span><span class="sxs-lookup"><span data-stu-id="d1605-154">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="d1605-155">Selecione a conta de recurso que você acabou de criar e clique em **Atribuir/desatribuição.**</span><span class="sxs-lookup"><span data-stu-id="d1605-155">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="d1605-156">Na lista **Telefone de tipos de número,** escolha **Online**.</span><span class="sxs-lookup"><span data-stu-id="d1605-156">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="d1605-157">Na caixa **Número de telefone atribuído,** pesquise o número que deseja usar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d1605-157">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="d1605-158">Certifique-se de incluir o código do país (por exemplo, **+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="d1605-158">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="d1605-159">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d1605-159">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1605-160">Próxima etapa: Atribuir números de telefone aos usuários</span><span class="sxs-lookup"><span data-stu-id="d1605-160">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
