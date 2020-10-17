---
title: 'Lync Server 2013: gerenciamento de objeto de contato do Exchange hospedado'
description: 'Lync Server 2013: gerenciamento de objeto de contato do Exchange hospedado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691bcea10d3a4f8b523c6565f384d6c4c9a2a2a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552767"
---
# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Gerenciamento de objeto de contato do Exchange hospedado no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-25_

Você precisa configurar um objeto de contato para cada número de atendedor automático e número de acesso do assinante em sua implantação entre locais.

Para a integração com a UM do Exchange hospedado, ocsumutil.exe não pode ser usado para gerenciar objetos de contato, pois ele depende das configurações do UM do Exchange Active Directory. Em uma implantação entre instalações, o Lync Server 2013 e o Exchange hospedado da UM estão instalados em florestas separadas sem nenhuma confiança entre elas. Por motivos de segurança, os administradores do Lync Server 2013 não têm acesso direto às configurações do Active Directory da UM do Exchange. Como resultado, o Lync Server 2013 fornece um modelo diferente para o gerenciamento de objetos de contato em um *espaço de endereçamento SIP compartilhado* que é acessível para o Lync Server 2013 e para o serviço um do Exchange hospedado.

<div>

## <a name="hosted-contact-object-workflow"></a>Fluxo de trabalho do objeto de contato hospedado

Veja a seguir as etapas gerais para trabalhar com seu administrador de locatários do Exchange hospedado para gerenciar objetos de contato:

1.  O administrador do Exchange solicita números de telefone para o acesso do assinante do UM do Exchange e objetos de contato de atendedor automático.

2.  O administrador do Lync Server 2013 cria um objeto de contato para cada número de telefone e atribui uma política de caixa postal hospedada a cada objeto de contato.

3.  O administrador do Lync Server 2013 fornece os números de telefone para o administrador do Exchange.

4.  O administrador do Exchange atribui os números de telefone aos planos de discagem da UM do Exchange apropriados para atendedores automáticos e acesso ao Assinante.

<div>


> [!NOTE]  
> Não é necessário definir as configurações de plano de discagem do Lync Server 2013 nos objetos de contato como ocorre com implantações locais.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Configurando objetos de contato hospedados

<div>


> [!NOTE]  
> Para que os objetos de contato do Lync Server 2013 possam ser habilitados para UM do Exchange hospedado, uma política de correio de voz hospedada que se aplica a eles deve ser implantada. A política pode ser do escopo global, no nível do site ou por usuário, desde que se aplique ao objeto de contato que você deseja habilitar. Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail Policies in Lync Server 2013</A>.



</div>

Para configurar objetos de contato hospedados de atendedor automático e de acesso ao assinante em uma implantação entre locais, você deve usar os seguintes cmdlets:

  - **New-CsExUmContact** cria um novo objeto de contato para um hospedado.

  - **Set-CsExUmContact** modifica um objeto de contato existente para um do Exchange hospedado.

O exemplo a seguir cria um objeto de contato de atendedor automático:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Este exemplo cria um novo objeto de contato do UM do Exchange com o endereço SIP sip:exumaa1@fabrikam.com. O nome do pool onde o serviço registrador do Lync Server 2013 está sendo executado é o RedmondPool.litwareinc.com. A unidade organizacional do Active Directory onde essas informações serão armazenadas é OU = ExUmContacts, DC = litwareinc, DC = com. O número de telefone do objeto de contato é 2065554567. O parâmetro opcional-AutoAttendant $True especifica que esse objeto é um objeto de contato de atendedor automático. A configuração do parâmetro-AutoAttendant como false (o padrão) especifica um objeto de contato de acesso ao Assinante.

Para obter detalhes sobre os cmdlets New-CsExUmContact e Set-CsExUmContact, consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

