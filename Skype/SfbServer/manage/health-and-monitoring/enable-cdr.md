---
title: Habilitar o registro de detalhes das chamadas no Skype for Business Server
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
description: 'Resumo: Saiba como habilitar registros cdr (registro de detalhes das chamadas) no Skype for Business Server.'
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816881"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="4d5a0-103">Habilitar o registro de detalhes das chamadas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d5a0-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="4d5a0-104">**Resumo:** Saiba como habilitar registros cdr (registro de detalhes das chamadas) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="4d5a0-105">O CDR (registro de detalhes das chamadas) registra informações de uso e diagnóstico sobre atividades ponto a ponto, incluindo mensagens de instância, chamadas VoIP, compartilhamento de aplicativos, transferência de arquivos e reuniões.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="4d5a0-106">Os dados de uso podem ser utilizados para calcular o retorno sobre o investimento, enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="4d5a0-107">Use o procedimento a seguir para habilitar o CDR para toda a organização ou para cada site da organização.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="4d5a0-108">Para habilitar o CDR, você deve configurar o monitoramento e um banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="4d5a0-109">Para obter detalhes, consulte [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="4d5a0-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="4d5a0-110">Para habilitar o CDR com o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4d5a0-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4d5a0-111">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="4d5a0-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="4d5a0-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="4d5a0-114">Na página **Registro de Detalhes das** Chamada, clique no site apropriado na tabela, clique em Ação e em **Habilitar CDR.** </span><span class="sxs-lookup"><span data-stu-id="4d5a0-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4d5a0-115">O CDR é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4d5a0-116">Habilitando o CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d5a0-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4d5a0-117">Você pode habilitar o CDR usando o Windows PowerShell e o cmdlet **Set-CsCdrConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="4d5a0-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="4d5a0-118">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4d5a0-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="4d5a0-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4d5a0-120">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="4d5a0-121">Para habilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="4d5a0-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="4d5a0-122">Para desabilitar o CDR, de definir o parâmetro EnableCDR como True ($True).</span><span class="sxs-lookup"><span data-stu-id="4d5a0-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="4d5a0-123">Para desabilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="4d5a0-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="4d5a0-124">Para desabilitar o CDR, de definir o parâmetro EnableCDR como False ($False).</span><span class="sxs-lookup"><span data-stu-id="4d5a0-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="4d5a0-125">Desabilitar o CDR não desinstala o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="4d5a0-126">Ele pausa a coleta e o armazenamento de dados de CDR.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-126">It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="4d5a0-127">Para usar um único comando para habilitar o CDR em vários locais</span><span class="sxs-lookup"><span data-stu-id="4d5a0-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="4d5a0-128">Este comando habilita o CDR para todas as definições de configuração de CDR em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="4d5a0-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="4d5a0-129">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4d5a0-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d5a0-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d5a0-130">See also</span></span>

[<span data-ttu-id="4d5a0-131">Planejamento do monitoramento</span><span class="sxs-lookup"><span data-stu-id="4d5a0-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="4d5a0-132">Implantando o monitoramento</span><span class="sxs-lookup"><span data-stu-id="4d5a0-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
