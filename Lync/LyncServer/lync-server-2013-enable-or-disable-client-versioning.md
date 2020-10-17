---
title: 'Lync Server 2013: habilitar ou desabilitar o controle de versão do cliente'
description: 'Lync Server 2013: habilitar ou desabilitar o controle de versão do cliente.'
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
ms.openlocfilehash: 0bbd190e827e028efc37365c3cd8ecab16b35dac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546617"
---
# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="2a73a-103">Habilitar ou desabilitar o controle de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a73a-103">Enable or disable client versioning in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a73a-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2a73a-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2a73a-105">As definições de configuração de versão do cliente são usadas para ativar ou desativar o controle de versão do cliente, globalmente ou para sites específicos.</span><span class="sxs-lookup"><span data-stu-id="2a73a-105">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="2a73a-106">A configuração de versão do cliente global é instalada com o Lync Server 2013 e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor.</span><span class="sxs-lookup"><span data-stu-id="2a73a-106">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="2a73a-107">Quando a configuração global estiver habilitada, todas as políticas de versão do cliente que estiverem em vigor serão efetivadas quando os usuários tentarem fazer logon.</span><span class="sxs-lookup"><span data-stu-id="2a73a-107">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="2a73a-108">Você pode desabilitar a configuração de versão do cliente global se não quiser que qualquer controle de versão do cliente ocorra.</span><span class="sxs-lookup"><span data-stu-id="2a73a-108">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="2a73a-109">Você pode habilitar ou desabilitar o controle de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a73a-109">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a73a-110">Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.</span><span class="sxs-lookup"><span data-stu-id="2a73a-110">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="2a73a-111">Para habilitar ou desabilitar a controle de versão do cliente usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="2a73a-111">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2a73a-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2a73a-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2a73a-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a73a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2a73a-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2a73a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2a73a-115">Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração da versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="2a73a-115">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="2a73a-116">Faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2a73a-116">Do the following:</span></span>
    
      - <span data-ttu-id="2a73a-117">Para habilitar ou desabilitar globalmente o controle de versão do cliente, clique duas vezes na configuração **global** e modifique as configurações.</span><span class="sxs-lookup"><span data-stu-id="2a73a-117">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="2a73a-118">Para habilitar ou desabilitar o controle de versão de cliente para um site específico, clique em **novo**, selecione o site, clique em **OK**e modifique as configurações do site.</span><span class="sxs-lookup"><span data-stu-id="2a73a-118">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2a73a-119">Habilitar ou desabilitar o controle de versão do cliente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a73a-119">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2a73a-120">Você pode habilitar ou desabilitar o controle de versão do cliente usando o cmdlet **set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2a73a-120">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="2a73a-121">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a73a-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2a73a-122">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="2a73a-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="2a73a-123">Para habilitar o controle de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="2a73a-123">To enable client versioning</span></span>

  - <span data-ttu-id="2a73a-124">Você pode habilitar o controle de versão do cliente definindo a propriedade **Enabled** como True ($true).</span><span class="sxs-lookup"><span data-stu-id="2a73a-124">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="2a73a-125">Para desabilitar o controle de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="2a73a-125">To disable client versioning</span></span>

  - <span data-ttu-id="2a73a-126">Você pode desabilitar o controle de versão do cliente definindo a propriedade **Enabled** como False ($false).</span><span class="sxs-lookup"><span data-stu-id="2a73a-126">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="2a73a-127">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="2a73a-127">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

