---
title: Habilitar a qualidade da experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Resumo: saiba como habilitar a QoE (Qualidade da Experiência) no Skype for Business Server.'
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095205"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="85c1e-103">Habilitar a qualidade da experiência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="85c1e-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="85c1e-104">**Resumo:** saiba como habilitar a QoE (Qualidade da Experiência) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85c1e-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="85c1e-105">A QoE (Qualidade da Experiência) registra dados numéricos que indicam a qualidade da mídia e informações sobre participantes, nomes de dispositivo, drivers, endereços IP e tipos de ponto de extremidade envolvidos em chamadas e sessões.</span><span class="sxs-lookup"><span data-stu-id="85c1e-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="85c1e-106">Para obter detalhes, consulte [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring), na documentação de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="85c1e-106">For details, see [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation.</span></span>

<span data-ttu-id="85c1e-107">Use o procedimento a seguir para habilitar QoE para toda sua organização ou para cada site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="85c1e-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="85c1e-108">Para habilitar o QoE, é necessário primeiro configurar o monitoramento e um back-end de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="85c1e-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="85c1e-109">Para obter detalhes, consulte [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span><span class="sxs-lookup"><span data-stu-id="85c1e-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="85c1e-110">Para habilitar a QoE usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="85c1e-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="85c1e-111">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85c1e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="85c1e-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85c1e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="85c1e-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Dados da Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="85c1e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="85c1e-114">Na página **Dados da Qualidade da Experiência**, clique no conjunto adequado na tabela, clique em **Ação** e em **habilitar QoE**.</span><span class="sxs-lookup"><span data-stu-id="85c1e-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="85c1e-115">Habilitando a QoE usando Windows PowerShell Cmdlets</span><span class="sxs-lookup"><span data-stu-id="85c1e-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="85c1e-116">Você pode habilitar a QoE usando Windows PowerShell e o cmdlet **Set-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="85c1e-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="85c1e-117">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85c1e-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="85c1e-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="85c1e-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="85c1e-119">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85c1e-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="85c1e-120">Para habilitar o QoE para um único local</span><span class="sxs-lookup"><span data-stu-id="85c1e-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="85c1e-121">Para habilitar o QoE, defina o parâmetro EnableQoE para True ($True).</span><span class="sxs-lookup"><span data-stu-id="85c1e-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="85c1e-122">Para desabilitar o QoE para um único local</span><span class="sxs-lookup"><span data-stu-id="85c1e-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="85c1e-p104">Para desabilitar o QoE, defina o parâmetro EnableQoE para False ($False). Isto não desinstala o monitoramento. Pausa o conjunto e armazena os dados do QoE.</span><span class="sxs-lookup"><span data-stu-id="85c1e-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="85c1e-126">Para usar um único comando para habilitar o QoE em vários locais</span><span class="sxs-lookup"><span data-stu-id="85c1e-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="85c1e-127">Este comando habilita o QoE para todas as definições de configuração do QoE atualmente em uso na sua organização.</span><span class="sxs-lookup"><span data-stu-id="85c1e-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="85c1e-128">Para obter detalhes, [consulte Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="85c1e-128">For details, see [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="85c1e-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="85c1e-129">See also</span></span>

[<span data-ttu-id="85c1e-130">Planejamento do monitoramento</span><span class="sxs-lookup"><span data-stu-id="85c1e-130">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="85c1e-131">Implantando o monitoramento</span><span class="sxs-lookup"><span data-stu-id="85c1e-131">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)