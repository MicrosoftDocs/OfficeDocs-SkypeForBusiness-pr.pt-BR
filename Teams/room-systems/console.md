---
title: Configurar um console de salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console de salas do Microsoft Teams e seus periféricos.
ms.openlocfilehash: 820921cdcf35f4c4072dae3b2029527b98454dc5
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493049"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="08c96-103">Configurar um console de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="08c96-104">Este artigo descreve como configurar o console de salas do Microsoft Teams e seus periféricos.</span><span class="sxs-lookup"><span data-stu-id="08c96-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="08c96-105">Você deve executar essas etapas somente se as contas necessárias do Microsoft Teams ou do Skype for Business e do Exchange já tiverem sido criadas e testadas, conforme descrito em [implantar salas do Microsoft Teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="08c96-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="08c96-106">Você precisará do hardware e do software descritos nos [requisitos de sala do Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08c96-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="08c96-107">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="08c96-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="08c96-108">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="08c96-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="08c96-109">Instalar um certificado de autoridade de certificação particular no console</span><span class="sxs-lookup"><span data-stu-id="08c96-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="08c96-110">Instalar o Windows 10 e o aplicativo de console de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="08c96-111">Configuração inicial do console</span><span class="sxs-lookup"><span data-stu-id="08c96-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="08c96-112">Lista de verificação de implantação de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="08c96-113">As salas do Microsoft Teams funcionarão apenas em um ambiente do Microsoft Teams ou do Skype for Business configurado corretamente, em que as contas do dispositivo são configuradas corretamente, conforme descrito em [implantar salas do Microsoft Teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="08c96-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="08c96-114">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="08c96-114">Prepare the installation media</span></span>
<span data-ttu-id="08c96-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="08c96-115"></span></span>

<span data-ttu-id="08c96-116">A instalação do aplicativo de console de salas do Microsoft Teams requer um dispositivo de armazenamento USB com pelo menos 32GB de capacidade.</span><span class="sxs-lookup"><span data-stu-id="08c96-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="08c96-117">Não deve haver outros arquivos no dispositivo; qualquer arquivo existente no armazenamento USB será perdido.</span><span class="sxs-lookup"><span data-stu-id="08c96-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08c96-118">Falha ao criar a mídia de instalação das salas do Microsoft Teams, de acordo com essas instruções, provavelmente resultará em um comportamento inesperado.</span><span class="sxs-lookup"><span data-stu-id="08c96-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="08c96-119">O processo abaixo destina-se à criação de mídia de instalação em imagens de novos dispositivos de sala do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08c96-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="08c96-120">Os dispositivos existentes, por padrão, são atualizados automaticamente no Windows Update e na Windows Store.</span><span class="sxs-lookup"><span data-stu-id="08c96-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="08c96-121">Baixe o [script CreateSrsMedia. ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="08c96-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="08c96-122">Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.</span><span class="sxs-lookup"><span data-stu-id="08c96-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="08c96-123">Siga as instruções do script para criar um disco de instalação USB de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08c96-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="08c96-124">Toda vez que o script CreateSrsMedia. ps1 for iniciado, a saída da tela incluirá o nome de um arquivo de log ou transcrição para a sessão.</span><span class="sxs-lookup"><span data-stu-id="08c96-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="08c96-125">Se houver problemas com a execução do script, certifique-se de ter uma cópia dessa transcrição disponível ao solicitar suporte.</span><span class="sxs-lookup"><span data-stu-id="08c96-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="08c96-126">O script CreateSrsMedia. ps1 automatiza as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="08c96-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="08c96-127">Baixe a versão mais recente do MSI Installer para salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08c96-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="08c96-128">Determine a compilação do Windows que o usuário deve fornecer.</span><span class="sxs-lookup"><span data-stu-id="08c96-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="08c96-129">As versões lançadas mais recentemente podem ou não ser testadas e com suporte para uso com dispositivos de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08c96-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="08c96-130">Baixe os componentes de suporte necessários.</span><span class="sxs-lookup"><span data-stu-id="08c96-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="08c96-131">Monte os componentes necessários na mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="08c96-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="08c96-132">Uma versão específica do Windows 10 é necessária, e essa versão só está disponível para clientes de licenciamento por volume.</span><span class="sxs-lookup"><span data-stu-id="08c96-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="08c96-133">Você pode obter uma cópia do [centro de serviços](https://www.microsoft.com/Licensing/servicecenter/)de licenciamento por volume.</span><span class="sxs-lookup"><span data-stu-id="08c96-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="08c96-134">Quando terminar, remova o disco USB do computador e prossiga para [instalar o Windows 10 e o aplicativo de console de salas do Microsoft Teams](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="08c96-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="08c96-135">Instalar o Windows 10 e o aplicativo de console de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="08c96-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="08c96-136"></span></span>

<span data-ttu-id="08c96-137">Agora, você precisa aplicar a mídia de configuração que você criou.</span><span class="sxs-lookup"><span data-stu-id="08c96-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="08c96-138">O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido para executar somente o aplicativo de console de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08c96-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="08c96-139">Se o dispositivo de destino for instalado em um Dock (por exemplo, um Surface pro), desconecte-o do Dock.</span><span class="sxs-lookup"><span data-stu-id="08c96-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="08c96-140">Verifique se o dispositivo de destino não está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="08c96-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="08c96-141">Verifique se o dispositivo de destino está conectado à alimentação de CA.</span><span class="sxs-lookup"><span data-stu-id="08c96-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="08c96-142">Conecte o disco de instalação USB ao dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="08c96-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="08c96-143">Inicialize no disco de instalação USB.</span><span class="sxs-lookup"><span data-stu-id="08c96-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="08c96-144">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="08c96-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="08c96-145">Se o seu dispositivo de destino for um Surface pro, use as seguintes etapas para inicializar o disco de instalação USB:</span><span class="sxs-lookup"><span data-stu-id="08c96-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="08c96-146">a.</span><span class="sxs-lookup"><span data-stu-id="08c96-146">a.</span></span> <span data-ttu-id="08c96-147">Pressione e continue a manter pressionado o botão Volume Down (-).</span><span class="sxs-lookup"><span data-stu-id="08c96-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="08c96-148">b.</span><span class="sxs-lookup"><span data-stu-id="08c96-148">b.</span></span> <span data-ttu-id="08c96-149">Pressione e libere o botão de energia.</span><span class="sxs-lookup"><span data-stu-id="08c96-149">Press and release the power button.</span></span>

    <span data-ttu-id="08c96-150">c.</span><span class="sxs-lookup"><span data-stu-id="08c96-150">c.</span></span> <span data-ttu-id="08c96-151">Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).</span><span class="sxs-lookup"><span data-stu-id="08c96-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="08c96-152">O sistema será desligado após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="08c96-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="08c96-153">Após o sistema ser desligado, é seguro remover o disco de instalação USB.</span><span class="sxs-lookup"><span data-stu-id="08c96-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="08c96-154">Nesse ponto, você pode colocar o dispositivo de destino em seu Dock (se estiver usando um produto baseado em encaixe), anexar os periféricos necessários para a sala de reunião e se conectar à rede.</span><span class="sxs-lookup"><span data-stu-id="08c96-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="08c96-155">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="08c96-155">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="08c96-156">As atualizações de software para salas do Microsoft Teams são automaticamente baixadas da Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="08c96-156">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="08c96-157">Veja [pré-requisitos para a Microsoft Store para empresas e instituições de ensino](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) para verificar se o console da sala poderá acessar a loja e a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="08c96-157">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="08c96-158">Selecionando um idioma</span><span class="sxs-lookup"><span data-stu-id="08c96-158">Selecting a language</span></span> 

<span data-ttu-id="08c96-159">Na atualização do criador, você precisará usar o script ApplyCurrentRegionAndLanguage. ps1 em cenários em que a seleção de idioma implícita não forneça ao usuário o idioma real do aplicativo desejado (por exemplo, que eles querem que o aplicativo de console seja exibido em francês, mas Ele está chegando em inglês).</span><span class="sxs-lookup"><span data-stu-id="08c96-159">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="08c96-160">As instruções a seguir funcionam apenas para consoles criados usando a atualização do criador do Windows.</span><span class="sxs-lookup"><span data-stu-id="08c96-160">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="08c96-161">Sistemas herdados/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não poderão usar essas instruções, mas também não devem ser prejudicadas com o problema inicial que exige essa intervenção manual (edição de aniversário permite que você escolha seu linguagem do aplicativo explicitamente como parte da instalação).</span><span class="sxs-lookup"><span data-stu-id="08c96-161">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="08c96-162">Para aplicar o idioma desejado</span><span class="sxs-lookup"><span data-stu-id="08c96-162">To apply your desired language</span></span>

1. <span data-ttu-id="08c96-163">Mude para o modo de Administrador.</span><span class="sxs-lookup"><span data-stu-id="08c96-163">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="08c96-164">Selecione o menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="08c96-164">Select the Start menu.</span></span>
    
3. <span data-ttu-id="08c96-165">Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="08c96-165">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="08c96-166">Selecione **o &amp; idioma do tempo**.</span><span class="sxs-lookup"><span data-stu-id="08c96-166">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="08c96-167">Selecione **idioma &amp; da região**.</span><span class="sxs-lookup"><span data-stu-id="08c96-167">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="08c96-168">Selecione **Adicionar um idioma**.</span><span class="sxs-lookup"><span data-stu-id="08c96-168">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="08c96-169">Selecione o idioma que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="08c96-169">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="08c96-170">Selecione o idioma que você acabou de adicionar à lista "idiomas".</span><span class="sxs-lookup"><span data-stu-id="08c96-170">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="08c96-171">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="08c96-171">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="08c96-172">Para idiomas que deseja remover:</span><span class="sxs-lookup"><span data-stu-id="08c96-172">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="08c96-p115">a. Selecione o idioma que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="08c96-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="08c96-p116">b. Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="08c96-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="08c96-177">Inicie um prompt de comandos com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="08c96-177">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="08c96-178">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="08c96-178">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="08c96-179">Reinicie o sistema.</span><span class="sxs-lookup"><span data-stu-id="08c96-179">Restart the system.</span></span>
    
<span data-ttu-id="08c96-180">O idioma desejado agora está aplicado ao console de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08c96-180">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="08c96-181">Configuração inicial do console</span><span class="sxs-lookup"><span data-stu-id="08c96-181">Initial set up of the console</span></span>
<span data-ttu-id="08c96-182"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="08c96-182"></span></span>

<span data-ttu-id="08c96-183">Após a instalação do Windows, o aplicativo de console de salas do Microsoft Teams entrará em seu processo inicial de configuração quando for iniciado em seguida, ou se a opção/reboot tiver sido escolhida.</span><span class="sxs-lookup"><span data-stu-id="08c96-183">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="08c96-184">A tela Conta de Usuário é exibida.</span><span class="sxs-lookup"><span data-stu-id="08c96-184">The User Account screen appears.</span></span> <span data-ttu-id="08c96-185">Insira o endereço de entrada do Skype (no formato do usuário @ domínio) da conta da sala a ser usada com o console.</span><span class="sxs-lookup"><span data-stu-id="08c96-185">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="08c96-186">Digite a senha para a conta da sala e digite-a novamente para verificar.</span><span class="sxs-lookup"><span data-stu-id="08c96-186">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="08c96-187">Em "configurar domínio", defina o FQDN do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="08c96-187">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="08c96-188">Se o domínio SIP do Skype for Business for diferente do domínio do Exchange do usuário, insira o domínio do Exchange nesse campo.</span><span class="sxs-lookup"><span data-stu-id="08c96-188">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="08c96-189">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="08c96-189">Click **Next**.</span></span>
    
5. <span data-ttu-id="08c96-190">Selecione os dispositivos indicados na tela recursos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="08c96-190">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="08c96-191">O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado.</span><span class="sxs-lookup"><span data-stu-id="08c96-191">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="08c96-192">Os dispositivos para selecionar são:</span><span class="sxs-lookup"><span data-stu-id="08c96-192">The devices to select are:</span></span>
    
   - <span data-ttu-id="08c96-193">Microfone para conferência: o microfone padrão para a sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="08c96-193">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="08c96-194">Alto-falante para conferência: o alto-falante padrão para conferência </span><span class="sxs-lookup"><span data-stu-id="08c96-194">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="08c96-195">Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.</span><span class="sxs-lookup"><span data-stu-id="08c96-195">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="08c96-p120">Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08c96-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="08c96-198">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="08c96-198">Click **Finish**.</span></span>
    
<span data-ttu-id="08c96-199">O aplicativo de console de salas do Microsoft Teams deve começar imediatamente a entrar no Skype for Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com o Exchange usando essas mesmas credenciais.</span><span class="sxs-lookup"><span data-stu-id="08c96-199">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="08c96-200">Para obter detalhes sobre como usar o aplicativo console, consulte a [ajuda de salas do Microsoft Teams](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="08c96-200">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="08c96-201">Salas do Microsoft Teams depende da presença de hardware de console certificado.</span><span class="sxs-lookup"><span data-stu-id="08c96-201">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="08c96-202">Até mesmo uma imagem criada corretamente contendo o aplicativo de console de salas do Microsoft Teams não será inicializada após o procedimento de configuração inicial, a menos que o hardware do console seja detectado.</span><span class="sxs-lookup"><span data-stu-id="08c96-202">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="08c96-203">Para soluções com base em Surface pro, o Surface pro deve estar conectado ao seu equipamento de encaixe que o acompanha para transmitir essa verificação.</span><span class="sxs-lookup"><span data-stu-id="08c96-203">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08c96-204">Alguns usuários do idioma diferente do inglês podem precisar de um teclado físico conectado ao console durante a configuração inicial, caso os símbolos não sejam compatíveis com o teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="08c96-204">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="08c96-205">Instalar um certificado de autoridade de certificação particular no console</span><span class="sxs-lookup"><span data-stu-id="08c96-205">Install a private CA certificate on the console</span></span>
<span data-ttu-id="08c96-206"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="08c96-206"></span></span>

<span data-ttu-id="08c96-207">O console de salas do Microsoft Teams precisa confiar nos certificados usados pelos servidores aos quais ele se conecta.</span><span class="sxs-lookup"><span data-stu-id="08c96-207">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="08c96-208">No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="08c96-208">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="08c96-209">Em um caso em que a autoridade de certificação é particular, por exemplo, uma implantação local com o Active Directory e a autoridade de certificação do Windows, você pode adicionar o certificado ao console de salas do Microsoft Teams de algumas maneiras:</span><span class="sxs-lookup"><span data-stu-id="08c96-209">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="08c96-210">Você pode ingressar no console no Active Directory e isso adicionará automaticamente os certificados obrigatórios, uma vez que a autoridade de certificação seja publicada no Active Directory (opção de implantação normal).</span><span class="sxs-lookup"><span data-stu-id="08c96-210">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="08c96-211">Você pode instalar o certificado manualmente após o processo de geração de imagens.</span><span class="sxs-lookup"><span data-stu-id="08c96-211">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="08c96-212">Antes de fazer isso, você deve concluir [a configuração inicial do console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="08c96-212">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="08c96-213">Para instalar o certificado manualmente </span><span class="sxs-lookup"><span data-stu-id="08c96-213">To manually install the certificate</span></span>

1. <span data-ttu-id="08c96-214">Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="08c96-214">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="08c96-215">Colocar o console no modo de administração (consulte o [modo de administrador e o gerenciamento de dispositivos](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="08c96-215">Place the console in admin mode (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="08c96-216">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="08c96-216">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="08c96-217">Ingressar em um domínio do Active Directory (opcional)</span><span class="sxs-lookup"><span data-stu-id="08c96-217">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="08c96-218"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="08c96-218"></span></span>

<span data-ttu-id="08c96-219">Você pode ingressar nos consoles de salas do Microsoft Teams no seu domínio.</span><span class="sxs-lookup"><span data-stu-id="08c96-219">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="08c96-220">Os consoles de salas do Microsoft Teams devem ser colocados em uma UO separada a partir de suas estações de trabalho de PC porque muitas políticas de estação de trabalho não são compatíveis com as salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08c96-220">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="08c96-221">Um exemplo comum são as políticas de imposição de senha que impedem o início automático das salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="08c96-221">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="08c96-222">Para obter informações sobre o gerenciamento de configurações de GPO, consulte [gerenciar salas do Microsoft Teams](room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="08c96-222">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="08c96-223">Para ingressar em salas do Microsoft Teams em um domínio</span><span class="sxs-lookup"><span data-stu-id="08c96-223">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="08c96-224">Conecte-se ao console da conta de administrador (consulte o [modo de administrador e o gerenciamento de dispositivos](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="08c96-224">Sign into the console from the admin account (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="08c96-225">Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.</span><span class="sxs-lookup"><span data-stu-id="08c96-225">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="08c96-226">Digite o seguinte comando no Powershell:</span><span class="sxs-lookup"><span data-stu-id="08c96-226">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="08c96-227">Por exemplo, se o seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de salas do Microsoft Team estejam em uma UO "salas do Microsoft Teams" que seja filho de uma OU "recursos", o comando será:</span><span class="sxs-lookup"><span data-stu-id="08c96-227">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="08c96-228">Se você quiser renomear o computador ao ingressar em um domínio, use o sinalizador-NewName seguido pelo nome novo do computador.</span><span class="sxs-lookup"><span data-stu-id="08c96-228">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="08c96-229">Lista de verificação de implantação de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-229">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="08c96-230"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="08c96-230"></span></span>

<span data-ttu-id="08c96-231">Use a lista de verificação a seguir ao fazer uma verificação final de que o console e todos os seus periféricos estão totalmente configurados:</span><span class="sxs-lookup"><span data-stu-id="08c96-231">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="08c96-232">**Configurações do aplicativo**</span><span class="sxs-lookup"><span data-stu-id="08c96-232">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="08c96-233">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-233">☐</span></span>  <br/> |<span data-ttu-id="08c96-234">O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console</span><span class="sxs-lookup"><span data-stu-id="08c96-234">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="08c96-235">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-235">☐</span></span>  <br/> |<span data-ttu-id="08c96-236">O nome do computador Windows está definido corretamente (útil para administração remota)</span><span class="sxs-lookup"><span data-stu-id="08c96-236">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="08c96-237">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-237">☐</span></span>  <br/> |<span data-ttu-id="08c96-238">A senha da conta do administrador foi definida e verificada</span><span class="sxs-lookup"><span data-stu-id="08c96-238">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="08c96-239">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-239">☐</span></span>  <br/> |<span data-ttu-id="08c96-240">Todas as atualizações de firmware foram aplicadas</span><span class="sxs-lookup"><span data-stu-id="08c96-240">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="08c96-241">**Periféricos de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="08c96-241">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="08c96-242">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-242">☐</span></span>  <br/> |<span data-ttu-id="08c96-243">A versão do firmware do periférico da câmera está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="08c96-243">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="08c96-244">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-244">☐</span></span>  <br/> |<span data-ttu-id="08c96-245">Câmera funcional e posicionada da maneira ideal</span><span class="sxs-lookup"><span data-stu-id="08c96-245">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="08c96-246">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-246">☐</span></span>  <br/> |<span data-ttu-id="08c96-247">Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="08c96-247">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="08c96-248">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-248">☐</span></span>  <br/> |<span data-ttu-id="08c96-249">Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="08c96-249">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="08c96-250">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-250">☐</span></span>  <br/> |<span data-ttu-id="08c96-251">A versão do firmware do periférico de áudio está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="08c96-251">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="08c96-252">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-252">☐</span></span>  <br/> |<span data-ttu-id="08c96-253">Dispositivo de entrada de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="08c96-253">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="08c96-254">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-254">☐</span></span>  <br/> |<span data-ttu-id="08c96-255">Dispositivo de saída de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="08c96-255">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="08c96-256">**Encaixe**</span><span class="sxs-lookup"><span data-stu-id="08c96-256">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="08c96-257">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-257">☐</span></span>  <br/> |<span data-ttu-id="08c96-258">Os cabos estão presos e não estão dobrados</span><span class="sxs-lookup"><span data-stu-id="08c96-258">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="08c96-259">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-259">☐</span></span>  <br/> |<span data-ttu-id="08c96-260">Ingestão de áudio via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="08c96-260">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="08c96-261">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-261">☐</span></span>  <br/> |<span data-ttu-id="08c96-262">Ingestão de vídeo via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="08c96-262">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="08c96-263">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-263">☐</span></span>  <br/> |<span data-ttu-id="08c96-264">O encaixe pode girar livremente</span><span class="sxs-lookup"><span data-stu-id="08c96-264">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="08c96-265">☐</span><span class="sxs-lookup"><span data-stu-id="08c96-265">☐</span></span>  <br/> |<span data-ttu-id="08c96-266">O brilho da tela é aceitável para o ambiente</span><span class="sxs-lookup"><span data-stu-id="08c96-266">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="08c96-267">Confira também</span><span class="sxs-lookup"><span data-stu-id="08c96-267">See also</span></span>
<span data-ttu-id="08c96-268"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="08c96-268"></span></span>

[<span data-ttu-id="08c96-269">Plano para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-269">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="08c96-270">Implantar salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-270">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="08c96-271">Configurar um console de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-271">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="08c96-272">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c96-272">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
