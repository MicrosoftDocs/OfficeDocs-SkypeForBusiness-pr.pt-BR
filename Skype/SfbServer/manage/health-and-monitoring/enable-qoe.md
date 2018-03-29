---
title: Habilitar a Qualidade da Experiência no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Resumo: Saiba como habilitar a qualidade da experiência (QoE) no Skype para Business Server 2015.'
ms.openlocfilehash: 8c63a1bf493e601c4936b83cc9edfaa6e3727f26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-quality-of-experience-in-skype-for-business-server-2015"></a><span data-ttu-id="2c30c-103">Habilitar a Qualidade da Experiência no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2c30c-103">Enable Quality of Experience in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2c30c-104">**Resumo:** Aprenda a habilitar a qualidade da experiência (QoE) no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2c30c-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2c30c-105">A QoE (Qualidade da Experiência) registra dados numéricos que indicam a qualidade da mídia e informações sobre participantes, nomes de dispositivo, drivers, endereços IP e tipos de ponto de extremidade envolvidos em chamadas e sessões.</span><span class="sxs-lookup"><span data-stu-id="2c30c-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="2c30c-106">Para obter detalhes, consulte [Planejando o monitoramento](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="2c30c-106">For details, see [Planning for Monitoring](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>
  
<span data-ttu-id="2c30c-107">Use o procedimento a seguir para habilitar QoE para toda sua organização ou para cada site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2c30c-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c30c-108">Para habilitar a QoE, é necessário primeiro configurar o monitoramento e um back-end de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2c30c-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="2c30c-109">Para obter detalhes, consulte [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c30c-109">For details, see [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span> 
  
### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2c30c-110">Para habilitar o QoE usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="2c30c-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="2c30c-111">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2c30c-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="2c30c-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="2c30c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2c30c-113">Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="2c30c-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span> 
    
4. <span data-ttu-id="2c30c-114">Na página **Dados de Qualidade da Experiência**, clique no conjunto adequado na tabela, clique em **Ação** e em **Habilitar QoE**.</span><span class="sxs-lookup"><span data-stu-id="2c30c-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>
    
## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2c30c-115">Habilitando o QoE usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c30c-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2c30c-116">É possível habilitar o QoE usando o Windows PowerShell e o cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2c30c-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="2c30c-117">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c30c-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2c30c-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="2c30c-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="2c30c-119">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c30c-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="2c30c-120">Para habilitar a QoE para um único local</span><span class="sxs-lookup"><span data-stu-id="2c30c-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="2c30c-121">Para habilitar a QoE, defina o parâmetro EnableQoE para True ($True).</span><span class="sxs-lookup"><span data-stu-id="2c30c-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="2c30c-122">Para desabilitar a QoE para um único local</span><span class="sxs-lookup"><span data-stu-id="2c30c-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="2c30c-p104">Para desabilitar a QoE, defina o parâmetro EnableQoE para False ($False). Isso não desinstala o monitoramento; pausa o conjunto e armazena os dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="2c30c-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="2c30c-126">Para usar um único comando para habilitar a QoE em vários locais</span><span class="sxs-lookup"><span data-stu-id="2c30c-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="2c30c-127">Este comando habilita a QoE para todas as definições de configuração de QoE atualmente em uso na sua organização.</span><span class="sxs-lookup"><span data-stu-id="2c30c-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="2c30c-128">Para obter detalhes, consulte [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2c30c-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c30c-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2c30c-129">See also</span></span>

[<span data-ttu-id="2c30c-130">Planejamento do monitoramento</span><span class="sxs-lookup"><span data-stu-id="2c30c-130">Planning for Monitoring</span></span>](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[<span data-ttu-id="2c30c-131">Implantando o Monitoring</span><span class="sxs-lookup"><span data-stu-id="2c30c-131">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

