---
title: Configurar um console de salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console de salas de equipes da Microsoft e seus periféricos.
ms.openlocfilehash: fc1d50ffe6dd7415848e02571eab1484bd3dfe22
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012610"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="c0d62-103">Configurar um console de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="c0d62-104">Este artigo descreve como configurar o console de salas de equipes da Microsoft e seus periféricos.</span><span class="sxs-lookup"><span data-stu-id="c0d62-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="c0d62-105">Você só deve executar estas etapas se o Skype necessária para contas de negócios e do Exchange já foram criado e testado, conforme descrito em [Implantar salas de equipes da Microsoft](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c0d62-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="c0d62-106">Você precisará de hardware e software descritos em [requisitos de salas de equipes da Microsoft](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0d62-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="c0d62-107">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="c0d62-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c0d62-108">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="c0d62-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="c0d62-109">Instale um certificado de autoridade de certificação privado no console do</span><span class="sxs-lookup"><span data-stu-id="c0d62-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="c0d62-110">Instalar o Windows 10 e o aplicativo de console de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="c0d62-111">Conjunto inicial backup do console</span><span class="sxs-lookup"><span data-stu-id="c0d62-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="c0d62-112">Lista de verificação de implantação de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="c0d62-113">Salas de equipes da Microsoft exemplos funcionam apenas em um Skype configurada adequadamente para onde as contas de dispositivo estão configuradas corretamente conforme descrito em [Implantar o Microsoft equipes salas](room-systems-v2.md)do ambiente de negócios.</span><span class="sxs-lookup"><span data-stu-id="c0d62-113">Microsoft Teams Rooms will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="c0d62-114">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="c0d62-114">Prepare the installation media</span></span>
<span data-ttu-id="c0d62-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="c0d62-115"></span></span>

<span data-ttu-id="c0d62-116">Instalar o aplicativo de console do Microsoft equipes salas requer um dispositivo de armazenamento USB com pelo menos 32GB de capacidade.</span><span class="sxs-lookup"><span data-stu-id="c0d62-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="c0d62-117">Não deve haver nenhum outro arquivo no dispositivo. todos os arquivos existentes no armazenamento USB será perdidos.</span><span class="sxs-lookup"><span data-stu-id="c0d62-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0d62-118">Falha ao criar sua mídia de instalação do Microsoft equipes salas de acordo com estas instruções provavelmente resultará em um comportamento inesperado.</span><span class="sxs-lookup"><span data-stu-id="c0d62-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="c0d62-119">O processo abaixo é para a criação de mídia de instalação para novos dispositivos de salas de equipes da Microsoft de imagem.</span><span class="sxs-lookup"><span data-stu-id="c0d62-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="c0d62-120">Dispositivos existentes, por padrão, atualizam automaticamente do Windows Update e o repositório do Windows.</span><span class="sxs-lookup"><span data-stu-id="c0d62-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="c0d62-121">Baixe o [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="c0d62-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="c0d62-122">Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c0d62-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="c0d62-123">Siga as instruções do script para criar um disco de instalação do Microsoft equipes salas USB.</span><span class="sxs-lookup"><span data-stu-id="c0d62-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>

> [!CAUTION]
> <span data-ttu-id="c0d62-124">O nome da pasta que executar o script de criação de mídia não pode conter um espaço.</span><span class="sxs-lookup"><span data-stu-id="c0d62-124">The name of the folder that you run the media creation script from can not contain a space.</span></span> <span data-ttu-id="c0d62-125">Se houver um espaço no nome de pasta, o script irá falhar.</span><span class="sxs-lookup"><span data-stu-id="c0d62-125">If there is a space in to folder name, the script will fail.</span></span>

<span data-ttu-id="c0d62-126">O script CreateSrsMedia.ps1 automatiza as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="c0d62-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="c0d62-127">Baixe o instalador MSI mais recente para salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c0d62-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="c0d62-128">Determine a compilação do Windows que o usuário deve fornecer.</span><span class="sxs-lookup"><span data-stu-id="c0d62-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="c0d62-129">As versões liberadas recentemente podem ou não podem ser testadas e suportadas para uso com dispositivos de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c0d62-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="c0d62-130">Baixe os componentes de suportados necessários.</span><span class="sxs-lookup"><span data-stu-id="c0d62-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="c0d62-131">Monte os componentes necessários na mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="c0d62-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="c0d62-132">É necessária uma versão específica do Windows 10 e esta versão só está disponível para clientes de licenciamento de volume.</span><span class="sxs-lookup"><span data-stu-id="c0d62-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="c0d62-133">Você pode obter uma cópia do [Centro de atendimento de licenciamento por Volume](https://www.microsoft.com/Licensing/servicecenter/).</span><span class="sxs-lookup"><span data-stu-id="c0d62-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="c0d62-134">Quando terminar, remova o disco USB do computador e prossiga para [instalar o Windows 10 e as salas de equipes da Microsoft app do console](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="c0d62-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="c0d62-135">Instalar o Windows 10 e o aplicativo de console de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="c0d62-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c0d62-136"></span></span>

<span data-ttu-id="c0d62-137">Agora, você precisa aplicar a mídia de instalação que você criou.</span><span class="sxs-lookup"><span data-stu-id="c0d62-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="c0d62-138">O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido como executar somente o aplicativo de console do Microsoft equipes salas.</span><span class="sxs-lookup"><span data-stu-id="c0d62-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="c0d62-139">Se o dispositivo de destino será instalado em um (por exemplo, um Surface Pro) de encaixe, desconecte-o do encaixe.</span><span class="sxs-lookup"><span data-stu-id="c0d62-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="c0d62-140">Certifique-se de que o dispositivo de destino não está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="c0d62-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="c0d62-141">Certifique-se de que o dispositivo de destino está conectado à alimentação AC.</span><span class="sxs-lookup"><span data-stu-id="c0d62-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="c0d62-142">Conecte seu disco de instalação do USB no dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="c0d62-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="c0d62-143">Inicialize o disco de instalação do USB.</span><span class="sxs-lookup"><span data-stu-id="c0d62-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="c0d62-144">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="c0d62-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="c0d62-145">Se seu dispositivo de destino for um Surface Pro, use as seguintes etapas para inicializar o disco de instalação do USB:</span><span class="sxs-lookup"><span data-stu-id="c0d62-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="c0d62-146">a.</span><span class="sxs-lookup"><span data-stu-id="c0d62-146">a.</span></span> <span data-ttu-id="c0d62-147">Pressione e continue armazenar o volume (-) botão pressionado.</span><span class="sxs-lookup"><span data-stu-id="c0d62-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="c0d62-148">b.</span><span class="sxs-lookup"><span data-stu-id="c0d62-148">b.</span></span> <span data-ttu-id="c0d62-149">Pressione e solte o botão de energia.</span><span class="sxs-lookup"><span data-stu-id="c0d62-149">Press and release the power button.</span></span>

    <span data-ttu-id="c0d62-150">c.</span><span class="sxs-lookup"><span data-stu-id="c0d62-150">c.</span></span> <span data-ttu-id="c0d62-151">Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).</span><span class="sxs-lookup"><span data-stu-id="c0d62-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="c0d62-152">O sistema será desligado depois que a instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="c0d62-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="c0d62-153">Depois que o sistema foi desligado, é seguro remover o disco de instalação do USB.</span><span class="sxs-lookup"><span data-stu-id="c0d62-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="c0d62-154">Neste ponto, você pode colocar o dispositivo de destino no seu encaixe (se estiver usando um produto com base em encaixe), anexar os periféricos necessários para a sala de reunião e conectar à rede.</span><span class="sxs-lookup"><span data-stu-id="c0d62-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="c0d62-155">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="c0d62-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="c0d62-156">Selecionar um idioma</span><span class="sxs-lookup"><span data-stu-id="c0d62-156">Selecting a language</span></span> 

<span data-ttu-id="c0d62-157">Em atualização do criador, você precisará usar o script de ApplyCurrentRegionAndLanguage.ps1 em cenários onde a seleção de idioma implícita não fornecer ao usuário com a linguagem de aplicativos real querem (por exemplo, eles querem que o aplicativo de console surgir em francês, mas ele está chegando em inglês).</span><span class="sxs-lookup"><span data-stu-id="c0d62-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0d62-158">As instruções a seguir funcionam apenas para consoles criados usando Update do criador do Windows.</span><span class="sxs-lookup"><span data-stu-id="c0d62-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="c0d62-159">Sistemas herdados/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não será capazes de usar estas instruções, mas também deve não sofrem o problema inicial que requer intervenção este manual (edição de aniversário permitam que você escolha sua idioma App explicitamente como parte da instalação).</span><span class="sxs-lookup"><span data-stu-id="c0d62-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c0d62-160">Para aplicar o idioma desejado</span><span class="sxs-lookup"><span data-stu-id="c0d62-160">To apply your desired language</span></span>

1. <span data-ttu-id="c0d62-161">Mude para o modo de Administrador.</span><span class="sxs-lookup"><span data-stu-id="c0d62-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c0d62-162">Selecione o menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="c0d62-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c0d62-163">Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c0d62-164">Selecione **tempo &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c0d62-165">Selecione **região &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c0d62-166">Selecione **Adicionar um idioma**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c0d62-167">Selecione o idioma que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="c0d62-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c0d62-168">Selecione o idioma que você acabou de adicionar à lista de "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="c0d62-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c0d62-169">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c0d62-170">Para idiomas que deseja remover:</span><span class="sxs-lookup"><span data-stu-id="c0d62-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c0d62-p114">a. Selecione o idioma que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="c0d62-p114">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c0d62-p115">b. Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-p115">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="c0d62-175">Inicie um prompt de comandos com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="c0d62-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c0d62-176">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c0d62-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="c0d62-177">Reinicie o sistema.</span><span class="sxs-lookup"><span data-stu-id="c0d62-177">Restart the system.</span></span>
    
<span data-ttu-id="c0d62-178">O idioma desejado agora é aplicado no console de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c0d62-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c0d62-179">Conjunto inicial backup do console</span><span class="sxs-lookup"><span data-stu-id="c0d62-179">Initial set up of the console</span></span>
<span data-ttu-id="c0d62-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c0d62-180"></span></span>

<span data-ttu-id="c0d62-181">Após a instalação do Windows, o aplicativo de console do Microsoft equipes salas entrará em seu processo de instalação inicial, quando ele é iniciado próximo ou se a opção /reboot foi escolhida.</span><span class="sxs-lookup"><span data-stu-id="c0d62-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c0d62-182">A tela Conta de Usuário é exibida.</span><span class="sxs-lookup"><span data-stu-id="c0d62-182">The User Account screen appears.</span></span> <span data-ttu-id="c0d62-183">Insira o Skype endereço de entrada (no formato user@domain) da conta a ser usado com o console de sala.</span><span class="sxs-lookup"><span data-stu-id="c0d62-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="c0d62-184">Digite a senha para a conta da sala e digite-a novamente para verificar.</span><span class="sxs-lookup"><span data-stu-id="c0d62-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c0d62-185">Em "Configurar domínio", defina o FQDN para o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0d62-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c0d62-186">Se o Skype para o domínio SIP de negócios for diferente do domínio do Exchange do usuário, insira o domínio do Exchange neste campo.</span><span class="sxs-lookup"><span data-stu-id="c0d62-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c0d62-187">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="c0d62-188">Selecione os dispositivos indicados na tela recursos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c0d62-189">O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado.</span><span class="sxs-lookup"><span data-stu-id="c0d62-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c0d62-190">Os dispositivos para selecionar são:</span><span class="sxs-lookup"><span data-stu-id="c0d62-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="c0d62-191">Microfone para conferência: o microfone padrão para a sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="c0d62-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c0d62-192">Alto-falante para conferência: o alto-falante padrão para conferência </span><span class="sxs-lookup"><span data-stu-id="c0d62-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c0d62-193">Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.</span><span class="sxs-lookup"><span data-stu-id="c0d62-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="c0d62-p119">Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0d62-p119">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c0d62-196">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c0d62-196">Click **Finish**.</span></span>
    
<span data-ttu-id="c0d62-197">O aplicativo de console do Microsoft equipes salas deve iniciar imediatamente entrando no Skype para Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com Exchange usando as mesmas credenciais.</span><span class="sxs-lookup"><span data-stu-id="c0d62-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c0d62-198">Para obter detalhes sobre como usar o aplicativo de console, consulte a [Ajuda do Microsoft equipes salas](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="c0d62-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c0d62-199">Salas de equipes da Microsoft depende da presença de hardware do console certificados.</span><span class="sxs-lookup"><span data-stu-id="c0d62-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="c0d62-200">Mesmo uma imagem criada corretamente que contém o aplicativo de console do Microsoft equipes salas não inicializa passado o procedimento de instalação inicial, a menos que o hardware do console for detectado.</span><span class="sxs-lookup"><span data-stu-id="c0d62-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="c0d62-201">Para obter soluções Surface Pro com base, o Surface Pro deve estar conectada a seu hardware de encaixe acompanha para passar essa verificação.</span><span class="sxs-lookup"><span data-stu-id="c0d62-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0d62-202">Alguns usuários de idioma diferente do inglês, talvez seja necessário um teclado físico conectado ao console durante a configuração inicial que símbolos não são suportados no teclado de toque.</span><span class="sxs-lookup"><span data-stu-id="c0d62-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="c0d62-203">Instale um certificado de autoridade de certificação privado no console do</span><span class="sxs-lookup"><span data-stu-id="c0d62-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="c0d62-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c0d62-204"></span></span>

<span data-ttu-id="c0d62-205">O console de salas de equipes da Microsoft deve confiar nos certificados usados pelo Skype para servidores de negócios e Exchange a que conecta-se.</span><span class="sxs-lookup"><span data-stu-id="c0d62-205">The Microsoft Teams Rooms console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="c0d62-206">No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c0d62-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c0d62-207">No caso em que a autoridade de certificação é particular, por exemplo, uma implantação de local com o Active Directory e a autoridade de certificação do Windows, você pode adicionar o certificado no console de salas de equipes da Microsoft de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="c0d62-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="c0d62-208">Ingresse o console do Active Directory e que adicionará automaticamente os certificados necessários dado da autoridade de certificação é publicado no Active Directory (opção de implantação normal).</span><span class="sxs-lookup"><span data-stu-id="c0d62-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c0d62-209">Você pode instalar o certificado manualmente após o processo de geração de imagens.</span><span class="sxs-lookup"><span data-stu-id="c0d62-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="c0d62-210">Antes de fazer isso, você deve concluir a [Configurar as iniciais do console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="c0d62-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c0d62-211">Para instalar o certificado manualmente </span><span class="sxs-lookup"><span data-stu-id="c0d62-211">To manually install the certificate</span></span>

1. <span data-ttu-id="c0d62-212">Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="c0d62-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c0d62-213">Coloque o console no modo de administração (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="c0d62-213">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c0d62-214">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c0d62-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c0d62-215">Ingressar em um domínio do Active Directory (opcional)</span><span class="sxs-lookup"><span data-stu-id="c0d62-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="c0d62-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c0d62-216"></span></span>

<span data-ttu-id="c0d62-217">Você pode ingressar consoles de salas de equipes da Microsoft para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c0d62-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="c0d62-218">Consoles de salas de equipes da Microsoft devem ser colocados em uma UO separada estações de trabalho do seu PC, porque muitos políticas de estação de trabalho não são compatíveis com Microsoft equipes salas.</span><span class="sxs-lookup"><span data-stu-id="c0d62-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="c0d62-219">Um exemplo comum são as diretivas de aplicação da senha que evitam a salas de equipes da Microsoft seja iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c0d62-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="c0d62-220">Para obter informações sobre o gerenciamento de configurações do GPO, consulte [Manage Rooms de equipes da Microsoft](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c0d62-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="c0d62-221">Para ingressar em salas de equipes da Microsoft a um domínio</span><span class="sxs-lookup"><span data-stu-id="c0d62-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="c0d62-222">Sinal de login no console do que o administrador da conta (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="c0d62-222">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c0d62-223">Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.</span><span class="sxs-lookup"><span data-stu-id="c0d62-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c0d62-224">Digite o seguinte comando no Powershell:</span><span class="sxs-lookup"><span data-stu-id="c0d62-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="c0d62-225">Por exemplo, se o seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de salas de equipes da Microsoft para estar em uma unidade Organizacional "Salas de equipes da Microsoft" que é um filho de uma unidade Organizacional "recursos", o comando será:</span><span class="sxs-lookup"><span data-stu-id="c0d62-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c0d62-226">Se você gostaria de renomear o computador ao ingressarem-lo a um domínio, use o sinalizador - NewName seguido pelo nome do novo do computador.</span><span class="sxs-lookup"><span data-stu-id="c0d62-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="c0d62-227">Lista de verificação de implantação de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="c0d62-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c0d62-228"></span></span>

<span data-ttu-id="c0d62-229">Use a seguinte lista de verificação enquanto efetua uma verificação final se o console e todos os seus periféricos totalmente estão configurados:</span><span class="sxs-lookup"><span data-stu-id="c0d62-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c0d62-230">**Configurações do aplicativo**</span><span class="sxs-lookup"><span data-stu-id="c0d62-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c0d62-231">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-231">☐</span></span>  <br/> |<span data-ttu-id="c0d62-232">O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console</span><span class="sxs-lookup"><span data-stu-id="c0d62-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c0d62-233">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-233">☐</span></span>  <br/> |<span data-ttu-id="c0d62-234">O nome do computador Windows está definido corretamente (útil para administração remota)</span><span class="sxs-lookup"><span data-stu-id="c0d62-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c0d62-235">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-235">☐</span></span>  <br/> |<span data-ttu-id="c0d62-236">A senha da conta do administrador foi definida e verificada</span><span class="sxs-lookup"><span data-stu-id="c0d62-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c0d62-237">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-237">☐</span></span>  <br/> |<span data-ttu-id="c0d62-238">Todas as atualizações de firmware tiverem sido aplicadas.</span><span class="sxs-lookup"><span data-stu-id="c0d62-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c0d62-239">**Periféricos de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="c0d62-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c0d62-240">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-240">☐</span></span>  <br/> |<span data-ttu-id="c0d62-241">A versão do firmware do periférico da câmera está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="c0d62-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c0d62-242">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-242">☐</span></span>  <br/> |<span data-ttu-id="c0d62-243">Câmera funcional e forma ideal posicionada</span><span class="sxs-lookup"><span data-stu-id="c0d62-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c0d62-244">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-244">☐</span></span>  <br/> |<span data-ttu-id="c0d62-245">Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="c0d62-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c0d62-246">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-246">☐</span></span>  <br/> |<span data-ttu-id="c0d62-247">Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="c0d62-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c0d62-248">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-248">☐</span></span>  <br/> |<span data-ttu-id="c0d62-249">A versão do firmware do periférico de áudio está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="c0d62-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c0d62-250">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-250">☐</span></span>  <br/> |<span data-ttu-id="c0d62-251">Dispositivo de entrada de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="c0d62-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c0d62-252">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-252">☐</span></span>  <br/> |<span data-ttu-id="c0d62-253">Dispositivo de saída de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="c0d62-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c0d62-254">**Encaixe**</span><span class="sxs-lookup"><span data-stu-id="c0d62-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c0d62-255">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-255">☐</span></span>  <br/> |<span data-ttu-id="c0d62-256">Os cabos estão presos e não estão dobrados</span><span class="sxs-lookup"><span data-stu-id="c0d62-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c0d62-257">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-257">☐</span></span>  <br/> |<span data-ttu-id="c0d62-258">Ingestão de áudio via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="c0d62-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c0d62-259">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-259">☐</span></span>  <br/> |<span data-ttu-id="c0d62-260">Ingestão de vídeo via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="c0d62-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c0d62-261">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-261">☐</span></span>  <br/> |<span data-ttu-id="c0d62-262">O encaixe pode girar livremente</span><span class="sxs-lookup"><span data-stu-id="c0d62-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c0d62-263">☐</span><span class="sxs-lookup"><span data-stu-id="c0d62-263">☐</span></span>  <br/> |<span data-ttu-id="c0d62-264">O brilho da tela é aceitável para o ambiente</span><span class="sxs-lookup"><span data-stu-id="c0d62-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c0d62-265">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0d62-265">See also</span></span>
<span data-ttu-id="c0d62-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c0d62-266"></span></span>

[<span data-ttu-id="c0d62-267">Planejar para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-267">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c0d62-268">Implantar salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c0d62-269">Configurar um console de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="c0d62-270">Gerenciar salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0d62-270">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)