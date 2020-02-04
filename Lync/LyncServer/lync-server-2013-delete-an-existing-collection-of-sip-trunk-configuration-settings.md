---
title: Excluir um conjunto existente das configurações do Tronco SIP
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
ms.openlocfilehash: b0dbb07a11cd96a330d503dc18db9102a7b33ca3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6d40c-102">Excluir uma coleção existente de definições de configuração de tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d40c-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d40c-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="6d40c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="6d40c-104">As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="6d40c-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="6d40c-105">Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="6d40c-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="6d40c-106">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="6d40c-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="6d40c-107">As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="6d40c-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="6d40c-108">Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="6d40c-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="6d40c-109">Ao instalar o Microsoft Lync Server 2013, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="6d40c-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="6d40c-110">Este conjunto global de configurações não pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="6d40c-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="6d40c-111">No entanto, você pode usar o painel de controle do Lync Server ou o cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) para "redefinir" as propriedades na coleção global para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="6d40c-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="6d40c-112">Por exemplo, se a propriedade Enable3pccRefer foi definida como Verdadeira, quando o conjunto global for redefinido, a propriedade Enable3pccRefer será revertida para o valor padrão Falso.</span><span class="sxs-lookup"><span data-stu-id="6d40c-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="6d40c-p103">Os administradores também podem criar definições personalizadas de configuração de tronco no escopo do site ou escopo do serviço (para um gateway PSDN individual); essas configurações padrão podem ser removidas. Ao remover essas configurações padrão, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="6d40c-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="6d40c-p104">Se você remover as configurações do escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="6d40c-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="6d40c-117">Se você remover as configurações pertencentes ao escopo do site, todos os troncos SIP gerenciados por essas configurações serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="6d40c-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="6d40c-118">Para remover as configurações de tronco com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6d40c-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6d40c-119">No painel de controle do Lync Server, clique em **Roteamento de voz** e, em seguida, clique em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="6d40c-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="6d40c-p105">Na guia **Configuração do Tronco**, selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e, então, clique em **Excluir**. Para excluir vários conjuntos na mesma operação, clique no primeiro conjunto a ser excluído, mantenha pressionada a tecla Ctrl e clique em todos os outros conjuntos que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="6d40c-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="6d40c-p106">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="6d40c-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="6d40c-124">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d40c-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="6d40c-125">Na caixa de diálogo **painel de controle do Microsoft Lync Server 2013** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d40c-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="6d40c-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span><span class="sxs-lookup"><span data-stu-id="6d40c-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="6d40c-127">Quando a caixa de diálogo **painel de controle do Microsoft Lync Server 2013** for exibida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d40c-127">When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6d40c-128">Como remover as configurações de tronco usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d40c-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6d40c-129">Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6d40c-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="6d40c-130">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d40c-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6d40c-131">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="6d40c-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="6d40c-132">Para remover uma coleção especificada das definições</span><span class="sxs-lookup"><span data-stu-id="6d40c-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="6d40c-133">O seguinte comando remove as definições de configuração do tronco aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="6d40c-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="6d40c-134">Para remover todos os conjuntos aplicados ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="6d40c-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="6d40c-135">Este comando remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:</span><span class="sxs-lookup"><span data-stu-id="6d40c-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="6d40c-136">Para remover todos os conjuntos em que o bypass de mídia está habilitado</span><span class="sxs-lookup"><span data-stu-id="6d40c-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="6d40c-137">O seguinte comando remove todas as definições de configuração do tronco em que o desvio de mídia está habilitado:</span><span class="sxs-lookup"><span data-stu-id="6d40c-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="6d40c-138">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="6d40c-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

