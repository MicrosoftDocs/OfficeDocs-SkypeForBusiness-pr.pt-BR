---
title: Identidades, escopos e locatários no Skype for Business Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b08c459f64a4655ebb4dc670255645f985452aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identidades, escopos e locatários no Skype for Business Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-03-09_

Muitos cmdlets do Windows PowerShell usados para gerenciar o Skype for Business online exigem que você seja muito específico sobre o item que está tentando gerenciar. Por exemplo, quando você executa o cmdlet [set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , você deve indicar qual usuário está tentando gerenciar. Isso faz sentido. A menos que você solicite especificamente o cmdlet que a conta de usuário gerenciar, o cmdlet **set-CsUserAcp** não tem a ideia de que as informações da conferência de áudio do usuário devem ser modificadas. Por esse motivo, cada vez que você executar o cmdlet **set-CsUserAcp** , será necessário incluir o parâmetro Identity, seguido da identidade da conta de usuário a ser modificada:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Se o termo *identidade* sempre se referir à identidade de uma conta de usuário, haveria algum motivo por confusão. Quando você está lidando com pessoas (usuários, contatos e assim por diante), as identidades fazem referência aos próprios usuários individuais. No entanto, itens que não sejam contas de usuário também têm identidades. Quando você está lidando com componentes do serviço Skype for Business online (políticas, configurações e assim por diante), o termo identidade significa algo ligeiramente diferente. Por exemplo, considere este comando:

    Get-CsMeetingConfiguration -Identity "global"

Nesse caso, a identidade "global" refere-se ao escopo das definições de configuração da reunião. *Escopo* é um termo usado no Skype for Business online (e no Lync Server) para designar esferas de gerenciamento. Por padrão, as políticas e configurações sempre têm um escopo global. Ao configurar pela primeira vez sua conta do Skype for Business Online, você terá, por padrão, um conjunto de políticas globais e configurações — configurações globais de reunião, uma política de acesso externo global, um plano de discagem global e assim por diante.

Essas políticas e configurações globais foram introduzidas no Microsoft Lync Server 2010 para ajudar a garantir que todos os usuários e todos os componentes sempre poderiam, de alguma maneira, serem gerenciados. Isso não foi necessariamente verdade no Microsoft Office Communicator 2007 R2. Dependendo de como você acessou o sistema, você pode acabar em um estado não gerenciado em grande parte (geralmente, porque a política de grupo não pôde ser aplicada à sua conta de usuário). Em contraste, no Lync Server e no Skype for Business Online, nunca é deixado não gerenciado. Isso ocorre porque, no lugar de qualquer outra coisa, políticas globais e configurações sempre serão impostas.

O que queremos dizer com "no lugar de qualquer outra coisa"? Bem, no caso do Skype for Business Online, é possível criar políticas no *escopo da marca*ou no círculo de gerenciamento. As políticas criadas no escopo da marca (também conhecido como *o escopo por usuário*) têm prioridade sobre as políticas criadas no escopo global. Em outras palavras, uma política por usuário sempre terá precedência sobre uma política global. Por exemplo, você pode ter duas políticas de acesso de usuário externo. A política global proíbe que os usuários se comuniquem com pessoas que têm contas em provedores públicos de mensagens instantâneas (IM), como o Windows Live. A política por usuário, AllowPublicIMCommunication, permite a comunicação com provedores de mensagens de chat públicas.

Você também pode ter dois usuários: Ken Myer e pilar Alverca. Ken Myer foi atribuído à política por usuário. Pilar Alverca não foi atribuída a uma política por usuário; ou seja, ele é gerenciado pela política de acesso externo global. A tabela a seguir mostra qual usuário (se houver) pode se comunicar com provedores de mensagens de chat públicos:


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
<td><p>O usuário pode se comunicar com provedores públicos de mensagens de chat</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
</tbody>
</table>


Como você pode ver, Ken Myer tem permissão para se comunicar com provedores de mensagens de chat públicos. Isso ocorre porque as configurações da política por usuário atribuídas a ele substituem as configurações na política global. Pilar Alverca não pode se comunicar com provedores de mensagens de chat públicas. Isso ocorre porque ela é gerenciada pela política global, e a política global proíbe essas comunicações.

Políticas por usuário devem ser criadas para você pelo suporte do Office 365. Após a criação das políticas, você pode atribuí-las aos usuários usando o cmdlet **Grant-cs** apropriado (por exemplo, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). Políticas por usuário são fáceis de identificar porque a identidade da política sempre começa com o **prefixo**da marca. Por exemplo:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> As datas de <STRONG>prefixo</STRONG> de marca de volta para os dias de desenvolvimento anteriores do Lync Server 2010. Nesses dias, as políticas por usuário eram chamadas de políticas de <EM>marca</EM> e foram identificadas pelo <STRONG>prefixo</STRONG>de marca. Essas políticas agora são mais precisamente conhecidas como <EM>políticas por usuário</EM>, e o escopo da marca é mais precisamente chamado como o <EM>escopo por usuário</EM>. No entanto, por motivos técnicos, o <STRONG>prefixo</STRONG> da marca nunca foi alterado.



</div>

Outro termo-chave usado ao trabalhar com o Skype for Business Online e com o Windows PowerShell é *locatário*. Ao configurar uma conta do Skype for Business Online, a nova implantação é atribuída a um número de ID de locatário, que é um GUID (Globally Unique Identifier) semelhante a isto:

    bf19b7db-6960-41e5-a139-2aa373474354

Alguns cmdlets do Skype for Business online exigem que você insira a ID do locatário sempre que executar o cmdlet. Você deve inserir a ID do locatário, mesmo se tiver feito logon em e apenas um locatário. Felizmente, você não precisa memorizar a ID do locatário. Você pode recuperar a sua ID de locatário a qualquer momento executando o seguinte comando do Windows PowerShell:

    Get-CsTenant | Select-Object TenantId

É claro, conhecer itens como a diferença entre o escopo global e o escopo por usuário (ou o escopo da marca) é apenas metade da batalha. Também é importante saber quando (ou mesmo se) você pode usar esses escopos. O mesmo se aplica às identidades e ao parâmetro locatário. Os tópicos a seguir descrevem como os diferentes cmdlets do Skype for Business online usam identidades, escopos e o parâmetro locatário:

  - [Cmdlets no Skype for Business online que usam apenas o escopo global](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets no Skype for Business online que usam o escopo global e o escopo de marca](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets no Skype for Business online que usam a identidade do usuário](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets no Skype for Business online que usam uma identidade de usuário e o escopo de marca](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets no Skype for Business online que usam o parâmetro locatário](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets no Skype for Business online que usam uma identidade de provedor de conferência](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets no Skype for Business online que não usam um escopo ou uma identidade](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

