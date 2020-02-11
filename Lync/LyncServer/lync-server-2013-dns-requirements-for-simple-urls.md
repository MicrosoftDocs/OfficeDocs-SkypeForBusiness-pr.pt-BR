---
title: 'Lync Server 2013: Requisitos de DNS para URLs simples'
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
ms.openlocfilehash: 2a05b5e5afc645c9219d02c8a551e4c0af9d93b0
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Requisitos de DNS para URLs simples no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

O Lync Server 2013 oferece suporte a URLs simples, que facilitam o ingresso em reuniões para seus usuários e facilitam a obtenção de ferramentas administrativas do Lync Server para seus administradores. Para obter detalhes sobre URLs simples, consulte [planejando URLs simples no Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

O Lync Server oferece suporte a estas três URLs simples: atender, discagem e administrador. Você é obrigado a configurar URLs simples para atender e discagem, e a URL simples de administrador é opcional. Os registros de sistema de nome de domínio (DNS) que você precisa para dar suporte a URLs simples dependem de como você definiu essas URLs simples e se deseja dar suporte à recuperação de desastres para URLs simples.

<div>

## <a name="simple-url-option-1"></a>Opção de URL simples 1

Na opção 1, você cria uma nova URL base para cada URL simples.

<div class="">


> [!NOTE]  
> Quando um usuário clica em um link de reunião de URL simples, o servidor ao qual o registro DNS é resolvido determina o software cliente correto para iniciar. Depois que o software cliente é iniciado, ele se comunica automaticamente com o pool em que a conferência está hospedada. Dessa forma, os usuários são direcionados ao servidor apropriado para o conteúdo da reunião, independentemente de qual servidor ou pool a URL simples dos registros DNS a resolver.



</div>

### <a name="simple-url-option-1"></a>Opção de URL simples 1

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


Se você usar a opção 1, deverá definir o seguinte:

  - Para cada uma das URLs mais simples, você precisa de um registro de DNS que resolva a URL para o endereço IP do diretor, se você tiver implantado. Caso contrário, ele deve ser resolvido para o endereço IP do balanceador de carga de um pool de front-ends. Se você não implantou um pool e está usando uma implantação do servidor Standard Edition, o registro DNS a deve ser resolvido para o endereço IP de um servidor Standard Edition em sua organização.
    
    Se você tiver mais de um domínio SIP em sua organização e usar essa opção, será necessário criar URLs simples para cada domínio SIP e precisará de um registro DNS A para cada URL simples. Por exemplo, se você tiver contoso.com e fabrikam.com, criará registros DNS A para ambos https://meet.contoso.com e. https://meet.fabrikam.com
    
    Como alternativa, se você tiver vários domínios SIP e quiser minimizar o registro DNS e os requisitos de certificado para essas URLs simples, use a opção 3 conforme descrito mais adiante neste tópico.

  - Para a URL simples de discagem, você precisa de um registro de DNS que resolva a URL para o endereço IP do diretor, se você tiver uma implantação. Caso contrário, ele deve ser resolvido para o endereço IP do balanceador de carga de um pool de front-ends. Se você não implantou um pool e está usando uma implantação do servidor Standard Edition, o registro DNS a deve ser resolvido para o endereço IP de um servidor Standard Edition em sua organização.

  - A URL simples de administrador é somente interna. Ele exige um registro de DNS que resolva a URL para o endereço IP do diretor, se você tiver uma implantação. Caso contrário, ele deve ser resolvido para o endereço IP do balanceador de carga de um pool de front-ends. Se você não implantou um pool e está usando uma implantação do servidor Standard Edition, o registro DNS a deve ser resolvido para o endereço IP de um servidor Standard Edition em sua organização.

</div>

<div>

## <a name="simple-url-option-2"></a>Opção de URL simples 2

Com a opção 2, as URLs de reunião, discada e administrador simples têm uma URL base comum, como lync.contoso.com. Portanto, você precisa de apenas um registro de DNS para essas URLs simples, o que resolve lync.contoso.com para o endereço IP de um pool de directors ou de front-end. Se você não implantou um pool e está usando uma implantação do servidor Standard Edition, o registro DNS a deve ser resolvido para o endereço IP de um servidor Standard Edition em sua organização.

Observe que, se você tiver mais de um domínio SIP em sua organização, ainda deverá criar URLs simples para cada domínio SIP e precisará de um registro DNS A para cada uma das URLs simples. Neste exemplo, enquanto três URLs simples são todas baseadas no lync.contoso.com, uma URL simples de reunião simples para fabrikam.com é configurada com uma URL base diferente. Neste exemplo, você deve criar registros DNS A para ambos https://lync.contoso.com e. https://lync.fabrikam.com A opção de URL simples 3 mostra outra maneira de lidar com nomes e registros DNS A, se você tiver vários domínios SIP.

### <a name="simple-url-option-2"></a>Opção de URL simples 2

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


</div>

<div>

## <a name="simple-url-option-3"></a>Opção de URL simples 3

A opção 3 será mais útil se você tiver muitos domínios SIP e quiser que eles tenham URLs simples separadas, mas desejem minimizar o registro DNS e os requisitos de certificado para essas URLs simples. Neste exemplo, você precisa apenas de um registro DNS A, que resolve lync.contoso.com para o endereço IP de um pool de directors ou um pool de front-ends.

### <a name="simple-url-option-3"></a>Opção de URL simples 3

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
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Locatário</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>Opção de recuperação de desastres para URLs simples

Se você tiver vários sites que contenham pools de front-end e o seu provedor de DNS oferecer suporte a GeoDNS, você poderá configurar seus registros DNS para URLs simples para dar suporte à recuperação de desastres, para que a funcionalidade de URL simples continue mesmo que um pool de front-end inteiro seja desligado. Este recurso de recuperação de desastres dá suporte a URLs simples e de reunião discada.

Para configurar isso, crie dois endereços do GeoDNS. Cada endereço tem dois registros DNS A ou CNAME que são resolvidos para dois pools que são emparelhados para fins de recuperação de desastres. Um endereço GeoDNS é usado para acesso interno e é resolvido para o FQDN da Web interna ou o endereço IP do balanceador de carga para os dois pools. O outro endereço GeoDNS é usado para acesso externo e resolve para o FQDN da Web externo ou o endereço IP do balanceador de carga para os dois pools. Veja a seguir um exemplo de URL simples de reunião, usando os FQDNs dos grupos.

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

Em seguida, crie registros CNAME que resolvem sua URL simples de reunião (como meet.contoso.com) para os dois endereços GeoDNS.

<div class="">


> [!NOTE]  
> Se a sua rede usa <EM>hairpinning</EM> (direcionar todo o tráfego de URL simples por meio do link externo, incluindo o tráfego que vem de dentro da sua organização), você pode apenas configurar o endereço de GeoDNS externo e resolver seu encontro URL simples para apenas esse endereço externo.



</div>

Ao usar esse método, você pode configurar cada endereço do GeoDNS para usar um método de rodízio para distribuir solicitações para os dois pools ou para se conectar principalmente a um pool (como o pool localizado geograficamente) e usar o outro pool somente em caso de falha na conectividade.

Você pode configurar a mesma configuração para a URL simples de discagem. Para fazer isso, crie registros adicionais como os do exemplo anterior, substituindo `dialin` para `meet` os registros DNS. Para a URL simples do administrador, use uma das três opções listadas anteriormente nesta seção.

Depois que essa configuração é configurada, você deve usar um aplicativo de monitoramento para configurar o monitoramento HTTP para observar falhas. Para acesso externo, monitor para ter certeza de que o HTTPS Obtém solicitações de descoberta automática para o FQDN da Web externa ou o endereço IP do balanceador de carga para os dois pools são bem-sucedidos. Por exemplo, as seguintes solicitações não devem conter cabeçalho **Accept** e devem retornar **200 OK**.

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para acesso interno, você deve monitorar a porta 5061 no FQDN da Web interno ou o endereço IP do balanceador de carga para os dois pools. Se alguma falha de conectividade for detectada, o VIP para esses pools deverá fechar as portas 80, 443 e 444.

</div>

</div>

<span> </span>

</div>

</div>

</div>

