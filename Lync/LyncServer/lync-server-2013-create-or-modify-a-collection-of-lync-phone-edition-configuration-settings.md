---
title: Criar ou modificar uma coleção de definições de configuração do Lync Phone Edition
description: Criar ou modificar um conjunto de definições de configuração do Lync Phone Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82a4becadf581ec965952e507c3eb2839b622d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578247"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1592c-103">Criar ou modificar um conjunto de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1592c-103">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1592c-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1592c-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1592c-105">Ao instalar o Lync Server, você obtém uma coleção global de configurações do Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1592c-105">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="1592c-106">Essas configurações se aplicam a todos os dispositivos que executam o Lync Phone Edition em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="1592c-106">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="1592c-107">Você pode alterar essas configurações a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="1592c-107">You can change these settings at any time.</span></span> <span data-ttu-id="1592c-108">Também é possível configurar um novo conjunto de configurações aplicáveis aos dispositivos em um site específico.</span><span class="sxs-lookup"><span data-stu-id="1592c-108">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="1592c-109">As configurações de site têm prioridade sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="1592c-109">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="1592c-110">As configurações consistem de nome do conjunto, escopo (global ou site), configuração de segurança SIP, nível de log, nível de QoS (qualidade de serviço) de voz, configuração de bloqueio de telefone e detalhes de bloqueio de telefone, isto é, a) o tamanho do PIN (número de identificação pessoal) de desbloqueio e b) por quanto tempo o telefone deve ficar ocioso antes de bloquear.</span><span class="sxs-lookup"><span data-stu-id="1592c-110">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="1592c-111">Para criar uma coleção de definições de configuração do Lync Phone Edition ou editar configurações de uma coleção existente</span><span class="sxs-lookup"><span data-stu-id="1592c-111">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="1592c-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1592c-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1592c-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1592c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1592c-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1592c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1592c-115">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração dos Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1592c-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1592c-116">Na página **Configuração dos Dispositivos**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="1592c-116">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1592c-117">Para criar um novo conjunto de definições de configuração do Lync Phone Edition, clique em **novo**, selecione um site, clique em **OK**, revise as configurações padrão e, se desejar, faça as alterações.</span><span class="sxs-lookup"><span data-stu-id="1592c-117">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="1592c-118">Para editar qualquer configuração de um conjunto existente, clique no menu **Editar**, clique em **Mostrar detalhes** e faça as alterações.</span><span class="sxs-lookup"><span data-stu-id="1592c-118">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="1592c-p103">Para voltar a usar as configurações padrão do conjunto global, clique no conjunto global, clique no menu <STRONG>Editar</STRONG>, clique em <STRONG>Excluir</STRONG> e clique em <STRONG>OK</STRONG>. Essa ação não excluirá o conjunto global, apenas irá restaurar os padrões das configurações.</span><span class="sxs-lookup"><span data-stu-id="1592c-p103">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>. This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="1592c-121">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1592c-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1592c-122">Criando novas definições de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1592c-122">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1592c-123">Você pode criar definições de configuração do Lync Phone Edition (somente no escopo do site) usando o Windows PowerShell e o cmdlet **New-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1592c-123">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="1592c-124">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1592c-124">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1592c-125">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1592c-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="1592c-126">Para criar novas definições de configuração do Lync Phone Edition que usem os valores padrão</span><span class="sxs-lookup"><span data-stu-id="1592c-126">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="1592c-127">Este comando cria um novo conjunto de configurações de telefone UC para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="1592c-127">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="1592c-128">Como nenhum parâmetro (além de Identidade, que é obrigatório) foi especificado no comando anterior, o novo conjunto de configurações usará os valores padrão para todas as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="1592c-128">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="1592c-129">Para alterar um valor de propriedade única ao criar novas definições de configuração do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1592c-129">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="1592c-p105">Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e valor de parâmetro adequados. Por exemplo, para criar um conjunto de configurações de telefone UC que, por padrão, exijam bloqueio do telefone, use um comando como este:</span><span class="sxs-lookup"><span data-stu-id="1592c-p105">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="1592c-132">Para alterar vários valores de propriedade ao criar novas definições de configuração do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1592c-132">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="1592c-p106">É possível modificar valores de várias propriedades incluindo vários parâmetros. Por exemplo, este comando aplica o bloqueio do telefone a também define um tamanho mínimo de PIN de oito dígitos:</span><span class="sxs-lookup"><span data-stu-id="1592c-p106">Multiple property values can be modified by including multiple parameters. For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="1592c-135">Para obter detalhes, consulte [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="1592c-135">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1592c-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="1592c-136">See Also</span></span>


[<span data-ttu-id="1592c-137">Excluir um conjunto existente de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1592c-137">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="1592c-138">Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1592c-138">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="1592c-139">Impor bloqueio de telefone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1592c-139">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

