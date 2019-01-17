---
title: Configurar o console do Skype Room Systems versão 2
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console do Skype sala sistemas v2 e seus periféricos.
ms.openlocfilehash: 00203c8aa781c489d8a1cc8c2bf91a364bea057f
ms.sourcegitcommit: c7c8e5f6d8b25e68bf071745517d38eb45c1e172
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2019
ms.locfileid: "28694717"
---
# <a name="configure-a-skype-room-systems-v2-console"></a><span data-ttu-id="3c3aa-103">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-103">Configure a Skype Room Systems v2 console</span></span>
 
<span data-ttu-id="3c3aa-104">Este artigo descreve como configurar o console do Skype sala sistemas v2 e seus periféricos.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-104">This article describes how to set up the Skype Room Systems v2 console and its peripherals.</span></span>
  
<span data-ttu-id="3c3aa-105">Você só deve executar estas etapas se o Skype necessária para contas de negócios e do Exchange já foram criado e testado, conforme descrito em [implantar sistemas de sala Skype v2](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-105">You should only perform these steps if the necessary Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span> <span data-ttu-id="3c3aa-106">Você precisará de hardware e software descritos em [sistemas de sala Skype v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-106">You will need the hardware and software described in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span> <span data-ttu-id="3c3aa-107">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="3c3aa-108">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="3c3aa-108">Prepare the installation media</span></span>](console.md#Prep_Media)
    
- [<span data-ttu-id="3c3aa-109">Instale um certificado de autoridade de certificação privado no console do</span><span class="sxs-lookup"><span data-stu-id="3c3aa-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
    
- [<span data-ttu-id="3c3aa-110">Instalar o Windows 10 e o aplicativo de console Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-110">Install Windows 10 and the Skype Room Systems v2 console app</span></span>](console.md#Reimage)
   
- [<span data-ttu-id="3c3aa-111">Conjunto inicial backup do console</span><span class="sxs-lookup"><span data-stu-id="3c3aa-111">Initial set up of the console</span></span>](console.md#Initial)
    
- [<span data-ttu-id="3c3aa-112">Lista de verificação de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-112">Skype Room Systems v2 deployment checklist</span></span>](console.md#Checklist)
    
> [!NOTE]
> <span data-ttu-id="3c3aa-113">Sistemas de sala Skype v2 exemplos funcionam apenas em um Skype configurada adequadamente para onde as contas de dispositivo estão configuradas corretamente conforme descrito em [implantar sistemas de sala Skype v2](room-systems-v2.md)do ambiente de negócios.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-113">Skype Room Systems v2 will only work in a properly configured Skype for Business environment where the device accounts are set up correctly as described in [Deploy Skype Room Systems v2](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="3c3aa-114">Preparar a mídia de instalação</span><span class="sxs-lookup"><span data-stu-id="3c3aa-114">Prepare the installation media</span></span>
<span data-ttu-id="3c3aa-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="3c3aa-115"></span></span>

<span data-ttu-id="3c3aa-116">Instalar o aplicativo de console do Skype sala sistemas v2 requer um dispositivo de armazenamento USB com pelo menos 32GB de capacidade.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-116">Installing the Skype Room Systems v2 console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="3c3aa-117">Não deve haver nenhum outro arquivo no dispositivo. todos os arquivos existentes no armazenamento USB será perdidos.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c3aa-118">Falha ao criar sua mídia de instalação do Skype sala sistemas v2 acordo com estas instruções provavelmente resultará em um comportamento inesperado.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-118">Failure to create your Skype Room Systems v2 installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="3c3aa-119">O processo abaixo é para a criação de mídia de instalação para novos dispositivos de v2 Skype sala System image.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-119">The process below is for creating installation media to image new Skype Room System v2 devices.</span></span> <span data-ttu-id="3c3aa-120">Dispositivos existentes, por padrão, atualizam automaticamente do Windows Update e o repositório do Windows.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="3c3aa-121">Baixe o [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842). </span><span class="sxs-lookup"><span data-stu-id="3c3aa-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="3c3aa-122">Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="3c3aa-123">Siga as instruções do script para criar um disco de instalação do Skype sala sistemas v2 USB.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-123">Follow the script's instructions to create a Skype Room Systems v2 USB setup disk.</span></span>

> [!CAUTION]
> <span data-ttu-id="3c3aa-124">O nome da pasta que executar o script de criação de mídia não pode conter um espaço.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-124">The name of the folder that you run the media creation script from can not contain a space.</span></span> <span data-ttu-id="3c3aa-125">Se houver um espaço no nome de pasta, o script irá falhar.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-125">If there is a space in to folder name, the script will fail.</span></span>

<span data-ttu-id="3c3aa-126">O script CreateSrsMedia.ps1 automatiza as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="3c3aa-127">Baixe o instalador MSI mais recente para sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-127">Download the latest MSI installer for Skype Room Systems v2.</span></span>
2. <span data-ttu-id="3c3aa-128">Determine a compilação do Windows que o usuário deve fornecer.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="3c3aa-129">As versões liberadas recentemente podem ou não podem ser testadas e suportadas para uso com dispositivos do sistema de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-129">The most recently released versions may or may not be tested and supported for use with Skype Room System v2 devices.</span></span>
3. <span data-ttu-id="3c3aa-130">Baixe os componentes de suportados necessários.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="3c3aa-131">Monte os componentes necessários na mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="3c3aa-132">Quando terminar, remova o disco USB do computador e prossiga para [instalar o Windows 10 e o aplicativo de console do Skype sala sistemas v2](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-132">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Skype Room Systems v2 console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a><span data-ttu-id="3c3aa-133">Instalar o Windows 10 e o aplicativo de console Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-133">Install Windows 10 and the Skype Room Systems v2 console app</span></span>
<span data-ttu-id="3c3aa-134"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="3c3aa-134"></span></span>

<span data-ttu-id="3c3aa-135">Agora, você precisa aplicar a mídia de instalação que você criou.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-135">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="3c3aa-136">O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido como executar somente o aplicativo de console do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-136">The target device will run as an appliance and the default user will be set to only run the Skype Room Systems v2 console app.</span></span>

1. <span data-ttu-id="3c3aa-137">Se o dispositivo de destino será instalado em um (por exemplo, um Surface Pro) de encaixe, desconecte-o do encaixe.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-137">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="3c3aa-138">Certifique-se de que o dispositivo de destino não está conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-138">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="3c3aa-139">Certifique-se de que o dispositivo de destino está conectado à alimentação AC.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-139">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="3c3aa-140">Conecte seu disco de instalação do USB no dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-140">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="3c3aa-141">Inicialize o disco de instalação do USB.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-141">Boot to the USB setup disk.</span></span> <span data-ttu-id="3c3aa-142">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-142">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="3c3aa-143">Se seu dispositivo de destino for um Surface Pro, use as seguintes etapas para inicializar o disco de instalação do USB:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-143">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="3c3aa-144">a.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-144">a.</span></span> <span data-ttu-id="3c3aa-145">Pressione e continue armazenar o volume (-) botão pressionado.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-145">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="3c3aa-146">b.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-146">b.</span></span> <span data-ttu-id="3c3aa-147">Pressione e solte o botão de energia.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-147">Press and release the power button.</span></span>

    <span data-ttu-id="3c3aa-148">c.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-148">c.</span></span> <span data-ttu-id="3c3aa-149">Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-149">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="3c3aa-150">O sistema será desligado depois que a instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-150">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="3c3aa-151">Depois que o sistema foi desligado, é seguro remover o disco de instalação do USB.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-151">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="3c3aa-152">Neste ponto, você pode colocar o dispositivo de destino no seu encaixe (se estiver usando um produto com base em encaixe), anexar os periféricos necessários para a sala de reunião e conectar à rede.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-152">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="3c3aa-153">Consulte as instruções do fabricante.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-153">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="3c3aa-154">Selecionar um idioma</span><span class="sxs-lookup"><span data-stu-id="3c3aa-154">Selecting a language</span></span> 

<span data-ttu-id="3c3aa-155">Em atualização do criador, você precisará usar o script de ApplyCurrentRegionAndLanguage.ps1 em cenários onde a seleção de idioma implícita não fornecer ao usuário com a linguagem de aplicativos real querem (por exemplo, eles querem que o aplicativo de console surgir em francês, mas ele está chegando em inglês).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-155">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c3aa-156">As instruções a seguir funcionam apenas para consoles criados usando Update do criador do Windows.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-156">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="3c3aa-157">Sistemas herdados/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não será capazes de usar estas instruções, mas também deve não sofrem o problema inicial que requer intervenção este manual (edição de aniversário permitam que você escolha sua idioma App explicitamente como parte da instalação).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-157">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="3c3aa-158">Para aplicar o idioma desejado</span><span class="sxs-lookup"><span data-stu-id="3c3aa-158">To apply your desired language</span></span>

1. <span data-ttu-id="3c3aa-159">Mude para o modo de Administrador.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-159">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="3c3aa-160">Selecione o menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-160">Select the Start menu.</span></span>
    
3. <span data-ttu-id="3c3aa-161">Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-161">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="3c3aa-162">Selecione **tempo &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-162">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="3c3aa-163">Selecione **região &amp; idioma**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-163">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="3c3aa-164">Selecione **Adicionar um idioma**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-164">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="3c3aa-165">Selecione o idioma que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-165">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="3c3aa-166">Selecione o idioma que você acabou de adicionar à lista de "Idiomas".</span><span class="sxs-lookup"><span data-stu-id="3c3aa-166">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="3c3aa-167">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-167">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="3c3aa-168">Para idiomas que deseja remover:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-168">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="3c3aa-p113">a. Selecione o idioma que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-p113">a. Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="3c3aa-p114">b. Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-p114">b. Select **Remove**.</span></span>
    
11. <span data-ttu-id="3c3aa-173">Inicie um prompt de comandos com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-173">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="3c3aa-174">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-174">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="3c3aa-175">Reinicie o sistema.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-175">Restart the system.</span></span>
    
<span data-ttu-id="3c3aa-176">O idioma desejado agora é aplicado ao console v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-176">Your desired language is now applied to the Skype Room Systems v2 console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="3c3aa-177">Conjunto inicial backup do console</span><span class="sxs-lookup"><span data-stu-id="3c3aa-177">Initial set up of the console</span></span>
<span data-ttu-id="3c3aa-178"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="3c3aa-178"></span></span>

<span data-ttu-id="3c3aa-179">Após a instalação do Windows, o aplicativo de console do Skype sala sistemas v2 entrará em seu processo de instalação inicial, quando ele é iniciado próximo ou se a opção /reboot foi escolhida.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-179">After Windows is installed, the Skype Room Systems v2 console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="3c3aa-180">A tela Conta de Usuário é exibida.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-180">The User Account screen appears.</span></span> <span data-ttu-id="3c3aa-181">Insira o Skype endereço de entrada (no formato user@domain) da conta a ser usado com o console de sala.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-181">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="3c3aa-182">Digite a senha para a conta da sala e digite-a novamente para verificar.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-182">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="3c3aa-183">Em "Configurar domínio", defina o FQDN para o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-183">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="3c3aa-184">Se o Skype para o domínio SIP de negócios for diferente do domínio do Exchange do usuário, insira o domínio do Exchange neste campo.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-184">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="3c3aa-185">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-185">Click **Next**.</span></span>
    
5. <span data-ttu-id="3c3aa-186">Selecione os dispositivos indicados na tela recursos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-186">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="3c3aa-187">O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-187">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="3c3aa-188">Os dispositivos para selecionar são:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-188">The devices to select are:</span></span>
    
   - <span data-ttu-id="3c3aa-189">Microfone para conferência: o microfone padrão para a sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-189">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="3c3aa-190">Alto-falante para conferência: o alto-falante padrão para conferência </span><span class="sxs-lookup"><span data-stu-id="3c3aa-190">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="3c3aa-191">Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-191">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="3c3aa-p118">Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-p118">Each item has a drop-down menu of options to select from. You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="3c3aa-194">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-194">Click **Finish**.</span></span>
    
<span data-ttu-id="3c3aa-195">O aplicativo de console do Skype sala sistemas v2 deve iniciar imediatamente entrando no Skype para Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com Exchange usando as mesmas credenciais.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-195">The Skype Room Systems v2 console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="3c3aa-196">Para obter detalhes sobre como usar o aplicativo de console, consulte a [Ajuda de sistemas de sala Skype versão 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-196">For details on using the console app, refer to the [Skype Room Systems version 2 help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3c3aa-197">Sistemas de sala Skype v2 depende da presença de hardware do console certificados.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-197">Skype Room Systems v2 relies on the presence of certified console hardware.</span></span> <span data-ttu-id="3c3aa-198">Mesmo uma imagem criada corretamente que contém o aplicativo de console do Skype sala sistemas v2 não inicializa passado o procedimento de instalação inicial, a menos que o hardware do console for detectado.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-198">Even a correctly created image containing the Skype Room Systems v2 console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="3c3aa-199">Para obter soluções Surface Pro com base, o Surface Pro deve estar conectada a seu hardware de encaixe acompanha para passar essa verificação.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-199">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3c3aa-200">Alguns usuários de idioma diferente do inglês, talvez seja necessário um teclado físico conectado ao console durante a configuração inicial que símbolos não são suportados no teclado de toque.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-200">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="3c3aa-201">Instale um certificado de autoridade de certificação privado no console do</span><span class="sxs-lookup"><span data-stu-id="3c3aa-201">Install a private CA certificate on the console</span></span>
<span data-ttu-id="3c3aa-202"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="3c3aa-202"></span></span>

<span data-ttu-id="3c3aa-203">O console do Skype sala sistemas v2 deve confiar nos certificados usados pelo Skype para servidores de negócios e Exchange a que conecta-se.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-203">The Skype Room Systems v2 console needs to trust the certificates used by the Skype for Business and Exchange servers it connects to.</span></span> <span data-ttu-id="3c3aa-204">No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-204">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="3c3aa-205">No caso em que a autoridade de certificação é particular, por exemplo, uma implantação de local com o Active Directory e a autoridade de certificação do Windows, você pode adicionar o certificado ao console v2 Skype sala sistemas de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-205">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Skype Room Systems v2 console in a couple of ways:</span></span>
  
- <span data-ttu-id="3c3aa-206">Ingresse o console do Active Directory e que adicionará automaticamente os certificados necessários dado da autoridade de certificação é publicado no Active Directory (opção de implantação normal).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-206">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="3c3aa-207">Você pode instalar o certificado manualmente após o processo de geração de imagens.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-207">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="3c3aa-208">Antes de fazer isso, você deve concluir a [Configurar as iniciais do console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-208">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="3c3aa-209">Para instalar o certificado manualmente </span><span class="sxs-lookup"><span data-stu-id="3c3aa-209">To manually install the certificate</span></span>

1. <span data-ttu-id="3c3aa-210">Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="3c3aa-210">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="3c3aa-211">Coloque o console no modo de administração (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-211">Place the console in admin mode (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="3c3aa-212">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-212">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="3c3aa-213">Ingressar em um domínio do Active Directory (opcional)</span><span class="sxs-lookup"><span data-stu-id="3c3aa-213">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="3c3aa-214"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="3c3aa-214"></span></span>

<span data-ttu-id="3c3aa-215">Você pode ingressar consoles de v2 de sistemas de sala Skype para seu domínio.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-215">You can join Skype Room Systems v2 consoles to your domain.</span></span> <span data-ttu-id="3c3aa-216">Consoles de v2 Skype sala sistemas devem ser colocados em uma UO separada estações de trabalho do seu PC porque muitos políticas de estação de trabalho não são compatíveis com sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-216">Skype Room Systems v2 consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Skype Room Systems v2.</span></span> <span data-ttu-id="3c3aa-217">Um exemplo comum são as diretivas de aplicação da senha que impeça os sistemas de sala Skype v2 seja iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-217">A common example are password enforcement policies that will prevent Skype Room Systems v2 from starting up automatically.</span></span> <span data-ttu-id="3c3aa-218">Para obter informações sobre o gerenciamento das configurações do GPO, consulte [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-218">For information about the management of GPO settings, please refer to [Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a><span data-ttu-id="3c3aa-219">Para fazer o Skype Room Systems versão 2 ingressar em um domínio</span><span class="sxs-lookup"><span data-stu-id="3c3aa-219">To join Skype Room System v2 to a domain</span></span>

1. <span data-ttu-id="3c3aa-220">Sinal de login no console do que o administrador da conta (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="3c3aa-220">Sign into the console from the admin account (see [Admin mode and device management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="3c3aa-221">Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-221">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="3c3aa-222">Digite o seguinte comando no Powershell:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-222">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="3c3aa-223">Por exemplo, se o seu domínio totalmente qualificado for redmond.corp.microsoft.com e quiser que seus consoles de v2 Skype sala sistemas estejam em uma "sala Skype sistemas v2" UO que é um filho de uma unidade Organizacional "recursos", o comando será:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-223">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Skype Room Systems v2 consoles to be in a "Skype Room Systems v2" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="3c3aa-224">Se você gostaria de renomear o computador ao ingressarem-lo a um domínio, use o sinalizador - NewName seguido pelo nome do novo do computador.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-224">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="skype-room-systems-v2-deployment-checklist"></a><span data-ttu-id="3c3aa-225">Lista de verificação de implantação do Skype sala sistemas v2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-225">Skype Room Systems v2 deployment checklist</span></span>
<span data-ttu-id="3c3aa-226"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="3c3aa-226"></span></span>

<span data-ttu-id="3c3aa-227">Use a seguinte lista de verificação enquanto efetua uma verificação final se o console e todos os seus periféricos totalmente estão configurados:</span><span class="sxs-lookup"><span data-stu-id="3c3aa-227">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="3c3aa-228">**Configurações do aplicativo**</span><span class="sxs-lookup"><span data-stu-id="3c3aa-228">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3c3aa-229">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-229">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-230">O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console</span><span class="sxs-lookup"><span data-stu-id="3c3aa-230">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="3c3aa-231">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-231">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-232">O nome do computador Windows está definido corretamente (útil para administração remota)</span><span class="sxs-lookup"><span data-stu-id="3c3aa-232">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="3c3aa-233">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-233">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-234">A senha da conta do administrador foi definida e verificada</span><span class="sxs-lookup"><span data-stu-id="3c3aa-234">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="3c3aa-235">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-235">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-236">Todas as atualizações de firmware tiverem sido aplicadas.</span><span class="sxs-lookup"><span data-stu-id="3c3aa-236">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="3c3aa-237">**Periféricos de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="3c3aa-237">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3c3aa-238">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-238">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-239">A versão do firmware do periférico da câmera está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="3c3aa-239">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="3c3aa-240">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-240">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-241">Câmera funcional e forma ideal posicionada</span><span class="sxs-lookup"><span data-stu-id="3c3aa-241">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="3c3aa-242">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-242">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-243">Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="3c3aa-243">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="3c3aa-244">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-244">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-245">Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado</span><span class="sxs-lookup"><span data-stu-id="3c3aa-245">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="3c3aa-246">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-246">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-247">A versão do firmware do periférico de áudio está correta (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="3c3aa-247">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="3c3aa-248">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-248">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-249">Dispositivo de entrada de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="3c3aa-249">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="3c3aa-250">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-250">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-251">Dispositivo de saída de áudio funcional e posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="3c3aa-251">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="3c3aa-252">**Encaixe**</span><span class="sxs-lookup"><span data-stu-id="3c3aa-252">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3c3aa-253">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-253">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-254">Os cabos estão presos e não estão dobrados</span><span class="sxs-lookup"><span data-stu-id="3c3aa-254">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="3c3aa-255">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-255">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-256">Ingestão de áudio via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="3c3aa-256">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="3c3aa-257">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-257">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-258">Ingestão de vídeo via HDMI funcional</span><span class="sxs-lookup"><span data-stu-id="3c3aa-258">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="3c3aa-259">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-259">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-260">O encaixe pode girar livremente</span><span class="sxs-lookup"><span data-stu-id="3c3aa-260">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="3c3aa-261">☐</span><span class="sxs-lookup"><span data-stu-id="3c3aa-261">☐</span></span>  <br/> |<span data-ttu-id="3c3aa-262">O brilho da tela é aceitável para o ambiente</span><span class="sxs-lookup"><span data-stu-id="3c3aa-262">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3c3aa-263">Ver também</span><span class="sxs-lookup"><span data-stu-id="3c3aa-263">See also</span></span>
<span data-ttu-id="3c3aa-264"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="3c3aa-264"></span></span>

[<span data-ttu-id="3c3aa-265">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-265">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="3c3aa-266">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-266">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="3c3aa-267">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-267">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="3c3aa-268">Gerenciar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="3c3aa-268">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)