---
title: Visão geral do gerenciamento de salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Visão geral do gerenciamento de salas de equipes da Microsoft.
ms.openlocfilehash: 5ee6d4a3f797ee8dbc5fa54a139b847e549611a1
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362595"
---
# <a name="management-overview"></a><span data-ttu-id="3285f-103">Visão geral do gerenciamento</span><span class="sxs-lookup"><span data-stu-id="3285f-103">Management overview</span></span> 

<span data-ttu-id="3285f-104">É essencial que você desenvolver e executar manutenção contínua e a experiência de operações para garantir que seus sistemas de salas de equipes da Microsoft estão disponíveis para seus usuários e oferecem um ótimo usuário.</span><span class="sxs-lookup"><span data-stu-id="3285f-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="3285f-105">Monitoramento</span><span class="sxs-lookup"><span data-stu-id="3285f-105">Monitoring</span></span> 

<span data-ttu-id="3285f-106">Monitorando sistemas de salas de equipes da Microsoft consiste em duas atividades principais:</span><span class="sxs-lookup"><span data-stu-id="3285f-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

-  <span data-ttu-id="3285f-107">Dispositivo, aplicativo e monitoramento de dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="3285f-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="3285f-108">Qualidade e confiabilidade monitoring (CQD)</span><span class="sxs-lookup"><span data-stu-id="3285f-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="3285f-109">Dispositivo de salas de equipes da Microsoft, aplicativo e monitoramento de dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="3285f-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="3285f-110">Para garantir que os usuários sejam capazes de usar as unidades de salas de equipes da Microsoft, as unidades devem estar na, conectado à rede com o aplicativo Microsoft equipes salas configurado corretamente e estar conectadas ao funcionamento dispositivos periféricos.</span><span class="sxs-lookup"><span data-stu-id="3285f-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="3285f-111">Informações sobre o estado do aplicativo Microsoft equipes salas e dispositivos periféricos conectados é gravadas pelo aplicativo salas de equipes da Microsoft para o log de eventos do Windows e documentadas no [entender as entradas de log](azure-monitor-manage.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="3285f-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="3285f-112">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="3285f-112">**Setting**</span></span>|<span data-ttu-id="3285f-113">**Permite**</span><span class="sxs-lookup"><span data-stu-id="3285f-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3285f-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="3285f-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="3285f-115">Permite que o Microsoft salas de equipes inicialize</span><span class="sxs-lookup"><span data-stu-id="3285f-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="3285f-116">Gerenciamento - de energia\> nas AC, desative tela após 10 minutos</span><span class="sxs-lookup"><span data-stu-id="3285f-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="3285f-117">Gerenciamento - de energia\> em AC, nunca colocar o sistema no modo de suspensão</span><span class="sxs-lookup"><span data-stu-id="3285f-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="3285f-118">Habilita a salas de equipes da Microsoft desativar exibe anexado e automaticamente de ativação</span><span class="sxs-lookup"><span data-stu-id="3285f-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="3285f-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="3285f-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="3285f-120">Ou equivalentes meios de desativação de expiração de senha da conta local.</span><span class="sxs-lookup"><span data-stu-id="3285f-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="3285f-121">Falha ao fazer isso, eventualmente, fará com que a conta do Skype falha de logon reclamando uma senha expirada.</span><span class="sxs-lookup"><span data-stu-id="3285f-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="3285f-122">Observe que isso afeta todas as contas locais na máquina, e assim falha configurar isso também fará com que a conta administrativa na caixa eventualmente expire também.</span><span class="sxs-lookup"><span data-stu-id="3285f-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="3285f-123">Permite que a conta do Skype esteja sempre conectada</span><span class="sxs-lookup"><span data-stu-id="3285f-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="3285f-124">Transferência de arquivos usando diretivas de grupo será discutido em [Configure um Item do arquivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="3285f-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="3285f-125">Gerenciamento remoto usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3285f-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="3285f-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="3285f-126"></span></span>

<span data-ttu-id="3285f-127">Recomendamos que você use o pacote do Microsoft Operations Manager para monitorar os sistemas de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3285f-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="3285f-128">Para obter orientação sobre como configurar o monitoramento e alerta básica, consulte [gerenciamento de implantar o Microsoft equipes salas com Monitor do Azure](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="3285f-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="3285f-129">Usando este guia, você pode criar um painel simples de usar para identificar problemas com suas unidades de salas de equipes da Microsoft em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="3285f-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="3285f-130">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="3285f-130">Decision points</span></span>|<ul><li><span data-ttu-id="3285f-131">Confirme que você usará o pacote de gerenciamento de operações para monitorar sua implantação de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3285f-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="3285f-132">Decida a lista de distribuição de destino que você usará para alertas de email.</span><span class="sxs-lookup"><span data-stu-id="3285f-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="3285f-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3285f-133">Next steps</span></span>|<ul><li><span data-ttu-id="3285f-134">Defina sua qualidade e a confiabilidade abordagem de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="3285f-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="3285f-135">Qualidade e confiabilidade monitoring (CQD)</span><span class="sxs-lookup"><span data-stu-id="3285f-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="3285f-136">É recomendável que você implemente qualidade operacional em andamento e a confiabilidade monitoring procedimentos como parte da sua implantação para monitorar as tendências de chamada e qualidade de reunião e confiabilidade, identificando quaisquer áreas de interesse e trabalhando com uma resolução.</span><span class="sxs-lookup"><span data-stu-id="3285f-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="3285f-137">Quando você carregar suas informações de construção para CQD, você pode investigar tendências de qualidade e confiabilidade de chamada em um nível por construção, que torna mais fácil comparar os prédios e focalizar problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="3285f-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="3285f-138">Para obter mais informações, baixe o [Monitor-CQD para Skype para entrega Business Online e um guia de operações](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="3285f-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="3285f-139">Recomendamos que você revise e siga o [Guia Quality of Experience revisar](https://aka.ms/qerguide) para identificar as tendências de qualidade e a confiabilidade e cria um plano de ação para resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="3285f-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="3285f-140">Atualizar o aplicativo Microsoft equipes salas SO e salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3285f-140">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="3285f-141">Recomendamos que você atualize o aplicativo Microsoft equipes salas SO e salas de equipes da Microsoft para se beneficiar de atualizações de produto e os aperfeiçoamentos.</span><span class="sxs-lookup"><span data-stu-id="3285f-141">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="3285f-142">Para obter orientações detalhadas, consulte [Manage Rooms de equipes da Microsoft](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="3285f-142">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="3285f-143">Atualizações do Windows</span><span class="sxs-lookup"><span data-stu-id="3285f-143">Windows Updates</span></span>

<span data-ttu-id="3285f-144">Salas de equipes da Microsoft é executado no Windows 10 Enterprise IoT ou Windows 10 Enterprise (VL) e recebe as mesmas compilações de atualizações do Windows e o sistema operacional como uma área de trabalho padrão.</span><span class="sxs-lookup"><span data-stu-id="3285f-144">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="3285f-145">Consulte [Gerenciar atualizações do Windows](updates.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="3285f-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="3285f-146">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="3285f-146">Troubleshooting</span></span>

<span data-ttu-id="3285f-147">Recomendamos que você configurar o pacote de gerenciamento de operações de alerta conforme descrito na seção acima para que sua equipe de operações e a assistência técnica serão alertados sobre qualquer problema de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3285f-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="3285f-148">As opções que disponíveis para gerenciamento remoto do PowerShell são descritas no [gerenciamento remoto usando o PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="3285f-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="3285f-149">Se um dispositivo periférico estiver desconectado, você talvez seja necessário contam com suporte de TI para investigar e reconectar os dispositivos ou de locais "ponteiros inteligentes".</span><span class="sxs-lookup"><span data-stu-id="3285f-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="3285f-150">Para obter mais informações sobre o modo de administração e solução de problemas, consulte [Manage Rooms de equipes da Microsoft](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="3285f-150">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="3285f-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="3285f-151">See also</span></span>

[<span data-ttu-id="3285f-152">Suporte às Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3285f-152">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="3285f-153">Planejar para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3285f-153">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="3285f-154">Implantar salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3285f-154">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="3285f-155">Configurar um console de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3285f-155">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="3285f-156">Gerenciar configurações do console um Microsoft equipes salas remotamente com um arquivo de configuração XML</span><span class="sxs-lookup"><span data-stu-id="3285f-156">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
