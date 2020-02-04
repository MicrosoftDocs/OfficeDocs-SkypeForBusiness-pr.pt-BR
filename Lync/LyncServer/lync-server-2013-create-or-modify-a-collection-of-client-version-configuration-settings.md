---
title: Criar ou modificar um conjunto de definições de configuração de versão do cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc50696444ddd0602bbf21fd9e05b5bba6eddde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="51c39-102">Criar ou modificar um conjunto de definições de configuração de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51c39-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51c39-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="51c39-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="51c39-104">As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="51c39-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="51c39-105">A configuração de versão do cliente global é instalada com o Lync Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor.</span><span class="sxs-lookup"><span data-stu-id="51c39-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="51c39-106">Você também pode configurar as definições de configuração de versão do cliente para sites individuais.</span><span class="sxs-lookup"><span data-stu-id="51c39-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="51c39-107">Você pode criar ou modificar as definições de configuração de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51c39-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="51c39-108">Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.</span><span class="sxs-lookup"><span data-stu-id="51c39-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="51c39-109">Para criar ou modificar as definições de configuração de versão do cliente usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="51c39-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="51c39-110">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="51c39-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="51c39-111">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="51c39-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="51c39-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="51c39-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="51c39-113">Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="51c39-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="51c39-114">Na página **configuração de versão do cliente** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="51c39-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="51c39-115">Para criar uma nova configuração, clique em **novo**, selecione um site, clique em **OK** nome e atualize as configurações.</span><span class="sxs-lookup"><span data-stu-id="51c39-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="51c39-116">Para modificar uma configuração, selecione a configuração, clique em **Editar**, clique em **Mostrar detalhes**e faça alterações nas configurações.</span><span class="sxs-lookup"><span data-stu-id="51c39-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="51c39-117">Criando ou modificando definições de configuração de versão do cliente usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51c39-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="51c39-118">Você pode criar definições de configuração de versão do cliente usando o cmdlet **New-CsClientVersionConfiguration** e modificá-las usando o cmdlet **set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="51c39-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="51c39-119">Esses cmdlets podem ser executados no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51c39-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="51c39-120">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="51c39-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="51c39-121">Para criar um novo conjunto de definições de configuração de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="51c39-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="51c39-122">O comando a seguir cria uma nova coleção de definições de configuração de versão do cliente aplicada ao site Redmond.</span><span class="sxs-lookup"><span data-stu-id="51c39-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="51c39-123">Neste exemplo, o controle de versão do cliente está desabilitado para o site Redmond.</span><span class="sxs-lookup"><span data-stu-id="51c39-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="51c39-124">Para habilitar o controle de versão do cliente para um site</span><span class="sxs-lookup"><span data-stu-id="51c39-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="51c39-125">Esse comando habilita o controle de versão do cliente para o site Redmond.</span><span class="sxs-lookup"><span data-stu-id="51c39-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="51c39-126">Para desabilitar o controle de versão do cliente em toda a organização</span><span class="sxs-lookup"><span data-stu-id="51c39-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="51c39-127">Neste exemplo, o controle de versão do cliente está desabilitado para todas as definições de configuração de versão do cliente em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="51c39-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="51c39-128">Para obter detalhes, consulte o tópico da ajuda para os cmdlets [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) e [set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="51c39-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

