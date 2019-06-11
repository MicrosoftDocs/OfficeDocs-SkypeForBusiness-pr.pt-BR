---
title: 'Lync Server 2013: solução de problemas do painel de controle do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 943f2ab5f0fe808d1bf5e10cf8b451ac1df2575b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="268aa-102">Solução de problemas do painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268aa-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="268aa-103">_**Tópico da última modificação:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="268aa-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="268aa-104">Este tópico fornece informações e procedimentos que podem ajudá-lo a solucionar problemas de acesso ao painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="268aa-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="268aa-105">Requisitos de navegador da Internet</span><span class="sxs-lookup"><span data-stu-id="268aa-105">Internet Browser Requirements</span></span>

<span data-ttu-id="268aa-106">O painel de controle do Lync Server requer a instalação do plug-in do navegador Microsoft Silverlight 4.0.50524.0 ou versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="268aa-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="268aa-107">Se o Silverlight não estiver instalado ou se uma versão anterior estiver instalada, siga as instruções na mensagem para instalar a versão necessária.</span><span class="sxs-lookup"><span data-stu-id="268aa-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="268aa-108">Outros requisitos de software para o painel de controle do Lync Server pertencem ao sistema operacional em que o painel de controle do Lync Server e todas as outras ferramentas administrativas do Lync Server 2013 podem ser instaladas.</span><span class="sxs-lookup"><span data-stu-id="268aa-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="268aa-109">Para obter detalhes, consulte <A href="lync-server-2013-server-and-tools-operating-system-support.md">suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013</A> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="268aa-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="268aa-110">Se o seu navegador da Internet bloquear a instalação do Silverlight devido a considerações de segurança, adicione o Uniform Resource Locator (URL) que abre o painel de controle do Lync Server à lista de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="268aa-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="268aa-111">Nas configurações de segurança do Internet Explorer, certifique-se de que a **execução de controles ActiveX e plug-ins** esteja definida como **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="268aa-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="268aa-112">Para obter detalhes, [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)consulte.</span><span class="sxs-lookup"><span data-stu-id="268aa-112">For details, see [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="268aa-113">Além disso, verifique se o navegador está configurado para usar SSL 3,0.</span><span class="sxs-lookup"><span data-stu-id="268aa-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="268aa-114">Se o navegador da Internet estiver configurado para usar um servidor proxy, verifique se o navegador está configurado para ignorar o servidor proxy para sites que sejam detectados automaticamente como sites internos.</span><span class="sxs-lookup"><span data-stu-id="268aa-114">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites.</span></span> <span data-ttu-id="268aa-115">Ou adicione o endereço à lista de exceções do navegador nas definições de configuração do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="268aa-115">Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="268aa-116">Requisitos de registro e certificado DNS para a URL de acesso administrativo</span><span class="sxs-lookup"><span data-stu-id="268aa-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="268aa-117">Se você configurou uma URL simples para acessar o painel de controle do Lync Server, verifique também se configurou o registro de recurso host (A) do sistema de nome de domínio estático (A) e o certificado necessário para usar essa URL de acesso administrativo.</span><span class="sxs-lookup"><span data-stu-id="268aa-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="268aa-118">Se você alterar a URL base a qualquer momento, certifique-se de que a alteração seja refletida no registro DNS e no certificado apropriados e execute o *Enable-CsComputer* em cada director e servidor front-end para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="268aa-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="268aa-119">Para obter detalhes, consulte os seguintes tópicos na documentação de planejamento:</span><span class="sxs-lookup"><span data-stu-id="268aa-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="268aa-120">Planejamento de URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268aa-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="268aa-121">Requisitos de DNS para URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268aa-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="268aa-122">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268aa-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="268aa-123">Para obter procedimentos passo a passo para configurar a URL de acesso administrativo, consulte [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="268aa-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="268aa-124">Requisitos dos serviços de informações da Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="268aa-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="268aa-125">O painel de controle do Lync Server é um dos componentes do Lync Server 2013 que exige serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="268aa-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="268aa-126">Em particular, verifique se o redirecionamento de HTTP e os recursos de autenticação do Windows estão habilitados e se o W3SVC (World Wide Web Publishing Service) está em execução.</span><span class="sxs-lookup"><span data-stu-id="268aa-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="268aa-127">Dependência do serviço de publicação na World Wide (serviço do Windows)</span><span class="sxs-lookup"><span data-stu-id="268aa-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="268aa-128">Quando o serviço de publicação na World Wide Web é interrompido, você não pode acessar o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="268aa-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="268aa-129">Você pode reiniciar o serviço usando o MMC (console de gerenciamento Microsoft) de serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="268aa-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="268aa-130">**Para iniciar o serviço de publicação na World Wide Web**</span><span class="sxs-lookup"><span data-stu-id="268aa-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="268aa-131">Faça logon no computador em que o serviço de publicação na World Wide Web é instalado como parte do IIS (serviços de informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="268aa-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="268aa-132">Clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **Serviços**.</span><span class="sxs-lookup"><span data-stu-id="268aa-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="268aa-133">Clique com o botão direito do mouse em **serviço de publicação na World Wide Web**e clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="268aa-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="268aa-134">Modo de pool de aplicativos</span><span class="sxs-lookup"><span data-stu-id="268aa-134">Application Pool Mode</span></span>

<span data-ttu-id="268aa-135">Configure o IIS para que o pool de aplicativos do CsManagementAppPool use a conta de serviço de rede como identidade do modelo de processo.</span><span class="sxs-lookup"><span data-stu-id="268aa-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="268aa-136">Direitos e permissões de usuário</span><span class="sxs-lookup"><span data-stu-id="268aa-136">User Rights and Permissions</span></span>

<span data-ttu-id="268aa-137">Você deve conectar-se ao painel de controle do Lync Server usando uma conta de domínio que seja membro do grupo CsAdministrator ou usando uma conta para a qual você tenha direitos e permissões de usuário delegado.</span><span class="sxs-lookup"><span data-stu-id="268aa-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="268aa-138">Você não pode entrar no painel de controle do Lync Server usando uma conta de computador local.</span><span class="sxs-lookup"><span data-stu-id="268aa-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="268aa-139">Para obter detalhes sobre como delegar tarefas administrativas por meio do controle de acesso baseado em função (RBAC), consulte [planejar o controle de acesso baseado em função no Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="268aa-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="268aa-140">Se você usar uma URL simples para acessar o painel de controle do Lync Server, certifique-se de que os servidores Web sejam adicionados aos grupos RTCUniversalServerAdmins e RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="268aa-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="268aa-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="268aa-141">See Also</span></span>


[<span data-ttu-id="268aa-142">Ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268aa-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

