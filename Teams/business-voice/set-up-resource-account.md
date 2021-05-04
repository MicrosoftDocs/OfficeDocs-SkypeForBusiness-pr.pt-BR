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
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130312"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="2b2f5-103">Etapa 4: Configurar uma conta de recurso do Business Voice</span><span class="sxs-lookup"><span data-stu-id="2b2f5-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="2b2f5-104">Em Microsoft Teams, uma conta de recurso é necessária para cada atendimento automático ou fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="2b2f5-105">Contas de recursos também podem ser atribuídas a números de telefone de serviço.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="2b2f5-106">É assim que você atribui números de telefone a atendimentos automáticos e filas de chamadas permitindo que os chamadores de fora Teams para alcançar o atendimento automático ou fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="2b2f5-107">Obter licenças de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="2b2f5-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="2b2f5-108">As contas de recursos exigem uma licença para trabalhar com os atendimentos automáticos e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="2b2f5-109">Você pode usar uma licença de *Microsoft 365 Sistema de Telefonia - Usuário Virtual.*</span><span class="sxs-lookup"><span data-stu-id="2b2f5-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="2b2f5-110">Acesse o Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="2b2f5-111">Acesse **Complementos dos serviços**  >  **de Compra** de  >  **Cobrança** Consulte  >  **todos os produtos de complementos**</span><span class="sxs-lookup"><span data-stu-id="2b2f5-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="2b2f5-112">Role até o final para encontrar a licença **Microsoft 365 Sistema de Telefonia – Usuário Virtual.**</span><span class="sxs-lookup"><span data-stu-id="2b2f5-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="2b2f5-113">Selecione **Detalhes** **e,** em seguida, Comprar .</span><span class="sxs-lookup"><span data-stu-id="2b2f5-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="2b2f5-114">Na página de compra de licença, selecione o número de licenças de usuário virtual que você deseja.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="2b2f5-115">Você precisa de uma licença virtual para cada atendimento automático e fila de chamada que planeja configurar.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="2b2f5-116">Recomendamos selecionar pelo menos cinco licenças para que você possa facilmente configurar mais atendimentos automáticos e filas de chamada no futuro sem precisar comprar mais licenças imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="2b2f5-117">**Desmarque Atribuir automaticamente a todos os seus usuários sem licenças**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="2b2f5-118">Selecione **Check-out agora**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="2b2f5-119">Confirme seu pedido, selecione **Próximo** e, em **seguida, Coloque o pedido**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="2b2f5-120">Lembre-se de que você ainda deve  **Comprar** a licença mesmo que ela tenha um custo zero.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="2b2f5-121">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="2b2f5-121">Create a resource account</span></span>

<span data-ttu-id="2b2f5-122">Depois de receber sua Microsoft 365 Sistema de Telefonia *- Licença de Usuário Virtual,* você pode criar sua conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Captura de tela da interface do usuário adicionar conta de recurso](../media/resource-account-add.png)

1. <span data-ttu-id="2b2f5-124">No centro Teams de administração, expanda **as** configurações de toda a organização e clique em **Contas de recursos.**</span><span class="sxs-lookup"><span data-stu-id="2b2f5-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="2b2f5-125">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-125">Select **Add**.</span></span>
3. <span data-ttu-id="2b2f5-126">No painel **Adicionar conta de** recurso, preencha Nome **de** exibição e, em seguida, Nome de **usuário**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="2b2f5-127">Escolha um nome de exibição descritivo, como "Atendimento automático de linha principal" para descrever a finalidade da conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="2b2f5-128">Em **Tipo de conta de recurso,** selecione Atendimento **automático**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="2b2f5-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-129">Select **Save**.</span></span>

![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="2b2f5-131">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="2b2f5-131">Assign a license</span></span>

<span data-ttu-id="2b2f5-132">Depois de criar sua conta de recurso, você precisará atribuir uma Microsoft 365 Sistema de Telefonia *- licença* de usuário virtual *ou* Sistema de Telefonia licença.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Captura de tela da interface do usuário atribuir licenças no Microsoft 365 de administração](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="2b2f5-134">No centro Microsoft 365 de administração, vá para **Usuários**  >  **Usuários ativos.**</span><span class="sxs-lookup"><span data-stu-id="2b2f5-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="2b2f5-135">Selecione sua conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-135">Select your resource account.</span></span>
1. <span data-ttu-id="2b2f5-136">Na guia **Licenças e Aplicativos,** em **Licenças,** selecione **Microsoft 365 Sistema de Telefonia - Usuário Virtual**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="2b2f5-137">Selecione **Salvar alterações** e, em **seguida, Fechar**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="2b2f5-138">Atribuir um número de serviço</span><span class="sxs-lookup"><span data-stu-id="2b2f5-138">Assign a service number</span></span>

![Captura de tela da interface do usuário atribuir número de serviço](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="2b2f5-140">No centro Teams de administração, acesse **Configurações** em toda a organização e contas **de recurso.**</span><span class="sxs-lookup"><span data-stu-id="2b2f5-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="2b2f5-141">Selecione a conta de recurso que você acabou de criar e clique em **Atribuir/desatribuição.**</span><span class="sxs-lookup"><span data-stu-id="2b2f5-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="2b2f5-142">Na lista **Telefone de tipos de número,** escolha **Online**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="2b2f5-143">Na caixa **Número de telefone atribuído,** pesquise o número que deseja usar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="2b2f5-144">Certifique-se de incluir o código do país (por exemplo, **+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="2b2f5-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="2b2f5-145">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2b2f5-146">Você não precisa selecionar um assistente automático em Atribuir **a** porque o atendimento automático ao que você deseja adicionar o número já está selecionado.</span><span class="sxs-lookup"><span data-stu-id="2b2f5-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2b2f5-147">Próxima etapa: Atribuir números de telefone aos usuários</span><span class="sxs-lookup"><span data-stu-id="2b2f5-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
