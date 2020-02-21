---
title: 'Lync Server 2013: testar direitos de topologia de administração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 050ba83b4598fc5ed8ed3d40d0b1aa02ba9356b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Testar os direitos de topologia de administração no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Agenda de verificação</p></td>
<td><p>Após a implantação inicial do Lync Server. Conforme necessário se surgirem problemas relacionados à permissão.</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões obrigatórias</p></td>
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsSetupPermission. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Por padrão, somente os administradores de domínio podem habilitar uma topologia do Lync Server e fazer grandes alterações na infraestrutura do Lync Server. Isso não será um problema, contanto que seus administradores de domínio e seus administradores do Lync Server sejam os mesmos. Em muitas organizações, os administradores do Lync Server não retêm direitos administrativos em todo o domínio. Por padrão, isso significa que esses administradores (definidos como membros do grupo RTCUniversalServerAdmins) não podem fazer alterações de topologia do Lync Server. Para dar aos membros do grupo RTCUniversalServerAdmins o direito de fazer alterações de topologia, você deve atribuir as permissões do Active Directory necessárias usando o cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .

O cmdlet Test-CsSetupPermission verifica se as permissões necessárias necessárias para instalar o Lync Server ou um de seus componentes estão configuradas no contêiner do Active Directory especificado. Se as permissões não forem atribuídas, você poderá executar o cmdlet Grant-CsSetupPermission para dar aos membros do grupo RTCUniversalServerAdmins o direito de instalar e habilitar o Lync Server.

<div>


> [!NOTE]  
> Para obter uma lista detalhada de permissões atribuídas pelo Grant-CsSetupPermission, consulte o blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission e Grant-CsOUPermission</A>.



</div>

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para determinar se as permissões de configuração são atribuídas a um contêiner do Active Directory, chame o cmdlet Test-CsSetupPermission. Especifique o nome distinto do contêiner a ser verificado. Por exemplo, este comando verifica as permissões de instalação no contêiner ou = CsServers, DC = litwareinc, DC = com:

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se Test-CsSetupPermission determinar que as permissões necessárias já foram definidas em um contêiner do Active Directory, o cmdlet retornará o valor true:

True

Se as permissões não forem definidas, Test-CsSetupPermission retornará o valor false. Observe que esse valor normalmente será incluído em várias mensagens de aviso. Por exemplo:

Aviso: entrada de controle de acesso (ACE) ATL-cs\\-001 RTCUniversalServerAdmins; Permitiu ExtendedRight; Nenhum Nenhum 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

Aviso: as entradas de controle de acesso (ACEs) no objeto "CN = computadores, DC = litwareinc, DC = com" não estão prontas.

Falso

Aviso: o processamento de "Test-CsSetupPermission" foi concluído com avisos. os avisos "2" foram registrados durante esta execução.

Aviso: resultados detalhados podem ser encontrados em "C\\:\\Users\\admin\\\\local\\Temp-CsSetupPermission-1da99ba6-abe2-45E4-8b16-dfd244763118. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Embora haja raras exceções, se Test-CsSetupPermission falhar, isso normalmente significa que as permissões de configuração não são atribuídas para o contêiner do Active Directory especificado. Essas permissões podem ser atribuídas usando o cmdlet Grant-CsSetupPermission. Por exemplo, esse comando concede permissões de configuração para o contêiner de computadores no domínio litwareinc.com:

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

