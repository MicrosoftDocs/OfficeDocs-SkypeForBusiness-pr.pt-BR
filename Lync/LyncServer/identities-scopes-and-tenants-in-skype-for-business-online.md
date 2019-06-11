---
title: Identidades, escopos e locatários no Skype for Business Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a759c53b717cbaf1ecdb747d5cb01e94b305f52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="429eb-102">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="429eb-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="429eb-103">_**Tópico da última modificação:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="429eb-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="429eb-104">Muitos cmdlets do Windows PowerShell usados para gerenciar o Skype for Business online exigem que você seja muito específico sobre o item que está tentando gerenciar.</span><span class="sxs-lookup"><span data-stu-id="429eb-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="429eb-105">Por exemplo, quando você executa o cmdlet [set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , você deve indicar qual usuário está tentando gerenciar.</span><span class="sxs-lookup"><span data-stu-id="429eb-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="429eb-106">Isso faz sentido.</span><span class="sxs-lookup"><span data-stu-id="429eb-106">This makes sense.</span></span> <span data-ttu-id="429eb-107">A menos que você solicite especificamente o cmdlet que a conta de usuário gerenciar, o cmdlet **set-CsUserAcp** não tem a ideia de que as informações da conferência de áudio do usuário devem ser modificadas.</span><span class="sxs-lookup"><span data-stu-id="429eb-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="429eb-108">Por esse motivo, cada vez que você executar o cmdlet **set-CsUserAcp** , será necessário incluir o parâmetro Identity, seguido da identidade da conta de usuário a ser modificada:</span><span class="sxs-lookup"><span data-stu-id="429eb-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="429eb-109">Se o termo *identidade* sempre se referir à identidade de uma conta de usuário, haveria algum motivo por confusão.</span><span class="sxs-lookup"><span data-stu-id="429eb-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="429eb-110">Quando você está lidando com pessoas (usuários, contatos e assim por diante), as identidades fazem referência aos próprios usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="429eb-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="429eb-111">No entanto, itens que não sejam contas de usuário também têm identidades.</span><span class="sxs-lookup"><span data-stu-id="429eb-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="429eb-112">Quando você está lidando com componentes do serviço Skype for Business online (políticas, configurações e assim por diante), o termo identidade significa algo ligeiramente diferente.</span><span class="sxs-lookup"><span data-stu-id="429eb-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="429eb-113">Por exemplo, considere este comando:</span><span class="sxs-lookup"><span data-stu-id="429eb-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="429eb-114">Nesse caso, a identidade "global" refere-se ao escopo das definições de configuração da reunião.</span><span class="sxs-lookup"><span data-stu-id="429eb-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="429eb-115">*Escopo* é um termo usado no Skype for Business online (e no Lync Server) para designar esferas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="429eb-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="429eb-116">Por padrão, as políticas e configurações sempre têm um escopo global.</span><span class="sxs-lookup"><span data-stu-id="429eb-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="429eb-117">Ao configurar pela primeira vez sua conta do Skype for Business Online, você terá, por padrão, um conjunto de políticas globais e configurações — configurações globais de reunião, uma política de acesso externo global, um plano de discagem global e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="429eb-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="429eb-118">Essas políticas e configurações globais foram introduzidas no Microsoft Lync Server 2010 para ajudar a garantir que todos os usuários e todos os componentes sempre poderiam, de alguma maneira, serem gerenciados.</span><span class="sxs-lookup"><span data-stu-id="429eb-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="429eb-119">Isso não foi necessariamente verdade no Microsoft Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="429eb-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="429eb-120">Dependendo de como você acessou o sistema, você pode acabar em um estado não gerenciado em grande parte (geralmente, porque a política de grupo não pôde ser aplicada à sua conta de usuário).</span><span class="sxs-lookup"><span data-stu-id="429eb-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="429eb-121">Em contraste, no Lync Server e no Skype for Business Online, nunca é deixado não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="429eb-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="429eb-122">Isso ocorre porque, no lugar de qualquer outra coisa, políticas globais e configurações sempre serão impostas.</span><span class="sxs-lookup"><span data-stu-id="429eb-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="429eb-123">O que queremos dizer com "no lugar de qualquer outra coisa"?</span><span class="sxs-lookup"><span data-stu-id="429eb-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="429eb-124">Bem, no caso do Skype for Business Online, é possível criar políticas no *escopo da marca*ou no círculo de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="429eb-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="429eb-125">As políticas criadas no escopo da marca (também conhecido como *o escopo por usuário*) têm prioridade sobre as políticas criadas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="429eb-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="429eb-126">Em outras palavras, uma política por usuário sempre terá precedência sobre uma política global.</span><span class="sxs-lookup"><span data-stu-id="429eb-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="429eb-127">Por exemplo, você pode ter duas políticas de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="429eb-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="429eb-128">A política global proíbe que os usuários se comuniquem com pessoas que têm contas em provedores públicos de mensagens instantâneas (IM), como o Windows Live.</span><span class="sxs-lookup"><span data-stu-id="429eb-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="429eb-129">A política por usuário, AllowPublicIMCommunication, permite a comunicação com provedores de mensagens de chat públicas.</span><span class="sxs-lookup"><span data-stu-id="429eb-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="429eb-130">Você também pode ter dois usuários: Ken Myer e pilar Alverca.</span><span class="sxs-lookup"><span data-stu-id="429eb-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="429eb-131">Ken Myer foi atribuído à política por usuário.</span><span class="sxs-lookup"><span data-stu-id="429eb-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="429eb-132">Pilar Alverca não foi atribuída a uma política por usuário; ou seja, ele é gerenciado pela política de acesso externo global.</span><span class="sxs-lookup"><span data-stu-id="429eb-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="429eb-133">A tabela a seguir mostra qual usuário (se houver) pode se comunicar com provedores de mensagens de chat públicos:</span><span class="sxs-lookup"><span data-stu-id="429eb-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="429eb-134">Configurações de política</span><span class="sxs-lookup"><span data-stu-id="429eb-134">Policy Settings</span></span></th>
<th><span data-ttu-id="429eb-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="429eb-135">Ken Myer</span></span></th>
<th><span data-ttu-id="429eb-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="429eb-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="429eb-137">Configuração de política global para provedores públicos de IM</span><span class="sxs-lookup"><span data-stu-id="429eb-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="429eb-138">Não</span><span class="sxs-lookup"><span data-stu-id="429eb-138">No</span></span></p></td>
<td><p><span data-ttu-id="429eb-139">Não</span><span class="sxs-lookup"><span data-stu-id="429eb-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="429eb-140">Configuração de política por usuário para provedores públicos de IM</span><span class="sxs-lookup"><span data-stu-id="429eb-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="429eb-141">Sim</span><span class="sxs-lookup"><span data-stu-id="429eb-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="429eb-142">Não</span><span class="sxs-lookup"><span data-stu-id="429eb-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="429eb-143">O usuário pode se comunicar com provedores públicos de mensagens de chat</span><span class="sxs-lookup"><span data-stu-id="429eb-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="429eb-144">Sim</span><span class="sxs-lookup"><span data-stu-id="429eb-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="429eb-145">Não</span><span class="sxs-lookup"><span data-stu-id="429eb-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="429eb-146">Como você pode ver, Ken Myer tem permissão para se comunicar com provedores de mensagens de chat públicos.</span><span class="sxs-lookup"><span data-stu-id="429eb-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="429eb-147">Isso ocorre porque as configurações da política por usuário atribuídas a ele substituem as configurações na política global.</span><span class="sxs-lookup"><span data-stu-id="429eb-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="429eb-148">Pilar Alverca não pode se comunicar com provedores de mensagens de chat públicas.</span><span class="sxs-lookup"><span data-stu-id="429eb-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="429eb-149">Isso ocorre porque ela é gerenciada pela política global, e a política global proíbe essas comunicações.</span><span class="sxs-lookup"><span data-stu-id="429eb-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="429eb-150">Políticas por usuário devem ser criadas para você pelo suporte do Office 365.</span><span class="sxs-lookup"><span data-stu-id="429eb-150">Per-user policies must be created for you by Office 365 Support.</span></span> <span data-ttu-id="429eb-151">Após a criação das políticas, você pode atribuí-las aos usuários usando o cmdlet **Grant-cs** apropriado (por exemplo, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="429eb-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="429eb-152">Políticas por usuário são fáceis de identificar porque a identidade da política sempre começa com o **prefixo**da marca.</span><span class="sxs-lookup"><span data-stu-id="429eb-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="429eb-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="429eb-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="429eb-154">As datas de <STRONG>prefixo</STRONG> de marca de volta para os dias de desenvolvimento anteriores do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="429eb-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="429eb-155">Nesses dias, as políticas por usuário eram chamadas de políticas de <EM>marca</EM> e foram identificadas pelo <STRONG>prefixo</STRONG>de marca.</span><span class="sxs-lookup"><span data-stu-id="429eb-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="429eb-156">Essas políticas agora são mais precisamente conhecidas como <EM>políticas por usuário</EM>, e o escopo da marca é mais precisamente chamado como o <EM>escopo por usuário</EM>.</span><span class="sxs-lookup"><span data-stu-id="429eb-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="429eb-157">No entanto, por motivos técnicos, o <STRONG>prefixo</STRONG> da marca nunca foi alterado.</span><span class="sxs-lookup"><span data-stu-id="429eb-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="429eb-158">Outro termo-chave usado ao trabalhar com o Skype for Business Online e com o Windows PowerShell é *locatário*.</span><span class="sxs-lookup"><span data-stu-id="429eb-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="429eb-159">Ao configurar uma conta do Skype for Business Online, a nova implantação é atribuída a um número de ID de locatário, que é um GUID (Globally Unique Identifier) semelhante a isto:</span><span class="sxs-lookup"><span data-stu-id="429eb-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="429eb-160">Alguns cmdlets do Skype for Business online exigem que você insira a ID do locatário sempre que executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="429eb-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="429eb-161">Você deve inserir a ID do locatário, mesmo se tiver feito logon em e apenas um locatário.</span><span class="sxs-lookup"><span data-stu-id="429eb-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="429eb-162">Felizmente, você não precisa memorizar a ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="429eb-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="429eb-163">Você pode recuperar a sua ID de locatário a qualquer momento executando o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="429eb-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="429eb-164">É claro, conhecer itens como a diferença entre o escopo global e o escopo por usuário (ou o escopo da marca) é apenas metade da batalha.</span><span class="sxs-lookup"><span data-stu-id="429eb-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="429eb-165">Também é importante saber quando (ou mesmo se) você pode usar esses escopos.</span><span class="sxs-lookup"><span data-stu-id="429eb-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="429eb-166">O mesmo se aplica às identidades e ao parâmetro locatário.</span><span class="sxs-lookup"><span data-stu-id="429eb-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="429eb-167">Os tópicos a seguir descrevem como os diferentes cmdlets do Skype for Business online usam identidades, escopos e o parâmetro locatário:</span><span class="sxs-lookup"><span data-stu-id="429eb-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="429eb-168">Cmdlets no Skype for Business online que usam apenas o escopo global</span><span class="sxs-lookup"><span data-stu-id="429eb-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="429eb-169">Cmdlets no Skype for Business online que usam o escopo global e o escopo de marca</span><span class="sxs-lookup"><span data-stu-id="429eb-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="429eb-170">Cmdlets no Skype for Business online que usam a identidade do usuário</span><span class="sxs-lookup"><span data-stu-id="429eb-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="429eb-171">Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca</span><span class="sxs-lookup"><span data-stu-id="429eb-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="429eb-172">Cmdlets no Skype for Business online que usam o parâmetro locatário</span><span class="sxs-lookup"><span data-stu-id="429eb-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="429eb-173">Cmdlets no Skype for Business online que usam uma identidade de provedor de conferência</span><span class="sxs-lookup"><span data-stu-id="429eb-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="429eb-174">Cmdlets no Skype for Business online que não usam um escopo ou uma identidade</span><span class="sxs-lookup"><span data-stu-id="429eb-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

