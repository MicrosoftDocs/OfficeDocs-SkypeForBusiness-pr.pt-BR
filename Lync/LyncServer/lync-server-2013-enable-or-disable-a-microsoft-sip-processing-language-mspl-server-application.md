---
title: 'Lync Server 2013: habilitar ou desabilitar um aplicativo de servidor do Microsoft SIP Processing Language (MSPL)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8aac965a375520ac46534846a65b67e6d9f92c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="d03e3-102">Habilitar ou desabilitar um aplicativo de servidor do Microsoft SIP Processing Language (MSPL) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03e3-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d03e3-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d03e3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d03e3-104">Você pode usar o painel de controle do Lync Server para habilitar ou desabilitar aplicativos de servidor do Microsoft SIP Processing Language (MSPL) que são executados no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d03e3-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="d03e3-105">Esses aplicativos são aplicativos somente com scripts que usam uma linguagem de scripts em vez do API do Microsoft Lync 2013 Preview.</span><span class="sxs-lookup"><span data-stu-id="d03e3-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="d03e3-p102">Nem todos os scripts podem ser habilitados ou desabilitados. Por exemplo, o script DefaultRouting está habilitado e essa opção não pode ser alterada para DefaultRouting.</span><span class="sxs-lookup"><span data-stu-id="d03e3-p102">Not all scripts can be enabled or disabled. For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="d03e3-108">Para habilitar ou desabilitar um aplicativo de servidor do MSPL</span><span class="sxs-lookup"><span data-stu-id="d03e3-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="d03e3-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d03e3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="d03e3-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d03e3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d03e3-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d03e3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d03e3-112">Na barra de navegação esquerda, clique em **Topologia** e em **Aplicativo de Servidor**.</span><span class="sxs-lookup"><span data-stu-id="d03e3-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="d03e3-113">Na página **Aplicativo de Servidor**, clique no título de uma coluna para classificar os aplicativos, se for necessário, e clique no aplicativo de servidor que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="d03e3-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="d03e3-114">Clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="d03e3-114">Click **Action**.</span></span>

6.  <span data-ttu-id="d03e3-115">Clique em **Habilitar aplicativo** ou **Desabilitar aplicativo** (ou seja, se o script suportar essa opção).</span><span class="sxs-lookup"><span data-stu-id="d03e3-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d03e3-116">Confira Também</span><span class="sxs-lookup"><span data-stu-id="d03e3-116">See Also</span></span>


[<span data-ttu-id="d03e3-117">Marcar um aplicativo de idioma de processamento SIP da Microsoft (MSPL) como crítico ou não crítico no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03e3-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="d03e3-118">Exibir aplicativos de servidor do idioma de processamento SIP da Microsoft (MSPL) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03e3-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="d03e3-119">Gerenciando a topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d03e3-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

