---
title: 'Lync Server 2013: excluindo uma configuração de arquivamento'
description: 'Lync Server 2013: excluindo uma configuração de arquivamento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb267c119b49c9bbf06f365c3bdf2cbab459628
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575807"
---
# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="39e4e-103">Excluindo uma configuração de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39e4e-103">Deleting an Archiving configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39e4e-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="39e4e-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="39e4e-105">Você pode excluir uma configuração de site ou configuração de pool.</span><span class="sxs-lookup"><span data-stu-id="39e4e-105">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="39e4e-106">A configuração global não pode ser removida.</span><span class="sxs-lookup"><span data-stu-id="39e4e-106">The global configuration cannot be removed.</span></span> <span data-ttu-id="39e4e-107">Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="39e4e-107">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="39e4e-108">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="39e4e-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="39e4e-109">Para excluir uma configuração de site ou pool para arquivamento</span><span class="sxs-lookup"><span data-stu-id="39e4e-109">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="39e4e-110">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="39e4e-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="39e4e-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39e4e-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="39e4e-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="39e4e-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="39e4e-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="39e4e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="39e4e-114">Na lista de configuração de arquivamento, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="39e4e-114">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="39e4e-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="39e4e-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="39e4e-116">Removendo definições de configuração de arquivamento usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39e4e-116">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="39e4e-117">As definições de configuração de arquivamento podem ser excluídas usando o Windows PowerShell e o cmdlet **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="39e4e-117">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="39e4e-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39e4e-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="39e4e-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="39e4e-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="39e4e-120">Para remover um conjunto especificado de definições de configuração de arquivamento</span><span class="sxs-lookup"><span data-stu-id="39e4e-120">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="39e4e-121">O comando a seguir remove as definições de configuração de arquivamento aplicadas ao site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="39e4e-121">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="39e4e-122">Para remover todas as definições de configuração de arquivamento aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="39e4e-122">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="39e4e-123">Esse comando remove todas as definições de configuração de arquivamento aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="39e4e-123">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="39e4e-124">Para remover as definições de configuração de arquivamento com base em um valor de propriedade especificado</span><span class="sxs-lookup"><span data-stu-id="39e4e-124">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="39e4e-125">Esse comando remove todas as definições de configuração de arquivamento onde o arquivamento do Exchange foi desativado:</span><span class="sxs-lookup"><span data-stu-id="39e4e-125">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="39e4e-126">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="39e4e-126">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="39e4e-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="39e4e-127">See Also</span></span>


[<span data-ttu-id="39e4e-128">Como o arquivamento funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39e4e-128">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="39e4e-129">Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39e4e-129">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

