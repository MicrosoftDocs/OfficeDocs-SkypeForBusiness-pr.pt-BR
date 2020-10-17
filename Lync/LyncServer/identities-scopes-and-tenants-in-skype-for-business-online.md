---
title: Identidades, escopos e locatários no Skype for Business Online
description: Identidades, escopos e locatários no Skype for Business online.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00ab84c3ca83dea2e328315ae7e616ad7830c227
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552507"
---
# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="db648-103">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="db648-103">Identities, scopes, and tenants in Skype for Business Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db648-104">_**Última modificação do tópico:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="db648-104">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="db648-105">Muitos dos cmdlets do Windows PowerShell usados para gerenciar o Skype for Business online exigem que você seja muito específico sobre o item que você está tentando gerenciar.</span><span class="sxs-lookup"><span data-stu-id="db648-105">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="db648-106">Por exemplo, ao executar o cmdlet [set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , você deve indicar qual usuário está tentando gerenciar.</span><span class="sxs-lookup"><span data-stu-id="db648-106">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="db648-107">Isso faz sentido.</span><span class="sxs-lookup"><span data-stu-id="db648-107">This makes sense.</span></span> <span data-ttu-id="db648-108">A menos que você informe especificamente ao cmdlet que a conta de usuário gerenciar, o cmdlet **set-CsUserAcp** não tem a idéia de que as informações de audioconferência de áudio do usuário devem ser modificadas.</span><span class="sxs-lookup"><span data-stu-id="db648-108">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="db648-109">Por esse motivo, cada vez que você executar o cmdlet **set-CsUserAcp** , precisará incluir o parâmetro Identity, seguido da identidade da conta de usuário a ser modificada:</span><span class="sxs-lookup"><span data-stu-id="db648-109">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="db648-110">Se a *identidade* do termo for sempre referida à identidade de uma conta de usuário, haveria pouca causa de confusão.</span><span class="sxs-lookup"><span data-stu-id="db648-110">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="db648-111">Quando você está lidando com pessoas (usuários, contatos e assim por diante), as identidades se referem aos próprios usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="db648-111">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="db648-112">No entanto, itens que não sejam contas de usuário também têm identidades.</span><span class="sxs-lookup"><span data-stu-id="db648-112">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="db648-113">Quando você está lidando com componentes do serviço do Skype for Business online — políticas, definições de configuração e assim por diante, a identidade do termo significa algo um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="db648-113">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="db648-114">Por exemplo, considere este comando:</span><span class="sxs-lookup"><span data-stu-id="db648-114">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="db648-115">Nesse caso, a identidade "global" se refere ao escopo das definições de configuração de reunião.</span><span class="sxs-lookup"><span data-stu-id="db648-115">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="db648-116">*Escopo* é um termo usado no Skype for Business online (e no Lync Server) para designar a partir do gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="db648-116">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="db648-117">Por padrão, políticas e configurações sempre têm um escopo global.</span><span class="sxs-lookup"><span data-stu-id="db648-117">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="db648-118">Ao configurar pela primeira vez sua conta do Skype for Business Online, por padrão, um conjunto de políticas globais e configurações — definições globais de configuração de reunião, uma política de acesso externo global, um plano de discagem global e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="db648-118">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="db648-119">Essas políticas e configurações globais foram introduzidas no Microsoft Lync Server 2010 para ajudar a garantir que todos os usuários e todos os componentes sempre, de alguma forma, sejam gerenciados.</span><span class="sxs-lookup"><span data-stu-id="db648-119">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="db648-120">Isso não foi necessariamente verdadeiro no Microsoft Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="db648-120">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="db648-121">Dependendo de como você acessou o sistema, você poderia acabar em um estado amplamente não gerenciado (normalmente, porque a diretiva de grupo não pôde ser aplicada à sua conta de usuário).</span><span class="sxs-lookup"><span data-stu-id="db648-121">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="db648-122">Por outro lado, no Lync Server e no Skype for Business Online, nada deixou de ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="db648-122">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="db648-123">Isso ocorre porque, no lugar de qualquer outra coisa, as políticas globais e configurações sempre serão aplicadas.</span><span class="sxs-lookup"><span data-stu-id="db648-123">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="db648-124">O que queremos dizer "em vez de qualquer outra coisa"?</span><span class="sxs-lookup"><span data-stu-id="db648-124">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="db648-125">Bem, no caso do Skype for Business Online, é possível criar políticas no *escopo da marca*ou no Sphere de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="db648-125">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="db648-126">As políticas criadas no escopo de marca (também conhecido como *o escopo por usuário*) têm prioridade sobre as políticas criadas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="db648-126">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="db648-127">Em outras palavras, uma política por usuário sempre terá precedência sobre uma política global.</span><span class="sxs-lookup"><span data-stu-id="db648-127">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="db648-128">Por exemplo, você pode ter duas políticas de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="db648-128">For example, you might have two external user access policies.</span></span> <span data-ttu-id="db648-129">A política global proíbe que os usuários se comuniquem com pessoas que têm contas em provedores públicos de mensagens instantâneas (IM), como o Windows Live.</span><span class="sxs-lookup"><span data-stu-id="db648-129">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="db648-130">A política por usuário, AllowPublicIMCommunication, permite a comunicação com os provedores públicos de IM.</span><span class="sxs-lookup"><span data-stu-id="db648-130">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="db648-131">Você também pode ter dois usuários: Ken Myer e pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="db648-131">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="db648-132">Ken Myer foi atribuído à política por usuário.</span><span class="sxs-lookup"><span data-stu-id="db648-132">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="db648-133">Pilar Ackerman não foi atribuído a uma política por usuário; ou seja, ela é gerenciada pela política de acesso externo global.</span><span class="sxs-lookup"><span data-stu-id="db648-133">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="db648-134">A tabela a seguir mostra qual usuário (se houver) pode se comunicar com provedores de IM públicos:</span><span class="sxs-lookup"><span data-stu-id="db648-134">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db648-135">Configurações de política</span><span class="sxs-lookup"><span data-stu-id="db648-135">Policy Settings</span></span></th>
<th><span data-ttu-id="db648-136">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="db648-136">Ken Myer</span></span></th>
<th><span data-ttu-id="db648-137">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="db648-137">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db648-138">Configuração de política global para provedores públicos de IM</span><span class="sxs-lookup"><span data-stu-id="db648-138">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="db648-139">Não</span><span class="sxs-lookup"><span data-stu-id="db648-139">No</span></span></p></td>
<td><p><span data-ttu-id="db648-140">Não</span><span class="sxs-lookup"><span data-stu-id="db648-140">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db648-141">Configuração de política por usuário para provedores públicos de IM</span><span class="sxs-lookup"><span data-stu-id="db648-141">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="db648-142">Sim</span><span class="sxs-lookup"><span data-stu-id="db648-142">Yes</span></span></p></td>
<td><p><span data-ttu-id="db648-143">Não</span><span class="sxs-lookup"><span data-stu-id="db648-143">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db648-144">O usuário pode se comunicar com provedores públicos de IM</span><span class="sxs-lookup"><span data-stu-id="db648-144">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="db648-145">Sim</span><span class="sxs-lookup"><span data-stu-id="db648-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="db648-146">Não</span><span class="sxs-lookup"><span data-stu-id="db648-146">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db648-147">Como você pode ver, Ken Myer tem permissão para se comunicar com provedores de IM públicos.</span><span class="sxs-lookup"><span data-stu-id="db648-147">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="db648-148">Isso ocorre porque as configurações da política por usuário atribuídas a ele substituem as configurações na política global.</span><span class="sxs-lookup"><span data-stu-id="db648-148">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="db648-149">Pilar Ackerman não pode se comunicar com provedores de IM públicos.</span><span class="sxs-lookup"><span data-stu-id="db648-149">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="db648-150">Isso ocorre porque ela é gerenciada pela política global e a política global proíbe essas comunicações.</span><span class="sxs-lookup"><span data-stu-id="db648-150">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="db648-151">As políticas por usuário devem ser criadas para você pelo suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db648-151">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="db648-152">Depois que as políticas são criadas, você pode atribuí-las aos usuários usando o cmdlet **Grant-cs** apropriado (por exemplo, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="db648-152">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="db648-153">As políticas por usuário são fáceis de identificar porque a identidade da política sempre começa com o **prefixo**da marca.</span><span class="sxs-lookup"><span data-stu-id="db648-153">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="db648-154">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="db648-154">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="db648-155">As datas de <STRONG>prefixo</STRONG> de marca de volta para os dias de desenvolvimento anteriores do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="db648-155">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="db648-156">Nesses dias, as políticas por usuário foram chamadas de políticas de <EM>marca</EM> e foram identificadas pelo <STRONG>prefixo</STRONG>da marca.</span><span class="sxs-lookup"><span data-stu-id="db648-156">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="db648-157">Agora, essas políticas são referidas com mais precisão como <EM>políticas por usuário</EM>e o escopo da marca é mais precisamente referido como o <EM>escopo por usuário</EM>.</span><span class="sxs-lookup"><span data-stu-id="db648-157">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="db648-158">No entanto, por motivos técnicos, o <STRONG>prefixo</STRONG> da marca nunca foi alterado.</span><span class="sxs-lookup"><span data-stu-id="db648-158">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="db648-159">Outro termo importante usado ao trabalhar com o Skype for Business Online e o Windows PowerShell é *locatário*.</span><span class="sxs-lookup"><span data-stu-id="db648-159">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="db648-160">Ao configurar uma conta do Skype for Business Online, a nova implantação é atribuída a um número de ID de locatário, que é um identificador global exclusivo (GUID) semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="db648-160">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="db648-161">Alguns dos cmdlets do Skype for Business online exigem que você insira a ID do locatário sempre que executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="db648-161">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="db648-162">Você deve inserir a ID de locatário, mesmo que tenha feito logon no e tenha apenas um locatário.</span><span class="sxs-lookup"><span data-stu-id="db648-162">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="db648-163">Felizmente, não é necessário memorizar a ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="db648-163">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="db648-164">Você pode recuperar sua ID de locatário a qualquer momento executando o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="db648-164">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="db648-165">Obviamente, conhecer coisas como a diferença entre o escopo global e o escopo por usuário (ou o escopo de marca) é apenas metade da batalha.</span><span class="sxs-lookup"><span data-stu-id="db648-165">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="db648-166">Também é importante saber quando (ou mesmo se) você pode usar esses escopos.</span><span class="sxs-lookup"><span data-stu-id="db648-166">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="db648-167">O mesmo é verdadeiro para identidades e o parâmetro de locatário.</span><span class="sxs-lookup"><span data-stu-id="db648-167">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="db648-168">Os tópicos a seguir descrevem como os cmdlets diferentes do Skype for Business online usam identidades, escopos e o parâmetro locatário:</span><span class="sxs-lookup"><span data-stu-id="db648-168">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="db648-169">Cmdlets no Skype for Business online que usam apenas o escopo global</span><span class="sxs-lookup"><span data-stu-id="db648-169">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="db648-170">Cmdlets no Skype for Business online que usam o escopo global e o escopo da marca</span><span class="sxs-lookup"><span data-stu-id="db648-170">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="db648-171">Cmdlets no Skype for Business online que usam uma identidade de usuário</span><span class="sxs-lookup"><span data-stu-id="db648-171">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="db648-172">Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca</span><span class="sxs-lookup"><span data-stu-id="db648-172">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="db648-173">Cmdlets no Skype for Business online que usam o parâmetro locatário</span><span class="sxs-lookup"><span data-stu-id="db648-173">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="db648-174">Cmdlets no Skype for Business online que usam uma identidade do provedor de conferência</span><span class="sxs-lookup"><span data-stu-id="db648-174">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="db648-175">Cmdlets no Skype for Business online que não usam um escopo ou uma identidade</span><span class="sxs-lookup"><span data-stu-id="db648-175">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

