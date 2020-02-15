---
title: 'Lync Server 2013: planejamento para URLs simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36e730aeef637c12102fbf425c04235d72eb382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="8a746-102">Planejamento de URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a746-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a746-103">_**Última modificação do tópico:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="8a746-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="8a746-104">URLs simples facilitam a associação de reuniões para seus usuários e facilitam a introdução às ferramentas administrativas do Lync Server para seus administradores.</span><span class="sxs-lookup"><span data-stu-id="8a746-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="8a746-105">O Lync Server oferece suporte a três URLs simples:</span><span class="sxs-lookup"><span data-stu-id="8a746-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="8a746-106">**Reunir** é usado como URL base para todas as conferências no site ou na organização.</span><span class="sxs-lookup"><span data-stu-id="8a746-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="8a746-107">Um exemplo de URL simples de reunião é https://meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8a746-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="8a746-108">Uma URL para uma reunião específica pode ser https://meet.contoso.com/ *username*/7322994.</span><span class="sxs-lookup"><span data-stu-id="8a746-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="8a746-109">Com o URL Reunir simples, os links para ingressar em reuniões são fáceis de compreender, de comunicar e distribuir.</span><span class="sxs-lookup"><span data-stu-id="8a746-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="8a746-110">**Discar** possibilita o acesso à página da web Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="8a746-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="8a746-111">Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência.</span><span class="sxs-lookup"><span data-stu-id="8a746-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="8a746-112">O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN.</span><span class="sxs-lookup"><span data-stu-id="8a746-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="8a746-113">Um exemplo da URL simples de discagem é https://dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8a746-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="8a746-114">O **administrador** permite acesso rápido ao painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a746-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="8a746-115">A partir de qualquer computador dentro de firewalls da sua organização, um administrador pode abrir o painel de controle do Lync Server digitando a URL simples do administrador em um navegador.</span><span class="sxs-lookup"><span data-stu-id="8a746-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="8a746-116">A URL simples de Admin é interna à organização.</span><span class="sxs-lookup"><span data-stu-id="8a746-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="8a746-117">Um exemplo da URL simples de admin éhttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8a746-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="8a746-118">Escopo do URL simples</span><span class="sxs-lookup"><span data-stu-id="8a746-118">Simple URL Scope</span></span>

<span data-ttu-id="8a746-119">Você pode configurar seus URLs simples para que tenham um escopo global ou você pode especificar URLs simples diferentes para cada site central na sua organização.</span><span class="sxs-lookup"><span data-stu-id="8a746-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="8a746-120">Se uma URL simples de escopo global e uma URL simples de escopo de site forem especificadas, a URL simples do escopo do site terá precedência.</span><span class="sxs-lookup"><span data-stu-id="8a746-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="8a746-p105">Na maioria dos casos, recomendamos que você defina URLs simples somente em um nível global, assim, o URL simples Reunir não é alterado se houver mudança de um site para outro. A exceção seria para organizações que precisam usar números de telefone diferentes para os usuários de discagem em locais diferentes. Observe que se você definir um URL simples (como o URL simples Discar) em um site para que ele seja um site de nível de URL simples, você deve definir também outros URLs simples para que eles também estejam no nível de site de URL simples.</span><span class="sxs-lookup"><span data-stu-id="8a746-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a746-124">Se você optar por usar URLs simples com escopo de site, os usuários não poderão se mover entre pools front-end em sites diferentes sem que os usuários reagendem todas as suas reuniões agendadas à medida que as URLs simples de reunião sejam diferentes entre sites.</span><span class="sxs-lookup"><span data-stu-id="8a746-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="8a746-125">Isso inclui cenários de failover em que os pools em relações de backup estão em sites separados.</span><span class="sxs-lookup"><span data-stu-id="8a746-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="8a746-126">Quando você precisar fazer failover entre sites onde as URLs simples com escopo de site são implantadas, os usuários não poderão ingressar em suas reuniões por causa do escopo da URL.</span><span class="sxs-lookup"><span data-stu-id="8a746-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="8a746-127">Para obter mais informações, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="8a746-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="8a746-128">Você pode definir URLs simples globais no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8a746-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="8a746-129">Para definir um URL simples no nível do site, você deve usar o cmdlet Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8a746-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="8a746-130">Nomeando seus URLs simples</span><span class="sxs-lookup"><span data-stu-id="8a746-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="8a746-p108">Existem três opções recomendadas para nomear seus URLs simples. A opção escolhida implica em como configurar seus registros A de DNS e os certificados que suportam URLs simples. Em cada opção, você deve configurar um URL de Reunião simples para cada domínio SIP na sua organização.</span><span class="sxs-lookup"><span data-stu-id="8a746-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="8a746-134">Você sempre precisa de um URL simples para toda sua organização para Discar e um para Administração, não importa quantos domínios SIP você tenha.</span><span class="sxs-lookup"><span data-stu-id="8a746-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="8a746-135">Para obter detalhes sobre os registros e certificados de DNS necessários, confira [requisitos de DNS para URLs simples no Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="8a746-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="8a746-136">Na Opção 1, você cria um novo nome de domínio SIP para cada URL simples.</span><span class="sxs-lookup"><span data-stu-id="8a746-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="8a746-137">Se usar esta opção, você precisará de um registro A de DNS separado para cada URL simples e cada URL Reunir simples deve ser nomeado em seus certificados.</span><span class="sxs-lookup"><span data-stu-id="8a746-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="8a746-138">Opção 1 de nome de URL simples</span><span class="sxs-lookup"><span data-stu-id="8a746-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a746-139"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="8a746-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="8a746-140"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="8a746-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a746-141">Cumpra</span><span class="sxs-lookup"><span data-stu-id="8a746-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="8a746-142">https://meet.contoso.com, https://meet.fabrikam.come assim por diante (um para cada domínio SIP em sua organização)</span><span class="sxs-lookup"><span data-stu-id="8a746-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a746-143">Discagem</span><span class="sxs-lookup"><span data-stu-id="8a746-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a746-144">Administrador</span><span class="sxs-lookup"><span data-stu-id="8a746-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8a746-p109">Com a opção 2, os URLs simples tem como base o nome de domínio lync.contoso.com. Por isso, você precisará somente de um registro A de DNS que permita todos os três tipos de URL simples. Esse registro A de DNS está relacionado a lync.contoso.com. além disso, você ainda precisa separar os registros A de DNS para os outros domínios SIP da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8a746-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="8a746-149">Opção 2 de nome de URL simples</span><span class="sxs-lookup"><span data-stu-id="8a746-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a746-150"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="8a746-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="8a746-151"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="8a746-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a746-152">Cumpra</span><span class="sxs-lookup"><span data-stu-id="8a746-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="8a746-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meete assim por diante (um para cada domínio SIP em sua organização)</span><span class="sxs-lookup"><span data-stu-id="8a746-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a746-154">Discagem</span><span class="sxs-lookup"><span data-stu-id="8a746-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a746-155">Administrador</span><span class="sxs-lookup"><span data-stu-id="8a746-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8a746-156">A opção 3 é mais útil se você tiver muitos domínios SIP e desejar que eles tenham URLs Reunir separadas, mas desejar minimizar o registro de DNS e os requisitos de certificação para esses URLs simples.</span><span class="sxs-lookup"><span data-stu-id="8a746-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="8a746-157">Opção 3 de nome de URL simples</span><span class="sxs-lookup"><span data-stu-id="8a746-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a746-158"><strong>URL simples</strong></span><span class="sxs-lookup"><span data-stu-id="8a746-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="8a746-159"><strong>Exemplo</strong></span><span class="sxs-lookup"><span data-stu-id="8a746-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a746-160">Cumpra</span><span class="sxs-lookup"><span data-stu-id="8a746-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a746-161">Discagem</span><span class="sxs-lookup"><span data-stu-id="8a746-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a746-162">Administrador</span><span class="sxs-lookup"><span data-stu-id="8a746-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="8a746-163">Nome e regras de validação de URLs simples</span><span class="sxs-lookup"><span data-stu-id="8a746-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="8a746-164">O construtor de topologias e os cmdlets do Shell de gerenciamento do Lync Server aplicam várias regras de validação para suas URLs simples.</span><span class="sxs-lookup"><span data-stu-id="8a746-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="8a746-165">Será solicitado que você defina URLs simples para Reunir e Discar, mas para Admin será opcional.</span><span class="sxs-lookup"><span data-stu-id="8a746-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="8a746-166">Cada domínio SIP deve ter um URL Reunir simples, mas você precisa somente de um URL Discar simples e um URL Admin simples para toda sua organização.</span><span class="sxs-lookup"><span data-stu-id="8a746-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="8a746-167">Cada URL simples na sua organização deve ter um nome exclusivo e não pode ser um prefixo para outra URL simples (por exemplo, você não pode definir lync.contoso.com/Reunir como sua URL de Reunião simples e 0lync/contoso.com/Reunir/Discar como sua URL de Discar simples).</span><span class="sxs-lookup"><span data-stu-id="8a746-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="8a746-168">Os nomes de URL simples não podem conter o FQDN de qualquer um dos seus pools ou qualquer informação de https://FQDN:88/meet porta (por exemplo, não é permitida).</span><span class="sxs-lookup"><span data-stu-id="8a746-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="8a746-169">Todas as URLs simples devem começar com o prefixo https://.</span><span class="sxs-lookup"><span data-stu-id="8a746-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="8a746-p112">URLs simples podem conter somente caracteres alfanuméricos (ou seja, a-z, A-Z, 0-9 e o ponto (.). Se você utilizar outros caracteres, o URL simples pode não funcionar como esperado.</span><span class="sxs-lookup"><span data-stu-id="8a746-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="8a746-172">Alteração de URLs simples após a implantação</span><span class="sxs-lookup"><span data-stu-id="8a746-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="8a746-173">Se você alterar uma URL simples após a implantação inicial, esteja ciente de quais alterações impactarão nos seus registros DNS e certificados para as URLs simples.</span><span class="sxs-lookup"><span data-stu-id="8a746-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="8a746-174">Se a alteração impactar a base de uma URL simples, você precisará alterar os registros de DNS e certificados também.</span><span class="sxs-lookup"><span data-stu-id="8a746-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="8a746-175">Por exemplo, alterar de https://lync.contoso.com/Meet para https://meet.contoso.com altera a URL base de Lync.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para fazer referência ao Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8a746-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="8a746-176">Se você alterou a URL simples https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingspara, a URL base do Lync.contoso.com permanecerá a mesma, portanto, não serão necessárias alterações de DNS ou de certificado.</span><span class="sxs-lookup"><span data-stu-id="8a746-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="8a746-177">No entanto, sempre que você alterar um nome de URL simples, deverá executar o **Enable-CsComputer** em cada diretor e servidor front-end para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="8a746-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a746-178">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a746-178">See Also</span></span>


[<span data-ttu-id="8a746-179">Requisitos de DNS para URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a746-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

