---
title: Configurar o console do Skype Room Systems versão 2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console do Skype Room Systems versão 2 e seus periféricos.
ms.openlocfilehash: 6e2ec8384387cefd074342abb3da316288af1f0f
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="33693-103">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="33693-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="33693-104">Este artigo descreve como configurar o console do Skype Room Systems versão 2 e seus periféricos.</span><span class="sxs-lookup"><span data-stu-id="33693-104">This article describes how to set up the Skype Room Systems v2 console device and its peripherals.</span></span>
  
<span data-ttu-id="33693-105">Você só deve executar estas etapas se o Skype necessária para contas de negócios e do Exchange já foram criado e testado, conforme descrito em [implantar sistemas de sala Skype v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="33693-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="33693-106">Você precisará de hardware e software descritos em [sistemas de sala Skype v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33693-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="33693-107">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="33693-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="33693-108">Preparar a imagem da instalação</span><span class="sxs-lookup"><span data-stu-id="33693-108">Prepare the installation image</span></span>](console.md#Prep_Image)
    
- [<span data-ttu-id="33693-109">Instalar um certificado de autoridade de certificação privado no dispositivo tablet</span><span class="sxs-lookup"><span data-stu-id="33693-109">Install a private CA certificate on the tablet device</span></span>](console.md#Certs)
    
- [<span data-ttu-id="33693-110">Instalar o Windows 10 e o aplicativo de console do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="33693-110">Install Windows 10 and the Skype Room Systems v2 console app </span></span>](console.md#Reimage)
   
- [<span data-ttu-id="33693-111">Conjunto inicial backup do Console</span><span class="sxs-lookup"><span data-stu-id="33693-111">Initial set up of the Console </span></span>](console.md#Initial)
    
- [<span data-ttu-id="33693-112">Lista de verificação de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="33693-112">Skype Room Systems v2 Deployment Checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="33693-113">Sistemas de sala Skype v2 exemplos funcionam apenas em um Skype configurada adequadamente para onde as contas de dispositivo estão configuradas corretamente conforme descrito em [implantar sistemas de sala Skype v2](room-systems-v2.md)do ambiente de negócios.</span><span class="sxs-lookup"><span data-stu-id="33693-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-image"></a><span data-ttu-id="33693-114">Preparar a imagem da instalação</span><span class="sxs-lookup"><span data-stu-id="33693-114">Prepare the installation image</span></span>
<span data-ttu-id="33693-115"><a name="Prep_Image"> </a></span><span class="sxs-lookup"><span data-stu-id="33693-115"></span></span>

<span data-ttu-id="33693-116">A instalação de sistemas de sala Skype v2 aplicativo em um 4 de Surface Pro ou Surface Pro requer um dispositivo de armazenamento USB com pelo menos 32GB de memória formatado como um disco FAT32.</span><span class="sxs-lookup"><span data-stu-id="33693-116">Installing the Skype Room Systems v2 app on a Surface Pro 4 or Surface Pro requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="33693-117">Não deve haver nenhum outro arquivo no dispositivo, todos os arquivos existentes no armazenamento USB serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="33693-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="33693-118">Se não for possível criar a imagem do console de acordo com estas instruções, provavelmente ocorrerão comportamentos inesperados.</span><span class="sxs-lookup"><span data-stu-id="33693-118">Failure to create your console image according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="33693-119">Atualização do Windows 10 Enterprise Data especial (versão 1607) não é mais suportada para criação de imagem do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="33693-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 image creation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="33693-120">Um v2 Skype sala sistemas existentes com Windows 10 Enterprise Data especial Update mudando para sistemas de sala Skype v2 atualização 3 por meio da Windows Store funcionará, mas deve ser feita uma nova instalação, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="33693-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="33693-121">Baixe o [MSU para KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span><span class="sxs-lookup"><span data-stu-id="33693-121">Download the [MSU for KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).</span></span>
2. <span data-ttu-id="33693-122">Baixe o [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="33693-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
3. <span data-ttu-id="33693-123">Coloque o MSU para KB4056892 no mesmo diretório que o script CreateSrsMedia.ps1.</span><span class="sxs-lookup"><span data-stu-id="33693-123">Place the MSU for KB4056892 in the same directory as the CreateSrsMedia.ps1 script.</span></span>
4. <span data-ttu-id="33693-124">Execute o script de CreateSrsMedia.ps1 por um prompt elevado em uma máquina Windows 10.</span><span class="sxs-lookup"><span data-stu-id="33693-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="33693-125">Siga as instruções do script para criar um disco de instalação do Skype sala sistemas v2 USB.</span><span class="sxs-lookup"><span data-stu-id="33693-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="33693-126">Quando terminar, remova o disco USB do computador e prossiga para [instalar o Windows 10 e o aplicativo de console do Skype sala sistemas v2 ](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="33693-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app ](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="33693-127">Instalar o Windows 10 e o aplicativo de console Skype Room Systems versão 2 </span><span class="sxs-lookup"><span data-stu-id="33693-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="33693-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="33693-128"></span></span>

<span data-ttu-id="33693-129">Agora, você precisa aplicar a imagem que criou.</span><span class="sxs-lookup"><span data-stu-id="33693-129">You now need to apply the image you've created.</span></span> <span data-ttu-id="33693-130">O tablet será executado como um aparelho e o usuário padrão será definido como executar somente o aplicativo de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="33693-130">The tablet will run as an appliance and the default user will be set to only run the Skype Room Systems v2 app.</span></span> 
  
1. <span data-ttu-id="33693-131">O tablet deve estar conectado a uma fonte de energia.</span><span class="sxs-lookup"><span data-stu-id="33693-131">The tablet should be connected to a power source.</span></span> <span data-ttu-id="33693-132">Inicie a partir de um estado totalmente desligado.</span><span class="sxs-lookup"><span data-stu-id="33693-132">Start from a completely powered-off state.</span></span> <span data-ttu-id="33693-133">Se necessário, mantenha pressionado o botão de energia até o tablet desligar.</span><span class="sxs-lookup"><span data-stu-id="33693-133">If necessary, press and keep pressing the Power button until the tablet switches off.</span></span>
    
2. <span data-ttu-id="33693-134">Conecte ao tablet o disco de instalação USB.</span><span class="sxs-lookup"><span data-stu-id="33693-134">Plug your USB Setup disk into the tablet.</span></span>
    
3. <span data-ttu-id="33693-135">Mantenha pressionado o botão de abaixar o volume (-) no tablet.</span><span class="sxs-lookup"><span data-stu-id="33693-135">Press and continue to hold the volume down (-) button on the tablet.</span></span> 
    
4. <span data-ttu-id="33693-136">Pressione e solte o botão liga/desliga do tablet.</span><span class="sxs-lookup"><span data-stu-id="33693-136">Press and release the power button on the tablet.</span></span>
    
5. <span data-ttu-id="33693-137">Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).</span><span class="sxs-lookup"><span data-stu-id="33693-137">Once Windows setup is booted, release the volume down (-) button.</span></span>
    
6. <span data-ttu-id="33693-138">O sistema será desligado depois que a instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="33693-138">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="33693-139">Depois que o sistema foi desligado, é seguro remover o disco de instalação do USB.</span><span class="sxs-lookup"><span data-stu-id="33693-139">After the system has shut down, it is safe to remove the USB Setup Disk.</span></span> <span data-ttu-id="33693-140">Nesse momento, você pode colocar o tablet no encaixe e conectar os periféricos necessários para sua sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="33693-140">At this point, you can place the tablet in the dock and attach the peripherals needed for your meeting room.</span></span> <span data-ttu-id="33693-141">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="33693-141">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="33693-142">Seleção de idioma no Creator’s Update</span><span class="sxs-lookup"><span data-stu-id="33693-142">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="33693-143">Em atualização do criador, você precisará usar o script de ApplyCurrentRegionAndLanguage.ps1 em cenários onde a seleção de idioma implícita não fornecer ao usuário com a linguagem de aplicativos real querem (por exemplo, eles querem que o aplicativo surgir em francês, mas é chegando em inglês).</span><span class="sxs-lookup"><span data-stu-id="33693-143">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="33693-144">As instruções a seguir funcionam apenas em dispositivos criados usando o Windows Creator's Update.</span><span class="sxs-lookup"><span data-stu-id="33693-144">The following instructions work only for devices created using Windows Creator's Update.</span></span> <span data-ttu-id="33693-145">Os sistemas herdados/disponíveis no mercado que não foram representados adequadamente no novo sistema de provisionamento não poderão usar essas instruções, mas também não deverão apresentar o problema inicial que exigia essa intervenção manual (a edição de aniversário permite que você escolha o idioma do seu aplicativo explicitamente como parte da configuração).</span><span class="sxs-lookup"><span data-stu-id="33693-145">Legacy/in-market systems that have not been re-imaged properly to the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span> 
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="33693-146">Para aplicar o idioma desejado</span><span class="sxs-lookup"><span data-stu-id="33693-146">To apply your desired language</span></span>

1. <span data-ttu-id="33693-147">Mude para o modo de Administrador.</span><span class="sxs-lookup"><span data-stu-id="33693-147">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="33693-148">Selecione o menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="33693-148">Select the Start menu.</span></span>
    
3. <span data-ttu-id="33693-149">Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="33693-149">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="33693-150">Selecione **tempo &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="33693-150">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="33693-151">Selecione **região &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="33693-151">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="33693-152">Selecione **Adicionar um idioma**.</span><span class="sxs-lookup"><span data-stu-id="33693-152">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="33693-153">Selecione o idioma que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="33693-153">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="33693-154">Selecione o idioma que você acabou de adicionar à lista de "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="33693-154">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="33693-155">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="33693-155">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="33693-156">Para idiomas que deseja remover:</span><span class="sxs-lookup"><span data-stu-id="33693-156">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="33693-157">a.</span><span class="sxs-lookup"><span data-stu-id="33693-157">a.</span></span> <span data-ttu-id="33693-158">Selecione o idioma que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="33693-158">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="33693-159">b.</span><span class="sxs-lookup"><span data-stu-id="33693-159">b.</span></span> <span data-ttu-id="33693-160">Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="33693-160">Select **Remove**.</span></span>
    
11. <span data-ttu-id="33693-161">Inicie um prompt de comandos com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="33693-161">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="33693-162">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="33693-162">Run the following command:</span></span> 
    
    <span data-ttu-id="33693-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="33693-163">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="33693-164">Reinicie o sistema.</span><span class="sxs-lookup"><span data-stu-id="33693-164">Restart the system.</span></span>
    
<span data-ttu-id="33693-165">O idioma desejado agora é aplicado ao dispositivo v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="33693-165">Your desired language is now applied to the Skype Room Systems v2 device.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="33693-166">Configuração inicial do console </span><span class="sxs-lookup"><span data-stu-id="33693-166">Initial set up of the Console</span></span>
<span data-ttu-id="33693-167"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="33693-167"></span></span>

<span data-ttu-id="33693-168">Após a instalação do Windows, o aplicativo do Skype sala sistemas v2 entrará em seu processo de instalação inicial, quando ele é iniciado próximo ou se a opção /reboot foi escolhida.</span><span class="sxs-lookup"><span data-stu-id="33693-168">After Windows is installed, the Skype Room Systems v2 app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="33693-p111">A tela Conta de Usuário é exibida. Digite o endereço de entrada do Skype (no formato usuário@domínio) da conta da sala a ser usada com o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33693-p111">The User Account screen appears. Enter the Skype sign-in address (in user@domain format) of the room account to be used with the device.</span></span>
    
2. <span data-ttu-id="33693-171">Digite a senha para a conta da sala e digite-a novamente para verificar.</span><span class="sxs-lookup"><span data-stu-id="33693-171">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="33693-172">Em "Configurar domínio", defina o FQDN para o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="33693-172">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="33693-173">Se o Skype para o domínio SIP de negócios for diferente do domínio do Exchange do usuário, insira o domínio do Exchange neste campo.</span><span class="sxs-lookup"><span data-stu-id="33693-173">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="33693-174">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="33693-174">Click **Next**.</span></span>
    
5. <span data-ttu-id="33693-175">Selecione os dispositivos indicados na tela recursos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="33693-175">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="33693-176">O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado.</span><span class="sxs-lookup"><span data-stu-id="33693-176">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="33693-177">Os dispositivos para selecionar são:</span><span class="sxs-lookup"><span data-stu-id="33693-177">The devices to select are:</span></span>
    
   - <span data-ttu-id="33693-178">Microfone para conferência: o microfone padrão para a sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="33693-178">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="33693-179">Alto-falante para conferência: o alto-falante padrão para conferência </span><span class="sxs-lookup"><span data-stu-id="33693-179">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="33693-180">Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.</span><span class="sxs-lookup"><span data-stu-id="33693-180">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="33693-p114">Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33693-p114">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="33693-183">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="33693-183">Click **Finish**.</span></span>
    
<span data-ttu-id="33693-184">O aplicativo deve iniciar imediatamente entrando no Skype para Business Server 2015 com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com Exchange usando as mesmas credenciais.</span><span class="sxs-lookup"><span data-stu-id="33693-184">The app should immediately start signing in to Skype for Business Server 2015 with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="33693-185">Para obter detalhes sobre como usar o aplicativo, consulte a [Ajuda de sistemas de sala Skype versão 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="33693-185">For details on using the app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="33693-186">Sistemas de sala Skype v2 depende da presença de hardware do console Certificados (o Logitech SmartDock).</span><span class="sxs-lookup"><span data-stu-id="33693-186">Skype Room Systems v2 relies on the presence of certified console hardware (the Logitech SmartDock).</span></span> <span data-ttu-id="33693-187">Mesmo uma imagem criada corretamente que contém o aplicativo de v2 de sistemas de sala Skype carregado em uma 4 do Surface Pro ou Surface Pro não inicializa passado o procedimento de instalação inicial, a menos que o hardware do console for detectado.</span><span class="sxs-lookup"><span data-stu-id="33693-187">Even a correctly created image containing the Skype Room Systems v2 app loaded on a Surface Pro 4 or Surface Pro will not boot past the initial setup procedure unless the console hardware is detected.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="33693-188">Talvez os usuários de alguns idiomas diferentes do inglês precisem de um teclado físico conectado ao console durante a instalação inicial, caso alguns símbolos não tenham suporte no teclado virtual.</span><span class="sxs-lookup"><span data-stu-id="33693-188">Some non-English language users may need a physical keyboard connected to the Console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span> 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a><span data-ttu-id="33693-189">Instale um certificado de Autoridade de Certificação privado no tablet</span><span class="sxs-lookup"><span data-stu-id="33693-189">Install a private CA certificate on the tablet device</span></span>
<span data-ttu-id="33693-190"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="33693-190"></span></span>

<span data-ttu-id="33693-191">O dispositivo de v2 Skype sala sistemas deve confiar nos certificados usados pelo Skype para servidores de negócios e Exchange a que conecta-se.</span><span class="sxs-lookup"><span data-stu-id="33693-191">The Skype Room Systems v2 device needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="33693-192">No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="33693-192">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="33693-193">No caso em que a autoridade de certificação é particular, por exemplo, uma implantação de local com o Active Directory e a autoridade de certificação do Windows, você pode adicionar o certificado ao dispositivo v2 Skype sala sistemas de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="33693-193">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 device in a couple of ways:</span></span>
  
- <span data-ttu-id="33693-194">Você pode adicionar o dispositivo ao Active Directory. Assim, os certificados necessários serão automaticamente adicionados, já que a Autoridade de Certificação é publicada no Active Directory (opção de implantação normal).</span><span class="sxs-lookup"><span data-stu-id="33693-194">You can join the device to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="33693-p118">Você pode instalar o certificado manualmente após o processo de geração de imagens. Antes disso, você deve concluir a [Configuração inicial do console](console.md#Initial). </span><span class="sxs-lookup"><span data-stu-id="33693-p118">You can install the certificate manually after the imaging process. Before you do this, you must complete [Initial set up of the Console ](console.md#Initial).</span></span> 
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="33693-197">Para instalar o certificado manualmente </span><span class="sxs-lookup"><span data-stu-id="33693-197">To manually install the certificate</span></span>

1. <span data-ttu-id="33693-198">Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="33693-198">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="33693-199">Coloque o 4 de superfície no modo de administração (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="33693-199">Place the Surface 4 in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="33693-200">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="33693-200">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="33693-201">Ingressar em um domínio do Active Directory (Opcional)</span><span class="sxs-lookup"><span data-stu-id="33693-201">Join an Active Directory Domain (Optional)</span></span>
<span data-ttu-id="33693-202"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="33693-202"></span></span>

<span data-ttu-id="33693-203">Você pode ingressar em dispositivos do Skype sala sistemas v2 para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="33693-203">You can join Skype Room Systems v2 devices to your domain.</span></span> <span data-ttu-id="33693-204">Dispositivos de v2 Skype sala sistemas devem ser colocados em uma UO separada estações de trabalho do seu PC porque muitos políticas de estação de trabalho não são compatíveis com sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="33693-204">Skype Room Systems v2 devices should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="33693-205">Um exemplo comum são as diretivas de aplicação da senha que impeça os sistemas de sala Skype v2 seja iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="33693-205">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="33693-206">Para obter informações sobre o gerenciamento de configurações do GPO, consulte [gerenciar sistemas de sala Skype v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="33693-206">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span> 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="33693-207">Para fazer o Skype Room Systems versão 2 ingressar em um domínio</span><span class="sxs-lookup"><span data-stu-id="33693-207">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="33693-208">Sinal de login no console do que o administrador da conta (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="33693-208">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="33693-209">Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.</span><span class="sxs-lookup"><span data-stu-id="33693-209">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="33693-210">Digite o seguinte comando no Powershell:</span><span class="sxs-lookup"><span data-stu-id="33693-210">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="33693-211">Por exemplo, se o seu domínio totalmente qualificado for redmond.corp.microsoft.com e quiser que seus dispositivos de v2 Skype sala sistemas estejam em uma "sala Skype sistemas v2" UO que é um filho de uma unidade Organizacional "recursos", o comando será:</span><span class="sxs-lookup"><span data-stu-id="33693-211">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 devices to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="33693-212">Se você gostaria de renomear o computador ao ingressarem-lo a um domínio, use o sinalizador - NewName seguido pelo nome do novo do computador.</span><span class="sxs-lookup"><span data-stu-id="33693-212">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="33693-213">Lista de verificação de implantação do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="33693-213">Skype Room Systems v2 Deployment Checklist</span></span>
<span data-ttu-id="33693-214"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="33693-214"></span></span>

<span data-ttu-id="33693-215">Use a lista de verificação a seguir ao fazer uma verificação final de que o dispositivo de console e todos os seus periféricos estão completamente configurados:</span><span class="sxs-lookup"><span data-stu-id="33693-215">Use the following checklist while doing a final verification that the console device and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="33693-216">**Configurações do aplicativo**</span><span class="sxs-lookup"><span data-stu-id="33693-216">**Application Settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="33693-217">☐</span><span class="sxs-lookup"><span data-stu-id="33693-217">☐</span></span>  <br/> |<span data-ttu-id="33693-218">O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console</span><span class="sxs-lookup"><span data-stu-id="33693-218">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="33693-219">☐</span><span class="sxs-lookup"><span data-stu-id="33693-219">☐</span></span>  <br/> |<span data-ttu-id="33693-220">O nome do computador Windows está definido corretamente (útil para administração remota)</span><span class="sxs-lookup"><span data-stu-id="33693-220">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="33693-221">☐</span><span class="sxs-lookup"><span data-stu-id="33693-221">☐</span></span>  <br/> |<span data-ttu-id="33693-222">A senha da conta do administrador foi definida e verificada</span><span class="sxs-lookup"><span data-stu-id="33693-222">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="33693-223">☐</span><span class="sxs-lookup"><span data-stu-id="33693-223">☐</span></span>  <br/> |<span data-ttu-id="33693-224">Todas as atualizações de sistema do Surface Pro 4 ou do Surface Pro foram aplicadas</span><span class="sxs-lookup"><span data-stu-id="33693-224">All Surface Pro 4 or Surface Pro System Updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="33693-225">**Periféricos de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="33693-225">**Audio/Video Peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="33693-226">☐</span><span class="sxs-lookup"><span data-stu-id="33693-226">☐</span></span>  <br/> |<span data-ttu-id="33693-227">A versão do firmware do periférico da câmera está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="33693-227">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="33693-228">☐</span><span class="sxs-lookup"><span data-stu-id="33693-228">☐</span></span>  <br/> |<span data-ttu-id="33693-229">Câmera funcional e forma ideal posicionada</span><span class="sxs-lookup"><span data-stu-id="33693-229">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="33693-230">☐</span><span class="sxs-lookup"><span data-stu-id="33693-230">☐</span></span>  <br/> |<span data-ttu-id="33693-231">Configurações do dispositivo de reprodução padrão e reprodução de dispositivo de comunicação padrão definida como áudio pretendido periféricos</span><span class="sxs-lookup"><span data-stu-id="33693-231">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="33693-232">☐</span><span class="sxs-lookup"><span data-stu-id="33693-232">☐</span></span>  <br/> |<span data-ttu-id="33693-233">Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="33693-233">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="33693-234">☐</span><span class="sxs-lookup"><span data-stu-id="33693-234">☐</span></span>  <br/> |<span data-ttu-id="33693-235">A versão do firmware do periférico de áudio está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="33693-235">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="33693-236">☐</span><span class="sxs-lookup"><span data-stu-id="33693-236">☐</span></span>  <br/> |<span data-ttu-id="33693-237">Dispositivo de entrada de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="33693-237">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="33693-238">☐</span><span class="sxs-lookup"><span data-stu-id="33693-238">☐</span></span>  <br/> |<span data-ttu-id="33693-239">Dispositivo de saída de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="33693-239">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="33693-240">**Encaixe**</span><span class="sxs-lookup"><span data-stu-id="33693-240">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="33693-241">☐</span><span class="sxs-lookup"><span data-stu-id="33693-241">☐</span></span>  <br/> |<span data-ttu-id="33693-242">Os cabos estão presos e não estão dobrados</span><span class="sxs-lookup"><span data-stu-id="33693-242">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="33693-243">☐</span><span class="sxs-lookup"><span data-stu-id="33693-243">☐</span></span>  <br/> |<span data-ttu-id="33693-244">Ingestão de áudio via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="33693-244">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="33693-245">☐</span><span class="sxs-lookup"><span data-stu-id="33693-245">☐</span></span>  <br/> |<span data-ttu-id="33693-246">Ingestão de vídeo via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="33693-246">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="33693-247">☐</span><span class="sxs-lookup"><span data-stu-id="33693-247">☐</span></span>  <br/> |<span data-ttu-id="33693-248">O encaixe pode girar livremente</span><span class="sxs-lookup"><span data-stu-id="33693-248">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="33693-249">☐</span><span class="sxs-lookup"><span data-stu-id="33693-249">☐</span></span>  <br/> |<span data-ttu-id="33693-250">O brilho da tela é aceitável para o ambiente</span><span class="sxs-lookup"><span data-stu-id="33693-250">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="33693-251">Ver também</span><span class="sxs-lookup"><span data-stu-id="33693-251">See also</span></span>
<span data-ttu-id="33693-252"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="33693-252"></span></span>

#### 

[<span data-ttu-id="33693-253">Planejar a sala Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="33693-253">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="33693-254">Implantar Skype sala v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="33693-254">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="33693-255">Configurar um console v2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="33693-255">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="33693-256">Gerenciar Skype sala v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="33693-256">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

