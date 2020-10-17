---
title: 'Lync Server 2013: excluir definições de configuração do registrador existente'
description: 'Lync Server 2013: excluir as definições de configuração do registrador existentes.'
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
ms.openlocfilehash: b625b97724edf0ecf8928ec31d89a6166230c4c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555407"
---
# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b313b-103">Excluir as definições de configuração do registrador existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b313b-103">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b313b-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b313b-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b313b-105">Siga estas etapas para excluir um registrador.</span><span class="sxs-lookup"><span data-stu-id="b313b-105">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="b313b-106">Para excluir as definições de configuração do registrador</span><span class="sxs-lookup"><span data-stu-id="b313b-106">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="b313b-107">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b313b-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b313b-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b313b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b313b-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b313b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b313b-110">Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="b313b-110">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="b313b-111">Na página **registrador** e, no campo de pesquisa, digite todo ou parte do nome do registrador que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="b313b-111">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="b313b-112">Na lista, clique no registrador desejado, clique em **Editar**e em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="b313b-112">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="b313b-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b313b-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b313b-114">Removendo definições de configuração do registrador usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b313b-114">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b313b-115">Você pode excluir as definições de configuração do registrador usando o Windows PowerShell e o cmdlet **Remove-CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b313b-115">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="b313b-116">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b313b-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b313b-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="b313b-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="b313b-118">Para remover um conjunto específico de configurações de segurança do registrador</span><span class="sxs-lookup"><span data-stu-id="b313b-118">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="b313b-119">O comando a seguir remove as configurações de segurança do registrador aplicadas ao servidor de borda atl-edge-011.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b313b-119">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="b313b-120">Para remover todas as configurações de segurança do registrador aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="b313b-120">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="b313b-121">O comando a seguir remove todas as configurações de segurança do registrador aplicadas ao serviço registrador:</span><span class="sxs-lookup"><span data-stu-id="b313b-121">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="b313b-122">Para remover todas as configurações de segurança do registrador que permitem a autenticação NTLM</span><span class="sxs-lookup"><span data-stu-id="b313b-122">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="b313b-123">O comando a seguir exclui todas as configurações de segurança do registrador que permitem o uso de NTLM para autenticação do cliente:</span><span class="sxs-lookup"><span data-stu-id="b313b-123">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="b313b-124">Para obter detalhes, consulte [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span><span class="sxs-lookup"><span data-stu-id="b313b-124">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

