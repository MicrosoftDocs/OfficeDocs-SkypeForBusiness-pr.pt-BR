---
title: Configurar o console do Skype Room Systems versão 2
ms.author: jambirk
author: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console do Skype sala sistemas v2 e seus periféricos.
ms.openlocfilehash: d652f4e7ccfd8b8630ce48b028f8f4ce7226a693
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887511"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="c660f-103">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="c660f-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="c660f-104">Este artigo descreve como configurar o console do Skype sala sistemas v2 e seus periféricos.</span><span class="sxs-lookup"><span data-stu-id="c660f-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="c660f-105">Você só deve executar estas etapas se o Skype necessária para contas de negócios e do Exchange já foram criado e testado, conforme descrito em [implantar sistemas de sala Skype v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c660f-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="c660f-106">Você precisará de hardware e software descritos em [sistemas de sala Skype v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c660f-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="c660f-107">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="c660f-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c660f-108">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="c660f-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="c660f-109">Instale um certificado de autoridade de certificação privado no console do</span><span class="sxs-lookup"><span data-stu-id="c660f-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="c660f-110">Instalar o Windows 10 e o aplicativo de console Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="c660f-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="c660f-111">Conjunto inicial backup do console</span><span class="sxs-lookup"><span data-stu-id="c660f-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="c660f-112">Lista de verificação de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="c660f-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="c660f-113">Sistemas de sala Skype v2 exemplos funcionam apenas em um Skype configurada adequadamente para onde as contas de dispositivo estão configuradas corretamente conforme descrito em [implantar sistemas de sala Skype v2](room-systems-v2.md)do ambiente de negócios.</span><span class="sxs-lookup"><span data-stu-id="c660f-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> 
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="c660f-114">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="c660f-114">Prepare the installation media</span></span>
<span data-ttu-id="c660f-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="c660f-115"></span></span>

<span data-ttu-id="c660f-116">Instalar o aplicativo de console do Skype sala sistemas v2 requer um dispositivo de armazenamento USB com pelo menos 32GB de memória formatado como um disco FAT32.</span><span class="sxs-lookup"><span data-stu-id="c660f-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of memory formatted as a FAT32 disk.</span></span> <span data-ttu-id="c660f-117">Não deve haver outros arquivos no dispositivo. Os arquivos existentes no armazenamento USB serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="c660f-117">There should be no other files on the device, any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c660f-118">Falha ao criar sua mídia de instalação do Skype sala sistemas v2 acordo com estas instruções provavelmente resultará em um comportamento inesperado.</span><span class="sxs-lookup"><span data-stu-id="c660f-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span> <span data-ttu-id="c660f-119">Atualização do Windows 10 Enterprise Data especial (versão 1607) não é mais suportada para criação de mídia de instalação do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="c660f-119">Windows 10 Enterprise Anniversary Update (Version 1607) is no longer supported for Skype Room Systems v2 installation media creation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c660f-120">Um v2 Skype sala sistemas existentes com Windows 10 Enterprise Data especial Update mudando para sistemas de sala Skype v2 atualização 3 por meio da Windows Store funcionará, mas deve ser feita uma nova instalação, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="c660f-120">An existing Skype Room Systems v2 with Windows 10 Enterprise Anniversary Update moving to Skype Room Systems v2 update 3 by way of the Windows Store will work, but a new installation should be done as described below.</span></span> 
  
1. <span data-ttu-id="c660f-121">Baixe o [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="c660f-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="c660f-122">(Opcional) Baixe e colocar quaisquer arquivos CAB do pacote de idioma desejado no mesmo diretório que o script.</span><span class="sxs-lookup"><span data-stu-id="c660f-122">(Optional) Download and place any desired language pack CAB files in the same directory as the script.</span></span> <span data-ttu-id="c660f-123">O script indicará onde você pode baixar os arquivos do pacote de idioma apropriados para o tipo de mídia que você está criando, se não tiver certeza onde adquirir os pacotes de idiomas do.</span><span class="sxs-lookup"><span data-stu-id="c660f-123">The script will indicate where you can download language pack files appropriate for the type of media you are creating, if you're unsure where to acquire the language packs from.</span></span>
3. <span data-ttu-id="c660f-124">Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c660f-124">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>


<span data-ttu-id="c660f-125">Siga as instruções do script para criar um disco de instalação do Skype sala sistemas v2 USB.</span><span class="sxs-lookup"><span data-stu-id="c660f-125">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span> <span data-ttu-id="c660f-126">Quando terminar, remova o disco USB do computador e prossiga para [instalar o Windows 10 e o aplicativo de console do Skype sala sistemas v2](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="c660f-126">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="c660f-127">Instalar o Windows 10 e o aplicativo de console Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="c660f-127">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="c660f-128"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c660f-128"></span></span>

<span data-ttu-id="c660f-129">Agora, você precisa aplicar a mídia de instalação que você criou.</span><span class="sxs-lookup"><span data-stu-id="c660f-129">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="c660f-130">O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido como executar somente o aplicativo de console do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="c660f-130">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="c660f-131">Se o dispositivo de destino será instalado em um (por exemplo, um Surface Pro) de encaixe, desconecte-o do encaixe.</span><span class="sxs-lookup"><span data-stu-id="c660f-131">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="c660f-132">Certifique-se de que o dispositivo de destino não está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="c660f-132">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="c660f-133">Certifique-se de que o dispositivo de destino está conectado à alimentação AC.</span><span class="sxs-lookup"><span data-stu-id="c660f-133">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="c660f-134">Conecte seu disco de instalação do USB no dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="c660f-134">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="c660f-135">Inicialize o disco de instalação do USB.</span><span class="sxs-lookup"><span data-stu-id="c660f-135">Boot to the USB setup disk.</span></span> <span data-ttu-id="c660f-136">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="c660f-136">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="c660f-137">Se seu dispositivo de destino for um Surface Pro, use as seguintes etapas para inicializar o disco de instalação do USB:</span><span class="sxs-lookup"><span data-stu-id="c660f-137">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    1. <span data-ttu-id="c660f-138">Pressione e continue armazenar o volume (-) botão pressionado.</span><span class="sxs-lookup"><span data-stu-id="c660f-138">Press and continue to hold the volume down (-) button.</span></span>

    2. <span data-ttu-id="c660f-139">Pressione e solte o botão de energia.</span><span class="sxs-lookup"><span data-stu-id="c660f-139">Press and release the power button.</span></span>

    3. <span data-ttu-id="c660f-140">Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).</span><span class="sxs-lookup"><span data-stu-id="c660f-140">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="c660f-141">O sistema será desligado depois que a instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="c660f-141">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="c660f-142">Depois que o sistema foi desligado, é seguro remover o disco de instalação do USB.</span><span class="sxs-lookup"><span data-stu-id="c660f-142">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="c660f-143">Neste ponto, você pode colocar o devcie de destino no seu encaixe (se estiver usando um produto com base em encaixe), anexar os periféricos necessários para a sala de reunião e conectar à rede.</span><span class="sxs-lookup"><span data-stu-id="c660f-143">At this point, you can place the target devcie in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="c660f-144">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="c660f-144">Refer to the manufacturer instructions.</span></span>
  
 
### <a name="selecting-a-language-in-creators-update"></a><span data-ttu-id="c660f-145">Seleção de idioma no Creator’s Update</span><span class="sxs-lookup"><span data-stu-id="c660f-145">Selecting a language in Creator's Update</span></span>

<span data-ttu-id="c660f-146">Em atualização do criador, você precisará usar o script de ApplyCurrentRegionAndLanguage.ps1 em cenários onde a seleção de idioma implícita não fornecer ao usuário com a linguagem de aplicativos real querem (por exemplo, eles querem que o aplicativo de console surgir em francês, mas ele está chegando em inglês).</span><span class="sxs-lookup"><span data-stu-id="c660f-146">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c660f-147">As instruções a seguir funcionam apenas para consoles criados usando Update do criador do Windows.</span><span class="sxs-lookup"><span data-stu-id="c660f-147">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="c660f-148">Sistemas herdados/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não será capazes de usar estas instruções, mas também deve não sofrem o problema inicial que requer intervenção este manual (edição de aniversário permitam que você escolha sua idioma App explicitamente como parte da instalação).</span><span class="sxs-lookup"><span data-stu-id="c660f-148">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c660f-149">Para aplicar o idioma desejado</span><span class="sxs-lookup"><span data-stu-id="c660f-149">To apply your desired language</span></span>

1. <span data-ttu-id="c660f-150">Mude para o modo de Administrador.</span><span class="sxs-lookup"><span data-stu-id="c660f-150">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c660f-151">Selecione o menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="c660f-151">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c660f-152">Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="c660f-152">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c660f-153">Selecione **tempo &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="c660f-153">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c660f-154">Selecione **região &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="c660f-154">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c660f-155">Selecione **Adicionar um idioma**.</span><span class="sxs-lookup"><span data-stu-id="c660f-155">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c660f-156">Selecione o idioma que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="c660f-156">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c660f-157">Selecione o idioma que você acabou de adicionar à lista de "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="c660f-157">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c660f-158">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="c660f-158">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c660f-159">Para idiomas que deseja remover:</span><span class="sxs-lookup"><span data-stu-id="c660f-159">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c660f-160">a.</span><span class="sxs-lookup"><span data-stu-id="c660f-160">a.</span></span> <span data-ttu-id="c660f-161">Selecione o idioma que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="c660f-161">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c660f-162">b.</span><span class="sxs-lookup"><span data-stu-id="c660f-162">b.</span></span> <span data-ttu-id="c660f-163">Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c660f-163">Select **Remove**.</span></span>
    
11. <span data-ttu-id="c660f-164">Inicie um prompt de comandos com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="c660f-164">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c660f-165">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c660f-165">Run the following command:</span></span> 
    
    <span data-ttu-id="c660f-166">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span><span class="sxs-lookup"><span data-stu-id="c660f-166">powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1</span></span>
    
13. <span data-ttu-id="c660f-167">Reinicie o sistema.</span><span class="sxs-lookup"><span data-stu-id="c660f-167">Restart the system.</span></span>
    
<span data-ttu-id="c660f-168">O idioma desejado agora é aplicado ao console v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="c660f-168">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c660f-169">Conjunto inicial backup do console</span><span class="sxs-lookup"><span data-stu-id="c660f-169">Initial set up of the console</span></span>
<span data-ttu-id="c660f-170"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c660f-170"></span></span>

<span data-ttu-id="c660f-171">Após a instalação do Windows, o aplicativo de console do Skype sala sistemas v2 entrará em seu processo de instalação inicial, quando ele é iniciado próximo ou se a opção /reboot foi escolhida.</span><span class="sxs-lookup"><span data-stu-id="c660f-171">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c660f-172">A tela Conta de Usuário é exibida.</span><span class="sxs-lookup"><span data-stu-id="c660f-172">The User Account screen appears.</span></span> <span data-ttu-id="c660f-173">Insira o Skype endereço de entrada (no formato user@domain) da conta a ser usado com o console de sala.</span><span class="sxs-lookup"><span data-stu-id="c660f-173">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="c660f-174">Digite a senha para a conta da sala e digite-a novamente para verificar.</span><span class="sxs-lookup"><span data-stu-id="c660f-174">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c660f-175">Em "Configurar domínio", defina o FQDN para o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c660f-175">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c660f-176">Se o Skype para o domínio SIP de negócios for diferente do domínio do Exchange do usuário, insira o domínio do Exchange neste campo.</span><span class="sxs-lookup"><span data-stu-id="c660f-176">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c660f-177">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c660f-177">Click **Next**.</span></span>
    
5. <span data-ttu-id="c660f-178">Selecione os dispositivos indicados na tela recursos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c660f-178">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c660f-179">O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado.</span><span class="sxs-lookup"><span data-stu-id="c660f-179">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c660f-180">Os dispositivos para selecionar são:</span><span class="sxs-lookup"><span data-stu-id="c660f-180">The devices to select are:</span></span>
    
   - <span data-ttu-id="c660f-181">Microfone para conferência: o microfone padrão para a sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="c660f-181">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c660f-182">Alto-falante para conferência: o alto-falante padrão para conferência </span><span class="sxs-lookup"><span data-stu-id="c660f-182">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c660f-183">Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.</span><span class="sxs-lookup"><span data-stu-id="c660f-183">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
    <span data-ttu-id="c660f-p115">Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c660f-p115">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c660f-186">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c660f-186">Click **Finish**.</span></span>
    
<span data-ttu-id="c660f-187">O aplicativo de console do Skype sala sistemas v2 deve iniciar imediatamente entrando no Skype para Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com Exchange usando as mesmas credenciais.</span><span class="sxs-lookup"><span data-stu-id="c660f-187">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c660f-188">Para obter detalhes sobre como usar o aplicativo de console, consulte a [Ajuda de sistemas de sala Skype versão 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="c660f-188">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c660f-189">Sistemas de sala Skype v2 depende da presença de hardware do console certificados.</span><span class="sxs-lookup"><span data-stu-id="c660f-189">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="c660f-190">Mesmo uma imagem criada corretamente que contém o aplicativo de console do Skype sala sistemas v2 não inicializa passado o procedimento de instalação inicial, a menos que o hardware do console for detectado.</span><span class="sxs-lookup"><span data-stu-id="c660f-190">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="c660f-191">Para obter soluções Surface Pro com base, o Surface Pro deve estar conectada a seu hardware de encaixe acompanha para passar essa verificação.</span><span class="sxs-lookup"><span data-stu-id="c660f-191">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c660f-192">Alguns usuários de idioma diferente do inglês, talvez seja necessário um teclado físico conectado ao console durante a configuração inicial que símbolos não são suportados no teclado de toque.</span><span class="sxs-lookup"><span data-stu-id="c660f-192">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="c660f-193">Instale um certificado de autoridade de certificação privado no console do</span><span class="sxs-lookup"><span data-stu-id="c660f-193">Install a private CA certificate on the console</span></span>
<span data-ttu-id="c660f-194"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c660f-194"></span></span>

<span data-ttu-id="c660f-195">O console do Skype sala sistemas v2 deve confiar nos certificados usados pelo Skype para servidores de negócios e Exchange a que conecta-se.</span><span class="sxs-lookup"><span data-stu-id="c660f-195">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="c660f-196">No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c660f-196">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c660f-197">No caso em que a autoridade de certificação é particular, por exemplo, uma implantação de local com o Active Directory e a autoridade de certificação do Windows, você pode adicionar o certificado ao console v2 Skype sala sistemas de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="c660f-197">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="c660f-198">Ingresse o console do Active Directory e que adicionará automaticamente os certificados necessários dado da autoridade de certificação é publicado no Active Directory (opção de implantação normal).</span><span class="sxs-lookup"><span data-stu-id="c660f-198">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c660f-199">Você pode instalar o certificado manualmente após o processo de geração de imagens.</span><span class="sxs-lookup"><span data-stu-id="c660f-199">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="c660f-200">Antes de fazer isso, você deve concluir a [Configurar as iniciais do console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="c660f-200">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c660f-201">Para instalar o certificado manualmente </span><span class="sxs-lookup"><span data-stu-id="c660f-201">To manually install the certificate</span></span>

1. <span data-ttu-id="c660f-202">Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="c660f-202">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c660f-203">Coloque o console no modo de administração (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="c660f-203">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c660f-204">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c660f-204">Run the following command:</span></span>
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c660f-205">Ingressar em um domínio do Active Directory (opcional)</span><span class="sxs-lookup"><span data-stu-id="c660f-205">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="c660f-206"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c660f-206"></span></span>

<span data-ttu-id="c660f-207">Você pode ingressar consoles de v2 de sistemas de sala Skype para seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c660f-207">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="c660f-208">Consoles de v2 Skype sala sistemas devem ser colocados em uma UO separada estações de trabalho do seu PC porque muitos políticas de estação de trabalho não são compatíveis com sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="c660f-208">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="c660f-209">Um exemplo comum são as diretivas de aplicação da senha que impeça os sistemas de sala Skype v2 seja iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c660f-209">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="c660f-210">Para obter informações sobre o gerenciamento de configurações do GPO, consulte [gerenciar sistemas de sala Skype v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c660f-210">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="c660f-211">Para fazer o Skype Room Systems versão 2 ingressar em um domínio</span><span class="sxs-lookup"><span data-stu-id="c660f-211">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="c660f-212">Sinal de login no console do que o administrador da conta (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="c660f-212">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c660f-213">Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.</span><span class="sxs-lookup"><span data-stu-id="c660f-213">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c660f-214">Digite o seguinte comando no Powershell:</span><span class="sxs-lookup"><span data-stu-id="c660f-214">Enter the following command in Powershell:</span></span>
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

<span data-ttu-id="c660f-215">Por exemplo, se o seu domínio totalmente qualificado for redmond.corp.microsoft.com e quiser que seus consoles de v2 Skype sala sistemas estejam em uma "sala Skype sistemas v2" UO que é um filho de uma unidade Organizacional "recursos", o comando será:</span><span class="sxs-lookup"><span data-stu-id="c660f-215">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c660f-216">Se você gostaria de renomear o computador ao ingressarem-lo a um domínio, use o sinalizador - NewName seguido pelo nome do novo do computador.</span><span class="sxs-lookup"><span data-stu-id="c660f-216">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="c660f-217">Lista de verificação de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="c660f-217">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="c660f-218"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c660f-218"></span></span>

<span data-ttu-id="c660f-219">Use a seguinte lista de verificação enquanto efetua uma verificação final se o console e todos os seus periféricos totalmente estão configurados:</span><span class="sxs-lookup"><span data-stu-id="c660f-219">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c660f-220">**Configurações do aplicativo**</span><span class="sxs-lookup"><span data-stu-id="c660f-220">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c660f-221">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-221">☐</span></span>  <br/> |<span data-ttu-id="c660f-222">O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console</span><span class="sxs-lookup"><span data-stu-id="c660f-222">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c660f-223">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-223">☐</span></span>  <br/> |<span data-ttu-id="c660f-224">O nome do computador Windows está definido corretamente (útil para administração remota)</span><span class="sxs-lookup"><span data-stu-id="c660f-224">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c660f-225">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-225">☐</span></span>  <br/> |<span data-ttu-id="c660f-226">A senha da conta do administrador foi definida e verificada</span><span class="sxs-lookup"><span data-stu-id="c660f-226">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c660f-227">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-227">☐</span></span>  <br/> |<span data-ttu-id="c660f-228">Todas as atualizações de firmware tiverem sido aplicadas.</span><span class="sxs-lookup"><span data-stu-id="c660f-228">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c660f-229">**Periféricos de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="c660f-229">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c660f-230">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-230">☐</span></span>  <br/> |<span data-ttu-id="c660f-231">A versão do firmware do periférico da câmera está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="c660f-231">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c660f-232">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-232">☐</span></span>  <br/> |<span data-ttu-id="c660f-233">Câmera funcional e forma ideal posicionada</span><span class="sxs-lookup"><span data-stu-id="c660f-233">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c660f-234">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-234">☐</span></span>  <br/> |<span data-ttu-id="c660f-235">Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado </span><span class="sxs-lookup"><span data-stu-id="c660f-235">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c660f-236">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-236">☐</span></span>  <br/> |<span data-ttu-id="c660f-237">Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="c660f-237">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c660f-238">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-238">☐</span></span>  <br/> |<span data-ttu-id="c660f-239">A versão do firmware do periférico de áudio está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="c660f-239">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c660f-240">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-240">☐</span></span>  <br/> |<span data-ttu-id="c660f-241">Dispositivo de entrada de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="c660f-241">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c660f-242">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-242">☐</span></span>  <br/> |<span data-ttu-id="c660f-243">Dispositivo de saída de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="c660f-243">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c660f-244">**Encaixe**</span><span class="sxs-lookup"><span data-stu-id="c660f-244">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c660f-245">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-245">☐</span></span>  <br/> |<span data-ttu-id="c660f-246">Os cabos estão presos e não estão dobrados</span><span class="sxs-lookup"><span data-stu-id="c660f-246">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c660f-247">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-247">☐</span></span>  <br/> |<span data-ttu-id="c660f-248">Ingestão de áudio via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="c660f-248">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c660f-249">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-249">☐</span></span>  <br/> |<span data-ttu-id="c660f-250">Ingestão de vídeo via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="c660f-250">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c660f-251">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-251">☐</span></span>  <br/> |<span data-ttu-id="c660f-252">O encaixe pode girar livremente</span><span class="sxs-lookup"><span data-stu-id="c660f-252">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c660f-253">☐</span><span class="sxs-lookup"><span data-stu-id="c660f-253">☐</span></span>  <br/> |<span data-ttu-id="c660f-254">O brilho da tela é aceitável para o ambiente</span><span class="sxs-lookup"><span data-stu-id="c660f-254">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c660f-255">Ver também</span><span class="sxs-lookup"><span data-stu-id="c660f-255">See also</span></span>
<span data-ttu-id="c660f-256"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c660f-256"></span></span>

[<span data-ttu-id="c660f-257">Planejar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="c660f-257">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c660f-258">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="c660f-258">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c660f-259">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="c660f-259">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="c660f-260">Gerenciar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="c660f-260">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)