---
title: Configurando aplicativos parceiros no Lync Server 2013 e no Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8743b012042738ea25653cf49a804e08d59a423
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532508"
---
# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="1621d-102">Configurando aplicativos parceiros no Microsoft Lync Server 2013 e no Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="1621d-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1621d-103">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="1621d-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="1621d-p101">A autenticação entre servidores geralmente envolve três entidades: os dois servidores que precisam se comunicam entre si e um terceiro servidor de token de segurança. Se dois servidores (por exemplo, Servidor A e Servidor B) precisarem se comunicar, então ambos geralmente iniciam entrando em contato com o servidor de token, obtendo um token de segurança mutuamente confiável. O Servidor A então apresenta esse token de segurança ao Servidor B (e vice-versa), como uma forma de garantir autenticidade e confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="1621d-p101">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server. If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token. Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="1621d-107">No entanto, esta é uma regra geral.</span><span class="sxs-lookup"><span data-stu-id="1621d-107">However, that's a general rule.</span></span> <span data-ttu-id="1621d-108">O Lync Server 2013, o Microsoft Exchange Server 2013 e o Microsoft SharePoint Server 2013 não precisam usar um servidor de token de terceiros ao se comunicar uns com os outros; Isso ocorre porque esses produtos de servidor podem criar tokens de segurança que podem ser aceitos por um do outro, sem a necessidade de um servidor token separado.</span><span class="sxs-lookup"><span data-stu-id="1621d-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="1621d-109">(Esse recurso só está disponível no Lync Server 2013, no Exchange 2013 e no SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1621d-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="1621d-110">Se você precisar configurar uma autenticação entre servidores com outros servidores, incluindo outros produtos de servidor da Microsoft, então será necessário fazer isso usando um terceiro servidor de token.</span><span class="sxs-lookup"><span data-stu-id="1621d-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="1621d-111">Para configurar a autenticação de servidor para servidor entre o Lync Server e o Exchange, você deve fazer duas coisas: 1) você deve atribuir os certificados apropriados a cada servidor; e 2) você deve configurar cada servidor para ser um aplicativo parceiro do outro servidor: isso significa que você deve configurar o Lync Server 2013 para ser um aplicativo parceiro para o Exchange 2013, e você deve configurar o Exchange 2013 para ser um aplicativo parceiro para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1621d-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="1621d-112">Configurando o Lync Server 2013 para ser um aplicativo parceiro para o Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="1621d-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="1621d-113">A maneira mais fácil de configurar o Lync Server 2013 para ser um aplicativo parceiro com o Exchange 2013 é executar o Configure-EnterprisePartnerApplication.ps1 script, um script do Windows PowerShell que acompanha o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="1621d-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="1621d-114">Para executar esse script, você deve fornecer a URL para o documento de metadados de autenticação do Lync Server; Normalmente, o nome de domínio totalmente qualificado do pool do Lync Server 2013, seguido do sufixo/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="1621d-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="1621d-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1621d-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="1621d-116">Para configurar o Lync Server como um aplicativo parceiro, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a este (supondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):</span><span class="sxs-lookup"><span data-stu-id="1621d-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="1621d-117">Após configurar o aplicativo parceiro, é recomendável que você pare e reinicie o IIS (serviços de informações da Internet) na caixa de correio do Exchange e nos servidores de acesso para cliente.</span><span class="sxs-lookup"><span data-stu-id="1621d-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="1621d-118">Você pode reiniciar o IIS usando um comando similar a este, que reinicia o serviço no computador atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="1621d-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="1621d-119">Este comando pode ser executado de dentro do Shell de gerenciamento do Exchange ou de qualquer outra janela de comando executada sob privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="1621d-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="1621d-120">Configurando o Exchange 2013 para ser um aplicativo parceiro para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1621d-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="1621d-121">Depois de configurar o Lync Server 2013 para ser um aplicativo parceiro para o Exchange 2013, configure o Exchange para ser um aplicativo parceiro para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1621d-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="1621d-122">Isso pode ser feito usando o Shell de gerenciamento do Lync Server e especificando o documento de metadados de autenticação para o Exchange; Este será tipicamente o URI do serviço de descoberta automática do Exchange seguido pelo sufixo/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="1621d-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="1621d-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1621d-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="1621d-124">No Lync Server, os aplicativos parceiros são configurados usando o cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="1621d-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="1621d-125">Além de especificar o URI dos metadados, você também deve definir o nível de confiança do aplicativo como completo; Isso permitirá que o Exchange represente tanto e qualquer usuário autorizado no realm.</span><span class="sxs-lookup"><span data-stu-id="1621d-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="1621d-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1621d-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="1621d-127">Como alternativa, você pode criar um aplicativo de parceiro copiando e modificando o código de script encontrado na documentação de autenticação de servidor para servidor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1621d-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="1621d-128">Confira o artigo [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1621d-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="1621d-129">Se você configurou com êxito aplicativos parceiros para o Lync Server e o Exchange, isso significa que você também configurou com êxito a autenticação de servidor para servidor entre os dois produtos.</span><span class="sxs-lookup"><span data-stu-id="1621d-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="1621d-130">O Lync Server 2013 inclui um cmdlet do Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), que permite verificar se a autenticação de servidor para servidor foi configurada corretamente e se o serviço de armazenamento do Lync Server pode se conectar ao Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="1621d-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="1621d-131">O cmdlet faz isso conectando-se à caixa de correio de um usuário do Exchange 2013, gravar um item na pasta de histórico de conversa desse usuário e, opcionalmente, excluir esse item.</span><span class="sxs-lookup"><span data-stu-id="1621d-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="1621d-132">Para testar a integração do Lync Server 2013 e do Exchange 2013, execute um comando semelhante a este no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1621d-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="1621d-133">No comando anterior, o SipUri representa o endereço SIP de um usuário com uma conta no Exchange 2013; o comando falhará se não for uma conta de usuário válida.</span><span class="sxs-lookup"><span data-stu-id="1621d-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="1621d-134">Se o teste for bem sucedido e a conectividade for estabelecida, será possível então prosseguir para configurar recursos opcionais, como integração de arquivamento e o armazenamento de contato unificado.</span><span class="sxs-lookup"><span data-stu-id="1621d-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

