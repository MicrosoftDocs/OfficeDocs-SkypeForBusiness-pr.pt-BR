---
title: Configurar telefones de área comum
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para telefones de área comum.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
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
ms.openlocfilehash: 12ed7d5c24649903f7cd3020d66ee4e9fcb77b6f
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="61bf0-103">Configurar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="61bf0-103">Set up Common Area Phones</span></span>

<span data-ttu-id="61bf0-104">Um telefone de área comum ou COBRIR, é geralmente colocada em uma área compartilhada e não associado a um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="61bf0-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="61bf0-105">Por exemplo, um telefone de área de recepção, porta telefone ou sala de reunião telefone, maiusculas são configuradas como dispositivos em vez de usuários e entrar automaticamente à rede.</span><span class="sxs-lookup"><span data-stu-id="61bf0-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="61bf0-106">Nas etapas abaixo, podemos ajudá-lo a configurar uma conta para o sistema de telefone da Microsoft com planos de chamada e, em seguida, implantar uma Capitular.</span><span class="sxs-lookup"><span data-stu-id="61bf0-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="61bf0-107">Pré-requisitos para telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="61bf0-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="61bf0-108">Confirme que você tenha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="61bf0-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="61bf0-109">Adquirido SKU do telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="61bf0-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="61bf0-110">(Consulte suporte Firmware tópico do firmware atualizadohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="61bf0-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="61bf0-111">Telefones aprovadas (exibir a lista nohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="61bf0-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 

## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="61bf0-112">Verifique o firmware para o seu telefone</span><span class="sxs-lookup"><span data-stu-id="61bf0-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="61bf0-113">**Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="61bf0-114">**Telefones Yealink**, vá para **Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="61bf0-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="61bf0-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="61bf0-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="61bf0-116">**Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="61bf0-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="61bf0-117">As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="61bf0-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="61bf0-118">Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.</span><span class="sxs-lookup"><span data-stu-id="61bf0-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="61bf0-119">Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="61bf0-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="61bf0-120">Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ para `false`.</span><span class="sxs-lookup"><span data-stu-id="61bf0-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="61bf0-121">Criar COBRIR</span><span class="sxs-lookup"><span data-stu-id="61bf0-121">Create CAP</span></span>
<span data-ttu-id="61bf0-122">Você pode criar o COBRIR definindo as configurações antes de configurar o telefone físico.</span><span class="sxs-lookup"><span data-stu-id="61bf0-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="61bf0-123">Adquira o telefone de área comum SKU.</span><span class="sxs-lookup"><span data-stu-id="61bf0-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="61bf0-124">Configurar o telefone de área comum<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="61bf0-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="61bf0-125">**Criar um usuário**</span><span class="sxs-lookup"><span data-stu-id="61bf0-125">**Create user**</span></span> 
1. <span data-ttu-id="61bf0-126">Atribuir um telefone de área comum SKU</span><span class="sxs-lookup"><span data-stu-id="61bf0-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="61bf0-127">Atribua chamar planejar (se estiver usando o sistema de telefone da Microsoft com planos de chamada).</span><span class="sxs-lookup"><span data-stu-id="61bf0-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="61bf0-128">Atribuir um número de telefone disponíveis no Skype para Business Admin Center, ou solicitar um novo número de telefone.</span><span class="sxs-lookup"><span data-stu-id="61bf0-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="61bf0-129">**Criar um novo usuário**</span><span class="sxs-lookup"><span data-stu-id="61bf0-129">**Create New User**</span></span>

1. <span data-ttu-id="61bf0-130">No painel de provisionamento, você tem uma opção para digitar um nome e sobrenome (por exemplo, Main de recepção).</span><span class="sxs-lookup"><span data-stu-id="61bf0-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="61bf0-131">Insira um nome para exibição (obrigatório), por exemplo, "Main recepção."</span><span class="sxs-lookup"><span data-stu-id="61bf0-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="61bf0-132">Insira um nome de usuário (obrigatório), por exemplo "MainReception" @"domínio" (nome de empresa ou enterprise)</span><span class="sxs-lookup"><span data-stu-id="61bf0-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="61bf0-133">Insira o local (país).</span><span class="sxs-lookup"><span data-stu-id="61bf0-133">Enter Location (country).</span></span>

<span data-ttu-id="61bf0-134">**Atribuir um telefone de área comum SKU** No Centro de administração do Office 365, vá para **faturamento > Serviços de compra** e adicione o **Telefone de área comum**</span><span class="sxs-lookup"><span data-stu-id="61bf0-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="61bf0-135">**Atribuir o plano de chamada no COBRIR SKU**</span><span class="sxs-lookup"><span data-stu-id="61bf0-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="61bf0-136">Selecione uma chamada planeja habilitar o telefone.</span><span class="sxs-lookup"><span data-stu-id="61bf0-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="61bf0-137">Adicione o limite para permitir que o sistema telefônico e Skype para negócios Online plano 2 na SKU COBRIR.</span><span class="sxs-lookup"><span data-stu-id="61bf0-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="61bf0-138">**Atribuir um número de telefone**</span><span class="sxs-lookup"><span data-stu-id="61bf0-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="61bf0-139">Verificar números de telefone disponíveis em **voz > números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="61bf0-140">Selecione um número na lista disponível do número de números de telefone.</span><span class="sxs-lookup"><span data-stu-id="61bf0-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="61bf0-141">Confirme sua seleção selecionando os **Números de telefone**e **voz** .</span><span class="sxs-lookup"><span data-stu-id="61bf0-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="61bf0-142">[Nota] Usuários de voz mostram somente se tiverem a licença do sistema telefônico aplicada, embora o mesmo depois de aplicar, poderá demorar para ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="61bf0-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="61bf0-143">Reabrir um dia Skype para Business Admin center ajuda.</span><span class="sxs-lookup"><span data-stu-id="61bf0-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="61bf0-144">Configurar o telefone</span><span class="sxs-lookup"><span data-stu-id="61bf0-144">Configure Phone</span></span>

<span data-ttu-id="61bf0-145">**Preparar os telefones físicos**</span><span class="sxs-lookup"><span data-stu-id="61bf0-145">**Prepare the physical phones**</span></span>

<span data-ttu-id="61bf0-146">Seu telefone escolhido precisa ter o modo de telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="61bf0-146">Your chosen phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="61bf0-147">***Telefone de Polycom VVX de exemplo***</span><span class="sxs-lookup"><span data-stu-id="61bf0-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="61bf0-148">Habilite o modo de telefone de área comum para o VVX Polycom seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="61bf0-148">Enable Common Area Phone Mode for the Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="61bf0-149">No seu navegador, use a interface da web para habilitar o modo de COBRIR o VVX</span><span class="sxs-lookup"><span data-stu-id="61bf0-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="61bf0-150">Vá para **configuração** e no Skype para a opção de configuração de negócios, selecione o **Telefone de área comum**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="61bf0-151">Clique em **Sim** para salvar as suas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="61bf0-151">Click **Yes** to save your configuration settings.</span></span>

<span data-ttu-id="61bf0-152">Agora que o modo de telefone COBRIR estiver habilitado, configure o telefone usando a exibição do telefone.</span><span class="sxs-lookup"><span data-stu-id="61bf0-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="61bf0-153">A exibição deve mostrar "CaAP está habilitado".</span><span class="sxs-lookup"><span data-stu-id="61bf0-153">The display should show "CaAP is enabled."</span></span>

1. <span data-ttu-id="61bf0-154">Clique em **configurações**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-154">Click **Settings**.</span></span>
2. <span data-ttu-id="61bf0-155">Selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-155">Select **Advanced**.</span></span>
3. <span data-ttu-id="61bf0-156">Insira a senha.</span><span class="sxs-lookup"><span data-stu-id="61bf0-156">Enter the password.</span></span>
4. <span data-ttu-id="61bf0-157">Nas configurações de administração, selecione **Configurações de telefone de área comum**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-157">In Administration settings, select **Common Area Phone Settings**.</span></span>
5. <span data-ttu-id="61bf0-158">Habilite **COBRIR** e **modo COBRIR Admin**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-158">Enable **CAP** and **CAP Admin Mode**.</span></span>
6. <span data-ttu-id="61bf0-159">Clique em **Salvar o arquivo Config**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-159">Click **Save Config**.</span></span>

<span data-ttu-id="61bf0-160">Seu telefone está pronto para ser provisionados, o qual você vai fazer quando você entrar na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="61bf0-160">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="61bf0-161">Entrar, selecionando **configurações** > **recursos** > **Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="61bf0-161">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
2. <span data-ttu-id="61bf0-162">Selecione **As credenciais do usuário**e, em seguida, selecione **entrar na web (COBRIR)** para gerar um código..</span><span class="sxs-lookup"><span data-stu-id="61bf0-162">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="61bf0-163">Vá para o portal do provisionamento em http://aka.ms/skypecape entrar como **admin**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-163">Go to the provisioning portal at http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="61bf0-164">Insira o nome de exibição (por exemplo, Main recepção) para exibir seu limite.</span><span class="sxs-lookup"><span data-stu-id="61bf0-164">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="61bf0-165">[Nota] Se "Pesquisa para telefones de área comum apenas" estiver marcada, desmarque a caixa de seleção e pesquisar novamente.</span><span class="sxs-lookup"><span data-stu-id="61bf0-165">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="61bf0-166">Na janela de código de emparelhamento, insira o código exibido no telefone e clique em **fornecimento**.</span><span class="sxs-lookup"><span data-stu-id="61bf0-166">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="61bf0-167">Após essa última etapa, o telefone deve entrar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="61bf0-167">Following this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="61bf0-168">Saiba mais sobre os telefones disponíveis em [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span><span class="sxs-lookup"><span data-stu-id="61bf0-168">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


