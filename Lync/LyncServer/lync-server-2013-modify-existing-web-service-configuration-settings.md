---
title: 'Lync Server 2013: modificar as configurações de configuração do serviço Web existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f53d0eb34412c746332a0f74d140b6c41c9c257f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="13ea6-102">Modificar as configurações de serviço Web existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ea6-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13ea6-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="13ea6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="13ea6-104">Você pode usar a página **serviço Web** para configurar os métodos de autenticação para acessar servidores Web relacionados ao Lync Server 2013 e serviços Web.</span><span class="sxs-lookup"><span data-stu-id="13ea6-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="13ea6-105">Execute estas etapas para modificar uma política de Serviço Web existente.</span><span class="sxs-lookup"><span data-stu-id="13ea6-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="13ea6-106">Para modificar definições de configuração de Serviço da Web</span><span class="sxs-lookup"><span data-stu-id="13ea6-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="13ea6-107">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="13ea6-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="13ea6-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13ea6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="13ea6-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="13ea6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="13ea6-110">Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.</span><span class="sxs-lookup"><span data-stu-id="13ea6-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="13ea6-111">Na página **Serviço da Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="13ea6-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="13ea6-112">Em **Editar Configuração do Serviço da Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="13ea6-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="13ea6-113">Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="13ea6-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="13ea6-114">**Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.</span><span class="sxs-lookup"><span data-stu-id="13ea6-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="13ea6-115">**Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="13ea6-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="13ea6-116">**Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.</span><span class="sxs-lookup"><span data-stu-id="13ea6-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="13ea6-117">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="13ea6-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13ea6-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="13ea6-118">See Also</span></span>


[<span data-ttu-id="13ea6-119">Configurando autenticação no painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ea6-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

