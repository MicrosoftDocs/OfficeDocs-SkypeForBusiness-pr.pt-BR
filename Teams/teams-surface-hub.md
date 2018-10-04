---
title: Implantar as equipes da Microsoft para o Hub de superfície
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 09/26/2018
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
ms.openlocfilehash: aca03693a7abea6e26f175cc49f0142894749160
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372177"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="8d206-103">Implantar as equipes da Microsoft para o Hub de superfície</span><span class="sxs-lookup"><span data-stu-id="8d206-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="8d206-104">Antes de implantar Teams da Microsoft para Microsoft Surface Hub, certifique-se de que você cumpre o hardware, sistema operacional e outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="8d206-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="8d206-105">Para obter mais informações, consulte o [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="8d206-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="8d206-106">Instalar equipes para o Hub de superfície do repositório de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d206-106">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="8d206-107">Essas instruções são para a instalação de equipes para o Hub de superfície do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="8d206-107">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="8d206-108">Inicie o repositório da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="8d206-108">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="8d206-109">a.</span><span class="sxs-lookup"><span data-stu-id="8d206-109">a.</span></span> <span data-ttu-id="8d206-110">Toque em **Iniciar** > **todos os aplicativos** > **configurações**.</span><span class="sxs-lookup"><span data-stu-id="8d206-110">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="8d206-111">b.</span><span class="sxs-lookup"><span data-stu-id="8d206-111">b.</span></span> <span data-ttu-id="8d206-112">Toque em **conta de dispositivo do Hub de superfície, gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="8d206-112">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="8d206-113">c.</span><span class="sxs-lookup"><span data-stu-id="8d206-113">c.</span></span> <span data-ttu-id="8d206-114">À esquerda, toque em da guia **aplicativos e recursos** .</span><span class="sxs-lookup"><span data-stu-id="8d206-114">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="8d206-115">d.</span><span class="sxs-lookup"><span data-stu-id="8d206-115">d.</span></span> <span data-ttu-id="8d206-116">À direita, toque no botão **Abrir armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="8d206-116">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="8d206-117">Do Microsoft Store, procure *As equipes da Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="8d206-117">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="8d206-118">As **Equipes da Microsoft para o Hub de superfície** será exibida.</span><span class="sxs-lookup"><span data-stu-id="8d206-118">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="8d206-119">Toque no botão **obter o aplicativo** para instalar.</span><span class="sxs-lookup"><span data-stu-id="8d206-119">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="8d206-120">Quando a instalação estiver concluída, reinicie o Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="8d206-120">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="8d206-121">Não toque no **início** do repositório de página de listagem.</span><span class="sxs-lookup"><span data-stu-id="8d206-121">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="8d206-122">Tornar as equipes a chamada padrão e a aplicação de reuniões</span><span class="sxs-lookup"><span data-stu-id="8d206-122">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="8d206-123">Há duas opções para configurar a política padrão de aplicativo de chamada e reuniões:</span><span class="sxs-lookup"><span data-stu-id="8d206-123">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="8d206-124">**Opção 1**: configurar via chave USB.</span><span class="sxs-lookup"><span data-stu-id="8d206-124">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="8d206-125">**Opção 2**: configurar via MDM como Intune.</span><span class="sxs-lookup"><span data-stu-id="8d206-125">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="8d206-126">Opção 1: Configurar via chave USB</span><span class="sxs-lookup"><span data-stu-id="8d206-126">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="8d206-127">Os pacotes podem ser encontrados na [página de download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="8d206-127">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="8d206-128">Selecione a adequada para o pacote que você estiver planejando instalar e copiá-lo para uma chave USB.</span><span class="sxs-lookup"><span data-stu-id="8d206-128">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="8d206-129">O arquivo .ppkg correto a ser usado depende a diretiva de aplicação de padrão que você gostaria de aplicar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8d206-129">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="8d206-130">Número</span><span class="sxs-lookup"><span data-stu-id="8d206-130">Number</span></span>  |<span data-ttu-id="8d206-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d206-131">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="8d206-132">0</span><span class="sxs-lookup"><span data-stu-id="8d206-132">0</span></span>     | <span data-ttu-id="8d206-133">App preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="8d206-133">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="8d206-134">1</span><span class="sxs-lookup"><span data-stu-id="8d206-134">1</span></span>     | <span data-ttu-id="8d206-135">As equipes de app preferencial na tela Iniciar, Skype reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="8d206-135">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="8d206-136">2</span><span class="sxs-lookup"><span data-stu-id="8d206-136">2</span></span>     | <span data-ttu-id="8d206-137">Equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível)</span><span class="sxs-lookup"><span data-stu-id="8d206-137">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="8d206-138">Anexe a chave USB com o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="8d206-138">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="8d206-139">Abra o aplicativo de **configurações** em um dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="8d206-139">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="8d206-140">Abra o **gerenciamento de contas de dispositivo do Hub de superfície**.</span><span class="sxs-lookup"><span data-stu-id="8d206-140">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="8d206-141">Abra o **gerenciamento de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8d206-141">Open **Device Management**.</span></span> 
5. <span data-ttu-id="8d206-142">Clique em **Adicionar ou remover um pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="8d206-142">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="8d206-143">Clique em **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="8d206-143">Click **Add Package**.</span></span>
7. <span data-ttu-id="8d206-144">Selecione a opção de **Mídia removível** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="8d206-144">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="8d206-145">Adicione o pacote adequado <strong>TeamsRTMMode\*.ppkg</strong> que anteriormente foi copiado para a chave USB.</span><span class="sxs-lookup"><span data-stu-id="8d206-145">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="8d206-146">Reinicie o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="8d206-146">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="8d206-147">Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário.</span><span class="sxs-lookup"><span data-stu-id="8d206-147">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="8d206-148">Opção 2: Configurar via MDM como Intune</span><span class="sxs-lookup"><span data-stu-id="8d206-148">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="8d206-149">Use o seguinte para configurar a chamada e reuniões aplicativo política padrão via Intune.</span><span class="sxs-lookup"><span data-stu-id="8d206-149">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="8d206-150">Consulte também o blog, [implantar as equipes da Microsoft para aplicativo de superfície Hub usando Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span><span class="sxs-lookup"><span data-stu-id="8d206-150">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="8d206-151">Configuração</span><span class="sxs-lookup"><span data-stu-id="8d206-151">Setting</span></span>   |<span data-ttu-id="8d206-152">Valor</span><span class="sxs-lookup"><span data-stu-id="8d206-152">Value</span></span>    |<span data-ttu-id="8d206-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d206-153">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="8d206-154">Path</span><span class="sxs-lookup"><span data-stu-id="8d206-154">Path</span></span>      | <span data-ttu-id="8d206-155">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="8d206-155">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="8d206-156">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8d206-156">Data Type</span></span> | <span data-ttu-id="8d206-157">inteiro (0-2)</span><span class="sxs-lookup"><span data-stu-id="8d206-157">integer (0-2)</span></span>   |<span data-ttu-id="8d206-158">0 - app preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="8d206-158">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="8d206-159">1 - equipes preferencial app na tela Iniciar, Skype reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="8d206-159">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="8d206-160">2 - equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível)</span><span class="sxs-lookup"><span data-stu-id="8d206-160">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="8d206-161">Operações</span><span class="sxs-lookup"><span data-stu-id="8d206-161">Operations</span></span>| <span data-ttu-id="8d206-162">Obter, definir</span><span class="sxs-lookup"><span data-stu-id="8d206-162">Get, Set</span></span>        |

|<span data-ttu-id="8d206-163">Configuração</span><span class="sxs-lookup"><span data-stu-id="8d206-163">Setting</span></span>   |<span data-ttu-id="8d206-164">Valor</span><span class="sxs-lookup"><span data-stu-id="8d206-164">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="8d206-165">Path</span><span class="sxs-lookup"><span data-stu-id="8d206-165">Path</span></span>      | <span data-ttu-id="8d206-166">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="8d206-166">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="8d206-167">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8d206-167">Data Type</span></span> | <span data-ttu-id="8d206-168">cadeia de caracteres - conjunto de cadeia de caracteres para a ID do pacote de aplicativo de equipes como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! As equipes**</span><span class="sxs-lookup"><span data-stu-id="8d206-168">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="8d206-169">Operações</span><span class="sxs-lookup"><span data-stu-id="8d206-169">Operations</span></span>| <span data-ttu-id="8d206-170">Obter, definir</span><span class="sxs-lookup"><span data-stu-id="8d206-170">Get, Set</span></span>        |

<span data-ttu-id="8d206-171">Reinicie o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="8d206-171">Restart the Surface Hub device.</span></span> <span data-ttu-id="8d206-172">Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário.</span><span class="sxs-lookup"><span data-stu-id="8d206-172">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

