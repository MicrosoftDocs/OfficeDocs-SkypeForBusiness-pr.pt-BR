---
title: Excluir um conjunto existente de definições de configuração de reunião
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee4aeac6c7fad8b82d2b34fd9d4a51b8984e716
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f68ff-102">Excluir um conjunto existente de definições de configuração de reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f68ff-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f68ff-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f68ff-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f68ff-p101">Você pode excluir uma configuração de site ou de usuário. A configuração global não pode ser removida. Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="f68ff-p101">You can delete a site or user configuration. The global configuration cannot be removed. If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="f68ff-107">Para excluir uma configuração de site ou de reunião</span><span class="sxs-lookup"><span data-stu-id="f68ff-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="f68ff-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f68ff-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f68ff-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f68ff-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f68ff-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f68ff-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f68ff-111">Na barra de navegação esquerda, clique em **Conferência** e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="f68ff-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="f68ff-112">Na lista de configurações de reunião, clique na configuração de site ou pool que deseja excluir, clique em **Editar**e em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="f68ff-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f68ff-113">Removendo definições de configuração de reunião usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f68ff-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f68ff-114">As configurações de reunião podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f68ff-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="f68ff-115">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f68ff-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f68ff-116">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="f68ff-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="f68ff-117">Para remover um conjunto especificado de definições de configuração de reunião</span><span class="sxs-lookup"><span data-stu-id="f68ff-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="f68ff-118">Este comando remove as definições de configuração de reunião aplicadas ao site da Redmond:</span><span class="sxs-lookup"><span data-stu-id="f68ff-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="f68ff-119">Para remover todas as definições de configuração de reunião aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="f68ff-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="f68ff-120">Este comando remove todas as definições de configuração de reunião aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="f68ff-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="f68ff-121">Para remover todas as definições de configuração de reunião que admitem usuários anônimos por padrão</span><span class="sxs-lookup"><span data-stu-id="f68ff-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="f68ff-122">E este remove todas as configurações que permitem que usuários anônimos sejam admitidos como padrão:</span><span class="sxs-lookup"><span data-stu-id="f68ff-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="f68ff-123">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="f68ff-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

