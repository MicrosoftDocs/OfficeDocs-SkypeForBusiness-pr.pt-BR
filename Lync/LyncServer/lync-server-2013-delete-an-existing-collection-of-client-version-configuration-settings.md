---
title: Excluir uma coleção existente de definições de configuração de versão do cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3015358c27786b03b505e580acd599e26d4f3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4fef6-102">Excluir uma coleção existente de definições de configuração de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fef6-102">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fef6-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4fef6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4fef6-104">Se quiser remover as configurações de configuração do cliente que foram configuradas anteriormente para um site, você pode remover as configurações do painel de controle do Lync Server 2013 ou do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fef6-104">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="4fef6-105">Para remover as definições de configuração do cliente usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="4fef6-105">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4fef6-106">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="4fef6-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4fef6-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4fef6-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fef6-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4fef6-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fef6-109">Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="4fef6-109">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="4fef6-110">Selecione o site, clique em **Editar**, clique em **excluir**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fef6-110">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4fef6-111">Como remover as configurações de versão do cliente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fef6-111">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4fef6-112">Você pode excluir as definições de configuração de versão do cliente usando o cmdlet **Remove-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4fef6-112">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="4fef6-113">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fef6-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4fef6-114">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="4fef6-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="4fef6-115">Para remover uma coleção especificada de definições de configuração de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="4fef6-115">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="4fef6-116">O comando a seguir remove as definições de configuração de versão do cliente aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="4fef6-116">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="4fef6-117">Para remover todas as definições de configuração de versão do cliente aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="4fef6-117">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="4fef6-118">Esse comando Remove todas as definições de configuração de versão do cliente definidas no escopo do site:</span><span class="sxs-lookup"><span data-stu-id="4fef6-118">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="4fef6-119">Para remover todas as definições de configuração de versão do cliente com base no valor da propriedade DefaultAction</span><span class="sxs-lookup"><span data-stu-id="4fef6-119">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="4fef6-120">E esse comando Remove todas as configurações de versão do cliente em que a ação padrão foi definida como "bloquear":</span><span class="sxs-lookup"><span data-stu-id="4fef6-120">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="4fef6-121">Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="4fef6-121">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

