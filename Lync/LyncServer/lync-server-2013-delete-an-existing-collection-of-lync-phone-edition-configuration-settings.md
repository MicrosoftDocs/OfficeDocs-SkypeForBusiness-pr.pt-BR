---
title: Excluir um conjunto existente de definições de configuração do Lync Phone Edition
description: Excluir um conjunto existente de definições de configuração do Lync Phone Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5137590a37b8bbb47f7445d20639157953597ca6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572857"
---
# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="714eb-103">Excluir um conjunto existente de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="714eb-103">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="714eb-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="714eb-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="714eb-105">Se você não quiser mais usar um conjunto de configurações para dispositivos que executam o Lync Phone Edition, exclua-o.</span><span class="sxs-lookup"><span data-stu-id="714eb-105">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="714eb-106">Se você excluir um conjunto de um site, as configurações globais serão aplicadas aos telefones neste site.</span><span class="sxs-lookup"><span data-stu-id="714eb-106">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="714eb-107">Não é possível excluir o conjunto global.</span><span class="sxs-lookup"><span data-stu-id="714eb-107">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="714eb-108">Ao invés de excluir um conjunto, você pode alterar algumas configurações.</span><span class="sxs-lookup"><span data-stu-id="714eb-108">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="714eb-109">Para obter detalhes sobre como fazer isso, consulte <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">create or Modify a Collection of Lync Phone Edition Configuration Settings in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="714eb-109">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="714eb-110">Para excluir uma coleção de definições de configuração do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="714eb-110">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="714eb-111">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="714eb-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="714eb-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="714eb-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="714eb-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="714eb-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="714eb-114">Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="714eb-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="714eb-115">Na página **Configuração do Dispositivo**, clique no conjunto que você deseja excluir, clique no menu **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="714eb-115">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="714eb-p104">Se você excluir o conjunto global, as configurações são revertidas para as configurações padrões. O conjunto não some.</span><span class="sxs-lookup"><span data-stu-id="714eb-p104">If you delete the global collection, the settings just revert to the default settings. The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="714eb-118">Na caixa de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="714eb-118">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="714eb-119">Removendo definições de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="714eb-119">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="714eb-120">Você pode excluir as definições de configuração do Lync Phone Edition usando o Windows PowerShell e o cmdlet **Remove-CsUCConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="714eb-120">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="714eb-121">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="714eb-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="714eb-122">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="714eb-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="714eb-123">Para remover uma coleção especificada das definições de configuração do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="714eb-123">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="714eb-124">Este comando excluir as definições de configuração do telefone UC para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="714eb-124">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="714eb-125">Para remover todas as definições de configuração do Lync Phone Edition aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="714eb-125">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="714eb-126">Este comando remove todas as definições de configuração do telefone UC aplicadas ao escopo de serviço:</span><span class="sxs-lookup"><span data-stu-id="714eb-126">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="714eb-127">Para remover todas as definições de configuração do Lync Phone Edition onde o bloqueio de telefone está desabilitado</span><span class="sxs-lookup"><span data-stu-id="714eb-127">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="714eb-128">Este comando exclui qualquer conjunto de definições de configuração do telefone UC onde o bloqueio de telefone foi desabilitado:</span><span class="sxs-lookup"><span data-stu-id="714eb-128">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="714eb-129">Para obter detalhes, consulte [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="714eb-129">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

