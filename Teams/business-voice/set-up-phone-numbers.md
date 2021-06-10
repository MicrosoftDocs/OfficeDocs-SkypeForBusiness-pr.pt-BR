---
title: Configurar Microsoft 365 Business Voice números de telefone
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
description: Saiba como configurar Microsoft 365 Business Voice números de telefone para usuários e serviços em sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7dcf582593cf09977f4992d6b78035a9726c12b8
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282538"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="60326-103">Etapa 2: Configurar números de telefone do Business Voice</span><span class="sxs-lookup"><span data-stu-id="60326-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="60326-104">Antes de configurar usuários ou atendentes automáticos em sua organização, você precisa obter números de telefone para eles.</span><span class="sxs-lookup"><span data-stu-id="60326-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="60326-105">Há vários tipos diferentes de números de telefone, no entanto, estes são os dois tipos de números que você precisa adicionar nesta etapa:</span><span class="sxs-lookup"><span data-stu-id="60326-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="60326-106">**Números de serviço** Esses números são usados para atendimento automático, audioconferência e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="60326-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="60326-107">Eles podem ser números de chamada gratuita ou gratuita e podem lidar com grandes quantidades de chamadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="60326-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="60326-108">O número de telefone da sua empresa precisa ser um número de serviço porque ele será atribuído a um atendimento automático em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="60326-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="60326-109">**Números de assinante** Esses números são usados para usuários regulares para que possam fazer e receber chamadas telefônicas.</span><span class="sxs-lookup"><span data-stu-id="60326-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60326-110">Mesmo que você queira usar seus números de telefone existentes, você precisa criar e atribuir números de telefone temporários à linha telefônica principal da sua empresa e aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="60326-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="60326-111">Você poderá substituir esses números temporários por seus números de telefone existentes em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="60326-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="60326-112">Pode levar várias horas para que seus novos números de telefone se tornem disponíveis Teams.</span><span class="sxs-lookup"><span data-stu-id="60326-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="60326-113">Configurar um número de serviço</span><span class="sxs-lookup"><span data-stu-id="60326-113">Set up a service number</span></span>

<span data-ttu-id="60326-114">O número de serviço que você configurar agora será usado em uma etapa posterior para o número de telefone principal da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="60326-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="60326-115">Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever no Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="60326-115">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="60326-116">Na navegação à esquerda, vá para <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **Voz**  >  **Telefone números**</a>e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="60326-116">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="60326-117">Insira um nome para a ordem e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="60326-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="60326-118">Na página Local e quantidade, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="60326-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="60326-119">Em **País ou região**, selecione um país ou região.</span><span class="sxs-lookup"><span data-stu-id="60326-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="60326-120">Em **Tipo de número,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="60326-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="60326-121">**Atendimento automático (Toll)** Número de telefone regular, não gratuito.</span><span class="sxs-lookup"><span data-stu-id="60326-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="60326-122">As taxas de longa distância são cobradas ao chamador.</span><span class="sxs-lookup"><span data-stu-id="60326-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="60326-123">**Atendimento automático (Gratuito)** Número de telefone gratuito (EUA e Canadá) ou telefone gratuito (Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="60326-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="60326-124">As taxas de longa distância são cobradas para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="60326-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="60326-125">Antes de selecionar essa opção, você precisa comprar Créditos de Comunicação.</span><span class="sxs-lookup"><span data-stu-id="60326-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="60326-126">Para obter mais informações, consulte [O que preciso comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="60326-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="60326-127">Em **Quantidade,** selecione **1**.</span><span class="sxs-lookup"><span data-stu-id="60326-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="60326-128">Se você receber a mensagem Você não tem **licenças** suficientes para solicitar mais números desse tipo, certifique-se de ter comprado licenças do Business Voice.</span><span class="sxs-lookup"><span data-stu-id="60326-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="60326-129">Para obter mais informações, consulte [O que preciso comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="60326-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="60326-130">Escolha **Local** ou **Código** de Área, dependendo se você deseja pesquisar números de telefone usando a cidade de um local ou se deseja pesquisar números em um código de área específico.</span><span class="sxs-lookup"><span data-stu-id="60326-130">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="60326-131">Se você selecionar **Local**:</span><span class="sxs-lookup"><span data-stu-id="60326-131">If you select **Location**:</span></span>

        1. <span data-ttu-id="60326-132">Digite a cidade na qual seu [](set-up-emergency-locations.md) endereço de emergência está localizado na etapa Configurar locais de emergência ou se precisar criar um novo local para outro escritório ou um home office, clique em **Adicionar um local**.</span><span class="sxs-lookup"><span data-stu-id="60326-132">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="60326-133">Em **Código de área,** selecione um código de área e selecione **Próximo** para reservar seu número.</span><span class="sxs-lookup"><span data-stu-id="60326-133">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="60326-134">Se você selecionar **Código de área,** digite o código de área que deseja pesquisar e selecione **Próximo** para reservar seu número.</span><span class="sxs-lookup"><span data-stu-id="60326-134">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>

5. <span data-ttu-id="60326-135">Selecione o número que deseja.</span><span class="sxs-lookup"><span data-stu-id="60326-135">Select the number you want.</span></span> <span data-ttu-id="60326-136">Você tem 10 minutos para selecionar seu número de telefone e fazer seu pedido.</span><span class="sxs-lookup"><span data-stu-id="60326-136">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="60326-137">Se você demorar mais de 10 minutos, o número de telefone será retornado para o pool de números.</span><span class="sxs-lookup"><span data-stu-id="60326-137">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="60326-138">Quando você estiver pronto para fazer seu pedido, clique em **Colocar ordem** e, em seguida, **Concluir**</span><span class="sxs-lookup"><span data-stu-id="60326-138">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="60326-139">Configurar números de telefone para seus usuários</span><span class="sxs-lookup"><span data-stu-id="60326-139">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="60326-140">Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever no Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="60326-140">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="60326-141">Na navegação à esquerda, vá para <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **Voz**  >  **Telefone números**</a>e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="60326-141">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="60326-142">Insira um nome para a ordem e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="60326-142">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="60326-143">Na página Local e quantidade, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="60326-143">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="60326-144">Em **País ou região**, selecione um país ou região.</span><span class="sxs-lookup"><span data-stu-id="60326-144">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="60326-145">Em **Tipo de número,** selecione **Usuário (assinante)**.</span><span class="sxs-lookup"><span data-stu-id="60326-145">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="60326-146">Em **Quantidade**, insira o número de números que você deseja para sua organização.</span><span class="sxs-lookup"><span data-stu-id="60326-146">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="60326-147">Escolha **Local** ou **Código** de Área, dependendo se você deseja pesquisar números de telefone usando a cidade de um local ou se deseja pesquisar números em um código de área específico.</span><span class="sxs-lookup"><span data-stu-id="60326-147">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="60326-148">Se você selecionar **Local**:</span><span class="sxs-lookup"><span data-stu-id="60326-148">If you select **Location**:</span></span>

        1. <span data-ttu-id="60326-149">Digite a cidade na qual seu [](set-up-emergency-locations.md) endereço de emergência está localizado na etapa Configurar locais de emergência ou se precisar criar um novo local para outro escritório ou um home office, clique em **Adicionar um local**.</span><span class="sxs-lookup"><span data-stu-id="60326-149">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="60326-150">Em **Código de área,** selecione um código de área e selecione **Próximo** para reservar seu número.</span><span class="sxs-lookup"><span data-stu-id="60326-150">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="60326-151">Se você selecionar **Código de área,** digite o código de área que deseja pesquisar e selecione **Próximo** para reservar seu número.</span><span class="sxs-lookup"><span data-stu-id="60326-151">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>
5. <span data-ttu-id="60326-152">Selecione os números que você deseja.</span><span class="sxs-lookup"><span data-stu-id="60326-152">Select the numbers you want.</span></span> <span data-ttu-id="60326-153">Você tem 10 minutos para selecionar seus números de telefone e fazer o pedido.</span><span class="sxs-lookup"><span data-stu-id="60326-153">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="60326-154">Se você demorar mais de 10 minutos, os números de telefone serão retornados para o pool de números.</span><span class="sxs-lookup"><span data-stu-id="60326-154">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="60326-155">Quando estiver pronto para fazer seu pedido, clique em **Colocar ordem** e, em seguida, **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="60326-155">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60326-156">Próxima etapa: atribuir licenças a Teams usuários</span><span class="sxs-lookup"><span data-stu-id="60326-156">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
