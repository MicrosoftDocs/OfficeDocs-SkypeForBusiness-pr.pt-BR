---
title: 'Lync Server 2013: Redefinir a política global para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="08938-102">Redefinir a política global para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08938-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08938-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="08938-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="08938-104">Não é possível excluir completamente uma política global.</span><span class="sxs-lookup"><span data-stu-id="08938-104">You cannot completely delete a global policy.</span></span> <span data-ttu-id="08938-105">Usar a opção **excluir** na política global somente redefine a política global para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="08938-105">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="08938-106">Para redefinir a política global para as configurações padrão</span><span class="sxs-lookup"><span data-stu-id="08938-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="08938-107">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="08938-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="08938-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08938-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="08938-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="08938-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="08938-110">Na barra de navegação à esquerda, clique em **acesso ao usuário externo**, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="08938-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="08938-111">Na guia **política de acesso externo** , clique na política global, clique em **Editar**e, em seguida, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="08938-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="08938-112">Quando for solicitado a confirmar a exclusão, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08938-112">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="08938-113">Uma mensagem é exibida na parte superior da página informando que a política global foi redefinida.</span><span class="sxs-lookup"><span data-stu-id="08938-113">A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="08938-114">Redefinindo a política de acesso externo global usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08938-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="08938-115">A política de acesso externo global pode ser redefinida usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="08938-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="08938-116">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08938-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="08938-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="08938-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="08938-118">Para redefinir a política de acesso externo global</span><span class="sxs-lookup"><span data-stu-id="08938-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="08938-119">Este comando redefine a política global de acesso externo:</span><span class="sxs-lookup"><span data-stu-id="08938-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="08938-120">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="08938-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

