---
title: 'Lync Server 2013: Modificar definições de configuração do serviço Web existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675cc97e8e16f4e8734f56a9d666b976606c4d2b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534338"
---
# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5658e-102">Modificar definições de configuração do serviço Web existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5658e-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5658e-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5658e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5658e-104">Você pode usar a página de **serviço Web** para configurar os métodos de autenticação para acessar os servidores Web e serviços Web relacionados ao Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5658e-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="5658e-105">Execute estas etapas para modificar uma política de Serviço Web existente.</span><span class="sxs-lookup"><span data-stu-id="5658e-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="5658e-106">Para modificar as definições de configuração do serviço da Web existente</span><span class="sxs-lookup"><span data-stu-id="5658e-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="5658e-107">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5658e-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5658e-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5658e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5658e-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5658e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5658e-110">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="5658e-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="5658e-111">Na página **Serviço Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5658e-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5658e-112">Em **Editar Configuração do Serviço Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="5658e-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="5658e-113">Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="5658e-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="5658e-114">**Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="5658e-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="5658e-115">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.</span><span class="sxs-lookup"><span data-stu-id="5658e-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="5658e-116">**Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.</span><span class="sxs-lookup"><span data-stu-id="5658e-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="5658e-117">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5658e-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5658e-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="5658e-118">See Also</span></span>


[<span data-ttu-id="5658e-119">Configurando a autenticação no painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5658e-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

