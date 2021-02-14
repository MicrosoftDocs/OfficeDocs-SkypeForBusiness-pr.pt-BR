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
description: Este artigo descreve como configurar e configurar o console de Salas do Microsoft Teams e seus periféricos.
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662056"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="afcc1-103">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="afcc1-104">Este artigo descreve como configurar o console salas do Microsoft Teams e seus periféricos.</span><span class="sxs-lookup"><span data-stu-id="afcc1-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="afcc1-105">Você só deverá executar essas etapas se as contas necessárias do Microsoft Teams ou skype for Business e do Exchange já foram criadas e testadas conforme descrito em Implantar Salas do [Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="afcc1-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="afcc1-106">Você precisará do hardware e do software descritos nos [requisitos de Salas do Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="afcc1-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="afcc1-107">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="afcc1-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="afcc1-108">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="afcc1-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="afcc1-109">Instalar um certificado de AC particular no console</span><span class="sxs-lookup"><span data-stu-id="afcc1-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="afcc1-110">Instalar o Windows 10 e o aplicativo de console salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="afcc1-111">Configuração inicial do console</span><span class="sxs-lookup"><span data-stu-id="afcc1-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="afcc1-112">Lista de verificação de implantação de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="afcc1-113">As Salas do Microsoft Teams só funcionarão em um ambiente do Microsoft Teams ou Skype for Business configurado corretamente, conforme descrito em Implantar Salas do [Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="afcc1-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="afcc1-114">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="afcc1-114">Prepare the installation media</span></span>
<span data-ttu-id="afcc1-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="afcc1-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="afcc1-116">Instalar o aplicativo de console salas do Microsoft Teams requer um dispositivo de armazenamento USB com pelo menos 32 GB de capacidade.</span><span class="sxs-lookup"><span data-stu-id="afcc1-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="afcc1-117">Não deve haver outros arquivos no dispositivo; todos os arquivos existentes no armazenamento USB serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="afcc1-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="afcc1-118">A falha na criação da mídia de instalação das Salas do Microsoft Teams de acordo com essas instruções provavelmente resultará em comportamento inesperado.</span><span class="sxs-lookup"><span data-stu-id="afcc1-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="afcc1-119">O processo a seguir é para criar mídia de instalação para imagem de novos dispositivos de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afcc1-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="afcc1-120">Os dispositivos existentes, por padrão, são atualizados automaticamente a partir do Windows Update e da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="afcc1-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afcc1-121">O computador windows 10 usado para criar a mídia de instalação do Microsoft Teams Rooms deve estar na mesma versão ou posterior do Windows que a mídia de instalação de destino.</span><span class="sxs-lookup"><span data-stu-id="afcc1-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="afcc1-122">Baixe o [CreateSrsMedia.ps1 script.](https://go.microsoft.com/fwlink/?linkid=867842)</span><span class="sxs-lookup"><span data-stu-id="afcc1-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="afcc1-123">Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.</span><span class="sxs-lookup"><span data-stu-id="afcc1-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="afcc1-124">Siga as instruções do script para criar um disco de configuração USB de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afcc1-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="afcc1-125">Sempre que o CreateSrsMedia.ps1 script for iniciado, a saída da tela incluirá o nome de um arquivo de log ou transcrição para a sessão.</span><span class="sxs-lookup"><span data-stu-id="afcc1-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="afcc1-126">Se houver problemas com a execução do script, certifique-se de ter uma cópia dessa transcrição disponível ao solicitar suporte.</span><span class="sxs-lookup"><span data-stu-id="afcc1-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="afcc1-127">O CreateSrsMedia.ps1 script automatiza as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="afcc1-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="afcc1-128">Baixe o instalador MSI mais recente para Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afcc1-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="afcc1-129">Determine o build do Windows que o usuário deve fornecer.</span><span class="sxs-lookup"><span data-stu-id="afcc1-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="afcc1-130">As versões mais recentes podem ou não ser testadas e ter suporte para uso com dispositivos microsoft teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="afcc1-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="afcc1-131">Baixe os componentes de suporte necessários.</span><span class="sxs-lookup"><span data-stu-id="afcc1-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="afcc1-132">Montar os componentes necessários na mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="afcc1-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="afcc1-133">Uma versão específica do Windows 10 é necessária, e esta versão só está disponível para clientes de licenciamento por volume.</span><span class="sxs-lookup"><span data-stu-id="afcc1-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="afcc1-134">Você pode obter uma cópia do Centro de Serviços de [Licenciamento por Volume.](https://www.microsoft.com/Licensing/servicecenter/)</span><span class="sxs-lookup"><span data-stu-id="afcc1-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="afcc1-135">Quando terminar, remova o disco USB do computador e prossiga para [Instalar o Windows 10 e](console.md#Reimage)o aplicativo de console salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afcc1-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="afcc1-136">Instalar o Windows 10 e o aplicativo de console salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="afcc1-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="afcc1-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="afcc1-138">Agora você precisa aplicar a mídia de configuração que criou.</span><span class="sxs-lookup"><span data-stu-id="afcc1-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="afcc1-139">O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido para executar apenas o aplicativo de console salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afcc1-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="afcc1-140">Se o dispositivo de destino for instalado em uma base (por exemplo, um Surface Pro), desconecte-o do dock.</span><span class="sxs-lookup"><span data-stu-id="afcc1-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="afcc1-141">Verifique se o dispositivo de destino não está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="afcc1-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="afcc1-142">Verifique se o dispositivo de destino está conectado à energia ac.</span><span class="sxs-lookup"><span data-stu-id="afcc1-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="afcc1-143">Conecte o disco de configuração USB ao dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="afcc1-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="afcc1-144">Inicializar no disco de configuração USB.</span><span class="sxs-lookup"><span data-stu-id="afcc1-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="afcc1-145">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="afcc1-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="afcc1-146">Se seu dispositivo de destino for um Surface Pro, use as seguintes etapas para inicializar o disco de configuração USB:</span><span class="sxs-lookup"><span data-stu-id="afcc1-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="afcc1-147">a.</span><span class="sxs-lookup"><span data-stu-id="afcc1-147">a.</span></span> <span data-ttu-id="afcc1-148">Pressione e continue a manter o botão de volume pressionado (-).</span><span class="sxs-lookup"><span data-stu-id="afcc1-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="afcc1-149">b.</span><span class="sxs-lookup"><span data-stu-id="afcc1-149">b.</span></span> <span data-ttu-id="afcc1-150">Pressione e solte o botão de energia.</span><span class="sxs-lookup"><span data-stu-id="afcc1-150">Press and release the power button.</span></span>

    <span data-ttu-id="afcc1-151">c.</span><span class="sxs-lookup"><span data-stu-id="afcc1-151">c.</span></span> <span data-ttu-id="afcc1-152">Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).</span><span class="sxs-lookup"><span data-stu-id="afcc1-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="afcc1-153">O sistema será desligado assim que a instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="afcc1-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="afcc1-154">Depois que o sistema for desligado, é seguro remover o disco de configuração USB.</span><span class="sxs-lookup"><span data-stu-id="afcc1-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="afcc1-155">Neste ponto, você pode colocar o dispositivo de destino no encaixe (se estiver usando um produto baseado em dock), anexar os periféricos necessários para a sala de reunião e conectar-se à rede.</span><span class="sxs-lookup"><span data-stu-id="afcc1-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="afcc1-156">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="afcc1-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="afcc1-157">As atualizações de software das Salas do Microsoft Teams são baixadas automaticamente da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="afcc1-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="afcc1-158">Consulte [Pré-requisitos da Microsoft Store](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) para Empresas e Educação para verificar se o console da sala será capaz de acessar a loja e fazer a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="afcc1-158">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="afcc1-159">Selecionando um idioma</span><span class="sxs-lookup"><span data-stu-id="afcc1-159">Selecting a language</span></span> 

<span data-ttu-id="afcc1-160">Na Atualização do Criador, você precisará usar o script do ApplyCurrentRegionAndLanguage.ps1 em cenários em que a seleção implícita de idioma não fornece ao usuário o idioma real do aplicativo que deseja (por exemplo, ele quer que o aplicativo de console seja usado em francês, mas está chegando em inglês).</span><span class="sxs-lookup"><span data-stu-id="afcc1-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="afcc1-161">As instruções a seguir funcionam somente para consoles criados usando a Atualização do Windows Creator.</span><span class="sxs-lookup"><span data-stu-id="afcc1-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="afcc1-162">Os sistemas herdado/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não poderão usar essas instruções, mas também não deverão ser prejudicados pelo problema inicial que requer essa intervenção manual (a Edição de Aniversário permite que você escolha explicitamente o idioma do aplicativo como parte da configuração).</span><span class="sxs-lookup"><span data-stu-id="afcc1-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="afcc1-163">Para aplicar o idioma desejado</span><span class="sxs-lookup"><span data-stu-id="afcc1-163">To apply your desired language</span></span>

1. <span data-ttu-id="afcc1-164">Mude para o modo de Administrador.</span><span class="sxs-lookup"><span data-stu-id="afcc1-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="afcc1-165">Selecione o menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="afcc1-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="afcc1-166">Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="afcc1-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="afcc1-167">Selecione **o idioma &amp; hora.**</span><span class="sxs-lookup"><span data-stu-id="afcc1-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="afcc1-168">Selecione **o idioma &amp; região.**</span><span class="sxs-lookup"><span data-stu-id="afcc1-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="afcc1-169">Selecione **Adicionar um idioma**.</span><span class="sxs-lookup"><span data-stu-id="afcc1-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="afcc1-170">Selecione o idioma que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="afcc1-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="afcc1-171">Selecione o idioma que você acabou de adicionar à lista "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="afcc1-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="afcc1-172">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="afcc1-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="afcc1-173">Para idiomas que deseja remover:</span><span class="sxs-lookup"><span data-stu-id="afcc1-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="afcc1-p115">a. Selecione o idioma que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="afcc1-p115">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="afcc1-p116">b. Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="afcc1-p116">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="afcc1-178">Inicie um prompt de comandos com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="afcc1-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="afcc1-179">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="afcc1-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="afcc1-180">Reinicie o sistema.</span><span class="sxs-lookup"><span data-stu-id="afcc1-180">Restart the system.</span></span>
    
<span data-ttu-id="afcc1-181">O idioma desejado agora é aplicado ao console salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afcc1-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="afcc1-182">Configuração inicial do console</span><span class="sxs-lookup"><span data-stu-id="afcc1-182">Initial set up of the console</span></span>
<span data-ttu-id="afcc1-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="afcc1-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="afcc1-184">Depois que o Windows estiver instalado, o aplicativo de console salas do Microsoft Teams entrará em seu processo inicial de Configuração quando ele for iniciado em seguida ou se a opção /reinicialização tiver sido escolhida.</span><span class="sxs-lookup"><span data-stu-id="afcc1-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="afcc1-185">A tela Conta de Usuário é exibida.</span><span class="sxs-lookup"><span data-stu-id="afcc1-185">The User Account screen appears.</span></span> <span data-ttu-id="afcc1-186">Insira o endereço de entrada do Skype (user@domain formato) da conta da sala a ser usada com o console.</span><span class="sxs-lookup"><span data-stu-id="afcc1-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="afcc1-187">Digite a senha para a conta da sala e digite-a novamente para verificar.</span><span class="sxs-lookup"><span data-stu-id="afcc1-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="afcc1-188">Em "Configurar Domínio", de definir o FQDN para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="afcc1-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="afcc1-189">Se o domínio SIP do Skype for Business for diferente do domínio exchange do usuário, insira o domínio exchange nesse campo.</span><span class="sxs-lookup"><span data-stu-id="afcc1-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="afcc1-190">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="afcc1-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="afcc1-191">Selecione os dispositivos indicados na tela Recursos e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="afcc1-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="afcc1-192">O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado.</span><span class="sxs-lookup"><span data-stu-id="afcc1-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="afcc1-193">Os dispositivos para selecionar são:</span><span class="sxs-lookup"><span data-stu-id="afcc1-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="afcc1-194">Microfone para conferência: o microfone padrão para a sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="afcc1-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="afcc1-195">Alto-falante para conferência: o alto-falante padrão para conferência </span><span class="sxs-lookup"><span data-stu-id="afcc1-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="afcc1-196">Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.</span><span class="sxs-lookup"><span data-stu-id="afcc1-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="afcc1-p120">Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="afcc1-p120">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="afcc1-199">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="afcc1-199">Click **Finish**.</span></span>
    
<span data-ttu-id="afcc1-200">O aplicativo de console salas do Microsoft Teams deve começar imediatamente a entrar no Skype for Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com o Exchange usando essas mesmas credenciais.</span><span class="sxs-lookup"><span data-stu-id="afcc1-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="afcc1-201">Para obter detalhes sobre como usar o aplicativo console, consulte a ajuda do [Microsoft Teams Rooms.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)</span><span class="sxs-lookup"><span data-stu-id="afcc1-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="afcc1-202">O Microsoft Teams Rooms depende da presença de hardware certificado do console.</span><span class="sxs-lookup"><span data-stu-id="afcc1-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="afcc1-203">Mesmo uma imagem criada corretamente contendo o aplicativo de console salas do Microsoft Teams não será inicializada após o procedimento de configuração inicial, a menos que o hardware do console seja detectado.</span><span class="sxs-lookup"><span data-stu-id="afcc1-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="afcc1-204">Para soluções baseadas no Surface Pro, o Surface Pro deve estar conectado ao hardware do encaixe que o acompanha para passar nessa verificação.</span><span class="sxs-lookup"><span data-stu-id="afcc1-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="afcc1-205">Alguns usuários que não são do idioma inglês podem precisar de um teclado físico conectado ao console durante a configuração inicial caso não sejam suportados símbolos no teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="afcc1-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="afcc1-206">Instalar um certificado de AC particular no console</span><span class="sxs-lookup"><span data-stu-id="afcc1-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="afcc1-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="afcc1-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="afcc1-208">O console salas do Microsoft Teams precisa confiar nos certificados usados pelos servidores aos que ele se conecta.</span><span class="sxs-lookup"><span data-stu-id="afcc1-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="afcc1-209">No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="afcc1-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="afcc1-210">Em um caso em que a Autoridade de Certificação é privada, por exemplo, uma implantação local com o Active Directory e a Autoridade de Certificação do Windows, você pode adicionar o certificado ao console salas do Microsoft Teams de algumas maneiras:</span><span class="sxs-lookup"><span data-stu-id="afcc1-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="afcc1-211">Você pode ingressar no console no Active Directory e isso adicionará automaticamente os certificados necessários, uma vez que a Autoridade de Certificação é publicada no Active Directory (opção de implantação normal).</span><span class="sxs-lookup"><span data-stu-id="afcc1-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="afcc1-212">Você pode instalar o certificado manualmente após o processo de geração de imagens.</span><span class="sxs-lookup"><span data-stu-id="afcc1-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="afcc1-213">Antes de fazer isso, você deve concluir [a configuração inicial do console.](console.md#Initial)</span><span class="sxs-lookup"><span data-stu-id="afcc1-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="afcc1-214">Para instalar o certificado manualmente </span><span class="sxs-lookup"><span data-stu-id="afcc1-214">To manually install the certificate</span></span>

1. <span data-ttu-id="afcc1-215">Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="afcc1-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="afcc1-216">Coloque o console no modo de administração (consulte [o modo de administração e o gerenciamento de dispositivo).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="afcc1-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="afcc1-217">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="afcc1-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="afcc1-218">Ingressar em um domínio do Active Directory (Opcional)</span><span class="sxs-lookup"><span data-stu-id="afcc1-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="afcc1-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="afcc1-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="afcc1-220">Você pode ingressar nos consoles das Salas do Microsoft Teams ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="afcc1-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="afcc1-221">Os consoles de Salas do Microsoft Teams devem ser colocados em uma OU separada das estações de trabalho do computador, pois muitas políticas de estação de trabalho não são compatíveis com salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afcc1-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="afcc1-222">Um exemplo comum são as políticas de imposição de senha que impedirão que as Salas do Microsoft Teams sejam criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="afcc1-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="afcc1-223">Para obter informações sobre o gerenciamento de configurações de GPO, consulte [Gerenciar Salas do Microsoft Teams.](rooms-operations.md)</span><span class="sxs-lookup"><span data-stu-id="afcc1-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="afcc1-224">Para ingressar no Microsoft Teams Rooms em um domínio</span><span class="sxs-lookup"><span data-stu-id="afcc1-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="afcc1-225">Entre no console da conta de administrador (consulte [o modo de administração e o gerenciamento de dispositivo).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="afcc1-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="afcc1-226">Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.</span><span class="sxs-lookup"><span data-stu-id="afcc1-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="afcc1-227">Digite o seguinte comando no Powershell:</span><span class="sxs-lookup"><span data-stu-id="afcc1-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="afcc1-228">Por exemplo, se seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de Salas do Microsoft Teams sejam em uma "Salas do Microsoft Teams" OU que seja filho de um "Recursos" OU, o comando será:</span><span class="sxs-lookup"><span data-stu-id="afcc1-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="afcc1-229">Se você quiser renomear o computador ao ingressar nele em um domínio, use o sinalizador -NovoNome seguido do novo nome do computador.</span><span class="sxs-lookup"><span data-stu-id="afcc1-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="afcc1-230">Lista de verificação de implantação de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="afcc1-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="afcc1-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="afcc1-232">Use a seguinte lista de verificação ao fazer uma verificação final de que o console e todos os seus periféricos estão totalmente configurados:</span><span class="sxs-lookup"><span data-stu-id="afcc1-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="afcc1-233">**Configurações do aplicativo**</span><span class="sxs-lookup"><span data-stu-id="afcc1-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="afcc1-234">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-234">☐</span></span>  <br/> |<span data-ttu-id="afcc1-235">O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console</span><span class="sxs-lookup"><span data-stu-id="afcc1-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="afcc1-236">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-236">☐</span></span>  <br/> |<span data-ttu-id="afcc1-237">O nome do computador Windows está definido corretamente (útil para administração remota)</span><span class="sxs-lookup"><span data-stu-id="afcc1-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="afcc1-238">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-238">☐</span></span>  <br/> |<span data-ttu-id="afcc1-239">A senha da conta do administrador foi definida e verificada</span><span class="sxs-lookup"><span data-stu-id="afcc1-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="afcc1-240">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-240">☐</span></span>  <br/> |<span data-ttu-id="afcc1-241">Todas as atualizações de firmware foram aplicadas</span><span class="sxs-lookup"><span data-stu-id="afcc1-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="afcc1-242">**Periféricos de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="afcc1-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="afcc1-243">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-243">☐</span></span>  <br/> |<span data-ttu-id="afcc1-244">A versão do firmware do periférico da câmera está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="afcc1-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="afcc1-245">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-245">☐</span></span>  <br/> |<span data-ttu-id="afcc1-246">Câmera funcional e posicionada de forma ideal</span><span class="sxs-lookup"><span data-stu-id="afcc1-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="afcc1-247">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-247">☐</span></span>  <br/> |<span data-ttu-id="afcc1-248">Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="afcc1-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="afcc1-249">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-249">☐</span></span>  <br/> |<span data-ttu-id="afcc1-250">Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="afcc1-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="afcc1-251">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-251">☐</span></span>  <br/> |<span data-ttu-id="afcc1-252">A versão do firmware do periférico de áudio está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="afcc1-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="afcc1-253">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-253">☐</span></span>  <br/> |<span data-ttu-id="afcc1-254">Dispositivo de entrada de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="afcc1-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="afcc1-255">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-255">☐</span></span>  <br/> |<span data-ttu-id="afcc1-256">Dispositivo de saída de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="afcc1-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="afcc1-257">**Encaixe**</span><span class="sxs-lookup"><span data-stu-id="afcc1-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="afcc1-258">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-258">☐</span></span>  <br/> |<span data-ttu-id="afcc1-259">Os cabos estão presos e não estão dobrados</span><span class="sxs-lookup"><span data-stu-id="afcc1-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="afcc1-260">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-260">☐</span></span>  <br/> |<span data-ttu-id="afcc1-261">Ingestão de áudio via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="afcc1-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="afcc1-262">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-262">☐</span></span>  <br/> |<span data-ttu-id="afcc1-263">Ingestão de vídeo via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="afcc1-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="afcc1-264">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-264">☐</span></span>  <br/> |<span data-ttu-id="afcc1-265">O encaixe pode girar livremente</span><span class="sxs-lookup"><span data-stu-id="afcc1-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="afcc1-266">☐</span><span class="sxs-lookup"><span data-stu-id="afcc1-266">☐</span></span>  <br/> |<span data-ttu-id="afcc1-267">O brilho da tela é aceitável para o ambiente</span><span class="sxs-lookup"><span data-stu-id="afcc1-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="afcc1-268">Confira também</span><span class="sxs-lookup"><span data-stu-id="afcc1-268">See also</span></span>
<span data-ttu-id="afcc1-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="afcc1-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="afcc1-270">Planejar as Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="afcc1-271">Implantar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="afcc1-272">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="afcc1-273">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcc1-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
