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

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Planejamento de URLs simples no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-12-11_

URLs simples facilitam a junção de reuniões para seus usuários e facilitam a obtenção de ferramentas administrativas do Lync Server para seus administradores.

O Lync Server oferece suporte a três URLs simples:

  - A **reunião** é usada como a URL base para todas as conferências no site ou na organização. Um exemplo de uma URL de reunião simples https://meet.contoso.comé. Uma URL para uma reunião específica pode ser https://meet.contoso.com/ *nome de usuário*/7322994.
    
    Com a URL simples de reunião, os links para ingressar em reuniões são fáceis de compreender e fáceis de se comunicar e distribuir.

  - **** A discagem permite o acesso à página da Web configurações de conferência discada. Esta página mostra os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (para reuniões que não necessitam de agendamento), controles DTMF durante a conferência, suporte de gerenciamento do PIN (número de identificação pessoal) e informações atribuídas da conferência. A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias. Um exemplo da URL simples de discagem é https://dialin.contoso.com.

  - O **administrador** habilita o acesso rápido ao painel de controle do Lync Server. Em qualquer computador dentro dos firewalls da sua organização, um administrador pode abrir o painel de controle do Lync Server digitando a URL simples do administrador em um navegador. A URL simples de Admin é parte interna da sua organização. Um exemplo da URL simples de administrador éhttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Escopo de URL simples

Você pode configurar suas URLs simples para ter escopo global ou pode especificar diferentes URLs simples para cada site central em sua organização. Se tanto uma URL simples de escopo global quanto uma URL simples de escopo de site forem especificadas, a URL simples de escopo do site terá precedência.

Na maioria dos casos, recomendamos que você defina URLs simples somente no nível global, de modo que a URL simples de um usuário não seja alterada se passar de um site para outro. A exceção seria organizações que precisam usar números de telefone diferentes para usuários de discagem em sites diferentes. Observe que, se você definir uma URL simples (como a URL simples de discagem) em um site para ser uma URL simples no nível do site, também deverá definir que outras URLs simples nesse site também sejam no nível do site.

<div>


> [!NOTE]  
> Se você optar por usar URLs simples com escopo de site, os usuários não poderão se mover entre os pools front-end em sites diferentes sem que esses usuários reagendem todas as suas reuniões agendadas, pois as URLs simples de reunião são diferentes entre sites. Isso inclui cenários de failover em que os pools de relações de backup estão em sites separados. Quando você precisar fazer failover entre sites onde URLs simples com escopo de site são implantadas, os usuários não poderão ingressar em suas reuniões devido ao escopo da URL. Para obter mais informações, confira <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Você pode definir URLs simples globais no construtor de topologias. Para definir uma URL simples no nível do site, você deve usar o cmdlet Set-CsSimpleURLConfiguration.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Nomeando suas URLs simples

Há três opções recomendadas para nomear suas URLs simples. Qual opção você escolhe tem implicações para a maneira como configurar seus registros DNS A e certificados que dão suporte a URLs simples. Em cada opção, você deve configurar uma URL simples de reunião para cada domínio SIP em sua organização.

Você sempre precisa de apenas uma URL simples em toda a sua organização para discagem e outra para o administrador, independentemente de quantos domínios SIP você tem.

Para obter detalhes sobre os registros e certificados de DNS necessários, consulte [requisitos de DNS para URLs simples no Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.

Na opção 1, crie um novo nome de domínio SIP para cada URL simples.

Se você usar essa opção, precisará de um registro DNS A separado para cada URL simples, e cada uma delas atenderá à URL simples deve ser nomeada em seus certificados.

### <a name="simple-url-naming-option-1"></a>Opção de nomeação de URL simples 1

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
<td><p>Atendimento</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.come assim por diante (um para cada domínio SIP em sua organização)</p></td>
</tr>
<tr class="odd">
<td><p>Discagem</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Locatário</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Com a opção 2, as URLs simples são baseadas no nome de domínio lync.contoso.com. Portanto, você precisa apenas de um registro de DNS que habilite todos os três tipos de URLs simples. Esse registro DNS faz referência a lync.contoso.com. Além disso, você ainda precisa de registros DNS A separados para outros domínios SIP em sua organização.

### <a name="simple-url-naming-option-2"></a>Opção de nomeação de URL simples 2

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
<td><p>Atendimento</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meete assim por diante (um para cada domínio SIP em sua organização)</p></td>
</tr>
<tr class="odd">
<td><p>Discagem</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Locatário</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


A opção 3 será mais útil se você tiver muitos domínios SIP e quiser que eles tenham URLs simples de reunião e desejem minimizar o registro DNS e os requisitos de certificado para essas URLs simples.

### <a name="simple-url-naming-option-3"></a>Opção de nomeação de URL simples 3

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
<td><p>Atendimento</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Discagem</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Locatário</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Regras de nomenclatura e validação de URL simples

O construtor de topologias e os cmdlets do Shell de gerenciamento do Lync Server impõem várias regras de validação para suas URLs simples. Você precisa definir URLs simples para atender e fazer chamadas, mas a configuração de um para administrador é opcional. Cada domínio SIP deve ter uma URL simples de reunião separada, mas você precisa apenas de uma URL simples de discagem e uma URL simples de administrador para toda a sua organização.

Cada URL simples em sua organização deve ter um nome exclusivo e não pode ser um prefixo de outra URL simples (por exemplo, não foi possível definir lync.contoso.com/Meet como o seu URL simples e o lync.contoso.com/Meet/Dialin como sua URL simples de discagem). Nomes de URL simples não podem conter o FQDN de qualquer um dos seus pools ou de qualquer informação de https://FQDN:88/meet porta (por exemplo, não é permitido). Todas as URLs simples devem começar com o prefixo https://.

As URLs simples podem conter apenas caracteres alfanuméricos (ou seja, a-z, A-Z, 0-9 e ponto final (.). Se você usar outros caracteres, as URLs simples podem não funcionar como esperado.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Alterar URLs simples após a implantação

Se você alterar uma URL simples após a implantação inicial, deve estar ciente de como a alteração afeta seus registros DNS e certificados para URLs simples. Se a base de uma URL simples for alterada, você deverá alterar também os registros DNS e os certificados. Por exemplo, mudar de https://lync.contoso.com/Meet para https://meet.contoso.com altera a URL base de Lync.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para se referirem ao Meet.contoso.com. Se você alterou a URL simples https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingspara, a URL base de Lync.contoso.com permanece a mesma, portanto, não é necessária nenhuma alteração de DNS ou certificado.

No entanto, sempre que você alterar um nome de URL simples, você deve executar **Enable-CsComputer** em cada director e servidor front-end para registrar a alteração.

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

