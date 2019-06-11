---
title: 'Lync Server 2013: Planejamento de URLs simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17dbfce9f699f31e09bb66d6d596e0a3cbf0ba96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="27f40-102">Planejamento de URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27f40-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27f40-103">_**Tópico da última modificação:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="27f40-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="27f40-104">URLs simples facilitam a junção de reuniões para seus usuários e facilitam a obtenção de ferramentas administrativas do Lync Server para seus administradores.</span><span class="sxs-lookup"><span data-stu-id="27f40-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="27f40-105">O Lync Server oferece suporte a três URLs simples:</span><span class="sxs-lookup"><span data-stu-id="27f40-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="27f40-106">A **reunião** é usada como a URL base para todas as conferências no site ou na organização.</span><span class="sxs-lookup"><span data-stu-id="27f40-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="27f40-107">Um exemplo de uma URL de reunião simples https://meet.contoso.comé.</span><span class="sxs-lookup"><span data-stu-id="27f40-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="27f40-108">Uma URL para uma reunião específica pode ser https://meet.contoso.com/ *nome de usuário*/7322994.</span><span class="sxs-lookup"><span data-stu-id="27f40-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="27f40-109">Com a URL simples de reunião, os links para ingressar em reuniões são fáceis de compreender e fáceis de se comunicar e distribuir.</span><span class="sxs-lookup"><span data-stu-id="27f40-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="27f40-110">\*\*\*\* A discagem permite o acesso à página da Web configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="27f40-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="27f40-111">Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência.</span><span class="sxs-lookup"><span data-stu-id="27f40-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="27f40-112">A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias.</span><span class="sxs-lookup"><span data-stu-id="27f40-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="27f40-113">Um exemplo da URL simples de discagem é https://dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="27f40-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="27f40-114">O **administrador** habilita o acesso rápido ao painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27f40-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="27f40-115">Em qualquer computador dentro dos firewalls da sua organização, um administrador pode abrir o painel de controle do Lync Server digitando a URL simples do administrador em um navegador.</span><span class="sxs-lookup"><span data-stu-id="27f40-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="27f40-116">A URL simples de Admin é parte interna da sua organização.</span><span class="sxs-lookup"><span data-stu-id="27f40-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="27f40-117">Um exemplo da URL simples de administrador éhttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27f40-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="27f40-118">Escopo de URL simples</span><span class="sxs-lookup"><span data-stu-id="27f40-118">Simple URL Scope</span></span>

<span data-ttu-id="27f40-119">Você pode configurar suas URLs simples para ter escopo global ou pode especificar diferentes URLs simples para cada site central em sua organização.</span><span class="sxs-lookup"><span data-stu-id="27f40-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="27f40-120">Se tanto uma URL simples de escopo global quanto uma URL simples de escopo de site forem especificadas, a URL simples de escopo do site terá precedência.</span><span class="sxs-lookup"><span data-stu-id="27f40-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="27f40-121">Na maioria dos casos, recomendamos que você defina URLs simples somente no nível global, de modo que a URL simples de um usuário não seja alterada se passar de um site para outro.</span><span class="sxs-lookup"><span data-stu-id="27f40-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="27f40-122">A exceção seria organizações que precisam usar números de telefone diferentes para usuários de discagem em sites diferentes.</span><span class="sxs-lookup"><span data-stu-id="27f40-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="27f40-123">Observe que, se você definir uma URL simples (como a URL simples de discagem) em um site para ser uma URL simples no nível do site, também deverá definir que outras URLs simples nesse site também sejam no nível do site.</span><span class="sxs-lookup"><span data-stu-id="27f40-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27f40-124">Se você optar por usar URLs simples com escopo de site, os usuários não poderão se mover entre os pools front-end em sites diferentes sem que esses usuários reagendem todas as suas reuniões agendadas, pois as URLs simples de reunião são diferentes entre sites.</span><span class="sxs-lookup"><span data-stu-id="27f40-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="27f40-125">Isso inclui cenários de failover em que os pools de relações de backup estão em sites separados.</span><span class="sxs-lookup"><span data-stu-id="27f40-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="27f40-126">Quando você precisar fazer failover entre sites onde URLs simples com escopo de site são implantadas, os usuários não poderão ingressar em suas reuniões devido ao escopo da URL.</span><span class="sxs-lookup"><span data-stu-id="27f40-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="27f40-127">Para obter mais informações, confira <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="27f40-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="27f40-128">Você pode definir URLs simples globais no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="27f40-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="27f40-129">Para definir uma URL simples no nível do site, você deve usar o cmdlet Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="27f40-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="27f40-130">Nomeando suas URLs simples</span><span class="sxs-lookup"><span data-stu-id="27f40-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="27f40-131">Há três opções recomendadas para nomear suas URLs simples.</span><span class="sxs-lookup"><span data-stu-id="27f40-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="27f40-132">Qual opção você escolhe tem implicações para a maneira como configurar seus registros DNS A e certificados que dão suporte a URLs simples.</span><span class="sxs-lookup"><span data-stu-id="27f40-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="27f40-133">Em cada opção, você deve configurar uma URL simples de reunião para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="27f40-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="27f40-134">Você sempre precisa de apenas uma URL simples em toda a sua organização para discagem e outra para o administrador, independentemente de quantos domínios SIP você tem.</span><span class="sxs-lookup"><span data-stu-id="27f40-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="27f40-135">Para obter detalhes sobre os registros e certificados de DNS necessários, consulte [requisitos de DNS para URLs simples no Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="27f40-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="27f40-136">Na opção 1, crie um novo nome de domínio SIP para cada URL simples.</span><span class="sxs-lookup"><span data-stu-id="27f40-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="27f40-137">Se você usar essa opção, precisará de um registro DNS A separado para cada URL simples, e cada uma delas atenderá à URL simples deve ser nomeada em seus certificados.</span><span class="sxs-lookup"><span data-stu-id="27f40-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="27f40-138">Opção de nomeação de URL simples 1</span><span class="sxs-lookup"><span data-stu-id="27f40-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f40-139"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="27f40-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="27f40-140"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="27f40-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f40-141">Atendimento</span><span class="sxs-lookup"><span data-stu-id="27f40-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="27f40-142">https://meet.contoso.com, https://meet.fabrikam.come assim por diante (um para cada domínio SIP em sua organização)</span><span class="sxs-lookup"><span data-stu-id="27f40-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f40-143">Discagem</span><span class="sxs-lookup"><span data-stu-id="27f40-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f40-144">Locatário</span><span class="sxs-lookup"><span data-stu-id="27f40-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27f40-145">Com a opção 2, as URLs simples são baseadas no nome de domínio lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="27f40-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="27f40-146">Portanto, você precisa apenas de um registro de DNS que habilite todos os três tipos de URLs simples.</span><span class="sxs-lookup"><span data-stu-id="27f40-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="27f40-147">Esse registro DNS faz referência a lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="27f40-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="27f40-148">Além disso, você ainda precisa de registros DNS A separados para outros domínios SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="27f40-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="27f40-149">Opção de nomeação de URL simples 2</span><span class="sxs-lookup"><span data-stu-id="27f40-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f40-150"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="27f40-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="27f40-151"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="27f40-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f40-152">Atendimento</span><span class="sxs-lookup"><span data-stu-id="27f40-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="27f40-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meete assim por diante (um para cada domínio SIP em sua organização)</span><span class="sxs-lookup"><span data-stu-id="27f40-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f40-154">Discagem</span><span class="sxs-lookup"><span data-stu-id="27f40-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f40-155">Locatário</span><span class="sxs-lookup"><span data-stu-id="27f40-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27f40-156">A opção 3 será mais útil se você tiver muitos domínios SIP e quiser que eles tenham URLs simples de reunião e desejem minimizar o registro DNS e os requisitos de certificado para essas URLs simples.</span><span class="sxs-lookup"><span data-stu-id="27f40-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="27f40-157">Opção de nomeação de URL simples 3</span><span class="sxs-lookup"><span data-stu-id="27f40-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f40-158"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="27f40-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="27f40-159"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="27f40-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f40-160">Atendimento</span><span class="sxs-lookup"><span data-stu-id="27f40-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f40-161">Discagem</span><span class="sxs-lookup"><span data-stu-id="27f40-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f40-162">Locatário</span><span class="sxs-lookup"><span data-stu-id="27f40-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="27f40-163">Regras de nomenclatura e validação de URL simples</span><span class="sxs-lookup"><span data-stu-id="27f40-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="27f40-164">O construtor de topologias e os cmdlets do Shell de gerenciamento do Lync Server impõem várias regras de validação para suas URLs simples.</span><span class="sxs-lookup"><span data-stu-id="27f40-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="27f40-165">Você precisa definir URLs simples para atender e fazer chamadas, mas a configuração de um para administrador é opcional.</span><span class="sxs-lookup"><span data-stu-id="27f40-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="27f40-166">Cada domínio SIP deve ter uma URL simples de reunião separada, mas você precisa apenas de uma URL simples de discagem e uma URL simples de administrador para toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="27f40-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="27f40-167">Cada URL simples em sua organização deve ter um nome exclusivo e não pode ser um prefixo de outra URL simples (por exemplo, não foi possível definir lync.contoso.com/Meet como o seu URL simples e o lync.contoso.com/Meet/Dialin como sua URL simples de discagem).</span><span class="sxs-lookup"><span data-stu-id="27f40-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="27f40-168">Nomes de URL simples não podem conter o FQDN de qualquer um dos seus pools ou de qualquer informação de https://FQDN:88/meet porta (por exemplo, não é permitido).</span><span class="sxs-lookup"><span data-stu-id="27f40-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="27f40-169">Todas as URLs simples devem começar com o prefixo https://.</span><span class="sxs-lookup"><span data-stu-id="27f40-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="27f40-170">As URLs simples podem conter apenas caracteres alfanuméricos (ou seja, a-z, A-Z, 0-9 e ponto final (.).</span><span class="sxs-lookup"><span data-stu-id="27f40-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="27f40-171">Se você usar outros caracteres, as URLs simples podem não funcionar como esperado.</span><span class="sxs-lookup"><span data-stu-id="27f40-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="27f40-172">Alterar URLs simples após a implantação</span><span class="sxs-lookup"><span data-stu-id="27f40-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="27f40-173">Se você alterar uma URL simples após a implantação inicial, deve estar ciente de como a alteração afeta seus registros DNS e certificados para URLs simples.</span><span class="sxs-lookup"><span data-stu-id="27f40-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="27f40-174">Se a base de uma URL simples for alterada, você deverá alterar também os registros DNS e os certificados.</span><span class="sxs-lookup"><span data-stu-id="27f40-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="27f40-175">Por exemplo, mudar de https://lync.contoso.com/Meet para https://meet.contoso.com altera a URL base de Lync.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para se referirem ao Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="27f40-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="27f40-176">Se você alterou a URL simples https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingspara, a URL base de Lync.contoso.com permanece a mesma, portanto, não é necessária nenhuma alteração de DNS ou certificado.</span><span class="sxs-lookup"><span data-stu-id="27f40-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="27f40-177">No entanto, sempre que você alterar um nome de URL simples, você deve executar **Enable-CsComputer** em cada director e servidor front-end para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="27f40-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27f40-178">Confira também</span><span class="sxs-lookup"><span data-stu-id="27f40-178">See Also</span></span>


[<span data-ttu-id="27f40-179">Requisitos de DNS para URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27f40-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

