---
title: 'Lync Server 2013: habilitar ou desabilitar a conferência discada para reuniões'
description: 'Lync Server 2013: habilitar ou desabilitar a conferência discada para reuniões.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3caa7b8cee14ca8471e7b7e42af7f7398e3b6c2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552438"
---
# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="bfbf1-103">Habilitar ou desabilitar a conferência discada para reuniões no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfbf1-103">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfbf1-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bfbf1-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bfbf1-105">O procedimento a seguir descreve como permitir que um usuário faça parte de uma reunião discada.</span><span class="sxs-lookup"><span data-stu-id="bfbf1-105">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="bfbf1-106">Para habilitar ou desabilitar a conferência discada</span><span class="sxs-lookup"><span data-stu-id="bfbf1-106">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="bfbf1-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="bfbf1-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bfbf1-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bfbf1-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bfbf1-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bfbf1-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bfbf1-110">Na barar de navegação à direita, clique em **Conferência** e, então, em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="bfbf1-110">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="bfbf1-111">Na lista de políticas de conferência, selecione a política que deseja ativar na conferência discada, clique em **Editar** e, então, em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="bfbf1-111">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="bfbf1-p102">Para permitir que os usuários participen por conexão discada, marque a caixa de verificação **Ativar a conferência via conexão discada PSTN**. Por padrão, os usuários podem discar para reuniões utilizando a 	Rede Telefônica Pública Comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="bfbf1-p102">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="bfbf1-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bfbf1-114">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

