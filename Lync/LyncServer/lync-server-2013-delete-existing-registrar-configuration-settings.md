---
title: 'Lync Server 2013: excluir definições de configuração de registrador existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960d0dd055ccf2f380b1ebf8124432da8daf6563
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8baf1-102">Excluir configurações de registrador existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8baf1-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8baf1-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8baf1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8baf1-104">Siga estas etapas para excluir um registrador.</span><span class="sxs-lookup"><span data-stu-id="8baf1-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="8baf1-105">Para excluir as definições de configuração do Registrador</span><span class="sxs-lookup"><span data-stu-id="8baf1-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="8baf1-106">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8baf1-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="8baf1-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8baf1-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8baf1-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8baf1-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8baf1-109">Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="8baf1-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="8baf1-110">Na página **Registrador Avançado** e no campo de pesquisa, digite todo ou parte do nome do Registrador Avançado que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="8baf1-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="8baf1-111">Na lista, clique no Registrador Avançado desejado, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="8baf1-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="8baf1-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8baf1-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8baf1-113">Como remover as configurações de registrador usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8baf1-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8baf1-114">Você pode excluir as definições de configuração do registrador usando o Windows PowerShell e o cmdlet **Remove-CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8baf1-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="8baf1-115">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8baf1-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8baf1-116">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="8baf1-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="8baf1-117">Para remover um conjunto específico de configurações de segurança do Registrador</span><span class="sxs-lookup"><span data-stu-id="8baf1-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="8baf1-118">O seguinte comando remove as configurações de segurança do Registrador aplicadas ao servidor de borda atl-edge-011.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="8baf1-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="8baf1-119">Para remover todas as configurações de segurança do Registrador aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="8baf1-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="8baf1-120">O seguinte comando remove todas as configurações de segurança do Registrador aplicadas ao serviço registrador:</span><span class="sxs-lookup"><span data-stu-id="8baf1-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="8baf1-121">Para remover todas as configurações de segurança do Registrador que permitem a autenticação de NTLM</span><span class="sxs-lookup"><span data-stu-id="8baf1-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="8baf1-122">O seguinte comando exclui todas as configurações de segurança do Registrador que permite o uso de NTLM para autenticação do cliente:</span><span class="sxs-lookup"><span data-stu-id="8baf1-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="8baf1-123">Para obter detalhes, consulte [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8baf1-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

