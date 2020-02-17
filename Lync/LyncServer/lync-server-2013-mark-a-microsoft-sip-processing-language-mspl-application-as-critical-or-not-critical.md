---
title: 'Lync Server 2013: marcar um aplicativo Microsoft SIP Processing Language (MSPL) como crítico ou não crítico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50dea89feb7e72c5076e58a38136d24b1b34499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="5f46b-102">Marcar um aplicativo de idioma de processamento SIP da Microsoft (MSPL) como crítico ou não crítico no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f46b-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f46b-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5f46b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5f46b-104">Os aplicativos de servidor do Microsoft SIP Processing Language (MSPL) são aplicativos de script que usam a linguagem de script do MSPL em vez da API do Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="5f46b-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="5f46b-105">Alguns aplicativos de servidor do MSPL são especificados como críticos.</span><span class="sxs-lookup"><span data-stu-id="5f46b-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="5f46b-106">Se um script for crítico, o script deve ser iniciado durante a inicialização do sistema para que o Lync Server 2013 seja iniciado.</span><span class="sxs-lookup"><span data-stu-id="5f46b-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="5f46b-107">Se o script falhar enquanto o Lync Server estiver em execução, o servidor não será desligado, mas interromperá o envio de tráfego para o script e gravará erros no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="5f46b-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="5f46b-108">Você pode usar o painel de controle do Lync Server para marcar aplicativos de servidor do Microsoft SIP Processing Language (MSPL) como críticos ou desmarcá-los.</span><span class="sxs-lookup"><span data-stu-id="5f46b-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="5f46b-109">Nem todos os scripts oferecem suporte a essa opção.</span><span class="sxs-lookup"><span data-stu-id="5f46b-109">Not all scripts support this option.</span></span> <span data-ttu-id="5f46b-110">Por exemplo, o script defaultrouting é marcado como crítico, e essa opção não pode ser alterada para defaultrouting.</span><span class="sxs-lookup"><span data-stu-id="5f46b-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="5f46b-111">Para marcar ou desmarcar um aplicativo de servidor do MSPL como crítico</span><span class="sxs-lookup"><span data-stu-id="5f46b-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="5f46b-112">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f46b-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5f46b-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f46b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5f46b-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5f46b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5f46b-115">Na barra de navegação esquerda, clique em **Topologia** e em **Aplicativo de Servidor**.</span><span class="sxs-lookup"><span data-stu-id="5f46b-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="5f46b-116">Na página **Aplicativo de Servidor**, clique no título de uma coluna para classificar os aplicativos, se for necessário, e clique no aplicativo de servidor que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="5f46b-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="5f46b-117">Clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="5f46b-117">Click **Action**.</span></span>

6.  <span data-ttu-id="5f46b-118">Clique em **Marcar como crítico** ou **desmarcar como crítico** (ou seja, se o script suportar essa opção).</span><span class="sxs-lookup"><span data-stu-id="5f46b-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f46b-119">Confira Também</span><span class="sxs-lookup"><span data-stu-id="5f46b-119">See Also</span></span>


[<span data-ttu-id="5f46b-120">Habilitar ou desabilitar um aplicativo de servidor do Microsoft SIP Processing Language (MSPL) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f46b-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="5f46b-121">Exibir aplicativos de servidor do idioma de processamento SIP da Microsoft (MSPL) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f46b-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="5f46b-122">Gerenciando a topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f46b-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

