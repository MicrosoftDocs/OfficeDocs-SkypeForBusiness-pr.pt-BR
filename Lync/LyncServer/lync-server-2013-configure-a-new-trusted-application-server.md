---
title: 'Lync Server 2013: configurar um novo servidor de aplicativos confiáveis'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e370c229442d90d6e962f0d73efbf4b94038926a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="9ee37-102">Configurar um novo servidor de aplicativos confiáveis no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ee37-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ee37-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9ee37-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9ee37-104">Um aplicativo confiável é um aplicativo baseado no SDK principal do Microsoft Unified Communications Managed API (UCMA) 3,0 Core que é confiável para o Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ee37-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="9ee37-105">Para obter detalhes sobre os aplicativos do UCMA, consulte "documentação do SDK básico do Unified [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)Communications Managed API 3,0 em.</span><span class="sxs-lookup"><span data-stu-id="9ee37-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="9ee37-106">Para obter informações sobre como configurar o Microsoft Outlook Web Access (OWA) e o Lync Server 2013, consulte "configurar o Outlook Web App e o Lync Server 2010 Integration" na documentação do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ee37-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="9ee37-107">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar um remover uma função do servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e de Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="9ee37-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="9ee37-108">Também é possível delegar as permissões e direitos de administrador adequadas para adicionar funções do servidor.</span><span class="sxs-lookup"><span data-stu-id="9ee37-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="9ee37-109">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9ee37-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="9ee37-110">Para outras alterações na configuração, apenas a associação ao grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="9ee37-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="9ee37-111">Para configurar um servidor de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="9ee37-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="9ee37-112">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9ee37-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="9ee37-113">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9ee37-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="9ee37-114">Selecione **Baixar topologia da implantação existente** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ee37-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="9ee37-115">Na caixa de diálogo **salvar topologia como** , clique no arquivo do construtor de topologia que você deseja usar e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9ee37-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="9ee37-116">No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis**e clique em **novo pool de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="9ee37-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="9ee37-117">Insira o **FQDN do Pool** do pool de aplicativos confiável, selecione se será um servidor único ou vários servidores e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9ee37-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="9ee37-118">Na página **selecionar o próximo salto** , na lista, selecione o pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ee37-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="9ee37-119">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="9ee37-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="9ee37-120">Selecione o nó superior **Lync Server 2013**e, no menu **ações** , clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="9ee37-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="9ee37-121">O **pool de aplicativos confiáveis** deve ter sido criado com êxito e associado ao pool de front-ends correto.</span><span class="sxs-lookup"><span data-stu-id="9ee37-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

