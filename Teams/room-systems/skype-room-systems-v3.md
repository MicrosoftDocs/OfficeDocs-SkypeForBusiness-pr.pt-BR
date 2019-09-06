---
title: Visão geral de gerenciamento para salas do Microsoft Teams
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Visão geral de gerenciamento para salas do Microsoft Teams.
ms.openlocfilehash: 28a48bb4aba417fba076e8c31492e8191e7164c9
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775082"
---
# <a name="management-overview"></a><span data-ttu-id="06cad-103">Visão geral do gerenciamento</span><span class="sxs-lookup"><span data-stu-id="06cad-103">Management overview</span></span>

<span data-ttu-id="06cad-104">É essencial que você desenvolva e execute manutenção e operações contínuas para garantir que seus sistemas de salas do Microsoft Teams estejam disponíveis para seus usuários e proporcionar uma excelente experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="06cad-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="06cad-105">Monitoramento</span><span class="sxs-lookup"><span data-stu-id="06cad-105">Monitoring</span></span> 

<span data-ttu-id="06cad-106">Monitorar as salas do Microsoft Teams Systems consiste em duas atividades importantes:</span><span class="sxs-lookup"><span data-stu-id="06cad-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="06cad-107">Monitoramento de dispositivos, aplicativos e periféricos</span><span class="sxs-lookup"><span data-stu-id="06cad-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="06cad-108">Monitoramento de qualidade e confiabilidade (CQD)</span><span class="sxs-lookup"><span data-stu-id="06cad-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="06cad-109">Monitoramento de dispositivos, aplicativos e dispositivos periféricos do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06cad-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="06cad-110">Para garantir que os usuários possam usar as unidades de sala do Microsoft Teams, as unidades devem estar conectadas à rede com o aplicativo salas do Microsoft Teams configurado corretamente e estar conectado a dispositivos periféricos em funcionamento.</span><span class="sxs-lookup"><span data-stu-id="06cad-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="06cad-111">Informações sobre o estado do aplicativo salas do Microsoft Teams e dispositivos periféricos conectados são escritos pelo aplicativo salas do Microsoft Teams para o log de eventos do Windows e documentados em [entender as entradas do log](azure-monitor-manage.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="06cad-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="06cad-112">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="06cad-112">**Setting**</span></span>|<span data-ttu-id="06cad-113">**Permite**</span><span class="sxs-lookup"><span data-stu-id="06cad-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="06cad-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1</span><span class="sxs-lookup"><span data-stu-id="06cad-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="06cad-115">Permite que salas do Microsoft Teams sejam inicializadas</span><span class="sxs-lookup"><span data-stu-id="06cad-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="06cad-116">Gerenciamento de energia\> -em AC, desligar a tela após 10 minutos</span><span class="sxs-lookup"><span data-stu-id="06cad-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="06cad-117">Gerenciamento de energia\> -em AC, nunca coloque o sistema em suspensão</span><span class="sxs-lookup"><span data-stu-id="06cad-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="06cad-118">Permite que as salas do Microsoft Teams desativem exibições anexadas e ativadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="06cad-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="06cad-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="06cad-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="06cad-120">Ou uma maneira equivalente de desabilitar a expiração de senha na conta local.</span><span class="sxs-lookup"><span data-stu-id="06cad-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="06cad-121">Deixar de fazer isso fará com que a conta do Skype falhe ao fazer logon com uma senha expirada.</span><span class="sxs-lookup"><span data-stu-id="06cad-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="06cad-122">Observe que isso afeta todas as contas locais do computador e, portanto, não definir isso também fará com que a conta administrativa na caixa acabe de expirar também.</span><span class="sxs-lookup"><span data-stu-id="06cad-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="06cad-123">Permite que a conta do Skype esteja sempre conectada</span><span class="sxs-lookup"><span data-stu-id="06cad-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="06cad-124">A transferência de arquivos usando políticas de grupo é discutida em [configurar um item de arquivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="06cad-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="06cad-125">Gerenciamento remoto usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="06cad-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="06cad-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="06cad-126"></span></span>

<span data-ttu-id="06cad-127">Recomendamos que você use o pacote do Microsoft Operations Manager para monitorar seus sistemas de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06cad-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="06cad-128">Para obter orientação sobre como configurar o monitoramento e o alerta básico, consulte [implantar gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="06cad-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="06cad-129">Usando esta orientação, você pode criar um painel simples de usar para identificar os problemas com as unidades de sala do Microsoft Teams na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="06cad-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="06cad-130">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="06cad-130">Decision points</span></span>|<ul><li><span data-ttu-id="06cad-131">Confirme que você usará o Operations Management Suite para monitorar a implantação de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06cad-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="06cad-132">Escolha a lista de distribuição de destino que você usará para alertas de email.</span><span class="sxs-lookup"><span data-stu-id="06cad-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="06cad-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="06cad-133">Next steps</span></span>|<ul><li><span data-ttu-id="06cad-134">Defina sua abordagem de qualidade e monitoramento de confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="06cad-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="06cad-135">Monitoramento de qualidade e confiabilidade (CQD)</span><span class="sxs-lookup"><span data-stu-id="06cad-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="06cad-136">Recomendamos que você implemente a qualidade operacional contínua e os procedimentos de monitoramento de confiabilidade como parte da sua implantação para monitorar a tendência da chamada e a qualidade e a confiabilidade da reunião, identificando as áreas de interesse e trabalhando em direção a uma resolução.</span><span class="sxs-lookup"><span data-stu-id="06cad-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="06cad-137">Ao carregar suas informações de construção para CQD, você pode investigar as tendências de qualidade de chamada e confiabilidade em um nível de construção, o que torna mais fácil comparar os prédios e concentrar sua atenção em problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="06cad-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="06cad-138">Recomendamos que você examine e siga o [Guia de revisão da qualidade da experiência](https://aka.ms/qerguide) para identificar as tendências de qualidade e confiabilidade e crie um plano de ação para solucioná-los.</span><span class="sxs-lookup"><span data-stu-id="06cad-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="06cad-139">Atualizando o aplicativo salas do Microsoft Teams e salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06cad-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="06cad-140">Recomendamos que você atualize o sistema operacional de salas do Microsoft Teams e o aplicativo de salas do Microsoft Teams para se beneficiar de atualizações e melhorias de produtos.</span><span class="sxs-lookup"><span data-stu-id="06cad-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="06cad-141">Para obter orientação detalhada, consulte [gerenciar salas do Microsoft Teams](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="06cad-141">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="06cad-142">Atualizações do Windows</span><span class="sxs-lookup"><span data-stu-id="06cad-142">Windows Updates</span></span>

<span data-ttu-id="06cad-143">As salas do Microsoft Teams são executadas no Windows 10 Enterprise IoT ou no Windows 10 Enterprise (VL) e recebe as mesmas versões do Windows e do sistema operacional do Windows como uma área de trabalho padrão.</span><span class="sxs-lookup"><span data-stu-id="06cad-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="06cad-144">Consulte [gerenciar atualizações do Windows](updates.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="06cad-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="06cad-145">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="06cad-145">Troubleshooting</span></span>

<span data-ttu-id="06cad-146">Recomendamos que você configure o alerta do Operations Management Suite conforme descrito na seção acima para que sua equipe de operações e helpdesks sejam alertados sobre problemas de sala do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06cad-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="06cad-147">As opções que você tem para gerenciamento remoto do PowerShell são descritas em [gerenciamento remoto usando o PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="06cad-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="06cad-148">Caso um dispositivo periférico seja desconectado, talvez seja necessário confiar em "práticas inteligentes" locais ou no suporte de ti para investigar e reconectar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="06cad-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="06cad-149">Para obter mais informações sobre solução de problemas e modo de administração, consulte [gerenciar salas do Microsoft Teams](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="06cad-149">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="06cad-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="06cad-150">See also</span></span>

[<span data-ttu-id="06cad-151">Suporte às Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06cad-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="06cad-152">Plano para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06cad-152">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="06cad-153">Implantar salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06cad-153">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="06cad-154">Configurar um console de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06cad-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="06cad-155">Gerenciar as configurações de um console de salas do Microsoft Teams remotamente com um arquivo de configuração XML</span><span class="sxs-lookup"><span data-stu-id="06cad-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
