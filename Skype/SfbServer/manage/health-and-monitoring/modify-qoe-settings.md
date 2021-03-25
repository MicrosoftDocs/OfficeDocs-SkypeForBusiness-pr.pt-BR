---
title: Modificar configurações de Qualidade de Experiência no Skype for Business Server
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Resumo: Saiba como especificar a retenção de dados QoE no Skype for Business Server.'
ms.openlocfilehash: cba8b2b98aa809c0583ad7323ff846e654ca9ace
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118610"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="3dbfe-103">Modificar configurações de Qualidade de Experiência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3dbfe-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="3dbfe-104">**Resumo:** Saiba como especificar a retenção de dados QoE no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="3dbfe-p101">Por padrão, os dados de QoE (Qualidade de Experiência) são limpos após 60 dias. Você pode usar as configurações da página **Dados de Qualidade de Experiência** para manter os dados por um período maior ou menor. Se você desabilitar a QoE, os dados capturados antes da habilitação da QoE também ficarão sujeitos à limpeza.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="3dbfe-p102">Você deve configurar o registro de detalhes de chamadas (CDR) e a QoE para manter dados durante o mesmo número de dias. Cada chamada nos relatórios de detalhes de chamadas (CDRs), disponíveis na página inicial de relatórios do Monitoring Reports, inclui informações de CDR e QoE. Se o momento da limpeza para o CDR e a QoE for diferente, algumas chamadas podem incluir somente dados de CDR, enquanto outros podem incluir somente dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="3dbfe-111">O procedimento a seguir descreve como definir as configurações de limpeza para dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3dbfe-112">Para especificar a retenção de dados QoE usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3dbfe-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="3dbfe-113">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3dbfe-114">Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-114">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="3dbfe-115">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="3dbfe-116">Na barra de navegação à esquerda, clique em **Monitoramento e Arquivamento** e clique em **Dados de Qualidade de Experiência**.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="3dbfe-117">Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="3dbfe-118">Para ativar a limpeza, selecione **Habilitar a Limpeza do QoE**.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="3dbfe-119">Em **Manter QoE por um período máximo de (dias)** selecione o número máximo de dias durante os quais dados de QoE devem ser mantidos.
</span><span class="sxs-lookup"><span data-stu-id="3dbfe-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="3dbfe-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3dbfe-121">Especificando a retenção de QoE usando Windows PowerShell Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3dbfe-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3dbfe-122">Você pode criar configurações de retenção de QoE usando Windows PowerShell e o cmdlet **Set-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="3dbfe-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="3dbfe-123">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3dbfe-124">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="3dbfe-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3dbfe-125">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="3dbfe-126">Para especificar a retenção de QoE de um local específico</span><span class="sxs-lookup"><span data-stu-id="3dbfe-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="3dbfe-127">Esse comando permite limpar os dados de QoE do site da Redmond e configura o site para manter os dados de QoE por 20 dias.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="3dbfe-128">Para especificar a retenção de QoE de vários locais</span><span class="sxs-lookup"><span data-stu-id="3dbfe-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="3dbfe-129">Esse comando configura a retenção de QoE para todos as configurações de QoE em uso em uma organização.</span><span class="sxs-lookup"><span data-stu-id="3dbfe-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="3dbfe-130">Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3dbfe-130">For more information, see the help topic for the [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="3dbfe-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="3dbfe-131">See also</span></span>

[<span data-ttu-id="3dbfe-132">Implantando o monitoramento</span><span class="sxs-lookup"><span data-stu-id="3dbfe-132">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)