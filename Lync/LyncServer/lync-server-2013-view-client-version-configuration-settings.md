---
title: 'Lync Server 2013: Exibir definições de configuração de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4213008c20181f7525c7cf62eb316820abe66f3f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6e691-102">Exibir as definições de configuração de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e691-102">View client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e691-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6e691-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6e691-104">As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="6e691-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="6e691-105">A configuração de versão do cliente global é instalada com o Lync Server 2013 e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor.</span><span class="sxs-lookup"><span data-stu-id="6e691-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="6e691-106">Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon.</span><span class="sxs-lookup"><span data-stu-id="6e691-106">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="6e691-107">Você pode exibir as definições de configuração de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e691-107">You can view client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e691-108">Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.</span><span class="sxs-lookup"><span data-stu-id="6e691-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="6e691-109">Para exibir as definições de configuração de versão do cliente usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6e691-109">To view client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6e691-110">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6e691-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6e691-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e691-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6e691-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6e691-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6e691-113">Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração da versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="6e691-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="6e691-114">Clique duas vezes no nome da configuração de versão do cliente que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="6e691-114">Double-click the name of the client version configuration you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6e691-115">Exibindo as definições de configuração de versão do cliente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e691-115">Viewing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6e691-116">Você pode exibir as definições de configuração de versão do cliente usando o cmdlet **Get-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6e691-116">You can view client version configuration settings by using the **Get-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="6e691-117">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e691-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6e691-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="6e691-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-configuration-information"></a><span data-ttu-id="6e691-119">Para exibir informações de configuração de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="6e691-119">To view client version configuration information</span></span>

  - <span data-ttu-id="6e691-120">Para exibir informações sobre todas as definições de configuração de versão do cliente, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="6e691-120">To view information about all your client version configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionConfiguration
    
    <span data-ttu-id="6e691-121">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e691-121">That will return information similar to this:</span></span>
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

<span data-ttu-id="6e691-122">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="6e691-122">For details, see the Help topic for the [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

