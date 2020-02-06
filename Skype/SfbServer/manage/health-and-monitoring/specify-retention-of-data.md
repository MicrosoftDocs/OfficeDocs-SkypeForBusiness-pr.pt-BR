---
title: Especificar a retenção de dados de CDR no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Resumo: saiba como gerenciar dados de registro de detalhes de chamadas (CDR) para o Skype for Business Server.'
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817670"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="c8cbd-103">Especificar a retenção de dados de CDR no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8cbd-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="c8cbd-104">**Resumo:** Saiba como gerenciar dados de registro de detalhes de chamadas (CDR) para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="c8cbd-p101">Por padrão, os dados de CDR (registro de detalhes das chamadas) são purgados após 60 dias. É possível usar as configurações da página **Registro de Detalhes das Chamadas** para manter os dados por um período maior ou menor. Se você desabilitar o CDR, os dados que foram capturados antes da desabilitação do CDR também poderão ser purgados.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8cbd-p102">Você deve configurar o CDR e a QoE (Qualidade da Experiência) para reter os dados durante o mesmo número de dias. Cada chamada nos CDRs (relatórios de detalhes de chamada), disponível na página da web de Relatórios do Monitoring Serve, inclui informações de CDR e QoE. Se a duração da limpeza de CDR e QoE for diferente, algumas chamadas poderão incluir apenas dados de CDR, enquanto outras poderão incluir apenas dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="c8cbd-111">Use o procedimento a seguir para definir as configurações de limpeza de dados de CDR.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="c8cbd-112">Para especificar a retenção de dados de CDR</span><span class="sxs-lookup"><span data-stu-id="c8cbd-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="c8cbd-113">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .</span><span class="sxs-lookup"><span data-stu-id="c8cbd-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c8cbd-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c8cbd-115">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="c8cbd-116">Na página **Registro de Detalhes de Chamada**, clique no site apropriado na tabela, clique em **Editar** e em **Mostrar Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="c8cbd-117">Para ativar a limpeza, selecione **Habilitar limpeza CDRs**.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="c8cbd-118">Em **Manter CDRs por um período máximo (dias):** selecione o número máximo de dias que os registros de detalhes de chamada devem ser retidos.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="c8cbd-119">Em **Manter dados de relatório de erros por um período máximo de (dias):** selecione o número máximo de dias que os relatórios de erros devem ser retidos.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="c8cbd-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8cbd-121">Especificando a retenção de CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8cbd-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c8cbd-122">Você pode criar configurações de retenção de CDR usando o Windows PowerShell e o cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="c8cbd-123">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8cbd-124">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="c8cbd-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c8cbd-125">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="c8cbd-126">Para especificar a retenção de CDR para um local específico</span><span class="sxs-lookup"><span data-stu-id="c8cbd-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="c8cbd-127">Este comando habilita a exclusão de dados CDR para o local Redmond e configura o local para manter os dados CDR e os dados do relatório de erro por 20 dias.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="c8cbd-128">Para especificar a retenção CDR para vários locais</span><span class="sxs-lookup"><span data-stu-id="c8cbd-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="c8cbd-129">Este comando configura a retenção CDR para todas as definições de configuração CDR em uso em uma organização.</span><span class="sxs-lookup"><span data-stu-id="c8cbd-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="c8cbd-130">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c8cbd-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8cbd-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="c8cbd-131">See also</span></span>

[<span data-ttu-id="c8cbd-132">Registro de detalhes de chamadas (CDR) no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8cbd-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
