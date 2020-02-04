---
title: 'Lync Server 2013: habilitar ou desabilitar o controle de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="1a581-102">Habilitar ou desabilitar o controle de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a581-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a581-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1a581-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1a581-104">As configurações de versão do cliente são usadas para ativar ou desativar o controle de versão do cliente, seja globalmente ou para sites específicos.</span><span class="sxs-lookup"><span data-stu-id="1a581-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="1a581-105">A configuração de versão do cliente global é instalada com o Lync Server 2013 e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor.</span><span class="sxs-lookup"><span data-stu-id="1a581-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="1a581-106">Quando a configuração global estiver habilitada, todas as políticas de versão do cliente que você tiver em vigor entrarão em vigor quando os usuários tentarem fazer logon.</span><span class="sxs-lookup"><span data-stu-id="1a581-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="1a581-107">Você pode desabilitar a configuração de versão do cliente global se não quiser que o controle de versão do cliente ocorra.</span><span class="sxs-lookup"><span data-stu-id="1a581-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="1a581-108">Você pode habilitar ou desabilitar o controle de versão do cliente a partir do painel de controle do Lync Server 2013 ou do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a581-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a581-109">Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.</span><span class="sxs-lookup"><span data-stu-id="1a581-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="1a581-110">Para habilitar ou desabilitar o controle de versão do cliente usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="1a581-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1a581-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1a581-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a581-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a581-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a581-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a581-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a581-114">Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="1a581-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1a581-115">Do the following:</span><span class="sxs-lookup"><span data-stu-id="1a581-115">Do the following:</span></span>
    
      - <span data-ttu-id="1a581-116">Para habilitar ou desabilitar globalmente o controle de versão do cliente, clique duas vezes na configuração **global** e modifique as configurações.</span><span class="sxs-lookup"><span data-stu-id="1a581-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="1a581-117">Para habilitar ou desabilitar o controle de versão do cliente para um site específico, clique em **novo**, selecione o site, clique em **OK**e modifique as configurações do site.</span><span class="sxs-lookup"><span data-stu-id="1a581-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1a581-118">Habilitar ou desabilitar o controle de versão do cliente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a581-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1a581-119">Você pode habilitar ou desabilitar o controle de versão do cliente usando o cmdlet **set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1a581-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="1a581-120">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a581-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1a581-121">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="1a581-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="1a581-122">Para habilitar o controle de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="1a581-122">To enable client versioning</span></span>

  - <span data-ttu-id="1a581-123">Você pode habilitar o controle de versão do cliente definindo a propriedade **Enabled** como True ($true).</span><span class="sxs-lookup"><span data-stu-id="1a581-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="1a581-124">Para desabilitar o controle de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="1a581-124">To disable client versioning</span></span>

  - <span data-ttu-id="1a581-125">Você pode desabilitar o controle de versão do cliente definindo a propriedade **Enabled** como False ($false).</span><span class="sxs-lookup"><span data-stu-id="1a581-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="1a581-126">Para obter detalhes, consulte o tópico da ajuda para o cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1a581-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

