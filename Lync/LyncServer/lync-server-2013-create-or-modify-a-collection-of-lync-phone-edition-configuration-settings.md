---
title: Criar ou modificar uma coleção de definições de configuração do Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3012ffeeb8dd4559ee05a45dd07becefd099691
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="33628-102">Criar ou modificar uma coleção de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33628-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33628-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="33628-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="33628-104">Ao instalar o Lync Server, você obtém uma coleção global das configurações do Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="33628-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="33628-105">Essas configurações se aplicam a todos os dispositivos que executam o Lync Phone Edition na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="33628-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="33628-106">Você pode alterar essas configurações a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="33628-106">You can change these settings at any time.</span></span> <span data-ttu-id="33628-107">Você também pode configurar um novo conjunto de configurações que se aplicam aos dispositivos em um site específico.</span><span class="sxs-lookup"><span data-stu-id="33628-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="33628-108">As configurações do site têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="33628-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="33628-109">As definições de configuração consistem no nome da coleção, escopo (global ou site), configuração de segurança SIP, nível de log, nível de qualidade do serviço (QoS), configuração de bloqueio de telefone e detalhes do bloqueio por telefone, ou seja, por quanto tempo o número de identificação pessoal do desbloquear ( PIN) deve ser e b) o telefone permanecerá ocioso antes de se bloquear.</span><span class="sxs-lookup"><span data-stu-id="33628-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="33628-110">Para criar um conjunto de definições de configuração do Lync Phone Edition ou editar configurações de uma coleção existente</span><span class="sxs-lookup"><span data-stu-id="33628-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="33628-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="33628-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33628-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33628-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33628-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="33628-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33628-114">Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="33628-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="33628-115">Na página **configuração de dispositivo** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="33628-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="33628-116">Para criar uma nova coleção de definições de configuração do Lync Phone Edition, clique em **novo**, selecione um site, clique em **OK**, examine as configurações padrão e, se quiser, faça as alterações.</span><span class="sxs-lookup"><span data-stu-id="33628-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="33628-117">Para editar qualquer uma das configurações em uma coleção existente, clique na coleção, clique no menu **Editar** , clique em **Mostrar detalhes**e, em seguida, faça as alterações.</span><span class="sxs-lookup"><span data-stu-id="33628-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="33628-118">Para voltar a usar as configurações padrão para a coleção global, clique na coleção global, clique no menu <STRONG>Editar</STRONG> , clique em <STRONG>excluir</STRONG>e, em seguida, clique em <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="33628-118">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>.</span></span> <span data-ttu-id="33628-119">Isso não excluirá a coleção global; Ele simplesmente redefine as configurações para os padrões.</span><span class="sxs-lookup"><span data-stu-id="33628-119">This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="33628-120">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="33628-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="33628-121">Criando novas configurações do Lync Phone Edition usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="33628-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="33628-122">Você pode criar as configurações de configuração do Lync Phone Edition (apenas em escopo do site) usando o Windows PowerShell e o cmdlet **New-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="33628-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="33628-123">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33628-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="33628-124">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="33628-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="33628-125">Para criar novas definições de configuração do Lync Phone Edition que usam os valores padrão</span><span class="sxs-lookup"><span data-stu-id="33628-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="33628-126">Esse comando cria um novo conjunto de definições de configuração de telefone UC para o site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="33628-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="33628-127">Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="33628-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="33628-128">Para alterar um único valor de propriedade ao criar novas configurações de configuração do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="33628-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="33628-129">Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e valor de parâmetro adequados.</span><span class="sxs-lookup"><span data-stu-id="33628-129">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="33628-130">Por exemplo, para criar um conjunto de configurações de configuração de telefone UC que, por padrão, exigem o bloqueio por telefone, use um comando como este:</span><span class="sxs-lookup"><span data-stu-id="33628-130">For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="33628-131">Para alterar vários valores de propriedade durante a criação de novas configurações do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="33628-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="33628-132">Vários valores de propriedade podem ser modificados incluindo vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="33628-132">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="33628-133">Por exemplo, esse comando reforça o bloqueio de telefone e também define o comprimento mínimo do PIN como 8 dígitos:</span><span class="sxs-lookup"><span data-stu-id="33628-133">For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="33628-134">Para obter detalhes, consulte [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="33628-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33628-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="33628-135">See Also</span></span>


[<span data-ttu-id="33628-136">Excluir uma coleção existente de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33628-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="33628-137">Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33628-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="33628-138">Impor o bloqueio de telefone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33628-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

