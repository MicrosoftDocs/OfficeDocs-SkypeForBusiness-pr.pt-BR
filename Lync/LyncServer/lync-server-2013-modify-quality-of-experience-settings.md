---
title: 'Lync Server 2013: modificar configurações de qualidade da experiência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da75a0be0e2f6aadd6cca95b19134f0653b3c9c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534339"
---
# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="682e5-102">Modificar as configurações de qualidade da experiência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="682e5-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="682e5-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="682e5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="682e5-p101">Por padrão, os dados de QoE (Qualidade de Experiência) são limpos após 60 dias. Você pode usar as configurações da página **Dados de Qualidade de Experiência** para manter os dados por um período maior ou menor. Se você desabilitar a QoE, os dados capturados antes da habilitação da QoE também ficarão sujeitos à limpeza.</span><span class="sxs-lookup"><span data-stu-id="682e5-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="682e5-p102">Você deve configurar o registro de detalhes de chamadas (CDR) e a QoE para manter dados durante o mesmo número de dias. Cada chamada nos relatórios de detalhes de chamadas (CDRs), disponíveis na página inicial de relatórios do Monitoring Reports, inclui informações de CDR e QoE. Se o momento da limpeza para o CDR e a QoE for diferente, algumas chamadas podem incluir somente dados de CDR, enquanto outros podem incluir somente dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="682e5-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="682e5-110">O procedimento a seguir descreve como definir as configurações de limpeza para dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="682e5-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="682e5-111">Para especificar a retenção de dados de QoE usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="682e5-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="682e5-112">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="682e5-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="682e5-113">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="682e5-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="682e5-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="682e5-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="682e5-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="682e5-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="682e5-116">Na barra de navegação à esquerda, clique em **Monitoramento e Arquivamento** e clique em **Dados de Qualidade de Experiência**.</span><span class="sxs-lookup"><span data-stu-id="682e5-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="682e5-117">Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="682e5-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="682e5-118">Para ativar a limpeza, selecione **Habilitar a Limpeza do QoE**.</span><span class="sxs-lookup"><span data-stu-id="682e5-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="682e5-119">Em **Manter QoE por um período máximo de (dias)** selecione o número máximo de dias durante os quais dados de QoE devem ser mantidos.
</span><span class="sxs-lookup"><span data-stu-id="682e5-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="682e5-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="682e5-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="682e5-121">Especificar a retenção de QoE usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="682e5-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="682e5-122">Você pode criar configurações de retenção de QoE usando o Windows PowerShell e o cmdlet **set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="682e5-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="682e5-123">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="682e5-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="682e5-124">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="682e5-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="682e5-125">Para especificar a retenção de QoE de um local específico</span><span class="sxs-lookup"><span data-stu-id="682e5-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="682e5-126">Esse comando permite limpar os dados de QoE do site da Redmond e configura o site para manter os dados de QoE por 20 dias.</span><span class="sxs-lookup"><span data-stu-id="682e5-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="682e5-127">Para especificar a retenção de QoE de vários locais</span><span class="sxs-lookup"><span data-stu-id="682e5-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="682e5-128">Esse comando configura a retenção de QoE para todos as configurações de QoE em uso em uma organização.</span><span class="sxs-lookup"><span data-stu-id="682e5-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="682e5-129">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="682e5-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="682e5-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="682e5-130">See Also</span></span>


[<span data-ttu-id="682e5-131">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="682e5-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

