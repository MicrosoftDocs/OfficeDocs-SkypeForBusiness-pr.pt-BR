---
title: Configurar um console de Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar e configurar o console das Salas do Microsoft Teams e seus periféricos.
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117569"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="359bd-103">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="359bd-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="359bd-104">Este artigo descreve como configurar o console do Microsoft Teams Rooms e seus periféricos.</span><span class="sxs-lookup"><span data-stu-id="359bd-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="359bd-105">Você só deve executar essas etapas se as contas necessárias do Microsoft Teams ou do Skype for Business e do Exchange já foram criadas e testadas conforme descrito em [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="359bd-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="359bd-106">Você precisará do hardware e software descritos nos [requisitos de Salas do Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="359bd-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="359bd-107">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="359bd-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="359bd-108">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="359bd-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="359bd-109">Instalar um certificado ca privado no console</span><span class="sxs-lookup"><span data-stu-id="359bd-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="359bd-110">Instalar o Windows 10 e o aplicativo de console do Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="359bd-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="359bd-111">Configuração inicial do console</span><span class="sxs-lookup"><span data-stu-id="359bd-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="359bd-112">Lista de verificação de implantação do Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="359bd-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="359bd-113">As Salas do Microsoft Teams só funcionarão em um ambiente do Microsoft Teams ou skype for Business configurado corretamente, onde as contas de dispositivo são configuradas corretamente, conforme descrito em [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="359bd-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="359bd-114">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="359bd-114">Prepare the installation media</span></span>
<span data-ttu-id="359bd-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="359bd-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="359bd-116">A instalação do aplicativo de console salas do Microsoft Teams requer um dispositivo de armazenamento USB com pelo menos 32 GB de capacidade.</span><span class="sxs-lookup"><span data-stu-id="359bd-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="359bd-117">Não deve haver outros arquivos no dispositivo; todos os arquivos existentes no armazenamento USB serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="359bd-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="359bd-118">A falha ao criar a mídia de instalação do Microsoft Teams Rooms de acordo com essas instruções provavelmente resultará em comportamento inesperado.</span><span class="sxs-lookup"><span data-stu-id="359bd-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="359bd-119">O processo a seguir é para criar mídia de instalação para imagem de novos dispositivos do Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="359bd-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="359bd-120">Dispositivos existentes, por padrão, são atualizados automaticamente do Windows Update e da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="359bd-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="359bd-121">A máquina do Windows 10 usada para criar a mídia de instalação do Microsoft Teams Rooms deve estar na mesma versão ou posterior do Windows que a mídia de instalação de destino.</span><span class="sxs-lookup"><span data-stu-id="359bd-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="359bd-122">Baixe o [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="359bd-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="359bd-123">Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.</span><span class="sxs-lookup"><span data-stu-id="359bd-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="359bd-124">Siga as instruções do script para criar um disco de configuração USB de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="359bd-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="359bd-125">Sempre que o script CreateSrsMedia.ps1 for iniciado, a saída de tela incluirá o nome de um arquivo de log ou transcrição da sessão.</span><span class="sxs-lookup"><span data-stu-id="359bd-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="359bd-126">Se houver problemas com a execução do script, certifique-se de ter uma cópia dessa transcrição disponível ao solicitar suporte.</span><span class="sxs-lookup"><span data-stu-id="359bd-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="359bd-127">O CreateSrsMedia.ps1 script automatiza as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="359bd-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="359bd-128">Baixe o instalador MSI mais recente para Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="359bd-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="359bd-129">Determine a com build do Windows que o usuário deve fornecer.</span><span class="sxs-lookup"><span data-stu-id="359bd-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="359bd-130">As versões lançadas mais recentemente podem ou não ser testadas e suportadas para uso com dispositivos Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="359bd-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="359bd-131">Baixe os componentes de suporte necessários.</span><span class="sxs-lookup"><span data-stu-id="359bd-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="359bd-132">Montar os componentes necessários na mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="359bd-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="359bd-133">Uma versão específica do Windows 10 é necessária e essa versão só está disponível para clientes de licenciamento por volume.</span><span class="sxs-lookup"><span data-stu-id="359bd-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="359bd-134">Você pode obter uma cópia do Centro de [Serviços de Licenciamento por Volume.](https://www.microsoft.com/Licensing/servicecenter/)</span><span class="sxs-lookup"><span data-stu-id="359bd-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="359bd-135">Quando terminar, remova o disco USB do computador e prossiga para [Instalar o Windows 10 e](console.md#Reimage)o aplicativo de console salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="359bd-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="359bd-136">Instalar o Windows 10 e o aplicativo de console do Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="359bd-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="359bd-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="359bd-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="359bd-138">Agora você precisa aplicar a mídia de instalação criada.</span><span class="sxs-lookup"><span data-stu-id="359bd-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="359bd-139">O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido para executar apenas o aplicativo de console salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="359bd-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="359bd-140">Se o dispositivo de destino for instalado em um dock (por exemplo, um Surface Pro), desconecte-o do dock.</span><span class="sxs-lookup"><span data-stu-id="359bd-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="359bd-141">Verifique se o dispositivo de destino não está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="359bd-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="359bd-142">Verifique se o dispositivo de destino está conectado à energia ac.</span><span class="sxs-lookup"><span data-stu-id="359bd-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="359bd-143">Conecte seu disco de configuração USB ao dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="359bd-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="359bd-144">Inicializar no disco de configuração USB.</span><span class="sxs-lookup"><span data-stu-id="359bd-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="359bd-145">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="359bd-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="359bd-146">Se o dispositivo de destino for um Surface Pro, use as etapas a seguir para inicializar no disco de configuração USB:</span><span class="sxs-lookup"><span data-stu-id="359bd-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="359bd-147">a.</span><span class="sxs-lookup"><span data-stu-id="359bd-147">a.</span></span> <span data-ttu-id="359bd-148">Pressione e continue a segurar o botão de volume para baixo (-).</span><span class="sxs-lookup"><span data-stu-id="359bd-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="359bd-149">b.</span><span class="sxs-lookup"><span data-stu-id="359bd-149">b.</span></span> <span data-ttu-id="359bd-150">Pressione e solte o botão de energia.</span><span class="sxs-lookup"><span data-stu-id="359bd-150">Press and release the power button.</span></span>

    <span data-ttu-id="359bd-151">c.</span><span class="sxs-lookup"><span data-stu-id="359bd-151">c.</span></span> <span data-ttu-id="359bd-152">Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).</span><span class="sxs-lookup"><span data-stu-id="359bd-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="359bd-153">O sistema será desligado depois que a instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="359bd-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="359bd-154">Depois que o sistema for desligado, é seguro remover o disco de configuração USB.</span><span class="sxs-lookup"><span data-stu-id="359bd-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="359bd-155">Neste ponto, você pode colocar o dispositivo de destino em seu encaixe (se estiver usando um produto baseado em dock), anexar os periféricos necessários para sua sala de reunião e se conectar à rede.</span><span class="sxs-lookup"><span data-stu-id="359bd-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="359bd-156">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="359bd-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="359bd-157">As atualizações de software para Salas do Microsoft Teams são baixadas automaticamente da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="359bd-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="359bd-158">Consulte [Pré-requisitos da Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business) e Educação para verificar se o console de sala poderá acessar a loja e a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="359bd-158">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="359bd-159">Selecionar um idioma</span><span class="sxs-lookup"><span data-stu-id="359bd-159">Selecting a language</span></span> 

<span data-ttu-id="359bd-160">Na Atualização do Criador, você precisará usar o script ApplyCurrentRegionAndLanguage.ps1 em cenários em que a seleção implícita de idioma não fornece ao usuário o idioma real do aplicativo que deseja (por exemplo, eles querem que o aplicativo de console seja usado em francês, mas está chegando em inglês).</span><span class="sxs-lookup"><span data-stu-id="359bd-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="359bd-161">As instruções a seguir funcionam apenas para consoles criados usando a Atualização do Windows Creator.</span><span class="sxs-lookup"><span data-stu-id="359bd-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="359bd-162">Os sistemas herdado/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não poderão usar essas instruções, mas também não devem sofrer com o problema inicial que exige essa intervenção manual (a Edição de Aniversário permite que você escolha explicitamente o idioma do aplicativo como parte da instalação).</span><span class="sxs-lookup"><span data-stu-id="359bd-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="359bd-163">Para aplicar o idioma desejado</span><span class="sxs-lookup"><span data-stu-id="359bd-163">To apply your desired language</span></span>

1. <span data-ttu-id="359bd-164">Mude para o modo de Administrador.</span><span class="sxs-lookup"><span data-stu-id="359bd-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="359bd-165">Selecione o menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="359bd-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="359bd-166">Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="359bd-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="359bd-167">Selecione **Idioma &amp; de hora**.</span><span class="sxs-lookup"><span data-stu-id="359bd-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="359bd-168">Selecione **Idioma &amp; de região**.</span><span class="sxs-lookup"><span data-stu-id="359bd-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="359bd-169">Selecione **Adicionar um idioma**.</span><span class="sxs-lookup"><span data-stu-id="359bd-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="359bd-170">Selecione o idioma que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="359bd-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="359bd-171">Selecione o idioma que você acabou de adicionar à lista "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="359bd-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="359bd-172">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="359bd-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="359bd-173">Para idiomas que deseja remover:</span><span class="sxs-lookup"><span data-stu-id="359bd-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="359bd-p115">a. Selecione o idioma que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="359bd-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="359bd-p116">b. Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="359bd-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="359bd-178">Inicie um prompt de comandos com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="359bd-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="359bd-179">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="359bd-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="359bd-180">Reinicie o sistema.</span><span class="sxs-lookup"><span data-stu-id="359bd-180">Restart the system.</span></span>
    
<span data-ttu-id="359bd-181">Seu idioma desejado agora é aplicado ao console de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="359bd-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="359bd-182">Configuração inicial do console</span><span class="sxs-lookup"><span data-stu-id="359bd-182">Initial set up of the console</span></span>
<span data-ttu-id="359bd-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="359bd-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="359bd-184">Depois que o Windows for instalado, o aplicativo de console do Microsoft Teams Rooms entrará em seu processo inicial de Instalação quando for iniciado em seguida ou se a opção /reboot foi escolhida.</span><span class="sxs-lookup"><span data-stu-id="359bd-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="359bd-185">A tela Conta de Usuário é exibida.</span><span class="sxs-lookup"><span data-stu-id="359bd-185">The User Account screen appears.</span></span> <span data-ttu-id="359bd-186">Insira o endereço de entrada do Skype (user@domain formato) da conta de sala a ser usada com o console.</span><span class="sxs-lookup"><span data-stu-id="359bd-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="359bd-187">Digite a senha para a conta da sala e digite-a novamente para verificar.</span><span class="sxs-lookup"><span data-stu-id="359bd-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="359bd-188">Em "Configurar Domínio", de definir o FQDN para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="359bd-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="359bd-189">Se o domínio SIP do Skype for Business for diferente do domínio exchange do usuário, insira o domínio exchange neste campo.</span><span class="sxs-lookup"><span data-stu-id="359bd-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="359bd-190">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="359bd-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="359bd-191">Selecione os dispositivos indicados na tela Recursos e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="359bd-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="359bd-192">O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado.</span><span class="sxs-lookup"><span data-stu-id="359bd-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="359bd-193">Os dispositivos para selecionar são:</span><span class="sxs-lookup"><span data-stu-id="359bd-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="359bd-194">Microfone para conferência: o microfone padrão para a sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="359bd-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="359bd-195">Alto-falante para conferência: o alto-falante padrão para conferência </span><span class="sxs-lookup"><span data-stu-id="359bd-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="359bd-196">Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.</span><span class="sxs-lookup"><span data-stu-id="359bd-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="359bd-p120">Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="359bd-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="359bd-199">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="359bd-199">Click **Finish**.</span></span>
    
<span data-ttu-id="359bd-200">O aplicativo de console salas do Microsoft Teams deve começar a entrar imediatamente no Skype for Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com o Exchange usando essas mesmas credenciais.</span><span class="sxs-lookup"><span data-stu-id="359bd-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="359bd-201">Para obter detalhes sobre como usar o aplicativo de console, consulte a ajuda salas [do Microsoft Teams.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)</span><span class="sxs-lookup"><span data-stu-id="359bd-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="359bd-202">As Salas do Microsoft Teams se baseam na presença de hardware de console certificado.</span><span class="sxs-lookup"><span data-stu-id="359bd-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="359bd-203">Mesmo uma imagem criada corretamente contendo o aplicativo de console do Microsoft Teams Rooms não será inicializada após o procedimento de instalação inicial, a menos que o hardware do console seja detectado.</span><span class="sxs-lookup"><span data-stu-id="359bd-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="359bd-204">Para soluções baseadas no Surface Pro, o Surface Pro deve estar conectado ao hardware de encaixe que acompanha para passar essa verificação.</span><span class="sxs-lookup"><span data-stu-id="359bd-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="359bd-205">Alguns usuários de idiomas que não são do inglês podem precisar de um teclado físico conectado ao console durante a configuração inicial, caso os símbolos não sejam suportados no teclado por toque.</span><span class="sxs-lookup"><span data-stu-id="359bd-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="359bd-206">Instalar um certificado ca privado no console</span><span class="sxs-lookup"><span data-stu-id="359bd-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="359bd-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="359bd-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="359bd-208">O console de Salas do Microsoft Teams precisa confiar nos certificados usados pelos servidores aos que ele se conecta.</span><span class="sxs-lookup"><span data-stu-id="359bd-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="359bd-209">No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="359bd-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="359bd-210">Em um caso em que a Autoridade de Certificação é privada, por exemplo, uma implantação local com o Active Directory e a Autoridade de Certificação do Windows, você pode adicionar o certificado ao console das Salas do Microsoft Teams de algumas maneiras:</span><span class="sxs-lookup"><span data-stu-id="359bd-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="359bd-211">Você pode ingressar o console no Active Directory e isso adicionará automaticamente os certificados necessários, uma vez que a Autoridade de Certificação é publicada no Active Directory (opção de implantação normal).</span><span class="sxs-lookup"><span data-stu-id="359bd-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="359bd-212">Você pode instalar o certificado manualmente após o processo de geração de imagens.</span><span class="sxs-lookup"><span data-stu-id="359bd-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="359bd-213">Antes de fazer isso, você deve concluir [a configuração inicial do console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="359bd-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="359bd-214">Para instalar o certificado manualmente </span><span class="sxs-lookup"><span data-stu-id="359bd-214">To manually install the certificate</span></span>

1. <span data-ttu-id="359bd-215">Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="359bd-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="359bd-216">Coloque o console no modo de administração (consulte [Admin mode and device management](rooms-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="359bd-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="359bd-217">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="359bd-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="359bd-218">Ingressar em um domínio do Active Directory (Opcional)</span><span class="sxs-lookup"><span data-stu-id="359bd-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="359bd-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="359bd-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="359bd-220">Você pode ingressar nos consoles das Salas do Microsoft Teams no seu domínio.</span><span class="sxs-lookup"><span data-stu-id="359bd-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="359bd-221">Os consoles de Salas do Microsoft Teams devem ser colocados em uma OU separada das estações de trabalho do computador, pois muitas políticas de estação de trabalho não são compatíveis com salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="359bd-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="359bd-222">Um exemplo comum são as políticas de aplicação de senha que impedirão que as Salas do Microsoft Teams sejam insu operacional automaticamente.</span><span class="sxs-lookup"><span data-stu-id="359bd-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="359bd-223">Para obter informações sobre o gerenciamento de configurações de GPO, consulte [Manage Microsoft Teams Rooms](rooms-operations.md).</span><span class="sxs-lookup"><span data-stu-id="359bd-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="359bd-224">Para ingressar as Salas do Microsoft Teams em um domínio</span><span class="sxs-lookup"><span data-stu-id="359bd-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="359bd-225">Entre no console da conta de administrador (consulte [Admin mode and device management](rooms-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="359bd-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="359bd-226">Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.</span><span class="sxs-lookup"><span data-stu-id="359bd-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="359bd-227">Digite o seguinte comando no Powershell:</span><span class="sxs-lookup"><span data-stu-id="359bd-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="359bd-228">Por exemplo, se seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de Salas do Microsoft Teams sejam em uma OU "Salas do Microsoft Teams" que seja filho de uma OU "Resources", o comando será:</span><span class="sxs-lookup"><span data-stu-id="359bd-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="359bd-229">Se você quiser renomear o computador ao jun-lo a um domínio, use o sinalizador -NewName seguido pelo novo nome do computador.</span><span class="sxs-lookup"><span data-stu-id="359bd-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="359bd-230">Lista de verificação de implantação do Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="359bd-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="359bd-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="359bd-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="359bd-232">Use a seguinte lista de verificação ao fazer uma verificação final de que o console e todos os periféricos estão totalmente configurados:</span><span class="sxs-lookup"><span data-stu-id="359bd-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="359bd-233">**Configurações do aplicativo**</span><span class="sxs-lookup"><span data-stu-id="359bd-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="359bd-234">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-234">☐</span></span>  <br/> |<span data-ttu-id="359bd-235">O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console</span><span class="sxs-lookup"><span data-stu-id="359bd-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="359bd-236">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-236">☐</span></span>  <br/> |<span data-ttu-id="359bd-237">O nome do computador Windows está definido corretamente (útil para administração remota)</span><span class="sxs-lookup"><span data-stu-id="359bd-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="359bd-238">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-238">☐</span></span>  <br/> |<span data-ttu-id="359bd-239">A senha da conta do administrador foi definida e verificada</span><span class="sxs-lookup"><span data-stu-id="359bd-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="359bd-240">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-240">☐</span></span>  <br/> |<span data-ttu-id="359bd-241">Todas as atualizações de firmware foram aplicadas</span><span class="sxs-lookup"><span data-stu-id="359bd-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="359bd-242">**Periféricos de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="359bd-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="359bd-243">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-243">☐</span></span>  <br/> |<span data-ttu-id="359bd-244">A versão do firmware do periférico da câmera está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="359bd-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="359bd-245">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-245">☐</span></span>  <br/> |<span data-ttu-id="359bd-246">Câmera funcional e posicionada de forma ideal</span><span class="sxs-lookup"><span data-stu-id="359bd-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="359bd-247">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-247">☐</span></span>  <br/> |<span data-ttu-id="359bd-248">Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="359bd-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="359bd-249">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-249">☐</span></span>  <br/> |<span data-ttu-id="359bd-250">Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="359bd-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="359bd-251">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-251">☐</span></span>  <br/> |<span data-ttu-id="359bd-252">A versão do firmware do periférico de áudio está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="359bd-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="359bd-253">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-253">☐</span></span>  <br/> |<span data-ttu-id="359bd-254">Dispositivo de entrada de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="359bd-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="359bd-255">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-255">☐</span></span>  <br/> |<span data-ttu-id="359bd-256">Dispositivo de saída de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="359bd-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="359bd-257">**Encaixe**</span><span class="sxs-lookup"><span data-stu-id="359bd-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="359bd-258">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-258">☐</span></span>  <br/> |<span data-ttu-id="359bd-259">Os cabos estão presos e não estão dobrados</span><span class="sxs-lookup"><span data-stu-id="359bd-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="359bd-260">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-260">☐</span></span>  <br/> |<span data-ttu-id="359bd-261">Ingestão de áudio via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="359bd-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="359bd-262">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-262">☐</span></span>  <br/> |<span data-ttu-id="359bd-263">Ingestão de vídeo via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="359bd-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="359bd-264">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-264">☐</span></span>  <br/> |<span data-ttu-id="359bd-265">O encaixe pode girar livremente</span><span class="sxs-lookup"><span data-stu-id="359bd-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="359bd-266">☐</span><span class="sxs-lookup"><span data-stu-id="359bd-266">☐</span></span>  <br/> |<span data-ttu-id="359bd-267">O brilho da tela é aceitável para o ambiente</span><span class="sxs-lookup"><span data-stu-id="359bd-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="359bd-268">Confira também</span><span class="sxs-lookup"><span data-stu-id="359bd-268">See also</span></span>
<span data-ttu-id="359bd-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="359bd-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="359bd-270">Planejar as Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="359bd-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="359bd-271">Implantar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="359bd-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="359bd-272">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="359bd-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="359bd-273">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="359bd-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)