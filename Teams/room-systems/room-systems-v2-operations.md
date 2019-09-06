---
title: Manutenção e operações de salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: Leia este tópico para saber mais sobre o gerenciamento de salas do Microsoft Teams, a próxima geração de sistemas de sala do Skype.
ms.openlocfilehash: 14f4fb23868cc3e4247c700d15851511310db471
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775225"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="e1563-103">Manutenção e operações de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1563-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="e1563-104">Leia este tópico para saber mais sobre o gerenciamento de salas do Microsoft Teams, a próxima geração de sistemas de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="e1563-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="e1563-105">Salas do Microsoft Teams é a solução de conferência mais recente da Microsoft projetada para transformar sua sala de reunião em uma experiência avançada e colaborativa.</span><span class="sxs-lookup"><span data-stu-id="e1563-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="e1563-106">Os usuários gostarão da interface familiar do Microsoft Teams ou do Skype for Business, e os administradores de ti apreciarão um aplicativo de reunião do Skype com facilidade de implantação e gerenciamento do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e1563-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="e1563-107">As salas do Microsoft Teams foram projetadas para aproveitar o equipamento existente, como painéis LCD, para facilitar a instalação e trazer o Microsoft Teams ou o Skype for Business para a sua sala de reuniões.</span><span class="sxs-lookup"><span data-stu-id="e1563-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="e1563-108">Com configurações adicionais, o gerenciamento remoto é possível usando o Microsoft Azure monitor, conforme descrito em [planejar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-plan.md), [implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md), [gerenciar Salas do Microsoft Teams para dispositivos com o Azure monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="e1563-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="e1563-109">Você também pode [gerenciar as configurações do console de salas do Microsoft Teams remotamente com um arquivo de configuração XML](xml-config-file.md), que inclui a aplicação de um tema de exibição personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1563-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="e1563-110">Coletando logs em salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1563-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="e1563-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-111"></span></span>

<span data-ttu-id="e1563-112">Para coletar logs, você deve invocar o script de coleta de log que acompanha o aplicativo salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1563-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="e1563-113">No modo Admin, inicie um prompt de comandos com privilégios elevados e emita o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e1563-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="e1563-114">Os logs serão exibidos como um arquivo ZIP em c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="e1563-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="e1563-115">Configurações da tela frontal da sala</span><span class="sxs-lookup"><span data-stu-id="e1563-115">Front of Room Display Settings</span></span>
<span data-ttu-id="e1563-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-116"></span></span>

<span data-ttu-id="e1563-117">Configure a tela frontal da sala para o modo Estendido.</span><span class="sxs-lookup"><span data-stu-id="e1563-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="e1563-118">Isso garantirá que a interface do usuário do console não seja duplicada naquele vídeo quando você desligar o monitor.</span><span class="sxs-lookup"><span data-stu-id="e1563-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1563-p105">A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs.</span><span class="sxs-lookup"><span data-stu-id="e1563-p105">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="e1563-121">Redefinição de salas do Microsoft Teams (restauração de fábrica)</span><span class="sxs-lookup"><span data-stu-id="e1563-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="e1563-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-122"></span></span>

<span data-ttu-id="e1563-123">Se as salas do Microsoft Teams não estiverem funcionando bem, executar uma redefinição de fábrica pode ajudar.</span><span class="sxs-lookup"><span data-stu-id="e1563-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="e1563-124">Isso pode ser feito no aplicativo configurações na guia **recuperação** . abaixo **restaurar este PC**, selecione **introdução**e, em seguida, **remover tudo**.</span><span class="sxs-lookup"><span data-stu-id="e1563-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="e1563-125">Siga os prompts restantes para redefinir o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1563-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1563-126">Há um problema conhecido em que as salas do Microsoft Teams podem ficar inúteis se a opção **manter meus arquivos-remove meus arquivos-remove aplicativos e configurações, mas mantém a opção arquivos pessoais** selecionada durante o processo de redefinição do Windows.</span><span class="sxs-lookup"><span data-stu-id="e1563-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="e1563-127">Não _Use essa_ opção.</span><span class="sxs-lookup"><span data-stu-id="e1563-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="e1563-128">Opções remotas com suporte</span><span class="sxs-lookup"><span data-stu-id="e1563-128">Supported Remote Options</span></span>
<span data-ttu-id="e1563-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-129"></span></span>

<span data-ttu-id="e1563-130">A tabela a seguir resume as operações remotas possíveis e os métodos que você pode usar para executá-las.</span><span class="sxs-lookup"><span data-stu-id="e1563-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="e1563-131">\*\*Grupo de trabalho \*\*</span><span class="sxs-lookup"><span data-stu-id="e1563-131">**Workgroup**</span></span>|<span data-ttu-id="e1563-132">**Não ingresso em domínio**</span><span class="sxs-lookup"><span data-stu-id="e1563-132">**Not domain joined**</span></span>|<span data-ttu-id="e1563-133">**Ingresso em domínio**</span><span class="sxs-lookup"><span data-stu-id="e1563-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1563-134">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="e1563-134">Restart</span></span>  <br/> |<span data-ttu-id="e1563-135">Área de trabalho remota</span><span class="sxs-lookup"><span data-stu-id="e1563-135">Remote desktop</span></span>  <br/> <span data-ttu-id="e1563-136">PowerShell Remoto</span><span class="sxs-lookup"><span data-stu-id="e1563-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="e1563-137">Área de trabalho remota (requer configuração adicional)</span><span class="sxs-lookup"><span data-stu-id="e1563-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="e1563-138">PowerShell remoto (requer configuração adicional)</span><span class="sxs-lookup"><span data-stu-id="e1563-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="e1563-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="e1563-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="e1563-140">Atualização do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="e1563-140">Update OS</span></span>  <br/> |<span data-ttu-id="e1563-141">Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:</span><span class="sxs-lookup"><span data-stu-id="e1563-141">Windows Update</span></span>  <br/> |<span data-ttu-id="e1563-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="e1563-142">Windows Update</span></span>  <br/> <span data-ttu-id="e1563-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="e1563-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="e1563-144">Atualização de aplicativos</span><span class="sxs-lookup"><span data-stu-id="e1563-144">App update</span></span>  <br/> |<span data-ttu-id="e1563-145">Windows Store</span><span class="sxs-lookup"><span data-stu-id="e1563-145">Windows Store</span></span>  <br/> |<span data-ttu-id="e1563-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="e1563-146">Windows Store</span></span>  <br/> <span data-ttu-id="e1563-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="e1563-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="e1563-148">Configuração de contas do Skype</span><span class="sxs-lookup"><span data-stu-id="e1563-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="e1563-149">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="e1563-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="e1563-150">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="e1563-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="e1563-151">Acesso aos logs</span><span class="sxs-lookup"><span data-stu-id="e1563-151">Access logs</span></span>  <br/> |<span data-ttu-id="e1563-152">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="e1563-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="e1563-153">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="e1563-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="e1563-154">Configurando a política de grupo para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1563-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="e1563-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-155"></span></span>

<span data-ttu-id="e1563-156">Esta seção abrange as configurações do sistema das quais as salas do Microsoft Teams dependem para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="e1563-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="e1563-157">Ao ingressar em salas do Microsoft Teams em um domínio, verifique se a política de grupo não substitui as configurações na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e1563-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="e1563-158">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="e1563-158">**Setting**</span></span>|<span data-ttu-id="e1563-159">**Permite**</span><span class="sxs-lookup"><span data-stu-id="e1563-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1563-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="e1563-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="e1563-161">Permite que salas do Microsoft Teams sejam inicializadas</span><span class="sxs-lookup"><span data-stu-id="e1563-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="e1563-162">Gerenciamento de energia\> -em AC, desligar a tela após 10 minutos</span><span class="sxs-lookup"><span data-stu-id="e1563-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="e1563-163">Gerenciamento de energia\> -em AC, nunca coloque o sistema em suspensão</span><span class="sxs-lookup"><span data-stu-id="e1563-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="e1563-164">Permite que as salas do Microsoft Teams desativem exibições anexadas e ativadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="e1563-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="e1563-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="e1563-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="e1563-166">Ou uma maneira equivalente de desabilitar a expiração de senha na conta local.</span><span class="sxs-lookup"><span data-stu-id="e1563-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="e1563-167">Deixar de fazer isso fará com que a conta do Skype falhe ao fazer logon com uma senha expirada.</span><span class="sxs-lookup"><span data-stu-id="e1563-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="e1563-168">Observe que isso afeta todas as contas locais do computador e, portanto, não definir isso também fará com que a conta administrativa na caixa acabe de expirar também.</span><span class="sxs-lookup"><span data-stu-id="e1563-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="e1563-169">Permite que a conta do Skype esteja sempre conectada</span><span class="sxs-lookup"><span data-stu-id="e1563-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="e1563-170">A transferência de arquivos usando políticas de grupo é discutida em [configurar um item de arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e1563-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="e1563-171">Quando o dispositivo de salas do Microsoft Teams é compatível com a próxima versão do Windows 10 OS, o dispositivo é atualizado automaticamente para a próxima versão por meio do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e1563-171">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="e1563-172">O dispositivo de salas do Microsoft Teams não deve ser atualizado manualmente para o próximo lançamento do Windows 10 ou por meio da habilitação das políticas de grupo do Windows Update for Business (WUFB) "selecionar o nível de preparação do Windows para as atualizações que você deseja receber" e "selecionar quando versões prévias e As atualizações de recursos são recebidas "através de um GPO.</span><span class="sxs-lookup"><span data-stu-id="e1563-172">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="e1563-173">Um dispositivo com essas políticas de grupo habilitada é conhecido por ter problemas com o aplicativo de salas do Microsoft Teams para a atualização do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e1563-173">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="e1563-174">Gerenciamento remoto usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1563-174">Remote Management using PowerShell</span></span>
<span data-ttu-id="e1563-175"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-175"></span></span>

<span data-ttu-id="e1563-176">Você pode executar as seguintes operações de gerenciamento remotamente usando o PowerShell (consulte a tabela abaixo para obter exemplos de script):</span><span class="sxs-lookup"><span data-stu-id="e1563-176">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="e1563-177">Obter dispositivos conectados</span><span class="sxs-lookup"><span data-stu-id="e1563-177">Get attached devices</span></span>
    
- <span data-ttu-id="e1563-178">Obter o status do aplicativo</span><span class="sxs-lookup"><span data-stu-id="e1563-178">Get app status</span></span>
    
- <span data-ttu-id="e1563-179">Obter informações do sistema</span><span class="sxs-lookup"><span data-stu-id="e1563-179">Get system info</span></span>
    
- <span data-ttu-id="e1563-180">Reiniciar o sistema</span><span class="sxs-lookup"><span data-stu-id="e1563-180">Reboot system</span></span>
    
- <span data-ttu-id="e1563-181">Recuperar logs</span><span class="sxs-lookup"><span data-stu-id="e1563-181">Retrieve logs</span></span>
    
- <span data-ttu-id="e1563-182">Transferir arquivos (requer salas do Microsoft Teams associadas a um domínio)</span><span class="sxs-lookup"><span data-stu-id="e1563-182">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="e1563-183">Essa funcionalidade está desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="e1563-183">This functionality is off by default.</span></span> <span data-ttu-id="e1563-184">Você precisa habilitar o PowerShell remoto para seu ambiente no sistema de salas do Microsoft Teams para executar as operações abaixo.</span><span class="sxs-lookup"><span data-stu-id="e1563-184">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="e1563-185">Consulte a documentação sobre **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** para obter informações sobre como habilitar o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="e1563-185">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="e1563-186">Por exemplo, você pode habilitar o PowerShell Remoto da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e1563-186">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="e1563-187">Entre como administrador em um dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1563-187">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="e1563-188">Abra um prompt de comando elevado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1563-188">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="e1563-189">Insira o seguinte comando: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="e1563-189">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="e1563-190">Para executar uma operação de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="e1563-190">To perform a management operation:</span></span>
  
1. <span data-ttu-id="e1563-191">Entre em um computador com credenciais de conta que têm permissão para executar comandos do PowerShell em um dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1563-191">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="e1563-192">Abra um prompt de comando normal do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="e1563-192">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="e1563-193">Copie o texto do comando da tabela abaixo e cole-o no prompt.</span><span class="sxs-lookup"><span data-stu-id="e1563-193">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="e1563-194">Substituir `<Device fqdn>` os campos pelos valores de FQDN apropriados para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="e1563-194">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="e1563-195">Substituir \* \<caminho\> \* com o nome do arquivo e o caminho local do arquivo de configuração Master SkypeSettings. XML (ou imagem do tema).</span><span class="sxs-lookup"><span data-stu-id="e1563-195">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="e1563-196">Para obter dispositivos conectados</span><span class="sxs-lookup"><span data-stu-id="e1563-196">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="e1563-197">Obter o status de aplicativos</span><span class="sxs-lookup"><span data-stu-id="e1563-197">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="e1563-198">Obter informações do sistema</span><span class="sxs-lookup"><span data-stu-id="e1563-198">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="e1563-199">Reiniciar o sistema</span><span class="sxs-lookup"><span data-stu-id="e1563-199">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="e1563-200">Recuperar logs</span><span class="sxs-lookup"><span data-stu-id="e1563-200">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="e1563-201">Enviar um arquivo de configuração XML (ou um elemento gráfico) do tema</span><span class="sxs-lookup"><span data-stu-id="e1563-201">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="e1563-202">Atualizações de software</span><span class="sxs-lookup"><span data-stu-id="e1563-202">Software updates</span></span>
<span data-ttu-id="e1563-203"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-203"></span></span>

<span data-ttu-id="e1563-204">Por padrão, as salas do Microsoft Teams tentam se conectar à Windows Store para obter a versão mais recente do software de salas do Microsoft Teams, para que o dispositivo exija acesso regular à Internet.</span><span class="sxs-lookup"><span data-stu-id="e1563-204">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="e1563-205">Antes de entrar em contato com a Microsoft com problemas de suporte, verifique se o dispositivo de salas do Microsoft Teams está carregado com a versão mais recente do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e1563-205">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="e1563-206">Por padrão, as salas do Microsoft Teams se conectam ao Windows Update para recuperar atualizações do sistema operacional e do firmware do dispositivo periférico USB e as instalam fora do horário comercial configurado.</span><span class="sxs-lookup"><span data-stu-id="e1563-206">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="e1563-207">Para configurar o horário comercial, entre na conta de administrador e execute o aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="e1563-207">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="e1563-208">Se você quiser gerenciar as atualizações manualmente e não conseguir seguir o procedimento normal para a [Microsoft Store para empresas](https://businessstore.microsoft.com/store) [distribuir aplicativos offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), você pode adquirir o arquivo Appx apropriado e as dependências do [Kit de implantação](https://go.microsoft.com/fwlink/?linkid=851168) (do as instruções para [configurar um console de salas do Microsoft Teams](console.md)) que podem ser usadas com o SCCM.</span><span class="sxs-lookup"><span data-stu-id="e1563-208">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="e1563-209">A versão do kit de implantação está atrasada atrás do lançamento da loja, portanto, talvez nem sempre corresponda à versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="e1563-209">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="e1563-210">Para atualizar usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1563-210">To update using Powershell</span></span>

1. <span data-ttu-id="e1563-211">Extraia o pacote do [MSI](https://go.microsoft.com/fwlink/?linkid=851168) de instalação para um compartilhamento que o dispositivo possa acessar.</span><span class="sxs-lookup"><span data-stu-id="e1563-211">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="e1563-212">Execute o script a seguir direcionando os dispositivos de sala do \<Microsoft\> Teams, alterando o compartilhamento para o compartilhamento de dispositivo conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="e1563-212">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="e1563-213">Modo de administração e gerenciamento de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e1563-213">Admin mode and device management</span></span>
<span data-ttu-id="e1563-214"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-214"></span></span>

<span data-ttu-id="e1563-215">Algumas funções de gerenciamento, como instalar manualmente um certificado de autoridade de certificação privado, exigem colocar o dispositivo Surface pro no modo de administração.</span><span class="sxs-lookup"><span data-stu-id="e1563-215">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="e1563-216">Alternar para o modo de administrador e voltar quando o aplicativo salas do Microsoft Teams estiver em execução</span><span class="sxs-lookup"><span data-stu-id="e1563-216">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="e1563-217">Desligue as chamadas em andamento e retorne à tela inicial.</span><span class="sxs-lookup"><span data-stu-id="e1563-217">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="e1563-218">Selecione o ícone de engrenagem e exibir o menu (opções são **configurações**, **acessibilidade**e **reinicialização do dispositivo** ).</span><span class="sxs-lookup"><span data-stu-id="e1563-218">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="e1563-219">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="e1563-219">Select **Settings**.</span></span>
    
4. <span data-ttu-id="e1563-220">Digite a senha do administrador.</span><span class="sxs-lookup"><span data-stu-id="e1563-220">Enter the Administrator Password.</span></span> <span data-ttu-id="e1563-221">A tela Configuração será exibida.</span><span class="sxs-lookup"><span data-stu-id="e1563-221">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1563-222">Se o dispositivo não for associado ao domínio, a conta administrativa local (nome de usuário "administrador") será usada por padrão.</span><span class="sxs-lookup"><span data-stu-id="e1563-222">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="e1563-223">A senha padrão para essa conta será 'sfb', mas é recomendável que sua organização mude essa senha o quanto antes por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="e1563-223">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="e1563-224">Se o computador for associado a um domínio, você poderá entrar com uma conta de domínio apropriadamente privilegiada.</span><span class="sxs-lookup"><span data-stu-id="e1563-224">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="e1563-225">Selecione **configurações do Windows** na coluna à esquerda.</span><span class="sxs-lookup"><span data-stu-id="e1563-225">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="e1563-226">Escolha **Vá para Entrada como Admin**.</span><span class="sxs-lookup"><span data-stu-id="e1563-226">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="e1563-227">Digite a senha do administrador.</span><span class="sxs-lookup"><span data-stu-id="e1563-227">Enter the Administrator Password.</span></span> <span data-ttu-id="e1563-228">Isso faz com que o aplicativo seja desativado e leva você até a tela de logon do Windows.</span><span class="sxs-lookup"><span data-stu-id="e1563-228">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="e1563-229">Faça logon no desktop usando as credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="e1563-229">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="e1563-230">Você terá os privilégios necessários para gerenciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1563-230">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="e1563-231">Execute as tarefas administrativas necessárias.</span><span class="sxs-lookup"><span data-stu-id="e1563-231">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="e1563-232">Saia da conta de Administrador.</span><span class="sxs-lookup"><span data-stu-id="e1563-232">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="e1563-233">Retorne a salas do Microsoft Teams selecionando o ícone de conta de usuário no lado esquerdo da tela e, em seguida, selecionando **Skype**.</span><span class="sxs-lookup"><span data-stu-id="e1563-233">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="e1563-234">Se o usuário do **Skype** não estiver listado, talvez seja necessário selecionar **outro usuário** , digitar **.\skype** como o nome de usuário e entrar.</span><span class="sxs-lookup"><span data-stu-id="e1563-234">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="e1563-235">O console agora está novamente em seu modo de operação normal. O procedimento a seguir exige que você anexe um teclado ao dispositivo, caso ele ainda não esteja conectado.</span><span class="sxs-lookup"><span data-stu-id="e1563-235">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="e1563-236">Alternar para o modo de administrador e voltar quando o aplicativo salas do Microsoft Teams falha</span><span class="sxs-lookup"><span data-stu-id="e1563-236">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="e1563-237">Pressione a tecla do Windows cinco vezes em uma sucessão rápida.</span><span class="sxs-lookup"><span data-stu-id="e1563-237">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="e1563-238">Isso levará você para a tela de logon do Windows.</span><span class="sxs-lookup"><span data-stu-id="e1563-238">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="e1563-239">Faça logon no desktop usando as credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="e1563-239">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1563-240">Esse método não registra o usuário do Skype ou encerra o aplicativo normalmente, mas você o usaria se o aplicativo não estivesse respondendo e o outro método não estivesse disponível.</span><span class="sxs-lookup"><span data-stu-id="e1563-240">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="e1563-241">Execute as tarefas administrativas necessárias.</span><span class="sxs-lookup"><span data-stu-id="e1563-241">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="e1563-242">Reinicie o computador quando tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="e1563-242">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="e1563-243">O console é reiniciado em seu modo de operação normal, executando o aplicativo salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1563-243">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="e1563-244">Você pode remover o teclado, se ele estiver associado, para permitir que você execute este procedimento.</span><span class="sxs-lookup"><span data-stu-id="e1563-244">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="e1563-245">Dicas para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="e1563-245">Troubleshooting tips</span></span>
   <span data-ttu-id="e1563-246"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="e1563-246"></span></span>

- <span data-ttu-id="e1563-247">Os convites de reunião podem não ser exibidos quando enviados entre os limites do domínio (por exemplo, entre duas empresas).</span><span class="sxs-lookup"><span data-stu-id="e1563-247">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="e1563-248">Nesses casos, os administradores de ti devem decidir se desejam permitir que usuários externos agendem uma reunião.</span><span class="sxs-lookup"><span data-stu-id="e1563-248">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="e1563-249">As salas do Microsoft Teams não dão suporte a redirecionamentos de descoberta automática do Exchange via Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="e1563-249">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="e1563-250">Em geral, é uma boa prática para os administradores de ti desabilitarem pontos de extremidade de áudio que eles não pretendam usar.</span><span class="sxs-lookup"><span data-stu-id="e1563-250">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="e1563-251">Caso seja exibida uma imagem espelhada na visualização da sala, o administrador de TI pode corrigir isso desligando e ligando a câmera ou invertendo a orientação da imagem com o controle remoto da câmera.</span><span class="sxs-lookup"><span data-stu-id="e1563-251">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="e1563-252">Sabe-se que pode ocorrer a perda do acesso à tela touch do console.</span><span class="sxs-lookup"><span data-stu-id="e1563-252">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="e1563-253">Nesses casos, o problema também é resolvido ao reiniciar o sistema de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1563-253">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="e1563-254">Sabe-se que pode ocorrer a perda do áudio local ao conectar um computador ao console via entrada com fio.</span><span class="sxs-lookup"><span data-stu-id="e1563-254">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="e1563-255">Nesses casos, reiniciar o computador pode resolver o problema de reprodução do áudio local.</span><span class="sxs-lookup"><span data-stu-id="e1563-255">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
