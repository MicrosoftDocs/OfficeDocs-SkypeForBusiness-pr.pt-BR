---
title: Operações e manutenção de salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Leia este tópico para saber mais sobre o gerenciamento de salas de equipes da Microsoft, a próxima geração de sistemas de sala Skype.
ms.openlocfilehash: 907abcbe07e52369aefa5065a359f0a3769b20c5
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013040"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="4ea07-103">Operações e manutenção de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ea07-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="4ea07-104">Leia este tópico para saber mais sobre o gerenciamento de salas de equipes da Microsoft, a próxima geração de sistemas de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="4ea07-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="4ea07-105">Salas de equipes da Microsoft é a solução de conferência mais recente da Microsoft projetada para transformar a sala de reunião em um Skype rica e colaboração para a experiência de negócios.</span><span class="sxs-lookup"><span data-stu-id="4ea07-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="4ea07-106">Os usuários apreciarão a interface familiar do Skype for Business, e os administradores de TI ficarão satisfeitos com a implantação e o gerenciamento fáceis do aplicativo Reunião do Skype para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4ea07-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="4ea07-107">Salas de equipes da Microsoft foi projetada para aproveitar o equipamento existente como painéis LCD para facilitar da instalação para trazer Skype for Business para sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="4ea07-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="4ea07-108">Com uma configuração adicional, gerenciamento remoto é possível usando o Microsoft Azure Monitor conforme descrito em [gerenciamento de planejar salas de equipes da Microsoft com o Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [gerenciamento de implantar o Microsoft equipes salas com Monitor do Azure](../../deploy/deploy-clients/azure-monitor.md), [Gerenciar Dispositivos de salas de equipes da Microsoft com o Azure Monitor](azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="4ea07-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor.md).</span></span> <span data-ttu-id="4ea07-109">Você também pode [Gerenciar salas de equipes da Microsoft configurações remotamente com um arquivo de configuração XML do console](xml-config-file.md), que inclui a aplicação de um tema de exibição personalizado.</span><span class="sxs-lookup"><span data-stu-id="4ea07-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="4ea07-110">Como salvar logs em salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ea07-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="4ea07-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-111"></span></span>

<span data-ttu-id="4ea07-112">Para coletar logs, você deve chamar o script de conjunto de log que acompanha o aplicativo Microsoft equipes salas.</span><span class="sxs-lookup"><span data-stu-id="4ea07-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="4ea07-113">No modo Admin, inicie um prompt de comandos com privilégios elevados e emita o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4ea07-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="4ea07-114">Os logs serão exibidos como um arquivo ZIP em c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="4ea07-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="4ea07-115">Configurações da tela frontal da sala</span><span class="sxs-lookup"><span data-stu-id="4ea07-115">Front of Room Display Settings</span></span>
<span data-ttu-id="4ea07-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-116"></span></span>

<span data-ttu-id="4ea07-117">Configure a tela frontal da sala para o modo Estendido.</span><span class="sxs-lookup"><span data-stu-id="4ea07-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="4ea07-118">Isso garantirá que o console de que interface do usuário não é duplicado em que exiba quando você desligue a exibição.</span><span class="sxs-lookup"><span data-stu-id="4ea07-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ea07-p105">A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs.</span><span class="sxs-lookup"><span data-stu-id="4ea07-p105">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="4ea07-121">Redefinição de salas de equipes da Microsoft (restauração de fábrica)</span><span class="sxs-lookup"><span data-stu-id="4ea07-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="4ea07-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-122"></span></span>

<span data-ttu-id="4ea07-123">Se salas de equipes da Microsoft não está funcionando bem, realizar uma restauração de fábrica pode ajudar.</span><span class="sxs-lookup"><span data-stu-id="4ea07-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="4ea07-124">Isso pode ser feito no aplicativo configurações na guia **recuperação** abaixo **Redefinir este PC**, selecione **começar**e **Remover tudo**.</span><span class="sxs-lookup"><span data-stu-id="4ea07-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="4ea07-125">Siga as instruções restantes para redefinir o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ea07-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ea07-126">Há um problema conhecido onde as salas de equipes da Microsoft podem se tornar disponível se a opção **Manter Meus arquivos - remove aplicativos e configurações, mas mantém os arquivos pessoais** está selecionada durante o processo de redefinição do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea07-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="4ea07-127">Faça _não_ use esta opção.</span><span class="sxs-lookup"><span data-stu-id="4ea07-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="4ea07-128">Opções remotas com suporte</span><span class="sxs-lookup"><span data-stu-id="4ea07-128">Supported Remote Options</span></span>
<span data-ttu-id="4ea07-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-129"></span></span>

<span data-ttu-id="4ea07-130">A tabela a seguir resume as operações remotas possíveis e os métodos que você pode usar para executá-las.</span><span class="sxs-lookup"><span data-stu-id="4ea07-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="4ea07-131">\*\*Grupo de trabalho \*\*</span><span class="sxs-lookup"><span data-stu-id="4ea07-131">**Workgroup**</span></span>|<span data-ttu-id="4ea07-132">**Não ingresso em domínio**</span><span class="sxs-lookup"><span data-stu-id="4ea07-132">**Not domain joined**</span></span>|<span data-ttu-id="4ea07-133">**Ingresso em domínio**</span><span class="sxs-lookup"><span data-stu-id="4ea07-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ea07-134">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="4ea07-134">Restart</span></span>  <br/> |<span data-ttu-id="4ea07-135">Área de trabalho remota</span><span class="sxs-lookup"><span data-stu-id="4ea07-135">Remote desktop</span></span>  <br/> <span data-ttu-id="4ea07-136">PowerShell Remoto</span><span class="sxs-lookup"><span data-stu-id="4ea07-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="4ea07-137">Área de trabalho remota (requer configuração adicional)</span><span class="sxs-lookup"><span data-stu-id="4ea07-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="4ea07-138">Powershell remoto (requer configuração adicional)</span><span class="sxs-lookup"><span data-stu-id="4ea07-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="4ea07-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="4ea07-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="4ea07-140">Atualização do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="4ea07-140">Update OS</span></span>  <br/> |<span data-ttu-id="4ea07-141">Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:</span><span class="sxs-lookup"><span data-stu-id="4ea07-141">Windows Update</span></span>  <br/> |<span data-ttu-id="4ea07-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="4ea07-142">Windows Update</span></span>  <br/> <span data-ttu-id="4ea07-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="4ea07-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="4ea07-144">Atualização de aplicativos</span><span class="sxs-lookup"><span data-stu-id="4ea07-144">App update</span></span>  <br/> |<span data-ttu-id="4ea07-145">Windows Store</span><span class="sxs-lookup"><span data-stu-id="4ea07-145">Windows Store</span></span>  <br/> |<span data-ttu-id="4ea07-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="4ea07-146">Windows Store</span></span>  <br/> <span data-ttu-id="4ea07-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="4ea07-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="4ea07-148">Configuração de contas do Skype</span><span class="sxs-lookup"><span data-stu-id="4ea07-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="4ea07-149">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="4ea07-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="4ea07-150">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="4ea07-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="4ea07-151">Acesso aos logs</span><span class="sxs-lookup"><span data-stu-id="4ea07-151">Access logs</span></span>  <br/> |<span data-ttu-id="4ea07-152">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="4ea07-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="4ea07-153">Sem suporte no momento</span><span class="sxs-lookup"><span data-stu-id="4ea07-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="4ea07-154">Configurando a diretiva de grupo para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ea07-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="4ea07-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-155"></span></span>

<span data-ttu-id="4ea07-156">Esta seção aborda as configurações do sistema Microsoft equipes salas depende funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="4ea07-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="4ea07-157">Ao ingressar em salas de equipes da Microsoft a um domínio, certifique-se de que sua política de grupo não substituem as definições na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="4ea07-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="4ea07-158">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="4ea07-158">**Setting**</span></span>|<span data-ttu-id="4ea07-159">**Permite**</span><span class="sxs-lookup"><span data-stu-id="4ea07-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4ea07-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="4ea07-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="4ea07-161">Permite que o Microsoft salas de equipes inicialize</span><span class="sxs-lookup"><span data-stu-id="4ea07-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="4ea07-162">Gerenciamento - de energia\> nas AC, desative tela após 10 minutos</span><span class="sxs-lookup"><span data-stu-id="4ea07-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="4ea07-163">Gerenciamento - de energia\> em AC, nunca colocar o sistema no modo de suspensão</span><span class="sxs-lookup"><span data-stu-id="4ea07-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="4ea07-164">Habilita a salas de equipes da Microsoft desativar exibe anexado e automaticamente de ativação</span><span class="sxs-lookup"><span data-stu-id="4ea07-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="4ea07-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="4ea07-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="4ea07-166">Ou equivalentes meios de desativação de expiração de senha da conta local.</span><span class="sxs-lookup"><span data-stu-id="4ea07-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="4ea07-167">Falha ao fazer isso, eventualmente, fará com que a conta do Skype falha de logon reclamando uma senha expirada.</span><span class="sxs-lookup"><span data-stu-id="4ea07-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="4ea07-168">Observe que isso afeta todas as contas locais na máquina, e assim falha configurar isso também fará com que a conta administrativa na caixa eventualmente expire também.</span><span class="sxs-lookup"><span data-stu-id="4ea07-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="4ea07-169">Permite que a conta do Skype esteja sempre conectada</span><span class="sxs-lookup"><span data-stu-id="4ea07-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="4ea07-170">Transferência de arquivos usando diretivas de grupo será discutido em [Configure um Item do arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4ea07-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="4ea07-171">Gerenciamento remoto usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea07-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="4ea07-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-172"></span></span>

<span data-ttu-id="4ea07-173">Você pode executar as seguintes operações de gerenciamento remotamente usando o PowerShell (consulte a tabela abaixo para amostras de script):</span><span class="sxs-lookup"><span data-stu-id="4ea07-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="4ea07-174">Obter dispositivos conectados</span><span class="sxs-lookup"><span data-stu-id="4ea07-174">Get attached devices</span></span>
    
- <span data-ttu-id="4ea07-175">Obter o status do aplicativo</span><span class="sxs-lookup"><span data-stu-id="4ea07-175">Get app status</span></span>
    
- <span data-ttu-id="4ea07-176">Obter informações do sistema</span><span class="sxs-lookup"><span data-stu-id="4ea07-176">Get system info</span></span>
    
- <span data-ttu-id="4ea07-177">Reiniciar o sistema</span><span class="sxs-lookup"><span data-stu-id="4ea07-177">Reboot system</span></span>
    
- <span data-ttu-id="4ea07-178">Recuperar logs</span><span class="sxs-lookup"><span data-stu-id="4ea07-178">Retrieve logs</span></span>
    
- <span data-ttu-id="4ea07-179">Transferir arquivos (requer um salas de equipes do Microsoft associados a um domínio)</span><span class="sxs-lookup"><span data-stu-id="4ea07-179">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ea07-180">Essa funcionalidade está desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="4ea07-180">This functionality is off by default.</span></span> <span data-ttu-id="4ea07-181">Você precisa ativar o PowerShell remoto para o seu ambiente no sistema de salas de equipes da Microsoft executar as operações abaixo.</span><span class="sxs-lookup"><span data-stu-id="4ea07-181">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="4ea07-182">Consulte a documentação sobre **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** para obter informações sobre como habilitar o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="4ea07-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="4ea07-183">Por exemplo, você pode habilitar o PowerShell Remoto da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ea07-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="4ea07-184">Entrar como administrador em um dispositivo de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ea07-184">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="4ea07-185">Abra um prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ea07-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="4ea07-186">Insira o seguinte comando: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="4ea07-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="4ea07-187">Para executar uma operação de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="4ea07-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="4ea07-188">Entrar em um PC com credenciais de conta que tem permissão para executar comandos do PowerShell em um dispositivo de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ea07-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="4ea07-189">Abra um prompt de comando do PowerShell regular no PC.</span><span class="sxs-lookup"><span data-stu-id="4ea07-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="4ea07-190">Copie o texto de comando da tabela a seguir e cole-o no prompt.</span><span class="sxs-lookup"><span data-stu-id="4ea07-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="4ea07-191">Substituir `<Device fqdn>` campos com valores FQDN apropriadas ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4ea07-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="4ea07-192">Substituir \* \<caminho\> \* com o nome de arquivo e o caminho local do arquivo de configuração SkypeSettings.xml mestre (ou imagem de tema).</span><span class="sxs-lookup"><span data-stu-id="4ea07-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="4ea07-193">Para obter os dispositivos conectados</span><span class="sxs-lookup"><span data-stu-id="4ea07-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="4ea07-194">Obter o status de aplicativos</span><span class="sxs-lookup"><span data-stu-id="4ea07-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="4ea07-195">Obter informações do sistema</span><span class="sxs-lookup"><span data-stu-id="4ea07-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="4ea07-196">Reiniciar o sistema</span><span class="sxs-lookup"><span data-stu-id="4ea07-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="4ea07-197">Recuperar logs</span><span class="sxs-lookup"><span data-stu-id="4ea07-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="4ea07-198">Enviar um arquivo de configuração XML (ou o gráfico do tema)</span><span class="sxs-lookup"><span data-stu-id="4ea07-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="4ea07-199">Atualizações de software</span><span class="sxs-lookup"><span data-stu-id="4ea07-199">Software updates</span></span>
<span data-ttu-id="4ea07-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-200"></span></span>

<span data-ttu-id="4ea07-201">Por padrão, o Microsoft equipes salas tenta se conectar ao repositório do Windows para obter a versão mais recente do software de salas de equipes da Microsoft, para que o dispositivo exigirá regular acesso à internet.</span><span class="sxs-lookup"><span data-stu-id="4ea07-201">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="4ea07-202">Antes de contatar o Microsoft com problemas de suporte, certifique-se de que o dispositivo de salas de equipes da Microsoft é carregado com a versão mais recente do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4ea07-202">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="4ea07-203">Por padrão, salas de equipes da Microsoft se conecta ao Windows Update para recuperar o sistema operacional e atualizações de firmware de dispositivos periféricos USB e as instala fora do horário de comercial configurado.</span><span class="sxs-lookup"><span data-stu-id="4ea07-203">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="4ea07-204">Para configurar o horário comercial, entre na conta de administrador e execute o aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="4ea07-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="4ea07-205">Se você deseja gerenciar atualizações manualmente e não conseguem siga o procedimento de normal para [Microsoft Store for Business](https://businessstore.microsoft.com/store) para [distribuir aplicativos de offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), você pode adquirir as arquivo APPX apropriado e dependências do [kit de implantação](https://go.microsoft.com/fwlink/?linkid=851168) (de as instruções para [Configurar um console de salas de equipes da Microsoft](../../deploy/deploy-clients/console.md)) que podem ser usados com o SCCM.</span><span class="sxs-lookup"><span data-stu-id="4ea07-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="4ea07-206">A versão do kit de implantação sofra a versão do repositório, portanto pode não sempre corresponder a compilação mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="4ea07-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="4ea07-207">Para atualizar usando Powershell</span><span class="sxs-lookup"><span data-stu-id="4ea07-207">To update using Powershell</span></span>

1. <span data-ttu-id="4ea07-208">Extraia o pacote da instalação [MSI](https://go.microsoft.com/fwlink/?linkid=851168) para um compartilhamento de dispositivo pode acessar.</span><span class="sxs-lookup"><span data-stu-id="4ea07-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="4ea07-209">Execute o seguinte script direcionando os dispositivos de salas de equipes da Microsoft, alterando \<compartilhar\> ao dispositivo compartilhar conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="4ea07-209">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="4ea07-210">Modo de administração e gerenciamento de dispositivo</span><span class="sxs-lookup"><span data-stu-id="4ea07-210">Admin mode and device management</span></span>
<span data-ttu-id="4ea07-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-211"></span></span>

<span data-ttu-id="4ea07-212">Algumas funções de gerenciamento, como manualmente instalando um certificado de autoridade de certificação privado, exigem colocando o dispositivo Surface Pro no modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="4ea07-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="4ea07-213">Alternando para o modo de administração e voltar quando o aplicativo de salas de equipes da Microsoft está sendo executado</span><span class="sxs-lookup"><span data-stu-id="4ea07-213">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="4ea07-214">Desligar todas as chamadas em andamento e retornar à tela inicial.</span><span class="sxs-lookup"><span data-stu-id="4ea07-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="4ea07-215">Selecione o ícone de engrenagem e acessar o menu (opções estarão **configurações**, **acessibilidade**e **Reinicie o dispositivo** ).</span><span class="sxs-lookup"><span data-stu-id="4ea07-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="4ea07-216">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="4ea07-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="4ea07-217">Digite a senha do administrador.</span><span class="sxs-lookup"><span data-stu-id="4ea07-217">Enter the Administrator Password.</span></span> <span data-ttu-id="4ea07-218">A tela Configuração será exibida.</span><span class="sxs-lookup"><span data-stu-id="4ea07-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ea07-219">Se o dispositivo não estiver associado ao domínio, a conta administrativa local (username "Admin") será usada por padrão.</span><span class="sxs-lookup"><span data-stu-id="4ea07-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="4ea07-220">A senha padrão para essa conta será 'sfb', mas é recomendável que sua organização mude essa senha o quanto antes por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="4ea07-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="4ea07-221">Se o computador estiver associado ao domínio, você pode entrar com uma conta de domínio apropriadamente privilegiado.</span><span class="sxs-lookup"><span data-stu-id="4ea07-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="4ea07-222">Selecione **Configurações do Windows** , na coluna esquerda.</span><span class="sxs-lookup"><span data-stu-id="4ea07-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="4ea07-223">Escolha **Vá para Entrada como Admin**.</span><span class="sxs-lookup"><span data-stu-id="4ea07-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="4ea07-224">Digite a senha do administrador.</span><span class="sxs-lookup"><span data-stu-id="4ea07-224">Enter the Administrator Password.</span></span> <span data-ttu-id="4ea07-225">Isso faz com que o aplicativo seja desativado e leva você até a tela de logon do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea07-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="4ea07-226">Faça logon no desktop usando as credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="4ea07-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="4ea07-227">Você terá os privilégios necessários para gerenciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ea07-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="4ea07-228">Execute as tarefas administrativas necessárias.</span><span class="sxs-lookup"><span data-stu-id="4ea07-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="4ea07-229">Saia da conta de Administrador.</span><span class="sxs-lookup"><span data-stu-id="4ea07-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="4ea07-230">Retorne à Microsoft equipes salas selecionando o ícone de conta de usuário no lado esquerdo da tela e, em seguida, selecionando **Skype**.</span><span class="sxs-lookup"><span data-stu-id="4ea07-230">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="4ea07-231">Se o usuário **Skype** não estiver listado, você pode precisar selecionar **outro usuário** e insira **. \skype** como o nome de usuário e de entrada.</span><span class="sxs-lookup"><span data-stu-id="4ea07-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="4ea07-232">O console agora é novamente em seu modo de operação normal. O procedimento a seguir exige que você anexar um teclado para o dispositivo, se ainda não estiver já anexado.</span><span class="sxs-lookup"><span data-stu-id="4ea07-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="4ea07-233">Alternando para o modo de administração e quando o aplicativo Microsoft equipes salas de travamento</span><span class="sxs-lookup"><span data-stu-id="4ea07-233">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="4ea07-234">Pressione a tecla do Windows cinco vezes em uma sucessão rápida.</span><span class="sxs-lookup"><span data-stu-id="4ea07-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="4ea07-235">Isso levará você para a tela de logon do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ea07-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="4ea07-236">Faça logon no desktop usando as credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="4ea07-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ea07-237">Esse método não logoff do usuário do Skype ou finalizado normalmente o aplicativo, mas você deve usá-lo se o aplicativo não estava respondendo e o outro método não estava disponível.</span><span class="sxs-lookup"><span data-stu-id="4ea07-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="4ea07-238">Execute as tarefas administrativas necessárias.</span><span class="sxs-lookup"><span data-stu-id="4ea07-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="4ea07-239">Quando tiver terminado, reinicie a máquina.</span><span class="sxs-lookup"><span data-stu-id="4ea07-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="4ea07-240">O console é reiniciado em seu modo de operação normal, executando o aplicativo Microsoft equipes salas.</span><span class="sxs-lookup"><span data-stu-id="4ea07-240">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="4ea07-241">Você pode remover o teclado, se ele foi conectado para permitir que você executar esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="4ea07-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="4ea07-242">Dicas para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="4ea07-242">Troubleshooting tips</span></span>
   <span data-ttu-id="4ea07-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="4ea07-243"></span></span>

- <span data-ttu-id="4ea07-244">Convites de reunião podem não aparecer quando enviado nos limites do domínio (por exemplo, entre as duas empresas).</span><span class="sxs-lookup"><span data-stu-id="4ea07-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="4ea07-245">Nesses casos, os administradores de TI devem decidir se deseja permitir que usuários externos agendar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="4ea07-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="4ea07-246">Salas de equipes da Microsoft não suporta os redirecionamentos de descoberta automática do Exchange por meio do Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="4ea07-246">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="4ea07-247">Em geral, é uma boa prática para administradores de TI desabilitar quaisquer pontos de extremidade de áudio não pretendem usar.</span><span class="sxs-lookup"><span data-stu-id="4ea07-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="4ea07-248">Caso seja exibida uma imagem espelhada na visualização da sala, o administrador de TI pode corrigir isso desligando e ligando a câmera ou invertendo a orientação da imagem com o controle remoto da câmera.</span><span class="sxs-lookup"><span data-stu-id="4ea07-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="4ea07-249">Sabe-se que pode ocorrer a perda do acesso à tela touch do console.</span><span class="sxs-lookup"><span data-stu-id="4ea07-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="4ea07-250">Nesses casos, o problema em alguns casos, é resolvido reiniciando-se o sistema de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ea07-250">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="4ea07-251">Sabe-se que pode ocorrer a perda do áudio local ao conectar um computador ao console via entrada com fio.</span><span class="sxs-lookup"><span data-stu-id="4ea07-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="4ea07-252">Nesses casos, reiniciar o computador pode resolver o problema de reprodução do áudio local.</span><span class="sxs-lookup"><span data-stu-id="4ea07-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
