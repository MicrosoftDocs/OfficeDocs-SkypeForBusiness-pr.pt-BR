---
title: 'Lync Server 2013: pré-requisitos para integração com o Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92f88d35e573f0914698db28ddcf1fa54967f97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="f86ec-102">Pré-requisitos para a integração do Microsoft Lync Server 2013 e do Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="f86ec-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f86ec-103">_**Última modificação do tópico:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="f86ec-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="f86ec-104">Para que você possa integrar o Microsoft Lync Server 2013 e o Microsoft Exchange Server 2013, você deve garantir que todas as etapas de pré-requisito foram concluídas.</span><span class="sxs-lookup"><span data-stu-id="f86ec-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="f86ec-105">Como você pode esperar, a integração não pode ocorrer até que o Exchange 2013 e o Lync Server 2013 estejam totalmente instalados e em execução.</span><span class="sxs-lookup"><span data-stu-id="f86ec-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="f86ec-106">Para obter detalhes sobre como instalar o Exchange, consulte a documentação de planejamento e [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)implantação do Exchange 2013 em.</span><span class="sxs-lookup"><span data-stu-id="f86ec-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="f86ec-107">Para obter detalhes sobre como instalar o Lync Server 2013, consulte a documentação de [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)planejamento e implantação em.</span><span class="sxs-lookup"><span data-stu-id="f86ec-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="f86ec-108">Após os servidores serem ativados e em execução, você deve atribuir certificados de autenticação de servidor para servidor ao Lync Server 2013 e ao Exchange 2013; esses certificados permitem que o Lync Server e o Exchange troquem informações e se comuniquem entre si.</span><span class="sxs-lookup"><span data-stu-id="f86ec-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="f86ec-109">Quando você instala o Exchange 2013, um certificado autoassinado com o nome certificado de autenticação do Microsoft Exchange Server é criado para você.</span><span class="sxs-lookup"><span data-stu-id="f86ec-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="f86ec-110">Esse certificado, que pode ser encontrado no repositório de certificados do computador local, deve ser usado para a autenticação de servidor para servidor no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f86ec-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="f86ec-111">Para obter detalhes sobre como atribuir certificados no Exchange 2013, consulte "configurar o fluxo de mensagens e o acesso [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)para cliente" em.</span><span class="sxs-lookup"><span data-stu-id="f86ec-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="f86ec-112">Para o Lync Server 2013, você pode usar um certificado existente do Lync Server como seu certificado de autenticação de servidor para servidor; por exemplo, seu certificado padrão também pode ser usado como o certificado OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="f86ec-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="f86ec-113">O Lync Server 2013 permite que você use qualquer certificado de servidor Web como o certificado de autenticação de servidor para servidor fornecido por:</span><span class="sxs-lookup"><span data-stu-id="f86ec-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="f86ec-114">O certificado inclua o nome de seu domínio SIP no campo de Entidade.</span><span class="sxs-lookup"><span data-stu-id="f86ec-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="f86ec-115">O mesmo certificado esteja configurado como o certificado do OAuthTokenIssuer em todos os seus servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="f86ec-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="f86ec-116">O certificado tenha no mínimo 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="f86ec-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="f86ec-117">Para obter detalhes sobre certificados de autenticação de servidor para servidor para o Microsoft Lync Server 2013, consulte [atribuir um certificado de autenticação de servidor para servidor ao Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="f86ec-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="f86ec-118">Depois que os certificados tiverem sido atribuídos, você deve configurar o serviço de descoberta automática no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f86ec-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="f86ec-119">No Exchange 2013, o serviço de descoberta automática configura perfis de usuário e fornece acesso aos serviços do Exchange quando os usuários fazem logon no sistema.</span><span class="sxs-lookup"><span data-stu-id="f86ec-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="f86ec-120">Os usuários apresentam seus endereços de email e senhas ao serviço de descoberta automática; por sua vez, os serviços fornecem aos usuários informações como:</span><span class="sxs-lookup"><span data-stu-id="f86ec-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="f86ec-121">Informações de conexão para conectividade interna e externa para o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f86ec-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="f86ec-122">A localização do servidor da Caixa de Correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="f86ec-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="f86ec-123">URLs para recursos do Outlook como informações de livre/ocupado, Unificação de Mensagens e o catálogo de endereços offline.</span><span class="sxs-lookup"><span data-stu-id="f86ec-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="f86ec-124">Configurações do servidor do Outlook Anywhere.</span><span class="sxs-lookup"><span data-stu-id="f86ec-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="f86ec-125">O serviço de descoberta automática deve ser configurado para que você possa integrar o Lync Server 2013 e o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f86ec-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="f86ec-126">Você pode verificar se o serviço de descoberta automática foi ou não configurado executando o seguinte comando no Shell de gerenciamento do Exchange e verificando o valor da propriedade AutoDiscoverServiceInternalUri:</span><span class="sxs-lookup"><span data-stu-id="f86ec-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="f86ec-p106">Caso o valor esteja em branco, você deve atribuir um URI ao serviço de descoberta automática:</span><span class="sxs-lookup"><span data-stu-id="f86ec-p106">If this value is blank, you must assign a URI to the autodiscover service. Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="f86ec-129">Você pode atribuir o URI de descoberta automática executando um comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="f86ec-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="f86ec-130">Para obter detalhes sobre o serviço de descoberta automática, consulte "Understanding the autodiscover Service" em [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span><span class="sxs-lookup"><span data-stu-id="f86ec-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="f86ec-131">Depois que o serviço de descoberta automática tiver sido configurado, você deve modificar as definições de configuração do Lync Server OAuth; Isso garante que o Lync Server saiba onde encontrar o serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="f86ec-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="f86ec-132">Para modificar as definições de configuração do OAuth no Lync Server 2013, execute o seguinte comando no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f86ec-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="f86ec-133">Ao executar esse comando, certifique-se de especificar o URI para o serviço de descoberta automática em execução no seu servidor do Exchange e se você usa o **autodiscover. svc** para apontar para o local do serviço em vez do **autodiscover. xml** (que aponta para o arquivo XML usado pelo serviço):</span><span class="sxs-lookup"><span data-stu-id="f86ec-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="f86ec-134">O parâmetro Identity no comando anterior é opcional; Isso ocorre porque o Lync Server permite que você tenha apenas uma única coleção global de definições de configuração OAuth.</span><span class="sxs-lookup"><span data-stu-id="f86ec-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="f86ec-135">Dentre outras coisas, isso significa que você pode configurar a URL de descoberta automática usando este comando um pouco mais simples:</span><span class="sxs-lookup"><span data-stu-id="f86ec-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="f86ec-136">Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="f86ec-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="f86ec-p109">Caso não esteja familiarizado com a tecnologia, o OAuth é um protocolo de autorização padrão usado por vários websites importantes. Com o OAuth, as credenciais de usuário e senhas não são passadas de um computador a outro. Ao invés disso, a autenticação e autorização são baseadas na troca de tokens de segurança; estas tokens concedem acesso a um conjunto específico de recursos por um período determinado de tempo.</span><span class="sxs-lookup"><span data-stu-id="f86ec-p109">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites. With OAuth, user credentials and passwords are not passed from one computer to another. Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="f86ec-140">Além de configurar o serviço de descoberta automática, você também deve criar um registro DNS para o serviço que aponta para o seu servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="f86ec-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="f86ec-141">Por exemplo, se o serviço de descoberta automática estiver localizado em autodiscover.litwareinc.com, você precisará criar um registro DNS para autodiscover.litwareinc.com que resolva o nome de domínio totalmente qualificado do seu servidor do Exchange (por exemplo, atl-exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="f86ec-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

