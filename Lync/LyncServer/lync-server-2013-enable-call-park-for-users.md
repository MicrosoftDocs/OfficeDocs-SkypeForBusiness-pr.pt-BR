---
title: 'Lync Server 2013: habilitar estacionamento de chamada para usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3046cc7daf0dd1fbaba16ffff4e8f41ee6d2e757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="12cfd-102">Habilitar estacionamento de chamada para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12cfd-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12cfd-103">_**Última modificação do tópico:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="12cfd-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="12cfd-104">Os usuários não podem estacionar chamadas ou recuperar chamadas estacionadas até que sejam habilitados para estacionamento de chamada na política de voz.</span><span class="sxs-lookup"><span data-stu-id="12cfd-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12cfd-105">Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="12cfd-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="12cfd-106">Você pode habilitar o estacionamento de chamadas no escopo global ou no escopo do site ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="12cfd-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="12cfd-107">O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global.</span><span class="sxs-lookup"><span data-stu-id="12cfd-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="12cfd-108">Se você tiver várias políticas de voz, revise todas as políticas para habilitar o estacionamento de chamadas, e não apenas a política global.</span><span class="sxs-lookup"><span data-stu-id="12cfd-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="12cfd-109">Para usar o painel de controle do Lync Server para habilitar o estacionamento de chamada para usuários</span><span class="sxs-lookup"><span data-stu-id="12cfd-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="12cfd-110">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="12cfd-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12cfd-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12cfd-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12cfd-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12cfd-113">Na barra de navegação à esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="12cfd-114">Clique na guia **Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="12cfd-115">Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="12cfd-116">Sob **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="12cfd-117">Clique em **OK** para salvar a política de voz</span><span class="sxs-lookup"><span data-stu-id="12cfd-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="12cfd-118">Para usar cmdlets para habilitar o estacionamento de chamada para usuários</span><span class="sxs-lookup"><span data-stu-id="12cfd-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="12cfd-119">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função administrativa CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="12cfd-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="12cfd-120">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="12cfd-121">Sejam</span><span class="sxs-lookup"><span data-stu-id="12cfd-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="12cfd-122">Por exemplo, para habilitar o estacionamento de chamada para a política de voz global padrão:</span><span class="sxs-lookup"><span data-stu-id="12cfd-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12cfd-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="12cfd-123">See Also</span></span>


[<span data-ttu-id="12cfd-124">Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12cfd-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

