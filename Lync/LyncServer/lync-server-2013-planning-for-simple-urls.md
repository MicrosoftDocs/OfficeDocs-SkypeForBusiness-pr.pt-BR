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
ms.openlocfilehash: c6bbbe8650ae1d7746c9b87ecf4518236f8b1575
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Planejamento de URLs simples no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-12-11_

URLs simples facilitam a associação de reuniões para seus usuários e facilitam a introdução às ferramentas administrativas do Lync Server para seus administradores.

O Lync Server oferece suporte a três URLs simples:

  - **Reunir** é usado como URL base para todas as conferências no site ou na organização. Um exemplo de URL simples de reunião é https://meet.contoso.com. Uma URL para uma reunião específica pode ser https://meet.contoso.com/ *username*/7322994.
    
    Com o URL Reunir simples, os links para ingressar em reuniões são fáceis de compreender, de comunicar e distribuir.

  - **Discar** possibilita o acesso à página da web Configurações de Conferência Discada. Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência. O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN. Um exemplo da URL simples de discagem é https://dialin.contoso.com.

  - O **administrador** permite acesso rápido ao painel de controle do Lync Server. A partir de qualquer computador dentro de firewalls da sua organização, um administrador pode abrir o painel de controle do Lync Server digitando a URL simples do administrador em um navegador. A URL simples de Admin é interna à organização. Um exemplo da URL simples de admin éhttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Escopo do URL simples

Você pode configurar seus URLs simples para que tenham um escopo global ou você pode especificar URLs simples diferentes para cada site central na sua organização. Se uma URL simples de escopo global e uma URL simples de escopo de site forem especificadas, a URL simples do escopo do site terá precedência.

Na maioria dos casos, recomendamos que você defina URLs simples somente em um nível global, assim, o URL simples Reunir não é alterado se houver mudança de um site para outro. A exceção seria para organizações que precisam usar números de telefone diferentes para os usuários de discagem em locais diferentes. Observe que se você definir um URL simples (como o URL simples Discar) em um site para que ele seja um site de nível de URL simples, você deve definir também outros URLs simples para que eles também estejam no nível de site de URL simples.

<div>


> [!NOTE]  
> Se você optar por usar URLs simples com escopo de site, os usuários não poderão se mover entre pools front-end em sites diferentes sem que os usuários reagendem todas as suas reuniões agendadas à medida que as URLs simples de reunião sejam diferentes entre sites. Isso inclui cenários de failover em que os pools em relações de backup estão em sites separados. Quando você precisar fazer failover entre sites onde as URLs simples com escopo de site são implantadas, os usuários não poderão ingressar em suas reuniões por causa do escopo da URL. Para obter mais informações, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Você pode definir URLs simples globais no construtor de topologias. Para definir um URL simples no nível do site, você deve usar o cmdlet Set-CsSimpleURLConfiguration.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Nomeando seus URLs simples

Existem três opções recomendadas para nomear seus URLs simples. A opção escolhida implica em como configurar seus registros A de DNS e os certificados que suportam URLs simples. Em cada opção, você deve configurar um URL de Reunião simples para cada domínio SIP na sua organização.

Você sempre precisa de um URL simples para toda sua organização para Discar e um para Administração, não importa quantos domínios SIP você tenha.

Para obter detalhes sobre os registros e certificados de DNS necessários, confira [requisitos de DNS para URLs simples no Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.

Na Opção 1, você cria um novo nome de domínio SIP para cada URL simples.

Se usar esta opção, você precisará de um registro A de DNS separado para cada URL simples e cada URL Reunir simples deve ser nomeado em seus certificados.

### <a name="simple-url-naming-option-1"></a>Opção 1 de nome de URL simples

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL simples</strong></p></td>
<td><p><strong>Exemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Cumpra</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.come assim por diante (um para cada domínio SIP em sua organização)</p></td>
</tr>
<tr class="odd">
<td><p>Discagem</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Administrador</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Com a opção 2, os URLs simples tem como base o nome de domínio lync.contoso.com. Por isso, você precisará somente de um registro A de DNS que permita todos os três tipos de URL simples. Esse registro A de DNS está relacionado a lync.contoso.com. além disso, você ainda precisa separar os registros A de DNS para os outros domínios SIP da sua organização.

### <a name="simple-url-naming-option-2"></a>Opção 2 de nome de URL simples

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL simples</strong></p></td>
<td><p><strong>Exemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Cumpra</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meete assim por diante (um para cada domínio SIP em sua organização)</p></td>
</tr>
<tr class="odd">
<td><p>Discagem</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrador</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


A opção 3 é mais útil se você tiver muitos domínios SIP e desejar que eles tenham URLs Reunir separadas, mas desejar minimizar o registro de DNS e os requisitos de certificação para esses URLs simples.

### <a name="simple-url-naming-option-3"></a>Opção 3 de nome de URL simples

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>URL simples</strong></p></td>
<td><p><strong>Exemplo</strong></p></td>
</tr>
<tr class="even">
<td><p>Cumpra</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Discagem</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrador</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Nome e regras de validação de URLs simples

O construtor de topologias e os cmdlets do Shell de gerenciamento do Lync Server aplicam várias regras de validação para suas URLs simples. Será solicitado que você defina URLs simples para Reunir e Discar, mas para Admin será opcional. Cada domínio SIP deve ter um URL Reunir simples, mas você precisa somente de um URL Discar simples e um URL Admin simples para toda sua organização.

Cada URL simples na sua organização deve ter um nome exclusivo e não pode ser um prefixo para outra URL simples (por exemplo, você não pode definir lync.contoso.com/Reunir como sua URL de Reunião simples e 0lync/contoso.com/Reunir/Discar como sua URL de Discar simples). Os nomes de URL simples não podem conter o FQDN de qualquer um dos seus pools ou qualquer informação de https://FQDN:88/meet porta (por exemplo, não é permitida). Todas as URLs simples devem começar com o prefixo https://.

URLs simples podem conter somente caracteres alfanuméricos (ou seja, a-z, A-Z, 0-9 e o ponto (.). Se você utilizar outros caracteres, o URL simples pode não funcionar como esperado.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Alteração de URLs simples após a implantação

Se você alterar uma URL simples após a implantação inicial, esteja ciente de quais alterações impactarão nos seus registros DNS e certificados para as URLs simples. Se a alteração impactar a base de uma URL simples, você precisará alterar os registros de DNS e certificados também. Por exemplo, alterar de https://lync.contoso.com/Meet para https://meet.contoso.com altera a URL base de Lync.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para fazer referência ao Meet.contoso.com. Se você alterou a URL simples https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingspara, a URL base do Lync.contoso.com permanecerá a mesma, portanto, não serão necessárias alterações de DNS ou de certificado.

No entanto, sempre que você alterar um nome de URL simples, deverá executar o **Enable-CsComputer** em cada diretor e servidor front-end para registrar a alteração.

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos de DNS para URLs simples no Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

