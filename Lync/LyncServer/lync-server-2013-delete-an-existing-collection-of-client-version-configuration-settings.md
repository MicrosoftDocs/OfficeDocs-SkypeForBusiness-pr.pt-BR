---
title: Excluir um conjunto existente de definições de configuração de versão do cliente
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
ms.openlocfilehash: c1709d783bf47537cec25f06232d5782975444f6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="59977-102">Excluir um conjunto existente de definições de configuração de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59977-102">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59977-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="59977-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="59977-104">Se você deseja remover as definições de configuração do cliente que foram previamente configuradas para um site, você pode remover as configurações do painel de controle do Lync Server 2013 ou do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59977-104">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="59977-105">Para remover as definições de configuração do cliente usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="59977-105">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="59977-106">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59977-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="59977-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59977-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="59977-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="59977-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="59977-109">Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração da versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="59977-109">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="59977-110">Selecione o site, clique em **Editar**, em **excluir**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="59977-110">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="59977-111">Removendo as definições de configuração de versão do cliente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59977-111">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="59977-112">Você pode excluir as definições de configuração de versão do cliente usando o cmdlet **Remove-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="59977-112">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="59977-113">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59977-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="59977-114">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="59977-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="59977-115">Para remover um conjunto especificado de definições de configuração de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="59977-115">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="59977-116">O comando a seguir remove as definições de configuração de versão do cliente aplicadas ao site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="59977-116">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="59977-117">Para remover todas as definições de configuração de versão do cliente aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="59977-117">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="59977-118">Este comando Remove todas as definições de configuração de versão do cliente configuradas no escopo do site:</span><span class="sxs-lookup"><span data-stu-id="59977-118">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="59977-119">Para remover todas as definições de configuração de versão do cliente com base no valor da propriedade DefaultAction</span><span class="sxs-lookup"><span data-stu-id="59977-119">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="59977-120">E este comando Remove todas as definições de configuração de versão do cliente em que a ação padrão foi definida como "bloquear":</span><span class="sxs-lookup"><span data-stu-id="59977-120">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="59977-121">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="59977-121">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

