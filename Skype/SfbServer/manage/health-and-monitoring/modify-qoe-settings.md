---
title: Modificar as configurações de qualidade da experiência no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Resumo: Saiba como especificar a retenção de dados de QoE em Skype para Business Server.'
ms.openlocfilehash: 743f3df6f58392e7d9107be9ae4c9313ef7a6781
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23243450"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="fcfb5-103">Modificar as configurações de qualidade da experiência no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="fcfb5-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="fcfb5-104">**Resumo:** Saiba como especificar a retenção de dados de QoE em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="fcfb5-p101">Por padrão, os dados de QoE (Qualidade de Experiência) são limpos após 60 dias. Você pode usar as configurações da página **Dados de Qualidade de Experiência** para manter os dados por um período maior ou menor. Se você desabilitar a QoE, os dados capturados antes da habilitação da QoE também ficarão sujeitos à limpeza.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="fcfb5-p102">Você deve configurar o registro de detalhes de chamadas (CDR) e a QoE para manter dados durante o mesmo número de dias. Cada chamada nos relatórios de detalhes de chamadas (CDRs), disponíveis na página inicial de relatórios do Monitoring Reports, inclui informações de CDR e QoE. Se o momento da limpeza para o CDR e a QoE for diferente, algumas chamadas podem incluir somente dados de CDR, enquanto outros podem incluir somente dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="fcfb5-111">O procedimento a seguir descreve como definir as configurações de limpeza para dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fcfb5-112">Para especificar a retenção de dados de QoE usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="fcfb5-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="fcfb5-113">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="fcfb5-114">Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-114">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="fcfb5-115">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="fcfb5-116">Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="fcfb5-117">Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="fcfb5-118">Para ativar a limpeza, selecione **Habilitar a Limpeza do QoE**.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="fcfb5-119">Em **Manter QoE por um período máximo de (dias)**, selecione o número máximo de dias durante os quais dados de QoE devem ser mantidos.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="fcfb5-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fcfb5-121">Especificar a retenção de QoE usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcfb5-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fcfb5-122">Você pode criar configurações de retenção de QoE usando o Windows PowerShell e o cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fcfb5-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="fcfb5-123">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fcfb5-124">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="fcfb5-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="fcfb5-125">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="fcfb5-126">Para especificar a retenção de QoE de um local específico</span><span class="sxs-lookup"><span data-stu-id="fcfb5-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="fcfb5-127">Esse comando permite limpar os dados de QoE do site da Redmond e configura o site para manter os dados de QoE por 20 dias.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="fcfb5-128">Para especificar a retenção de QoE de vários locais</span><span class="sxs-lookup"><span data-stu-id="fcfb5-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="fcfb5-129">Esse comando configura a retenção de QoE para todos as configurações de QoE em uso em uma organização.</span><span class="sxs-lookup"><span data-stu-id="fcfb5-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="fcfb5-130">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="fcfb5-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcfb5-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fcfb5-131">See also</span></span>

[<span data-ttu-id="fcfb5-132">Implantando o Monitoring</span><span class="sxs-lookup"><span data-stu-id="fcfb5-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)