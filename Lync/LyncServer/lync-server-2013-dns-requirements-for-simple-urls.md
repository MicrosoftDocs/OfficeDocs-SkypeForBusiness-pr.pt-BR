---
title: 'Lync Server 2013: requisitos de DNS para URLs simples'
description: 'Lync Server 2013: requisitos de DNS para URLs simples.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564957"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Requisitos de DNS para URLs simples no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

O Lync Server 2013 oferece suporte a URLs simples, que facilitam a associação de reuniões para seus usuários e facilitam o acesso às ferramentas administrativas do Lync Server para seus administradores. Para obter detalhes sobre URLs simples, consulte [Planning for Simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

O Lync Server suporta as seguintes três URLs simples: atender, discar e administrador. É necessário configurar URLs simples para a reunião e discagem, e a URL simples do administrador é opcional. Os registros de DNS (Sistema de Nomes de Domínio) necessários para dar suporte às URLs simples dependem de como elas foram definidas e de você deseja dar suporte à recuperação de desastre para URLs simples.

<div>

## <a name="simple-url-option-1"></a>Opção 1 de URL simples

Na Opção 1, você cria uma nova URL de base para cada URL simples.

<div class="">


> [!NOTE]  
> Quando um usuário clica no link de reunião de uma URL simples, o servidor que o registro do DNS A resolve determina o software do cliente correto para iniciar. Depois que o software de cliente é iniciado, ele se comunica automaticamente com o pool em que a conferência está hospedada. Assim, os usuários são encaminhados ao servidor apropriado para o conteúdo da reunião, independente do servidor ou pool para o qual os registros de DNS A da URL resolvem.



</div>

### <a name="simple-url-option-1"></a>Opção 1 de URL simples

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
<td><p>https://meet.contoso.com, https://meet.fabrikam.com e assim por diante (um para cada domínio SIP em sua organização)</p></td>
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


Se você usar a Opção 1, defina o seguinte:

  - Para cada URL simples Reunir, você precisa de um registro DNS A que resolva a URL para o endereço IP do Diretor, se estiver implantado. Do contrário, ele deve resolver para o endereço IP do balanceador de carga ou do pool de Front-End. Se você não implantou um pool e está usando a implantação de servidor do Standard Edition, o registro de DNS A deve resolver para o endereço IP do servidor do Standard Edition na sua organização.
    
    Se você tiver mais de um domínio SIP em sua organização e usar essa opção, crie URLs simples Reunir para cada domínio SIP; um registro de DNS A é necessário para cada uma dessas URLs. Por exemplo, se você tiver o contoso.com e o fabrikam.com, criará registros DNS A para o https://meet.contoso.com e o https://meet.fabrikam.com .
    
    Ou então, se você tiver vários domínios SIP e deseja minimizar os registros de DNS e requisitos de certificado para essas URLs simples, use a Opção 3 descrita adiante neste tópico.

  - Para a URL simples Discar, você precisa de um registro DNS A que resolva a URL para o endereço IP do Diretor, se estiver implantado. Do contrário, ele deve resolver para o endereço IP do balanceador de carga ou do pool de Front-End. Se você não implantou um pool e está usando a implantação de servidor do Standard Edition, o registro de DNS A deve resolver para o endereço IP do servidor do Standard Edition na sua organização.

  - A URL simples Admin é apenas interna. Ela exige um registro DNS A que resolva a URL para o endereço IP do Diretor, se estiver implantado. Do contrário, ele deve resolver para o endereço IP do balanceador de carga ou do pool de Front-End. Se você não implantou um pool e está usando a implantação de servidor do Standard Edition, o registro de DNS A deve resolver para o endereço IP do servidor do Standard Edition na sua organização.

</div>

<div>

## <a name="simple-url-option-2"></a>Opção 2 de URL simples

Na Opção 2, as URLs simples Reunir, Discar e Admin têm uma URL de base comum, como lync.contoso.com. Portanto, você só precisa de um registro de DNS A para essas URLs simples, que resolve lync.contoso.com para o endereço IP de um pool do Diretor ou pool de Front-End. Se você não implantou um pool e está usando a implantação de servidor do Standard Edition, o registro de DNS A deve resolver para o endereço IP do servidor do Standard Edition na sua organização.

Observe que se você tiver mais de um domínio SIP em sua organização, deve criar URLs simples Reunir para cada domínio SIP; um registro de DNS A é necessário para cada uma dessas URLs. Neste exemplo, embora três URLs simples sejam baseadas no lync.contoso.com, uma URL simples Reunir adicional para fabrikam.com é configurada com uma URL de base diferente. Neste exemplo, você deve criar registros DNS A para o https://lync.contoso.com e o https://lync.fabrikam.com . A Opção 3 de URL Simples mostra outra maneira de manipular a nomeação e os registros de DNS A, se você tiver vários domínios SIP.

### <a name="simple-url-option-2"></a>Opção 2 de URL simples

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
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet e assim por diante (um para cada domínio SIP em sua organização)</p></td>
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


</div>

<div>

## <a name="simple-url-option-3"></a>Opção 3 de URL simples

A Opção 3 é muito útil se você tem diversos domínios SIP, e deseja que eles tenham URLs simples separadas, mas deseja minimizar os registros de DNS e requisitos de certificado para essas URLs simples. Neste exemplo, você só precisa de um registro de DNS A que resolve lync.contoso.com para o endereço IP de um pool do Diretor ou pool de Front-End.

### <a name="simple-url-option-3"></a>Opção 3 de URL simples

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
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrador</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>Opção de recuperação de desastres para URLs simples

Se você tiver vários sites que contenham pools de front-ends e o seu provedor de DNS oferecer suporte ao GeoDNS, você poderá configurar seus registros DNS para URLs simples para oferecer suporte à recuperação de desastres, de modo que a funcionalidade de URL simples continue mesmo que um pool de front-ends inteiro seja desativado. Este recurso de recuperação de desastres dá suporte às URLs simples Meet e Dial-In.

Para fazer essa configuração, crie dois endereços de GeoDNS. Cada endereço contém dois registros DNS A ou CNAME que são decompostos em dois pools que são unidos para fins de recuperação de desastres. Um endereço de GeoDNS é usado para acesso interno e é decomposto no FQDN da Web interno ou endereço IP do balanceador de carga dos dois pools. O outro endereço GeoDNS é usado para acesso externo e é decomposto no FQDN da Web externo ou endereço IP do balanceador de carga dos dois pools. Veja a seguir um exemplo da URL simples Meet, usando os FQDNs dos pools:

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

Em seguida, crie registros CNAME que decomponham sua URL simples Meet (como meet.contoso.com) nos dois endereços de GeoDNS.

<div class="">


> [!NOTE]  
> Se sua rede usar <EM>grampeamento</EM> (roteamento de todo o tráfego de URLs simples pelos links externos, inclusive o tráfego que vem de dentro de sua organização), será possível simplesmente configurar os endereços de GeoDNS externos e decompor sua URL simples Meet apenas nesses endereços externos.



</div>

Quando esse método é usado, é possível configurar cada endereço de GeoDNS para usar um método de round robin e distribuir solicitações nos dois pools ou para fazer a conexão principalmente com um pool (como o pool localizado geograficamente mais perto) e usar o outro pool apenas em caso de falhas de conectividade.

Você pode definir a mesma configuração para a URL simples Dial-In. Para fazer isso, crie registros adicionais como os do exemplo anterior, substituindo `dialin` para `meet` nos registros DNS. Para a URL simples Admin, use uma das três opções listadas anteriormente nesta seção.

Depois que esta configuração é definida, é preciso usar um aplicativo de monitoramento para definir que o monitoramento de HTTP rastreie as falhas. Para acesso externo, monitor para garantir que o HTTPS Obtém solicitações de descoberta automática para o FQDN da Web externo ou o endereço IP do balanceador de carga para os dois pools são bem-sucedidos. Por exemplo, as solicitações a seguir não devem conter nenhum cabeçalho **ACCEPT** e devem retornar **200 OK**.

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para acesso interno, é preciso monitorar a porta 5061 no FQDN da Web interno ou endereço IP do balanceador de carga dos dois pools. Se alguma falha de conectividade for detectada, o VIP desses pools deverão fechar as portas 80, 443 e 444.

</div>

</div>

<span> </span>

</div>

</div>

</div>

