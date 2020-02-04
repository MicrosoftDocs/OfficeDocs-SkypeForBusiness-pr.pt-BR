---
title: Excluir uma coleção existente de definições de configuração de reunião
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
ms.openlocfilehash: 96fe774830a8efc6f0cc88a2dd929b3126335b51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6cea8-102">Excluir uma coleção existente de definições de configuração de reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cea8-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cea8-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6cea8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6cea8-104">Você pode excluir uma configuração de site ou de usuário.</span><span class="sxs-lookup"><span data-stu-id="6cea8-104">You can delete a site or user configuration.</span></span> <span data-ttu-id="6cea8-105">A configuração global não pode ser removida.</span><span class="sxs-lookup"><span data-stu-id="6cea8-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="6cea8-106">Se você excluir a configuração global, ela automaticamente retorna para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="6cea8-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="6cea8-107">Para excluir uma configuração de reunião de site ou de usuário</span><span class="sxs-lookup"><span data-stu-id="6cea8-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="6cea8-108">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6cea8-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6cea8-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6cea8-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6cea8-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6cea8-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6cea8-111">Na barra de navegação à esquerda, clique em **conferência** e em **configuração de reunião**.</span><span class="sxs-lookup"><span data-stu-id="6cea8-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="6cea8-112">Na lista de configuração de reunião, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="6cea8-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6cea8-113">Como remover as configurações de reunião usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cea8-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6cea8-114">As configurações de reunião podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6cea8-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="6cea8-115">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cea8-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6cea8-116">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="6cea8-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="6cea8-117">Para remover uma coleção especificada de definições de configuração de reunião</span><span class="sxs-lookup"><span data-stu-id="6cea8-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="6cea8-118">Este comando remove as definições de configuração de reunião aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="6cea8-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="6cea8-119">Para remover todas as definições de configuração de reunião aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="6cea8-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="6cea8-120">Esse comando Remove todas as definições de configuração de reunião aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="6cea8-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="6cea8-121">Para remover todas as configurações de reunião que admitem usuários anônimos por padrão</span><span class="sxs-lookup"><span data-stu-id="6cea8-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="6cea8-122">E isso remove todas as configurações que permitem que os usuários anônimos sejam admitidos por padrão:</span><span class="sxs-lookup"><span data-stu-id="6cea8-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="6cea8-123">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="6cea8-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

