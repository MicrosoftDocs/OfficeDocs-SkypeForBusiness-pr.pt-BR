---
title: Habilitar o registro de detalhes da chamada no Skype for Business Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumo: Saiba como habilitar registros cdr (registro de detalhes de chamada) no Skype for Business Server.'
ms.openlocfilehash: e2f652eeef77c336fb34be07c123f1ef026d458c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095225"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="13ed4-103">Habilitar o registro de detalhes da chamada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="13ed4-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="13ed4-104">**Resumo:** Saiba como habilitar registros cdr (registro de detalhes de chamada) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="13ed4-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="13ed4-105">O CDR (registro de detalhes de chamada) registra informações de uso e diagnóstico sobre atividades ponto a ponto, incluindo mensagens de instância, chamadas VoIP (Voice over Internet Protocol), compartilhamento de aplicativos, transferência de arquivo e reuniões.</span><span class="sxs-lookup"><span data-stu-id="13ed4-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="13ed4-106">Os dados de uso podem ser utilizados para calcular o retorno sobre o investimento, enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões.</span><span class="sxs-lookup"><span data-stu-id="13ed4-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="13ed4-107">Use o procedimento a seguir para habilitar a CDR para toda a sua organização ou cada site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="13ed4-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="13ed4-108">Para habilitar a CDR, você deve configurar o monitoramento e um banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="13ed4-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="13ed4-109">Para obter detalhes, consulte [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span><span class="sxs-lookup"><span data-stu-id="13ed4-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="13ed4-110">Para habilitar a CDR com o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="13ed4-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="13ed4-111">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="13ed4-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="13ed4-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="13ed4-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="13ed4-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.</span><span class="sxs-lookup"><span data-stu-id="13ed4-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="13ed4-114">Na página **Registro de Detalhes de** Chamada, clique no site apropriado da tabela, clique em **Ação** e em **Habilitar CDR**.</span><span class="sxs-lookup"><span data-stu-id="13ed4-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13ed4-115">A CDR está habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="13ed4-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="13ed4-116">Habilitando a CDR usando Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="13ed4-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="13ed4-117">Você pode habilitar a CDR usando Windows PowerShell e o cmdlet **Set-CsCdrConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="13ed4-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="13ed4-118">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13ed4-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="13ed4-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="13ed4-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="13ed4-120">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="13ed4-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="13ed4-121">Para habilitar a CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="13ed4-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="13ed4-122">Para desabilitar o CDR, de definir o parâmetro EnableCDR como True ($True).</span><span class="sxs-lookup"><span data-stu-id="13ed4-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="13ed4-123">Para desabilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="13ed4-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="13ed4-124">Para desabilitar o CDR, de definir o parâmetro EnableCDR como False ($False).</span><span class="sxs-lookup"><span data-stu-id="13ed4-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="13ed4-125">Desabilitar a CDR não desinstala o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="13ed4-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="13ed4-126">Ele pausa a coleção e o armazenamento de dados cdr.</span><span class="sxs-lookup"><span data-stu-id="13ed4-126">It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="13ed4-127">Para usar um único comando para habilitar o CDR em vários locais</span><span class="sxs-lookup"><span data-stu-id="13ed4-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="13ed4-128">Esse comando habilita a CDR para todas as configurações de CDR em uso na sua organização.</span><span class="sxs-lookup"><span data-stu-id="13ed4-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="13ed4-129">Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="13ed4-129">For more information, see the help topic for the [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="13ed4-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="13ed4-130">See also</span></span>

[<span data-ttu-id="13ed4-131">Planejamento do monitoramento</span><span class="sxs-lookup"><span data-stu-id="13ed4-131">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="13ed4-132">Implantando o monitoramento</span><span class="sxs-lookup"><span data-stu-id="13ed4-132">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)