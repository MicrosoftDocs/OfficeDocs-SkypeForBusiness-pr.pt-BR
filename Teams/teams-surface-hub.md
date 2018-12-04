---
title: Implantar as equipes da Microsoft para o Hub de superfície
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Defina configurações de administração for Microsoft Teams para o Hub de superfície.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2018
ms.locfileid: "27131999"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="24a28-103">Implantar as equipes da Microsoft para o Hub de superfície</span><span class="sxs-lookup"><span data-stu-id="24a28-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="24a28-104">Antes de implantar Teams da Microsoft para Microsoft Surface Hub, certifique-se de que você cumpre o hardware, sistema operacional e outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="24a28-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="24a28-105">Para obter mais informações, consulte o [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="24a28-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

> [!NOTE]
> <span data-ttu-id="24a28-106">Se você estiver fazer a transição do Skype para Business Online, será necessário confirmar que uma licença do Microsoft Teams é atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="24a28-106">If you are transitioning from Skype for Business Online, you need to confirm that a Microsoft Teams license is assigned to the user.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="24a28-107">Instalar equipes para o Hub de superfície do repositório de Microsoft</span><span class="sxs-lookup"><span data-stu-id="24a28-107">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="24a28-108">Essas instruções são para a instalação de equipes para o Hub de superfície do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="24a28-108">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="24a28-109">Inicie o repositório da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="24a28-109">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="24a28-110">a.</span><span class="sxs-lookup"><span data-stu-id="24a28-110">a.</span></span> <span data-ttu-id="24a28-111">Toque em **Iniciar** > **todos os aplicativos** > **configurações**.</span><span class="sxs-lookup"><span data-stu-id="24a28-111">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="24a28-112">b.</span><span class="sxs-lookup"><span data-stu-id="24a28-112">b.</span></span> <span data-ttu-id="24a28-113">Toque em **conta de dispositivo do Hub de superfície, gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="24a28-113">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="24a28-114">c.</span><span class="sxs-lookup"><span data-stu-id="24a28-114">c.</span></span> <span data-ttu-id="24a28-115">À esquerda, toque em da guia **aplicativos e recursos** .</span><span class="sxs-lookup"><span data-stu-id="24a28-115">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="24a28-116">d.</span><span class="sxs-lookup"><span data-stu-id="24a28-116">d.</span></span> <span data-ttu-id="24a28-117">À direita, toque no botão **Abrir armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="24a28-117">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="24a28-118">Do Microsoft Store, procure *As equipes da Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="24a28-118">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="24a28-119">As **Equipes da Microsoft para o Hub de superfície** será exibida.</span><span class="sxs-lookup"><span data-stu-id="24a28-119">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="24a28-120">Toque no botão **obter o aplicativo** para instalar.</span><span class="sxs-lookup"><span data-stu-id="24a28-120">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="24a28-121">Quando a instalação estiver concluída, reinicie o Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="24a28-121">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="24a28-122">Não toque na **inicialização** do repositório de página de listagem.</span><span class="sxs-lookup"><span data-stu-id="24a28-122">Do not tap **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="24a28-123">Tornar as equipes a chamada padrão e a aplicação de reuniões</span><span class="sxs-lookup"><span data-stu-id="24a28-123">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="24a28-124">Há duas opções para configurar a política padrão de aplicativo de chamada e reuniões:</span><span class="sxs-lookup"><span data-stu-id="24a28-124">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="24a28-125">**Opção 1**: configurar via chave USB.</span><span class="sxs-lookup"><span data-stu-id="24a28-125">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="24a28-126">**Opção 2**: configurar via MDM como Intune.</span><span class="sxs-lookup"><span data-stu-id="24a28-126">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="24a28-127">Opção 1: Configurar via chave USB</span><span class="sxs-lookup"><span data-stu-id="24a28-127">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="24a28-128">Os pacotes podem ser encontrados na [página de download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="24a28-128">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="24a28-129">Selecione a adequada para o pacote que você estiver planejando instalar e copiá-lo para uma chave USB.</span><span class="sxs-lookup"><span data-stu-id="24a28-129">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="24a28-130">O arquivo .ppkg correto a ser usado depende a diretiva de aplicação de padrão que você gostaria de aplicar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="24a28-130">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="24a28-131">Número</span><span class="sxs-lookup"><span data-stu-id="24a28-131">Number</span></span>  |<span data-ttu-id="24a28-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="24a28-132">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="24a28-133">0</span><span class="sxs-lookup"><span data-stu-id="24a28-133">0</span></span>     | <span data-ttu-id="24a28-134">App preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="24a28-134">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="24a28-135">1</span><span class="sxs-lookup"><span data-stu-id="24a28-135">1</span></span>     | <span data-ttu-id="24a28-136">As equipes de app preferencial na tela Iniciar, Skype reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="24a28-136">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="24a28-137">2</span><span class="sxs-lookup"><span data-stu-id="24a28-137">2</span></span>     | <span data-ttu-id="24a28-138">Equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível)</span><span class="sxs-lookup"><span data-stu-id="24a28-138">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="24a28-139">Anexe a chave USB com o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="24a28-139">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="24a28-140">Abra o aplicativo de **configurações** em um dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="24a28-140">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="24a28-141">Abra o **gerenciamento de contas de dispositivo do Hub de superfície**.</span><span class="sxs-lookup"><span data-stu-id="24a28-141">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="24a28-142">Abra o **gerenciamento de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="24a28-142">Open **Device Management**.</span></span> 
5. <span data-ttu-id="24a28-143">Clique em **Adicionar ou remover um pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="24a28-143">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="24a28-144">Clique em **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="24a28-144">Click **Add Package**.</span></span>
7. <span data-ttu-id="24a28-145">Selecione a opção de **Mídia removível** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="24a28-145">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="24a28-146">Adicione o pacote adequado <strong>TeamsRTMMode\*.ppkg</strong> que anteriormente foi copiado para a chave USB.</span><span class="sxs-lookup"><span data-stu-id="24a28-146">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="24a28-147">Reinicie o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="24a28-147">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="24a28-148">Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário.</span><span class="sxs-lookup"><span data-stu-id="24a28-148">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="24a28-149">Opção 2: Configurar via MDM como Intune</span><span class="sxs-lookup"><span data-stu-id="24a28-149">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="24a28-150">Use o seguinte para configurar a chamada e reuniões aplicativo política padrão via Intune.</span><span class="sxs-lookup"><span data-stu-id="24a28-150">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="24a28-151">Consulte também o blog, [implantar as equipes da Microsoft para aplicativo de superfície Hub usando Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="24a28-151">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="24a28-152">Configuração</span><span class="sxs-lookup"><span data-stu-id="24a28-152">Setting</span></span>   |<span data-ttu-id="24a28-153">Valor</span><span class="sxs-lookup"><span data-stu-id="24a28-153">Value</span></span>    |<span data-ttu-id="24a28-154">Descrição</span><span class="sxs-lookup"><span data-stu-id="24a28-154">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="24a28-155">Path</span><span class="sxs-lookup"><span data-stu-id="24a28-155">Path</span></span>      | <span data-ttu-id="24a28-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="24a28-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="24a28-157">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="24a28-157">Data Type</span></span> | <span data-ttu-id="24a28-158">inteiro (0-2)</span><span class="sxs-lookup"><span data-stu-id="24a28-158">integer (0-2)</span></span>   |<span data-ttu-id="24a28-159">0 - app preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="24a28-159">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="24a28-160">1 - equipes preferencial app na tela Iniciar, Skype reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="24a28-160">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="24a28-161">2 - equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível)</span><span class="sxs-lookup"><span data-stu-id="24a28-161">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="24a28-162">Operações</span><span class="sxs-lookup"><span data-stu-id="24a28-162">Operations</span></span>| <span data-ttu-id="24a28-163">Obter, definir</span><span class="sxs-lookup"><span data-stu-id="24a28-163">Get, Set</span></span>        |

|<span data-ttu-id="24a28-164">Configuração</span><span class="sxs-lookup"><span data-stu-id="24a28-164">Setting</span></span>   |<span data-ttu-id="24a28-165">Valor</span><span class="sxs-lookup"><span data-stu-id="24a28-165">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="24a28-166">Path</span><span class="sxs-lookup"><span data-stu-id="24a28-166">Path</span></span>      | <span data-ttu-id="24a28-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="24a28-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="24a28-168">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="24a28-168">Data Type</span></span> | <span data-ttu-id="24a28-169">cadeia de caracteres - conjunto de cadeia de caracteres para a ID do pacote de aplicativo de equipes como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! As equipes**</span><span class="sxs-lookup"><span data-stu-id="24a28-169">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="24a28-170">Operações</span><span class="sxs-lookup"><span data-stu-id="24a28-170">Operations</span></span>| <span data-ttu-id="24a28-171">Obter, definir</span><span class="sxs-lookup"><span data-stu-id="24a28-171">Get, Set</span></span>        |

<span data-ttu-id="24a28-172">Reinicie o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="24a28-172">Restart the Surface Hub device.</span></span> <span data-ttu-id="24a28-173">Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário.</span><span class="sxs-lookup"><span data-stu-id="24a28-173">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

