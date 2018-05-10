---
title: Implantar telefones para o Skype for Business Online
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para telefones de área comum.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a><span data-ttu-id="09118-103">Telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="09118-103">Common Area Phones</span></span>
<span data-ttu-id="09118-104">Um telefone de área comum ou COBRIR, é geralmente colocada em uma área compartilhada e não associado a um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="09118-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="09118-105">Por exemplo, um telefone de área de recepção, porta telefone ou sala de reunião telefone, maiusculas são configuradas como dispositivos em vez de usuários e entrar automaticamente à rede.</span><span class="sxs-lookup"><span data-stu-id="09118-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="09118-106">Nas etapas abaixo, podemos ajudá-lo a configurar uma conta para o sistema de telefone da Microsoft com planos de chamada e, em seguida, implantar uma Capitular.</span><span class="sxs-lookup"><span data-stu-id="09118-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="09118-107">Pré-requisitos para telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="09118-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="09118-108">Confirme que você tenha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="09118-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="09118-109">Adquirido SKU do telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="09118-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="09118-110">(Consulte suporte Firmware tópico do firmware atualizadohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="09118-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="09118-111">Telefones aprovadas (exibir a lista nohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="09118-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 


## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="09118-112">Verifique o firmware para o seu telefone</span><span class="sxs-lookup"><span data-stu-id="09118-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="09118-113">**Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="09118-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="09118-114">**Telefones Yealink**, vá para **Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="09118-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="09118-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="09118-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="09118-116">**Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="09118-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="09118-117">As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="09118-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="09118-118">Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.</span><span class="sxs-lookup"><span data-stu-id="09118-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="09118-119">Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="09118-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="09118-120">Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ para `false`.</span><span class="sxs-lookup"><span data-stu-id="09118-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="09118-121">Criar COBRIR</span><span class="sxs-lookup"><span data-stu-id="09118-121">Create CAP</span></span>
<span data-ttu-id="09118-122">Você pode criar o COBRIR definindo as configurações antes de configurar o telefone físico.</span><span class="sxs-lookup"><span data-stu-id="09118-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="09118-123">Adquira o telefone de área comum SKU.</span><span class="sxs-lookup"><span data-stu-id="09118-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="09118-124">Configurar o telefone de área comum<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="09118-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="09118-125">**Criar um usuário**</span><span class="sxs-lookup"><span data-stu-id="09118-125">**Create user**</span></span> 
1. <span data-ttu-id="09118-126">Atribuir um telefone de área comum SKU</span><span class="sxs-lookup"><span data-stu-id="09118-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="09118-127">Atribua chamar planejar (se estiver usando o sistema de telefone da Microsoft com planos de chamada).</span><span class="sxs-lookup"><span data-stu-id="09118-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="09118-128">Atribuir um número de telefone disponíveis no Skype para Business Admin Center, ou solicitar um novo número de telefone.</span><span class="sxs-lookup"><span data-stu-id="09118-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="09118-129">**Criar um novo usuário**</span><span class="sxs-lookup"><span data-stu-id="09118-129">**Create New User**</span></span>

1. <span data-ttu-id="09118-130">No painel de provisionamento, você tem uma opção para digitar um nome e sobrenome (por exemplo, Main de recepção).</span><span class="sxs-lookup"><span data-stu-id="09118-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="09118-131">Insira um nome para exibição (obrigatório), por exemplo, "Main recepção."</span><span class="sxs-lookup"><span data-stu-id="09118-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="09118-132">Insira um nome de usuário (obrigatório), por exemplo "MainReception" @"domínio" (nome de empresa ou enterprise)</span><span class="sxs-lookup"><span data-stu-id="09118-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="09118-133">Insira o local (país).</span><span class="sxs-lookup"><span data-stu-id="09118-133">Enter Location (country).</span></span>

<span data-ttu-id="09118-134">**Atribuir um telefone de área comum SKU** No Centro de administração do Office 365, vá para **faturamento > Serviços de compra** e adicione o **Telefone de área comum**</span><span class="sxs-lookup"><span data-stu-id="09118-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="09118-135">**Atribuir o plano de chamada no COBRIR SKU**</span><span class="sxs-lookup"><span data-stu-id="09118-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="09118-136">Selecione uma chamada planeja habilitar o telefone.</span><span class="sxs-lookup"><span data-stu-id="09118-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="09118-137">Adicione o limite para permitir que o sistema telefônico e Skype para negócios Online plano 2 na SKU COBRIR.</span><span class="sxs-lookup"><span data-stu-id="09118-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="09118-138">**Atribuir um número de telefone**</span><span class="sxs-lookup"><span data-stu-id="09118-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="09118-139">Verificar números de telefone disponíveis em **voz > números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="09118-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="09118-140">Selecione um número na lista disponível do número de números de telefone.</span><span class="sxs-lookup"><span data-stu-id="09118-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="09118-141">Confirme sua seleção selecionando os **Números de telefone**e **voz** .</span><span class="sxs-lookup"><span data-stu-id="09118-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="09118-142">[Nota] Usuários de voz mostram somente se tiverem a licença do sistema telefônico aplicada, embora o mesmo depois de aplicar, poderá demorar para ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="09118-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="09118-143">Reabrir um dia Skype para Business Admin center ajuda.</span><span class="sxs-lookup"><span data-stu-id="09118-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="09118-144">Configurar o telefone</span><span class="sxs-lookup"><span data-stu-id="09118-144">Configure Phone</span></span>

<span data-ttu-id="09118-145">**Preparar os telefones físicos**</span><span class="sxs-lookup"><span data-stu-id="09118-145">**Prepare the physical phones**</span></span> 

<span data-ttu-id="09118-146">Seu telefone selecionado precisa ter o modo de telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="09118-146">Your selected phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="09118-147">***Telefone de Polycom VVX de exemplo***</span><span class="sxs-lookup"><span data-stu-id="09118-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="09118-148">Habilite o modo do telefone de área comum em Polycom VVX seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="09118-148">Enable Common Area Phone Mode on Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="09118-149">No seu navegador, use a interface da web para habilitar o modo de COBRIR o VVX</span><span class="sxs-lookup"><span data-stu-id="09118-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="09118-150">Vá para **configuração** e no Skype para a opção de configuração de negócios, selecione o **Telefone de área comum**.</span><span class="sxs-lookup"><span data-stu-id="09118-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="09118-151">Clique em **Salvar** para salvar as suas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="09118-151">Click **Save** to save your configuration settings.</span></span>

<span data-ttu-id="09118-152">Agora que o modo de telefone COBRIR estiver habilitado, configure o telefone usando a exibição do telefone.</span><span class="sxs-lookup"><span data-stu-id="09118-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span>

1. <span data-ttu-id="09118-153">Nas configurações, selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="09118-153">In the Settings, select **Advanced**.</span></span>
2. <span data-ttu-id="09118-154">Insira a senha.</span><span class="sxs-lookup"><span data-stu-id="09118-154">Enter password.</span></span>
3. <span data-ttu-id="09118-155">Nas configurações de administração, selecione **Configurações de telefone de área comum**.</span><span class="sxs-lookup"><span data-stu-id="09118-155">In Administration settings, select **Common Area Phone Settings**.</span></span>
4. <span data-ttu-id="09118-156">Habilitar o Common Area Phone and COBRIR Admin</span><span class="sxs-lookup"><span data-stu-id="09118-156">Enable Common Area Phone and CAP Admin</span></span>
5. <span data-ttu-id="09118-157">Selecione **Salvar o arquivo Config**.</span><span class="sxs-lookup"><span data-stu-id="09118-157">Select **Save Config**.</span></span>

<span data-ttu-id="09118-158">Seu telefone está pronto para ser provisionados, o qual você vai fazer quando você entrar na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="09118-158">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="09118-159">Entrar selecionando **Configurações > recursos > Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="09118-159">Sign in by selecting **settings > features > Skype for Business.**</span></span>
2. <span data-ttu-id="09118-160">Selecione as credenciais do usuário e, em seguida, selecione selecionar **entrar na web (COBRIR)** para gerar um código..</span><span class="sxs-lookup"><span data-stu-id="09118-160">Select User Credentials, and select select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="09118-161">Vá para o portal de provisionamento http://aka.ms/skypecape entrar como **admin**.</span><span class="sxs-lookup"><span data-stu-id="09118-161">Go to the provisioning portal http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="09118-162">Insira o nome de exibição (por exemplo, Main recepção) para exibir seu limite.</span><span class="sxs-lookup"><span data-stu-id="09118-162">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="09118-163">[Nota] Se "Pesquisa para telefones de área comum apenas" estiver marcada, desmarque a caixa de seleção e pesquisar novamente.</span><span class="sxs-lookup"><span data-stu-id="09118-163">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="09118-164">Na janela de código de emparelhamento, insira o código exibido no telefone e clique em **fornecimento**.</span><span class="sxs-lookup"><span data-stu-id="09118-164">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="09118-165">WHT essa última etapa, o telefone deve entrar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="09118-165">Wht this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="09118-166">Saiba mais sobre os telefones disponíveis em [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span><span class="sxs-lookup"><span data-stu-id="09118-166">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


