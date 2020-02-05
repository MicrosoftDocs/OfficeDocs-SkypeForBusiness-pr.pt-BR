---
title: Implantar o plug-in VDI do Lync com o Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Este tópico discute os procedimentos de implantação para usar o Skype for Business enquanto se conecta a uma área de trabalho virtual remota.
ms.openlocfilehash: f864136ab55f37a9bfaf54d6c31d74d31844da59
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768940"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="4c480-103">Implantar o plug-in VDI do Lync com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4c480-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="4c480-104">Este tópico discute os procedimentos de implantação para usar o Skype for Business enquanto se conecta a uma área de trabalho virtual remota.</span><span class="sxs-lookup"><span data-stu-id="4c480-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="4c480-105">As considerações de planejamento estão no [plano para o Skype for Business em ambientes VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span><span class="sxs-lookup"><span data-stu-id="4c480-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="4c480-106">Um ambiente VDI (Virtual Desktop Infrastructure) é usado em algumas organizações nas quais questões de segurança e conformidade são especialmente sensíveis.</span><span class="sxs-lookup"><span data-stu-id="4c480-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="4c480-107">Seus usuários trabalham em computadores Windows locais e utilizam clientes em uma área de trabalho virtual.</span><span class="sxs-lookup"><span data-stu-id="4c480-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="4c480-108">Usar o Skype for Business em uma conexão como essa requer software de plug-in VDI adicional.</span><span class="sxs-lookup"><span data-stu-id="4c480-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="4c480-109">Há duas soluções disponíveis para o componente plug-in VDI – uma oferecida pela Microsoft e uma oferecida pela Citrix.</span><span class="sxs-lookup"><span data-stu-id="4c480-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="4c480-110">A Microsoft recomenda o uso da nova solução de pacote de otimização HDX RealTime em novas implantações, mas continuará a oferecer suporte ao plug-in do VDI do Lync original para o restante do ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="4c480-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="4c480-111">Este tópico fornece detalhes sobre a implantação do plug-in VDI do Microsoft Lync, que só tem suporte no Windows 7 e Windows 8 ou no Windows Server 2008, e só tem suporte para os clientes do Lync 2013 ou do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4c480-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="4c480-112">Não há planos para atualizar este plugin, mas o [pacote de otimização do Citrix HDX Realtime](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) para o Skype for Business será atualizado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4c480-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="4c480-113">Preparar seu ambiente para o plug-in VDI do Lync</span><span class="sxs-lookup"><span data-stu-id="4c480-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="4c480-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="4c480-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="4c480-115">No Skype for Business Server, certifique-se de que o EnableMediaRedirection está definido como TRUE para todos os usuários de plug-in do Lync da VDI.</span><span class="sxs-lookup"><span data-stu-id="4c480-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="4c480-116">Para obter detalhes, consulte os tópicos da ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="4c480-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="4c480-117">No servidor do Data Center, instale o cliente Skype for Business em todas as áreas de trabalho virtuais.</span><span class="sxs-lookup"><span data-stu-id="4c480-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="4c480-118">Nos computadores locais, instale o plug-in VDI do Lync.</span><span class="sxs-lookup"><span data-stu-id="4c480-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="4c480-119">Os usuários agora devem conectar um dispositivo, como um fone de ouvido com microfone ou uma webcam, ao computador local.</span><span class="sxs-lookup"><span data-stu-id="4c480-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="4c480-120">Definir as configurações da Conexão de Área de Trabalho Remota</span><span class="sxs-lookup"><span data-stu-id="4c480-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="4c480-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="4c480-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="4c480-122">Para preparar a conexão de área de trabalho remota para o plug-in VDI do Lync, siga estas etapas no computador local:</span><span class="sxs-lookup"><span data-stu-id="4c480-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="4c480-123">Se o computador local estiver executando o Windows 8, pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="4c480-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="4c480-124">Se o computador local estiver executando o Windows 7 com SP1, instale a versão mais recente do Windows 8 do [cliente dos serviços de área de trabalho remota](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="4c480-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="4c480-125">Inicie o cliente de Serviços de Área de Trabalho Remota clicando em **Iniciar** e em **Conexão de Área de Trabalho Remota**.</span><span class="sxs-lookup"><span data-stu-id="4c480-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="4c480-126">Clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="4c480-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="4c480-127">Clique na guia **Recursos Locais**. Em **Áudio remoto**, clique em **Configurações** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c480-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="4c480-128">Em **Reprodução de áudio remoto**, selecione **Reproduzir neste computador**.</span><span class="sxs-lookup"><span data-stu-id="4c480-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="4c480-129">Em **Gravação de áudio remoto**, selecione **Não gravar**.</span><span class="sxs-lookup"><span data-stu-id="4c480-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="4c480-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c480-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="4c480-131">Clique na guia **Experiência**. Em **Desempenho**, desmarque a caixa de seleção **Armazenamento persistente de bitmaps em cache**.</span><span class="sxs-lookup"><span data-stu-id="4c480-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="4c480-132">Clique na guia **Geral**. Em **Computador**, digite o nome da área de trabalho virtual e clique em **Conectar**. </span><span class="sxs-lookup"><span data-stu-id="4c480-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="4c480-133">Entrar e usar o Skype for Business na área de trabalho virtual</span><span class="sxs-lookup"><span data-stu-id="4c480-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="4c480-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="4c480-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="4c480-135">Depois que o plug-in VDI do Lync estiver habilitado, o usuário seguirá estas etapas ao entrar no Skype for Business na área de trabalho virtual.</span><span class="sxs-lookup"><span data-stu-id="4c480-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="4c480-136">O usuário digita suas credenciais para o cliente Skype for Business em execução na área de trabalho virtual.</span><span class="sxs-lookup"><span data-stu-id="4c480-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="4c480-137">Depois que o Skype for Business detectar o plug-in VDI do Lync, o Skype for Business solicitará que o usuário digite novamente as credenciais.</span><span class="sxs-lookup"><span data-stu-id="4c480-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="4c480-138">Nessa caixa de diálogo, é recomendável que o usuário marque a caixa de seleção **Salvar minha senha** para que não precise inserir as credenciais na próxima entrada.</span><span class="sxs-lookup"><span data-stu-id="4c480-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="4c480-139">O Skype for Business começa a emparelhar com o plug-in VDI do Lync.</span><span class="sxs-lookup"><span data-stu-id="4c480-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="4c480-140">Enquanto isso acontece, o cliente exibe dois ícones na barra de status do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4c480-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="4c480-141">O ícone no canto inferior esquerdo indica que não há dispositivos de áudio disponíveis, e o ícone piscante no canto inferior direito indica que o emparelhamento com VDI está em andamento: a.</span><span class="sxs-lookup"><span data-stu-id="4c480-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="4c480-142">Após o emparelhamento com o VDI ter êxito, os ícones são alterados para indicar o dispositivo de áudio que será usado para chamadas e o sucesso de emparelhamento da VDI: b.</span><span class="sxs-lookup"><span data-stu-id="4c480-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="4c480-143">Agora o usuário pode ver sua presença em dispositivos compatíveis com o Skype for Business que estão conectados ao computador local e fazer e atender chamadas normalmente.</span><span class="sxs-lookup"><span data-stu-id="4c480-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="4c480-144">Solução de problemas do plug-in VDI do Lync</span><span class="sxs-lookup"><span data-stu-id="4c480-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="4c480-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="4c480-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="4c480-146">Consulte as seções a seguir se houver problemas após a instalação do plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="4c480-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="4c480-147">Problemas na instalação do plug-in VDI do Lync </span><span class="sxs-lookup"><span data-stu-id="4c480-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="4c480-148">Se houver problemas para instalar o plug-in VDI do Lync, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c480-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="4c480-149">Verifique se há espaço em disco suficiente na pasta que você especificou nas variáveis do sistema TEMP e TMP.</span><span class="sxs-lookup"><span data-stu-id="4c480-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="4c480-150">Verifique se a proteção contra gravação está desativada.</span><span class="sxs-lookup"><span data-stu-id="4c480-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="4c480-151">Consulte a documentação do fabricante do dispositivo para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="4c480-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="4c480-152">Solução de problemas de emparelhamento</span><span class="sxs-lookup"><span data-stu-id="4c480-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="4c480-153">Quando o emparelhamento do plug-in do Lync da VDI falha, o ícone de emparelhamento no canto inferior direito é exibido como um "X" vermelho, conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="4c480-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="4c480-154">Veja a seguir os possíveis motivos das falhas e as ações que você pode tomar para corrigir o problema. </span><span class="sxs-lookup"><span data-stu-id="4c480-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="4c480-155">**O usuário inseriu credenciais incorretas durante a entrada.**</span><span class="sxs-lookup"><span data-stu-id="4c480-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="4c480-156">O usuário deve desconectar-se do Skype for Business e entrar novamente com as credenciais corretas.</span><span class="sxs-lookup"><span data-stu-id="4c480-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="4c480-157">A caixa de diálogo de emparelhamento será exibida novamente e mostrará se o emparelhamento foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="4c480-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="4c480-158">**Outra instância do cliente de área de trabalho remota está sendo executada.**</span><span class="sxs-lookup"><span data-stu-id="4c480-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="4c480-159">Se eles estiverem usando a conexão de área de trabalho remota no Windows, os usuários devem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c480-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="4c480-160">Iniciar o Gerenciador de Tarefas: pressionar **Alt+Ctrl+Delete** e depois clicar em **Iniciar Gerenciador de Tarefas**.</span><span class="sxs-lookup"><span data-stu-id="4c480-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="4c480-161">Clicar na guia **Processos** e procurar todos os processos chamados **mstsc.exe** na lista.</span><span class="sxs-lookup"><span data-stu-id="4c480-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="4c480-162">Realçar cada processo **mstsc.exe** e clicar em **Finalizar Processo**. </span><span class="sxs-lookup"><span data-stu-id="4c480-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="4c480-163">Iniciar uma nova sessão de área de trabalho remota e tentar conectar-se novamente. </span><span class="sxs-lookup"><span data-stu-id="4c480-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="4c480-164">**Os arquivos necessários não foram instalados corretamente.**</span><span class="sxs-lookup"><span data-stu-id="4c480-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="4c480-165">Depois que o plug-in for instalado no computador local, verifique se estes arquivos estão presentes em C:\Arquivos de Programas\Microsoft Office\Office15 (ou na letra da unidade apropriada):</span><span class="sxs-lookup"><span data-stu-id="4c480-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="4c480-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="4c480-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="4c480-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="4c480-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="4c480-168">**O cliente Skype for Business está em execução no computador local.**</span><span class="sxs-lookup"><span data-stu-id="4c480-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="4c480-169">Para usar o plug-in VDI do Lync, um cliente Skype for Business não deve estar em execução no computador local, caso contrário, haverá falha no emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="4c480-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="4c480-170">Como prática recomendada, o usuário não deve instalar um cliente Skype for Business no computador local.</span><span class="sxs-lookup"><span data-stu-id="4c480-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4c480-171">Confira também</span><span class="sxs-lookup"><span data-stu-id="4c480-171">See also</span></span>
<span data-ttu-id="4c480-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="4c480-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="4c480-173">Plan for Skype for Business in VDI environments</span><span class="sxs-lookup"><span data-stu-id="4c480-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
