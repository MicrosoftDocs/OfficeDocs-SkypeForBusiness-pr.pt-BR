---
title: Excluir um conjunto existente de definições de configuração do tronco SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f80192db366f5a691724078ba8f8c6948b3472f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1a143-102">Excluir um conjunto existente de definições de configuração do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a143-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a143-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1a143-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1a143-p101">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="1a143-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="1a143-106">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="1a143-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="1a143-107">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="1a143-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="1a143-108">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="1a143-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="1a143-109">Quando você instala o Microsoft Lync Server 2013, uma coleção global de definições de configuração do tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="1a143-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="1a143-110">Este conjunto global de configurações não pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="1a143-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="1a143-111">No entanto, você pode usar o painel de controle do Lync Server ou o cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) para "redefinir" as propriedades na coleção global para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="1a143-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="1a143-112">Por exemplo, se você tiver definido a propriedade Enable3pccRefer como true, ao redefinir a coleção global, a propriedade Enable3pccRefer será revertida para o valor padrão false.</span><span class="sxs-lookup"><span data-stu-id="1a143-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="1a143-113">Os administradores também podem criar definições de configuração de tronco personalizadas no escopo do site ou no escopo do serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas.</span><span class="sxs-lookup"><span data-stu-id="1a143-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="1a143-114">Ao remover essas configurações personalizadas, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="1a143-114">When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="1a143-115">Se você remover as configurações de escopo de serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao seu site, caso existam.</span><span class="sxs-lookup"><span data-stu-id="1a143-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="1a143-116">Se as configurações do site não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="1a143-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="1a143-117">Se você remover as configurações no escopo do site, todos os troncos SIP gerenciados por essas configurações agora serão gerenciados pelo conjunto global de definições de configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="1a143-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="1a143-118">Para remover as definições de configuração de tronco com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="1a143-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1a143-119">No painel de controle do Lync Server, clique em **Roteamento de voz** e em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="1a143-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="1a143-120">Na guia **configuração de tronco** , selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="1a143-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="1a143-121">Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída e, em seguida, pressione a tecla CTRL e clique em qualquer coleção adicional que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="1a143-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="1a143-p106">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="1a143-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="1a143-124">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a143-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="1a143-125">Na caixa de diálogo **Painel de Controle do Microsoft Lync Server 2013**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a143-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="1a143-126">Se você mudar de ideia e optar por não excluir a coleção, clique em **confirmar** e em **cancelar todas as alterações não confirmadas**.</span><span class="sxs-lookup"><span data-stu-id="1a143-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="1a143-127">Quando a caixa de diálogo **painel de controle do Microsoft Lync Server 2013** for exibida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a143-127">When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1a143-128">Removendo definições de configuração de tronco usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a143-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1a143-129">Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1a143-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="1a143-130">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a143-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1a143-131">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="1a143-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="1a143-132">Para remover uma coleção especificada de configurações</span><span class="sxs-lookup"><span data-stu-id="1a143-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="1a143-133">O comando a seguir remove as definições de configuração do tronco aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="1a143-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="1a143-134">Para remover todas as coleções aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="1a143-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="1a143-135">Este comando Remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:</span><span class="sxs-lookup"><span data-stu-id="1a143-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="1a143-136">Para remover todas as coleções nas quais o bypass de mídia está habilitado</span><span class="sxs-lookup"><span data-stu-id="1a143-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="1a143-137">O comando a seguir remove todas as definições de configuração de tronco em que o bypass de mídia foi habilitado:</span><span class="sxs-lookup"><span data-stu-id="1a143-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="1a143-138">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="1a143-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

