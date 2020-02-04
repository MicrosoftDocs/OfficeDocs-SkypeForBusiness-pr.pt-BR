---
title: 'Lync Server 2013: publicar alterações pendentes na configuração de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="3e49d-102">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e49d-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e49d-103">_**Tópico da última modificação:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="3e49d-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="3e49d-104">Após fazer alterações em qualquer uma das definições de configuração nas páginas do grupo **Roteamento de Voz**, execute este procedimento para examinar, publicar ou cancelar as alterações pendentes.</span><span class="sxs-lookup"><span data-stu-id="3e49d-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e49d-105">Certifique-se de que somente um usuário por vez modifique as definições de configurações do Roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="3e49d-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="3e49d-p101">Todas as alterações pendentes devem ser publicadas ao mesmo tempo, executando o comando <STRONG>Confirmar todos</STRONG>. Não é possível publicar seletivamente as alterações pendentes. Antes de publicar as alterações pendentes, execute o comando <STRONG>Revisar alterações não confirmadas</STRONG> e cancele qualquer alteração de configuração que não deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="3e49d-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="3e49d-109">Se você navegar longe das páginas do grupo <STRONG>Roteamento de voz</STRONG> antes de confirmar as alterações pendentes, todas as alterações pendentes serão perdida.</span><span class="sxs-lookup"><span data-stu-id="3e49d-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="3e49d-110">No entanto, é possível exportar a configuração atual (incluindo quaisquer alterações pendentes) para um arquivo de configuração de voz e, em seguida, importar e publicar a configuração atualizada.</span><span class="sxs-lookup"><span data-stu-id="3e49d-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="3e49d-111">Para obter detalhes, consulte <A href="lync-server-2013-export-a-voice-route-configuration-file.md">exportar um arquivo de configuração de rota de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e49d-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="3e49d-112">Para revisar, publicar ou cancelar as alterações de configuração do roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="3e49d-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="3e49d-113">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3e49d-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3e49d-114">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3e49d-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3e49d-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e49d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e49d-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e49d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e49d-117">Na barra de navegação esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="3e49d-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="3e49d-118">Faça as alterações de configuração que deseja para as configurações em cada página do grupo **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="3e49d-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="3e49d-119">Para revisar as alterações pendentes sem publicá-las, selecione **Revisar alterações não confirmadas** no menu **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3e49d-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="3e49d-120">Se você deseja cancelar qualquer alteração pendente, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3e49d-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="3e49d-121">Selecione **Cancelar todas as alterações não confirmadas** no menu **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3e49d-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="3e49d-122">Navegue até a guia da página **Roteamento de voz** que possui as alterações pendente que deseja cancelar, selecione o item com as alterações pendentes, clique em **Confirmar** e em **Cancelar alterações selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="3e49d-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="3e49d-123">Após revisar todas as alterações pendentes e cancelar qualquer uma que não deseja publicar, clique em **Confirmar** e em **Confirmar todas**.</span><span class="sxs-lookup"><span data-stu-id="3e49d-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="3e49d-124">Na caixa de diálogo **Definições da configuração de voz não confirmadas** que exibe uma lista de todas as alterações pendentes, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e49d-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="3e49d-125">Quando o painel de controle do Lync Server tiver confirmado as alterações, a mensagem de **configuração de roteamento de voz publicada com êxito** será exibida.</span><span class="sxs-lookup"><span data-stu-id="3e49d-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

