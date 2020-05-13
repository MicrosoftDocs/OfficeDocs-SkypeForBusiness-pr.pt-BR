---
title: Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f3f32b4e0c13ea68df183d19b020118e32205b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="70b07-102">Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70b07-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70b07-103">_**Última modificação do tópico:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="70b07-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="70b07-104">O Microsoft Lync Server 2013 deve ser capaz de se comunicar de forma segura e direta com outros produtos de servidor e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="70b07-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="70b07-105">Por exemplo, você pode configurar o Lync Server 2013 para que os dados de contato e/ou dados de arquivamento sejam armazenados no Microsoft Exchange Server 2013; no entanto, isso só poderá ser feito se o Lync Server e o Exchange puderem se comunicar com segurança uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="70b07-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="70b07-106">Da mesma forma, é possível agendar uma conferência do Lync Server a partir do Microsoft SharePoint Server; novamente, isso só poderá ser feito se dois servidores (SharePoint e Lync Server) confiarem um no outro.</span><span class="sxs-lookup"><span data-stu-id="70b07-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="70b07-107">Embora seja possível usar um mecanismo de autenticação para a comunicação do Lync para o Exchange e um mecanismo separado para a comunicação do Lync para o SharePoint, uma abordagem melhor e mais eficiente é usar um método padronizado para todas as autenticações e autorizações de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="70b07-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="70b07-108">O uso de um único método padronizado para autenticação de servidor para servidor é a abordagem realizada pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70b07-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="70b07-109">Para a versão 2013, o Lync Server 2013 (bem como outros produtos de servidor da Microsoft, incluindo o Exchange 2013 e o Microsoft SharePoint Server) dão suporte ao protocolo OAuth (autorização aberta) para autenticação e autorização de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="70b07-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="70b07-110">Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro.</span><span class="sxs-lookup"><span data-stu-id="70b07-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="70b07-111">Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.</span><span class="sxs-lookup"><span data-stu-id="70b07-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="70b07-112">A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si.</span><span class="sxs-lookup"><span data-stu-id="70b07-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="70b07-113">(Você também pode fazer a autenticação de servidor para servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Os tokens de segurança são emitidos pelo servidor de autorização (também conhecido como servidor de token de segurança) para os dois territórios que precisam se comunicar; esses tokens verificam se as comunicações originárias de um realm devem ser confiáveis para o outro realm.</span><span class="sxs-lookup"><span data-stu-id="70b07-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="70b07-114">Por exemplo, o servidor de autorização pode emitir tokens que verificam se os usuários de um território específico do Lync Server 2013 podem acessar um realm do Exchange 2013 especificado e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="70b07-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="70b07-115">Um realm é simplesmente um contêiner de segurança.</span><span class="sxs-lookup"><span data-stu-id="70b07-115">A realm is simply a security container.</span></span> <span data-ttu-id="70b07-116">Por padrão, o Lync Server 2013 usa seu domínio SIP padrão como seu Realm OAuth.</span><span class="sxs-lookup"><span data-stu-id="70b07-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="70b07-117">Namespaces SIP adicionais são adicionados à lista de nomes alternativos de entidade no certificado OAuth.</span><span class="sxs-lookup"><span data-stu-id="70b07-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="70b07-118">O Lync Server 2013 oferece suporte a três cenários de autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="70b07-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="70b07-119">Com o Lync Server 2013, você pode:</span><span class="sxs-lookup"><span data-stu-id="70b07-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="70b07-120">Configure a autenticação de servidor para servidor entre uma instalação local do Lync Server 2013 e uma instalação local do Exchange 2013 e/ou Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="70b07-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="70b07-121">Configure a autenticação de servidor para servidor entre um par de componentes do Microsoft 365 (por exemplo, entre o Microsoft Exchange e o Microsoft Lync Server, ou entre o Microsoft Lync Server e o Microsoft SharePoint).</span><span class="sxs-lookup"><span data-stu-id="70b07-121">Configure server-to-server authentication between a pair of Microsoft 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="70b07-122">Configure a autenticação de servidor para servidor em um ambiente entre locais (ou seja, autenticação de servidor para servidor entre um servidor local e um componente do Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="70b07-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Microsoft 365 component).</span></span>

<span data-ttu-id="70b07-123">Observe que, neste momento, somente o Exchange 2013, o SharePoint Server e o Lync Server 2013 dão suporte à autenticação de servidor para servidor; Se você não estiver executando um desses servidores, não poderá implementar completamente a autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="70b07-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="70b07-124">Também deve ser indicado que você não precisa usar a autenticação de servidor para servidor: a autenticação de servidor para servidor não é necessária para implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70b07-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="70b07-125">Se o Lync Server 2013 não precisar se comunicar com outros servidores (como o Exchange 2013), a autenticação de servidor para servidor não será necessária.</span><span class="sxs-lookup"><span data-stu-id="70b07-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="70b07-126">No entanto, a autenticação de servidor para servidor será exigida ser você quiser usar os novos recursos do Lync Server, como o "armazenamento de contato unificado".</span><span class="sxs-lookup"><span data-stu-id="70b07-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="70b07-127">Com o repositório unificado de contatos, as informações de contato do Lync Server 2013 são armazenadas no Exchange 2013, e não no Lync Server; Isso permite que os usuários tenham um único conjunto de contatos prontamente acessível no Lync, no Microsoft Outlook ou no Microsoft Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="70b07-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="70b07-128">Como o repositório unificado de contatos requer o Lync Server 2013 para compartilhar informações com o Exchange 2013, você deve usar a autenticação de servidor para servidor a fim de implantar o recurso.</span><span class="sxs-lookup"><span data-stu-id="70b07-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="70b07-129">A autenticação de servidor para servidor também é necessária se você optar por usar o arquivamento do Exchange, em que as transcrições de sessões de mensagens instantâneas são salvas como emails do Exchange 2013, e não como registros de banco de dados individuais.</span><span class="sxs-lookup"><span data-stu-id="70b07-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="70b07-130">Para a versão do Microsoft 365 do Lync Server para se comunicar com seu representante do Exchange, o Lync Server 2013 deve primeiro obter um token de segurança do servidor de autorização.</span><span class="sxs-lookup"><span data-stu-id="70b07-130">For the Microsoft 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="70b07-131">O Lync Server usa o token de segurança para se identificar para o Exchange.</span><span class="sxs-lookup"><span data-stu-id="70b07-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="70b07-132">A versão Microsoft 365 do Exchange deve passar pelo mesmo processo para se comunicar com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70b07-132">The Microsoft 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="70b07-133">No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado.</span><span class="sxs-lookup"><span data-stu-id="70b07-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="70b07-134">Os produtos de servidor como o Lync Server 2013 e o Exchange 2013 têm um servidor token interno que pode ser usado para fins de autenticação com outros servidores da Microsoft (como o SharePoint Server) que dão suporte à autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="70b07-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="70b07-135">Por exemplo, o Lync Server 2013 pode ele mesmo gerar e assinar um token de segurança e usá-lo para se comunicar com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="70b07-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="70b07-136">Em um caso como esse, não há a necessidade de um servidor de token terceirizado.</span><span class="sxs-lookup"><span data-stu-id="70b07-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="70b07-137">Para configurar a autenticação de servidor para servidor para uma implementação local do Lync Server 2013, você deve fazer duas coisas:</span><span class="sxs-lookup"><span data-stu-id="70b07-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="70b07-138">Atribuir um certificado ao emissor de token integrado do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70b07-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="70b07-139">Configure o servidor para o qual o Lync Server 2013 se comunicará como um "aplicativo de parceiro".</span><span class="sxs-lookup"><span data-stu-id="70b07-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="70b07-140">Por exemplo, se o Lync Server 2013 precisa se comunicar com o Exchange 2013, será necessário configurar o Exchange para ser um aplicativo parceiro.</span><span class="sxs-lookup"><span data-stu-id="70b07-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="70b07-141">Um "aplicativo de parceiro" é qualquer aplicativo que o Lync Server 2013 possa trocar diretamente tokens de segurança com, sem precisar passar por um servidor de token de segurança de terceiros.</span><span class="sxs-lookup"><span data-stu-id="70b07-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="70b07-142">Observe que o OAuth é uma parte principal do produto e não pode ser desabilitado ou removido.</span><span class="sxs-lookup"><span data-stu-id="70b07-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="70b07-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="70b07-143">See Also</span></span>


[<span data-ttu-id="70b07-144">Atribuindo um certificado de autenticação de servidor para servidor ao Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70b07-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="70b07-145">Configurando o Microsoft Lync Server 2013 em um ambiente entre locais</span><span class="sxs-lookup"><span data-stu-id="70b07-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

