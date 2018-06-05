---
title: Implantar o plug-in VDI do Lync com o Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Este tópico aborda os procedimentos de implantação para uso do Skype for Business durante a conexão a uma área de trabalho remota virtual.
ms.openlocfilehash: 47491b4409f21386cf28f811b6c2c3cbffe1e69b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501668"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a><span data-ttu-id="3cf10-103">Implantar o plug-in VDI do Lync com o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3cf10-103">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3cf10-104">Este tópico aborda os procedimentos de implantação para uso do Skype for Business durante a conexão a uma área de trabalho remota virtual.</span><span class="sxs-lookup"><span data-stu-id="3cf10-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="3cf10-105">Um ambiente VDI (Virtual Desktop Infrastructure) é usado em algumas organizações nas quais questões de segurança e conformidade são especialmente sensíveis.</span><span class="sxs-lookup"><span data-stu-id="3cf10-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="3cf10-106">Seus usuários trabalham em computadores Windows locais e utilizam clientes em uma área de trabalho virtual.</span><span class="sxs-lookup"><span data-stu-id="3cf10-106">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="3cf10-107">Usando Skype para a empresa em uma conexão como esta requer o software de plug-in de VDI adicional.</span><span class="sxs-lookup"><span data-stu-id="3cf10-107">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="3cf10-108">Existem duas soluções disponíveis para o componente de plug-in de VDI - uma oferecida pela Microsoft e outro oferecidos pelo Citrix.</span><span class="sxs-lookup"><span data-stu-id="3cf10-108">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="3cf10-109">A Microsoft recomenda usar a nova solução de pacote de otimização do HDX em tempo real em novas implantações, mas continuará a dar suporte a plug-in VDI do Lync original para o restante do seu ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3cf10-109">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="3cf10-110">Este tópico fornece detalhes sobre como implantar o Microsoft Lync VDI plug-in, que só tem suporte no Windows 7 e Windows 8 ou Windows Server 2008 e suporta apenas o Lync 2013 ou Skype para clientes corporativos 2015.</span><span class="sxs-lookup"><span data-stu-id="3cf10-110">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="3cf10-111">Não existem planos para atualizar este plug-in, mas o [Pacote de otimização do Citrix HDX em tempo real](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) para Skype para negócios serão atualizados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3cf10-111">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="3cf10-112">Preparar seu ambiente para o plug-in VDI do Lync</span><span class="sxs-lookup"><span data-stu-id="3cf10-112">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="3cf10-113"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-113"></span></span>

1. <span data-ttu-id="3cf10-114">No Skype para Business Server 2015, certifique-se de que o EnableMediaRedirection está definido como TRUE para todos os usuários de plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="3cf10-114">In Skype for Business Server 2015, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="3cf10-115">Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e o cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="3cf10-115">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="3cf10-116">No servidor do Centro de dados, instale o Skype para negócios 2015 cliente em todas as áreas de trabalho virtuais.</span><span class="sxs-lookup"><span data-stu-id="3cf10-116">On the data center server, install the Skype for Business 2015 client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="3cf10-117">Nos computadores locais, instale o plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="3cf10-117">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="3cf10-118">Os usuários agora devem conectar um dispositivo, como um fone de ouvido com microfone ou uma webcam, ao computador local.</span><span class="sxs-lookup"><span data-stu-id="3cf10-118">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="3cf10-119">Definir as configurações da Conexão de Área de Trabalho Remota</span><span class="sxs-lookup"><span data-stu-id="3cf10-119">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="3cf10-120"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-120"></span></span>

<span data-ttu-id="3cf10-121">Para preparar a Conexão de área de trabalho remota para o Lync VDI plug-in, siga estas etapas no computador local:</span><span class="sxs-lookup"><span data-stu-id="3cf10-121">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="3cf10-122">Se o computador local estiver executando o Windows 8, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="3cf10-122">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="3cf10-123">Se o computador local executando o Windows 7 com SP1, instale a versão mais recente do Windows 8 do [cliente de serviços de área de trabalho remota](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="3cf10-123">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="3cf10-124">Inicie o cliente de Serviços de Área de Trabalho Remota clicando em **Iniciar** e em **Conexão de Área de Trabalho Remota**.</span><span class="sxs-lookup"><span data-stu-id="3cf10-124">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="3cf10-125">Clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="3cf10-125">Click **Options**.</span></span>
    
4. <span data-ttu-id="3cf10-126">Clique na guia **Recursos Locais**. Em **Áudio remoto**, clique em **Configurações** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3cf10-126">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
  - <span data-ttu-id="3cf10-127">Em **Reprodução de áudio remoto**, selecione **Reproduzir neste computador**.</span><span class="sxs-lookup"><span data-stu-id="3cf10-127">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
  - <span data-ttu-id="3cf10-128">Em **Gravação de áudio remoto**, selecione **Não gravar**.</span><span class="sxs-lookup"><span data-stu-id="3cf10-128">Under **Remote audio recording**, select **Do not record**.</span></span>
    
  - <span data-ttu-id="3cf10-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cf10-129">Click **OK**.</span></span>
    
5. <span data-ttu-id="3cf10-130">Clique na guia **Experiência**. Em **Desempenho**, desmarque a caixa de seleção **Armazenamento persistente de bitmaps em cache**.</span><span class="sxs-lookup"><span data-stu-id="3cf10-130">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="3cf10-131">Clique na guia **Geral**. Em **Computador**, digite o nome da área de trabalho virtual e clique em **Conectar**. </span><span class="sxs-lookup"><span data-stu-id="3cf10-131">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="3cf10-132">Entrar e usar o Skype for Business na área de trabalho virtual</span><span class="sxs-lookup"><span data-stu-id="3cf10-132">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="3cf10-133"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-133"></span></span>

<span data-ttu-id="3cf10-134">Depois que o Lync VDI plug-in estiver habilitado, o usuário segue estas etapas ao entrar no Skype para negócios 2015 na área de trabalho virtual.</span><span class="sxs-lookup"><span data-stu-id="3cf10-134">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business 2015 on the virtual desktop.</span></span>
  
1. <span data-ttu-id="3cf10-135">O usuário digita suas credenciais para o Skype para cliente 2015 corporativos em execução na área de trabalho virtual.</span><span class="sxs-lookup"><span data-stu-id="3cf10-135">The user types his or her credentials in to the Skype for Business 2015 client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="3cf10-136">Depois Skype para negócios 2015 detecta o plug-in Lync VDI, Skype para negócios 2015 solicita ao usuário inserir novamente as credenciais.</span><span class="sxs-lookup"><span data-stu-id="3cf10-136">After Skype for Business 2015 detects the Lync VDI plug-in, Skype for Business 2015 prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="3cf10-137">Nessa caixa de diálogo, é recomendável que o usuário marque a caixa de seleção **Salvar minha senha** para que não precise inserir as credenciais na próxima entrada.</span><span class="sxs-lookup"><span data-stu-id="3cf10-137">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="3cf10-138">Skype para negócios 2015 começa emparelhamento com o Lync VDI plug-in.</span><span class="sxs-lookup"><span data-stu-id="3cf10-138">Skype for Business 2015 begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="3cf10-139">Enquanto isso acontece, o cliente exibe dois ícones do Skype para a barra de status de negócios 2015.</span><span class="sxs-lookup"><span data-stu-id="3cf10-139">While that happens, the client displays two icons in the Skype for Business 2015 status bar.</span></span> <span data-ttu-id="3cf10-140">O ícone no canto inferior esquerdo indica que nenhum dispositivo de áudio está disponível, e o ícone piscante no canto inferior direito indica que o emparelhamento de VDI está em andamento:</span><span class="sxs-lookup"><span data-stu-id="3cf10-140">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress:</span></span>
    4. <span data-ttu-id="3cf10-141">Após o emparelhamento bem-sucedido de VDI, os ícones mudarão para indicar o dispositivo de áudio que será usado para chamadas e o êxito do emparelhamento de VDI:</span><span class="sxs-lookup"><span data-stu-id="3cf10-141">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    5. <span data-ttu-id="3cf10-142">O usuário agora pode ver sua presença no Skype para dispositivos compatíveis de negócios 2015 que estão conectados ao computador local e fazer e atender chamadas como de costume.</span><span class="sxs-lookup"><span data-stu-id="3cf10-142">The user can now see his or her presence on Skype for Business 2015 compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="3cf10-143">Solução de problemas do plug-in VDI do Lync</span><span class="sxs-lookup"><span data-stu-id="3cf10-143">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="3cf10-144"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-144"></span></span>

<span data-ttu-id="3cf10-145">Consulte as seções a seguir se houver problemas após a instalação do plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="3cf10-145">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="3cf10-146">Problemas na instalação do plug-in VDI do Lync </span><span class="sxs-lookup"><span data-stu-id="3cf10-146">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="3cf10-147">Se houver problemas com a instalação do plug-in Lync VDI, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3cf10-147">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="3cf10-148">Verifique se há espaço em disco suficiente na pasta que você especificou nas variáveis do sistema TEMP e TMP.</span><span class="sxs-lookup"><span data-stu-id="3cf10-148">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="3cf10-149">Verifique se a proteção contra gravação está desativada.</span><span class="sxs-lookup"><span data-stu-id="3cf10-149">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="3cf10-150">Consulte a documentação do fabricante do dispositivo para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="3cf10-150">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="3cf10-151">Solução de problemas de emparelhamento</span><span class="sxs-lookup"><span data-stu-id="3cf10-151">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="3cf10-152">Quando o pareamento plug-in Lync VDI falhar, o ícone de pareamento no inferior direito é exibido como um "X" vermelho como mostrado:</span><span class="sxs-lookup"><span data-stu-id="3cf10-152">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="3cf10-153">Veja a seguir os possíveis motivos das falhas e as ações que você pode tomar para corrigir o problema. </span><span class="sxs-lookup"><span data-stu-id="3cf10-153">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="3cf10-154">**O usuário inseriu credenciais incorretas durante a entrada.**</span><span class="sxs-lookup"><span data-stu-id="3cf10-154">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="3cf10-155">O usuário deve sair do Skype para negócios e entrar novamente com as credenciais corretas.</span><span class="sxs-lookup"><span data-stu-id="3cf10-155">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="3cf10-156">A caixa de diálogo de emparelhamento será exibida novamente e mostrará se o emparelhamento foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="3cf10-156">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="3cf10-157">**Outra instância do cliente de área de trabalho remota está sendo executada.**</span><span class="sxs-lookup"><span data-stu-id="3cf10-157">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="3cf10-158">Caso estejam usando Conexão de área de trabalho remota no Windows, os usuários devem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3cf10-158">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="3cf10-159">Iniciar o Gerenciador de Tarefas: pressionar **Alt+Ctrl+Delete** e depois clicar em **Iniciar Gerenciador de Tarefas**.</span><span class="sxs-lookup"><span data-stu-id="3cf10-159">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="3cf10-160">Clicar na guia **Processos** e procurar todos os processos chamados **mstsc.exe** na lista.</span><span class="sxs-lookup"><span data-stu-id="3cf10-160">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="3cf10-161">Realçar cada processo **mstsc.exe** e clicar em **Finalizar Processo**. </span><span class="sxs-lookup"><span data-stu-id="3cf10-161">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="3cf10-162">Iniciar uma nova sessão de área de trabalho remota e tentar conectar-se novamente. </span><span class="sxs-lookup"><span data-stu-id="3cf10-162">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="3cf10-163">**Os arquivos necessários não foram instalados corretamente.**</span><span class="sxs-lookup"><span data-stu-id="3cf10-163">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="3cf10-164">Depois que o plug-in for instalado no computador local, verifique se estes arquivos estão presentes em C:\Arquivos de Programas\Microsoft Office\Office15 (ou na letra da unidade apropriada):</span><span class="sxs-lookup"><span data-stu-id="3cf10-164">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="3cf10-165">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="3cf10-165">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="3cf10-166">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="3cf10-166">UcVdi.dll</span></span>
    
- <span data-ttu-id="3cf10-167">**O Skype para negócios 2015 cliente está sendo executado no computador local.**</span><span class="sxs-lookup"><span data-stu-id="3cf10-167">**The Skype for Business 2015 client is running on the local computer.**</span></span>
    
    <span data-ttu-id="3cf10-168">Para usar o Lync VDI plug-in, que um Skype para negócios 2015 cliente não deve estar executando no computador local, caso contrário, emparelhamento irá falhar.</span><span class="sxs-lookup"><span data-stu-id="3cf10-168">To use the Lync VDI plug-in, a Skype for Business 2015 client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="3cf10-169">Como prática recomendada, o usuário não deve instalar um Skype para negócios 2015 cliente no computador local.</span><span class="sxs-lookup"><span data-stu-id="3cf10-169">As a best practice, the user should not install a Skype for Business 2015 client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3cf10-170">Ver também</span><span class="sxs-lookup"><span data-stu-id="3cf10-170">See also</span></span>
<span data-ttu-id="3cf10-171"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="3cf10-171"></span></span>

[<span data-ttu-id="3cf10-172">Planejar Skype para negócios em ambientes de VDI</span><span class="sxs-lookup"><span data-stu-id="3cf10-172">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)