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
# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identidades, escopos e locatários no Skype for Business Online

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-03-09_

Muitos dos cmdlets do Windows PowerShell usados para gerenciar o Skype for Business online exigem que você seja muito específico sobre o item que você está tentando gerenciar. Por exemplo, ao executar o cmdlet [set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , você deve indicar qual usuário está tentando gerenciar. Isso faz sentido. A menos que você informe especificamente ao cmdlet que a conta de usuário gerenciar, o cmdlet **set-CsUserAcp** não tem a idéia de que as informações de audioconferência de áudio do usuário devem ser modificadas. Por esse motivo, cada vez que você executar o cmdlet **set-CsUserAcp** , precisará incluir o parâmetro Identity, seguido da identidade da conta de usuário a ser modificada:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Se a *identidade* do termo for sempre referida à identidade de uma conta de usuário, haveria pouca causa de confusão. Quando você está lidando com pessoas (usuários, contatos e assim por diante), as identidades se referem aos próprios usuários individuais. No entanto, itens que não sejam contas de usuário também têm identidades. Quando você está lidando com componentes do serviço do Skype for Business online — políticas, definições de configuração e assim por diante, a identidade do termo significa algo um pouco diferente. Por exemplo, considere este comando:

    Get-CsMeetingConfiguration -Identity "global"

Nesse caso, a identidade "global" se refere ao escopo das definições de configuração de reunião. *Escopo* é um termo usado no Skype for Business online (e no Lync Server) para designar a partir do gerenciamento. Por padrão, políticas e configurações sempre têm um escopo global. Ao configurar pela primeira vez sua conta do Skype for Business Online, por padrão, um conjunto de políticas globais e configurações — definições globais de configuração de reunião, uma política de acesso externo global, um plano de discagem global e assim por diante.

Essas políticas e configurações globais foram introduzidas no Microsoft Lync Server 2010 para ajudar a garantir que todos os usuários e todos os componentes sempre, de alguma forma, sejam gerenciados. Isso não foi necessariamente verdadeiro no Microsoft Office Communicator 2007 R2. Dependendo de como você acessou o sistema, você poderia acabar em um estado amplamente não gerenciado (normalmente, porque a diretiva de grupo não pôde ser aplicada à sua conta de usuário). Por outro lado, no Lync Server e no Skype for Business Online, nada deixou de ser gerenciado. Isso ocorre porque, no lugar de qualquer outra coisa, as políticas globais e configurações sempre serão aplicadas.

O que queremos dizer "em vez de qualquer outra coisa"? Bem, no caso do Skype for Business Online, é possível criar políticas no *escopo da marca*ou no Sphere de gerenciamento. As políticas criadas no escopo de marca (também conhecido como *o escopo por usuário*) têm prioridade sobre as políticas criadas no escopo global. Em outras palavras, uma política por usuário sempre terá precedência sobre uma política global. Por exemplo, você pode ter duas políticas de acesso de usuário externo. A política global proíbe que os usuários se comuniquem com pessoas que têm contas em provedores públicos de mensagens instantâneas (IM), como o Windows Live. A política por usuário, AllowPublicIMCommunication, permite a comunicação com os provedores públicos de IM.

Você também pode ter dois usuários: Ken Myer e pilar Ackerman. Ken Myer foi atribuído à política por usuário. Pilar Ackerman não foi atribuído a uma política por usuário; ou seja, ela é gerenciada pela política de acesso externo global. A tabela a seguir mostra qual usuário (se houver) pode se comunicar com provedores de IM públicos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configurações de política</th>
<th>Ken Myer</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuração de política global para provedores públicos de IM</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Configuração de política por usuário para provedores públicos de IM</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>O usuário pode se comunicar com provedores públicos de IM</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
</tbody>
</table>


Como você pode ver, Ken Myer tem permissão para se comunicar com provedores de IM públicos. Isso ocorre porque as configurações da política por usuário atribuídas a ele substituem as configurações na política global. Pilar Ackerman não pode se comunicar com provedores de IM públicos. Isso ocorre porque ela é gerenciada pela política global e a política global proíbe essas comunicações.

As políticas por usuário devem ser criadas para você pelo suporte da Microsoft. Depois que as políticas são criadas, você pode atribuí-las aos usuários usando o cmdlet **Grant-cs** apropriado (por exemplo, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). As políticas por usuário são fáceis de identificar porque a identidade da política sempre começa com o **prefixo**da marca. Por exemplo:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> As datas de <STRONG>prefixo</STRONG> de marca de volta para os dias de desenvolvimento anteriores do Lync Server 2010. Nesses dias, as políticas por usuário foram chamadas de políticas de <EM>marca</EM> e foram identificadas pelo <STRONG>prefixo</STRONG>da marca. Agora, essas políticas são referidas com mais precisão como <EM>políticas por usuário</EM>e o escopo da marca é mais precisamente referido como o <EM>escopo por usuário</EM>. No entanto, por motivos técnicos, o <STRONG>prefixo</STRONG> da marca nunca foi alterado.



</div>

Outro termo importante usado ao trabalhar com o Skype for Business Online e o Windows PowerShell é *locatário*. Ao configurar uma conta do Skype for Business Online, a nova implantação é atribuída a um número de ID de locatário, que é um identificador global exclusivo (GUID) semelhante a este:

    bf19b7db-6960-41e5-a139-2aa373474354

Alguns dos cmdlets do Skype for Business online exigem que você insira a ID do locatário sempre que executar o cmdlet. Você deve inserir a ID de locatário, mesmo que tenha feito logon no e tenha apenas um locatário. Felizmente, não é necessário memorizar a ID do locatário. Você pode recuperar sua ID de locatário a qualquer momento executando o seguinte comando do Windows PowerShell:

    Get-CsTenant | Select-Object TenantId

Obviamente, conhecer coisas como a diferença entre o escopo global e o escopo por usuário (ou o escopo de marca) é apenas metade da batalha. Também é importante saber quando (ou mesmo se) você pode usar esses escopos. O mesmo é verdadeiro para identidades e o parâmetro de locatário. Os tópicos a seguir descrevem como os cmdlets diferentes do Skype for Business online usam identidades, escopos e o parâmetro locatário:

  - [Cmdlets no Skype for Business online que usam apenas o escopo global](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets no Skype for Business online que usam o escopo global e o escopo da marca](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets no Skype for Business online que usam uma identidade de usuário](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets no Skype for Business online que usam o parâmetro locatário](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets no Skype for Business online que usam uma identidade do provedor de conferência](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets no Skype for Business online que não usam um escopo ou uma identidade](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

