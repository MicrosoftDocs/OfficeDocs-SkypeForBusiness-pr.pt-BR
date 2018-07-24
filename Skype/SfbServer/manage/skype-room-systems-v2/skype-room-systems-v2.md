---
title: Visão geral do gerenciamento de sistemas de sala Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Visão geral do gerenciamento de sistemas de sala Skype v2.
ms.openlocfilehash: 81ad0e43f68127e3a178434ebdd8ac8a43c94adc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014900"
---
# <a name="management-overview"></a><span data-ttu-id="53e02-103">Visão geral do gerenciamento</span><span class="sxs-lookup"><span data-stu-id="53e02-103">Management overview</span></span> 

<span data-ttu-id="53e02-104">É essencial que você desenvolver e executar manutenção contínua e a experiência de operações para garantir que seus sistemas de v2 Skype sala sistemas estão disponíveis para os usuários e oferecem um ótimo usuário.</span><span class="sxs-lookup"><span data-stu-id="53e02-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Skype Room Systems v2 systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="53e02-105">Monitoramento</span><span class="sxs-lookup"><span data-stu-id="53e02-105">Monitoring</span></span> 

<span data-ttu-id="53e02-106">Sistemas de sala Skype v2 sistemas de monitoramento consistem em duas atividades principais:</span><span class="sxs-lookup"><span data-stu-id="53e02-106">Monitoring Skype Room Systems v2 systems consists of two key activities:</span></span>

-  <span data-ttu-id="53e02-107">Dispositivo, aplicativo e monitoramento de dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="53e02-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="53e02-108">Qualidade e confiabilidade monitoring (CQD)</span><span class="sxs-lookup"><span data-stu-id="53e02-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="53e02-109">Dispositivo de v2 Skype sala sistemas, aplicativos e o monitoramento de dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="53e02-109">Skype Room Systems v2 device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="53e02-110">Para garantir que os usuários sejam capazes de usar as unidades do Skype sala sistemas v2, as unidades devem estar na, conectado à rede com o aplicativo de v2 de sistemas de sala Skype configurado corretamente e estar conectadas ao funcionamento dispositivos periféricos.</span><span class="sxs-lookup"><span data-stu-id="53e02-110">To ensure that users are able to use the Skype Room Systems v2 units, the units must be on, connected to the network with the Skype Room Systems v2 application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="53e02-111">Informações sobre o estado do aplicativo de v2 Skype sala sistemas e dispositivos periféricos conectados são gravadas pelo aplicativo Skype sala sistemas v2 para o log de eventos do Windows e documentadas [neste artigo](oms.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="53e02-111">Information about the state of the Skype Room Systems v2 application and connected peripheral devices is written by the Skype Room Systems v2 application to the Windows event log and documented [in this article](oms.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="53e02-112">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="53e02-112">**Setting**</span></span>|<span data-ttu-id="53e02-113">**Permite**</span><span class="sxs-lookup"><span data-stu-id="53e02-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="53e02-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="53e02-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="53e02-115">Permite que os sistemas de sala Skype v2 inicialize</span><span class="sxs-lookup"><span data-stu-id="53e02-115">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="53e02-116">Gerenciamento - de energia\> nas AC, desative tela após 10 minutos</span><span class="sxs-lookup"><span data-stu-id="53e02-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="53e02-117">Gerenciamento - de energia\> em AC, nunca colocar o sistema no modo de suspensão</span><span class="sxs-lookup"><span data-stu-id="53e02-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="53e02-118">Permite que os sistemas de sala Skype v2 desativar exibe anexado e automaticamente de ativação</span><span class="sxs-lookup"><span data-stu-id="53e02-118">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="53e02-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="53e02-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="53e02-p101">Ou um modo equivalente de desabilitar a expiração da senha na conta local. A impossibilidade de fazer isso pode causar uma falha no logon com a conta do Skype com uma mensagem de senha expirada. Observe que isso afeta todas as contas locais do computador. Portanto, se isso não for definido, com o tempo, a conta de administrador também vai expirar. </span><span class="sxs-lookup"><span data-stu-id="53e02-p101">Or equivalent means of disabling password expiration on the local account. Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password. Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="53e02-123">Permite que a conta do Skype esteja sempre conectada</span><span class="sxs-lookup"><span data-stu-id="53e02-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="53e02-124">Transferência de arquivos usando diretivas de grupo será discutido em [Configure um Item do arquivo](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="53e02-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="53e02-125">Gerenciamento remoto usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="53e02-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="53e02-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="53e02-126"></span></span>


<span data-ttu-id="53e02-127">Recomendamos que você use o pacote do Microsoft Operations Manager para monitorar os sistemas de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="53e02-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Skype Room Systems v2 systems.</span></span> <span data-ttu-id="53e02-128">Para obter orientação sobre como configurar o monitoramento e alerta básica, consulte [gerenciamento de v2 de implantar sistemas do Skype sala com OMS](../../deploy/deploy-clients/with-oms.md).</span><span class="sxs-lookup"><span data-stu-id="53e02-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md).</span></span> 

<span data-ttu-id="53e02-129">Usando este guia, você pode criar um painel simples de usar para identificar problemas com suas unidades v2 de sistemas de sala Skype entre sua implantação.</span><span class="sxs-lookup"><span data-stu-id="53e02-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Skype Room Systems v2 units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="53e02-130">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="53e02-130">Decision points</span></span>|<ul><li><span data-ttu-id="53e02-131">Confirme que você usará o pacote de gerenciamento de operações para monitorar sua implantação do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="53e02-131">Confirm that you'll use Operations Management Suite to monitor your Skype Room Systems v2 deployment.</span></span></li><li><span data-ttu-id="53e02-132">Decida a lista de distribuição de destino que você usará para alertas de email.</span><span class="sxs-lookup"><span data-stu-id="53e02-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="53e02-133">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="53e02-133">Next steps</span></span>|<ul><li><span data-ttu-id="53e02-134">Defina sua qualidade e a confiabilidade abordagem de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="53e02-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="53e02-135">Qualidade e confiabilidade monitoring (CQD)</span><span class="sxs-lookup"><span data-stu-id="53e02-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="53e02-136">É recomendável que você implemente qualidade operacional em andamento e a confiabilidade monitoring procedimentos como parte da sua implantação para monitorar as tendências de chamada e qualidade de reunião e confiabilidade, identificando quaisquer áreas de interesse e trabalhando com uma resolução.</span><span class="sxs-lookup"><span data-stu-id="53e02-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="53e02-137">Quando você carregar suas informações de construção para CQD, você pode investigar tendências de qualidade e confiabilidade de chamada em um nível por construção, que torna mais fácil comparar os prédios e focalizar problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="53e02-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="53e02-138">Para obter mais informações, baixe o [Monitor-CQD para Skype para entrega Business Online e um guia de operações](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="53e02-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="53e02-139">Recomendamos que você revise e siga o [Guia Quality of Experience revisar](https://aka.ms/qerguide) para identificar as tendências de qualidade e a confiabilidade e cria um plano de ação para resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="53e02-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a><span data-ttu-id="53e02-140">Atualizar o aplicativo de sistemas de sala Skype v2 SO e sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="53e02-140">Updating the Skype Room Systems v2 OS and Skype Room Systems application</span></span> 

<span data-ttu-id="53e02-141">Recomendamos que você atualize o Skype sala sistemas v2 SO e sistemas de sala Skype v2 aplicativo para se beneficiar de atualizações de produto e os aperfeiçoamentos.</span><span class="sxs-lookup"><span data-stu-id="53e02-141">We recommend that you update the Skype Room Systems v2 OS and Skype Room Systems v2 application to benefit from product updates and improvements.</span></span> <span data-ttu-id="53e02-142">Para obter orientações detalhadas, consulte [gerenciar sistemas de sala Skype v2](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="53e02-142">For detailed guidance, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="53e02-143">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="53e02-143">Troubleshooting</span></span>

<span data-ttu-id="53e02-144">Recomendamos que você configure conforme descrito na seção acima para que sua equipe de operações e a assistência técnica serão alertados sobre qualquer problema de sistemas de sala Skype v2 alerta do pacote de gerenciamento de operações.</span><span class="sxs-lookup"><span data-stu-id="53e02-144">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Skype Room Systems v2 issues.</span></span> <span data-ttu-id="53e02-145">As opções que disponíveis para gerenciamento remoto do PowerShell são descritas no [gerenciamento remoto usando o PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="53e02-145">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="53e02-146">Se um dispositivo periférico estiver desconectado, você talvez seja necessário contam com suporte de TI para investigar e reconectar os dispositivos ou de locais "ponteiros inteligentes".</span><span class="sxs-lookup"><span data-stu-id="53e02-146">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="53e02-147">Para obter mais informações sobre o modo de administração e solução de problemas, consulte [gerenciar sistemas de sala Skype v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="53e02-147">For more information about troubleshooting and admin mode, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 

## <a name="see-also"></a><span data-ttu-id="53e02-148">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53e02-148">See also</span></span>

[<span data-ttu-id="53e02-149">Ajuda da versão 2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="53e02-149">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="53e02-150">Planejar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="53e02-150">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="53e02-151">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="53e02-151">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="53e02-152">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="53e02-152">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="53e02-153">Gerenciar as configurações de um console do Skype Room Systems v2 remotamente usando um arquivo de configuração XML</span><span class="sxs-lookup"><span data-stu-id="53e02-153">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
