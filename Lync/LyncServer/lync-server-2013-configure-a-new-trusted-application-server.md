---
title: 'Lync Server 2013: configurar um novo servidor de aplicativos confiável'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="646f1-102">Configurar um novo servidor de aplicativos confiável no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="646f1-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="646f1-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="646f1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="646f1-104">Um aplicativo confiável é um aplicativo baseado em SDK do Microsoft UCMA (Microsoft Unified Communications Managed) 3,0 Core SDK que é confiável para o Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="646f1-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="646f1-105">Para obter detalhes sobre aplicativos do UCMA, consulte "documentação do SDK do 3,0 Core Communications [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)Managed API" em.</span><span class="sxs-lookup"><span data-stu-id="646f1-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="646f1-106">Para obter informações sobre como configurar o Microsoft Outlook Web Access (OWA) e o Lync Server 2013, consulte "configurar o Outlook Web App e o Lync Server 2010 Integration" na documentação do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="646f1-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="646f1-107">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio.</span><span class="sxs-lookup"><span data-stu-id="646f1-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="646f1-108">Também é possível delegar as permissões e direitos de administrador adequados para adicionar funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="646f1-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="646f1-109">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="646f1-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="646f1-110">Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="646f1-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="646f1-111">Para configurar um servidor de aplicativos confiável</span><span class="sxs-lookup"><span data-stu-id="646f1-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="646f1-112">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="646f1-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="646f1-113">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="646f1-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="646f1-114">Selecione **baixar topologia da implantação existente**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="646f1-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="646f1-115">Na caixa de diálogo **salvar topologia como** , clique no arquivo do construtor de topologias que você deseja usar e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="646f1-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="646f1-116">No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis**e, em seguida, clique em **novo pool de aplicativos confiável**.</span><span class="sxs-lookup"><span data-stu-id="646f1-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="646f1-117">Digite o **FQDN do pool** do pool de aplicativos confiáveis, selecione se ele será um único servidor ou vários servidores e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="646f1-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="646f1-118">Na página **selecionar o próximo salto** , na lista, selecione o pool de front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="646f1-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="646f1-119">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="646f1-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="646f1-120">Selecione o nó superior do **Lync Server 2013**e, em seguida, no menu **ações** , clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="646f1-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="646f1-121">O **pool de aplicativos confiável** deve ter sido criado com êxito e associado ao pool de front-end correto.</span><span class="sxs-lookup"><span data-stu-id="646f1-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

