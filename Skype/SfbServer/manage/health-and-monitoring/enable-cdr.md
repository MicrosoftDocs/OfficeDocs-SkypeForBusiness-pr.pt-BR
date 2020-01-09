---
title: Habilitar a gravação de detalhes da chamada no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumo: saiba como habilitar registros CDR (registro de detalhes de chamadas) no Skype for Business Server.'
ms.openlocfilehash: 3474a82bfc9ed8e8bad954bb91346989d9181465
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992941"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="1f16d-103">Habilitar a gravação de detalhes da chamada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1f16d-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="1f16d-104">**Resumo:** Saiba como habilitar registros CDR (registro de detalhes de chamadas) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1f16d-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="1f16d-p101">O CDR (registro de detalhes das chamadas) registra informações de utilização e diagnóstico sobre atividades ponto a ponto, incluindo serviço de mensagens instantâneas, chamadas do protocolo VoIP, compartilhamento de aplicativos, transferência de arquivos e reuniões. Os dados de uso podem ser utilizados para calcular o ROI (retorno sobre o investimento), enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões.</span><span class="sxs-lookup"><span data-stu-id="1f16d-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="1f16d-107">Use o procedimento a seguir para ativar o CDR para a organização inteira ou para cada local da organização.</span><span class="sxs-lookup"><span data-stu-id="1f16d-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="1f16d-p102">Para habilitar o CDR, é preciso configurar o monitoramento e o banco de dados de monitoramento. Para obter detalhes, consulte [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="1f16d-p102">In order to enable CDR you must configure monitoring and a monitoring database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="1f16d-110">Para habilitar CDR com o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1f16d-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1f16d-111">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .</span><span class="sxs-lookup"><span data-stu-id="1f16d-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="1f16d-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1f16d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1f16d-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes das Chamadas**.</span><span class="sxs-lookup"><span data-stu-id="1f16d-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="1f16d-114">Na página **Registro de Detalhes das Chamadas**, clique no local apropriado na tabela, em **Ação** e em **Habilitar CDR**.</span><span class="sxs-lookup"><span data-stu-id="1f16d-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f16d-115">O CDR é ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="1f16d-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1f16d-116">Como habilitar o CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f16d-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1f16d-117">Você pode habilitar o CDR usando o Windows PowerShell e o cmdlet **set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1f16d-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="1f16d-118">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f16d-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1f16d-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="1f16d-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1f16d-120">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1f16d-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="1f16d-121">Para habilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="1f16d-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="1f16d-122">Para desabilitar o CDR, defina o parâmetro EnableCDR como Verdadeiro ($True).</span><span class="sxs-lookup"><span data-stu-id="1f16d-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="1f16d-123">Para desabilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="1f16d-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="1f16d-p104">Para desabilitar o CDR, defina o parâmetro EnableCDR como Falso ($False). Desabilitar o CDR não desinstalará o monitoramento, apenas pausará a coleta e o armazenamento de dados de CDR.</span><span class="sxs-lookup"><span data-stu-id="1f16d-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="1f16d-127">Para usar um único comando para habilitar o CDR em vários locais</span><span class="sxs-lookup"><span data-stu-id="1f16d-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="1f16d-128">Este comando habilita o CDR para todas as configurações do CDR em uso na sua organização.</span><span class="sxs-lookup"><span data-stu-id="1f16d-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="1f16d-129">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1f16d-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f16d-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="1f16d-130">See also</span></span>

[<span data-ttu-id="1f16d-131">Planejando o monitoramento</span><span class="sxs-lookup"><span data-stu-id="1f16d-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="1f16d-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="1f16d-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
