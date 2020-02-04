---
title: 'Lync Server 2013: marque um aplicativo Microsoft SIP Processing Language (MSPL) como crítico ou não crítico'
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
ms.openlocfilehash: 54d8b0858145930e0a2144ade55934b39394dcaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="180e9-102">Marcar um aplicativo Microsoft SIP Processing Language (MSPL) como crítico ou não crítico no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="180e9-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="180e9-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="180e9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="180e9-104">Os aplicativos do servidor Microsoft SIP Processing Language (MSPL) são aplicativos somente script que usam a linguagem de script MSPL em vez da API do Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="180e9-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="180e9-105">Alguns aplicativos do MSPL Server são especificados como críticos.</span><span class="sxs-lookup"><span data-stu-id="180e9-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="180e9-106">Se um script for essencial, o script deve iniciar durante a inicialização do sistema para que o Lync Server 2013 seja iniciado.</span><span class="sxs-lookup"><span data-stu-id="180e9-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="180e9-107">Se o script falhar enquanto o Lync Server estiver em execução, o servidor não será desligado, mas ele para de enviar o tráfego para o script e gravará erros no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="180e9-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="180e9-108">Você pode usar o painel de controle do Lync Server para marcar os aplicativos do servidor do Microsoft SIP Processing Language (MSPL) como críticos ou desmarcá-los.</span><span class="sxs-lookup"><span data-stu-id="180e9-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="180e9-109">Nem todos os scripts dão suporte a essa opção.</span><span class="sxs-lookup"><span data-stu-id="180e9-109">Not all scripts support this option.</span></span> <span data-ttu-id="180e9-110">Por exemplo, o script defaultrouting é marcado como Critical, e essa opção não pode ser alterada para defaultrouting.</span><span class="sxs-lookup"><span data-stu-id="180e9-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="180e9-111">Para marcar ou desmarcar um aplicativo de servidor MSPL como crítico</span><span class="sxs-lookup"><span data-stu-id="180e9-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="180e9-112">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="180e9-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="180e9-113">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="180e9-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="180e9-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="180e9-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="180e9-115">Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **aplicativo para servidor**.</span><span class="sxs-lookup"><span data-stu-id="180e9-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="180e9-116">Na página **aplicativo do servidor** , clique em um título de coluna para classificar os aplicativos, se necessário, e clique no aplicativo servidor que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="180e9-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="180e9-117">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="180e9-117">Click **Action**.</span></span>

6.  <span data-ttu-id="180e9-118">Clique em **Marcar como crítica** ou **desmarcar como crítica** (ou seja, se o script der suporte a essa opção).</span><span class="sxs-lookup"><span data-stu-id="180e9-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="180e9-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="180e9-119">See Also</span></span>


[<span data-ttu-id="180e9-120">Habilitar ou desabilitar um aplicativo de servidor Microsoft SIP Processing Language (MSPL) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="180e9-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="180e9-121">Exibir aplicativos de servidor do Idioma de Processamento SIP da Microsoft (MSPL) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="180e9-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="180e9-122">Gerenciando a topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="180e9-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

