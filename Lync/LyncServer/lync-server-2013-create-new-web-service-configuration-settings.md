---
title: 'Lync Server 2013: criar novas definições de configuração do serviço Web'
description: 'Lync Server 2013: criar novas definições de configuração do serviço Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc66b0c8f394260fbe30e444f800640c774b6bcf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553957"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5329b-103">Criar novas definições de configuração do serviço Web no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5329b-103">Create new Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5329b-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5329b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5329b-105">Você pode usar a página de **serviço Web** para configurar os métodos de autenticação para acessar os servidores Web e serviços Web relacionados ao Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5329b-105">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="5329b-106">Siga estas etapas para criar uma nova política de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="5329b-106">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="5329b-107">Para criar novas definições de configuração de serviço da Web</span><span class="sxs-lookup"><span data-stu-id="5329b-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="5329b-108">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5329b-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5329b-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5329b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5329b-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5329b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5329b-111">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="5329b-111">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="5329b-112">Na página **serviço Web** , clique em **novo**e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5329b-112">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5329b-113">Para configurar o serviço Web de um site, clique em **configuração do site**.</span><span class="sxs-lookup"><span data-stu-id="5329b-113">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="5329b-114">Em **selecionar um site**, clique no site ao qual a política de serviço da Web será aplicada a um site e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5329b-114">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="5329b-115">Para configurar o serviço Web para um pool, clique em **configuração do pool**.</span><span class="sxs-lookup"><span data-stu-id="5329b-115">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="5329b-116">Em **selecionar um serviço**, clique no serviço ao qual a política de serviço da Web será aplicada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5329b-116">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="5329b-117">Em **nova configuração de serviço da Web**, em **autenticação integrada do Windows**, selecione **negociar**, **autenticação integrada do Windows**ou **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="5329b-117">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="5329b-118">Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="5329b-118">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="5329b-119">**Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="5329b-119">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="5329b-120">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.</span><span class="sxs-lookup"><span data-stu-id="5329b-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="5329b-121">**Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.</span><span class="sxs-lookup"><span data-stu-id="5329b-121">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="5329b-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5329b-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

