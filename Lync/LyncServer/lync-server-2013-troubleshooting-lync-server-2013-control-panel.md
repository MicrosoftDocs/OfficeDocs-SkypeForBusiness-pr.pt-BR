---
title: 'Lync Server 2013: solução de problemas do painel de controle do Lync Server 2013'
description: 'Lync Server 2013: solução de problemas do painel de controle do Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c3559c26b7b0a8d715563665c4b9a57e5999156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549017"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="bfada-103">Resolver problemas do painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfada-103">Troubleshooting Lync Server 2013 Control Panel</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfada-104">_**Última modificação do tópico:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="bfada-104">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="bfada-105">Este tópico fornece informações e procedimentos que podem ajudá-lo a solucionar problemas de acesso ao Lync Server 2013 painel de controle.</span><span class="sxs-lookup"><span data-stu-id="bfada-105">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="bfada-106">Requisitos de navegador da Internet</span><span class="sxs-lookup"><span data-stu-id="bfada-106">Internet Browser Requirements</span></span>

<span data-ttu-id="bfada-107">O painel de controle do Lync Server exige que o plug-in do navegador Microsoft Silverlight versão 4.0.50524.0 ou versão mais recente esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="bfada-107">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="bfada-108">Se o Silverlight não estiver instalado ou se uma versão anterior estiver instalada, siga as instruções na mensagem para instalar a versão necessária.</span><span class="sxs-lookup"><span data-stu-id="bfada-108">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bfada-109">Outros requisitos de software para o painel de controle do Lync Server pertencem ao sistema operacional em que o painel de controle do Lync Server e todas as outras ferramentas administrativas do Lync Server 2013 podem ser instaladas.</span><span class="sxs-lookup"><span data-stu-id="bfada-109">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="bfada-110">Para obter detalhes, consulte <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System support in Lync Server 2013</A> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="bfada-110">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="bfada-111">Se o seu navegador da Internet bloquear a instalação do Silverlight devido a considerações de segurança, adicione o Uniform Resource Locator (URL) que abre o painel de controle do Lync Server à lista de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="bfada-111">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="bfada-112">Nas configurações de segurança do Internet Explorer, certifique-se de **Executar controles e plug-ins do ActiveX** está definido para **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="bfada-112">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="bfada-113">Para obter detalhes, consulte [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) .</span><span class="sxs-lookup"><span data-stu-id="bfada-113">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="bfada-114">Além disso, certifique-se de que o navegador está configurado para usar SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="bfada-114">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="bfada-p104">Se o navegador da Internet estiver configurado para usar um servidor proxy, verifique se o navegador está configurado para ignorar o servidor proxy para os sites que são detectados automaticamente como sites internos. Ou adicione o endereço à lista de exceções do navegador nas definições de configuração de servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="bfada-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="bfada-117">Requisitos de registro DNS e de certificado para a URL de Acesso Administrativo</span><span class="sxs-lookup"><span data-stu-id="bfada-117">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="bfada-118">Se você configurou uma URL simples para acessar o painel de controle do Lync Server, certifique-se de que você também configurou o registro de recurso de host (A) do DNS (sistema de nomes de domínio) estático e o certificado necessário para usar essa URL de acesso administrativo.</span><span class="sxs-lookup"><span data-stu-id="bfada-118">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="bfada-119">Se você alterar a URL base a qualquer momento, certifique-se de que a alteração é refletida no registro DNS apropriado e no certificado e que você executa o *Enable-CsComputer* em cada diretor e servidor front-end para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="bfada-119">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="bfada-120">Para obter detalhes, consulte os seguintes tópicos na documentação de Planejamento:</span><span class="sxs-lookup"><span data-stu-id="bfada-120">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="bfada-121">Planejamento de URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfada-121">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="bfada-122">Requisitos de DNS para URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfada-122">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="bfada-123">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfada-123">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="bfada-124">Para obter os procedimentos passo a passo para configurar a URL de acesso administrativo, consulte [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="bfada-124">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="bfada-125">Requisitos de IIS (Serviços de Informações da Internet)</span><span class="sxs-lookup"><span data-stu-id="bfada-125">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="bfada-126">O painel de controle do Lync Server é um dos componentes do Lync Server 2013 que requer o IIS (serviços de informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="bfada-126">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="bfada-127">Em particular, verifique se o redirecionamento de HTTP e os recursos de autenticação do Windows estão habilitados e se o W3SVC (Serviço de Publicação na World Wide Web ) está em execução.</span><span class="sxs-lookup"><span data-stu-id="bfada-127">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="bfada-128">Dependência do Serviço de Publicação na World Wide Web (Serviço do Windows)</span><span class="sxs-lookup"><span data-stu-id="bfada-128">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="bfada-129">Quando o serviço de publicação na World Wide Web é interrompido, não é possível acessar o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bfada-129">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="bfada-130">Você pode reiniciar o serviço usando o MMC (Console de Gerenciamento Microsoft) dos Serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="bfada-130">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="bfada-131">**Para iniciar o Serviço de Publicação na World Wide Web**</span><span class="sxs-lookup"><span data-stu-id="bfada-131">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="bfada-132">Faça logon no computador em que o serviço de publicação na World Wide Web está instalado como parte do serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="bfada-132">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="bfada-133">Clique em **Iniciar**, em **Ferramentas administrativas** e em **Serviços**.</span><span class="sxs-lookup"><span data-stu-id="bfada-133">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="bfada-134">Com o botão direito do mouse em **Serviço de Publicação na World Wide Web**e clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="bfada-134">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="bfada-135">Modo de pool de aplicativos</span><span class="sxs-lookup"><span data-stu-id="bfada-135">Application Pool Mode</span></span>

<span data-ttu-id="bfada-136">Configure o IIS para que o pool de aplicativos CsManagementAppPool use a conta do Serviço de Rede como sua identidade do modelo de processo.</span><span class="sxs-lookup"><span data-stu-id="bfada-136">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="bfada-137">Permissões e direitos de usuário</span><span class="sxs-lookup"><span data-stu-id="bfada-137">User Rights and Permissions</span></span>

<span data-ttu-id="bfada-138">Você deve entrar no painel de controle do Lync Server usando uma conta de domínio que seja membro do grupo CsAdministrator ou usando uma conta à qual você tenha delegado direitos e permissões de usuário.</span><span class="sxs-lookup"><span data-stu-id="bfada-138">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="bfada-139">Você não pode entrar no painel de controle do Lync Server usando uma conta de máquina local.</span><span class="sxs-lookup"><span data-stu-id="bfada-139">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="bfada-140">Para obter detalhes sobre como delegar tarefas administrativas por meio de controle de acesso baseado em função (RBAC), consulte [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="bfada-140">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="bfada-141">Se você usar uma URL simples para acessar o painel de controle do Lync Server, verifique se os servidores Web foram adicionados aos grupos RTCUniversalServerAdmins e RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="bfada-141">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfada-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="bfada-142">See Also</span></span>


[<span data-ttu-id="bfada-143">Ferramentas administrativas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfada-143">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

