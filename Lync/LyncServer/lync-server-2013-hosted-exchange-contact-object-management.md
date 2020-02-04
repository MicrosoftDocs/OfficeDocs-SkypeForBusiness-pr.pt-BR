---
title: 'Lync Server 2013: Gerenciamento de objeto de Contato no Exchange hospedado'
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
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Gerenciamento de objeto de Contato no Exchange hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-25_

Você precisa configurar um objeto de contato para cada número de autoatendimento e número de acesso do assinante em sua implantação interfuncional.

Para a integração com o Exchange UM hospedado, ocsumutil. exe não pode ser usado para gerenciar objetos de contato, pois isso depende das configurações de UM do Exchange UM do Active Directory. Em uma implantação interfuncional, o Lync Server 2013 e o Exchange UM Hosted são instalados em florestas separadas sem nenhuma confiança entre elas. Por motivos de segurança, os administradores do Lync Server 2013 não têm acesso direto às configurações do Active Directory de UM Exchange. Como resultado, o Lync Server 2013 fornece um modelo diferente para o gerenciamento de objetos de contato em um *espaço de endereço SIP compartilhado* que é acessível para o Lync Server 2013 e para o serviço um Hosted Exchange um.

<div>

## <a name="hosted-contact-object-workflow"></a>Fluxo de trabalho do objeto de contato hospedado

Veja a seguir as etapas gerais para trabalhar com o administrador de locatários do Exchange hospedado para gerenciar objetos de contato:

1.  O administrador do Exchange solicita números de telefone para o acesso do assinante do Exchange UM e objetos de contato do AutoAttendant.

2.  O administrador do Lync Server 2013 cria um objeto de contato para cada número de telefone e atribui uma política de caixa postal hospedada a cada objeto de contato.

3.  O administrador do Lync Server 2013 fornece os números de telefone para o administrador do Exchange.

4.  O administrador do Exchange atribui os números de telefone aos planos de discagem de UM do Exchange apropriados para atendedores automáticos e acesso do Assinante.

<div>


> [!NOTE]  
> Não é necessário configurar nenhuma configuração de plano de discagem do Lync Server 2013 nos objetos de contato como há implantações locais.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Configurar objetos de contato hospedados

<div>


> [!NOTE]  
> Os objetos de contato do Lync Server 2013 podem ser habilitados para o Exchange UM hospedado, uma política de caixa postal hospedada que se aplica a ele deve ser implantada. A política pode ser do escopo global, no nível do site ou por usuário, desde que ele se aplique ao objeto de contato que você deseja habilitar. Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">políticas de caixa postal hospedadas no Lync Server 2013</A>.



</div>

Para configurar objetos de contato de atendedor automático hospedado e de acesso ao assinante em uma implantação em várias instalações, você deve usar os seguintes cmdlets:

  - **New-CsExUmContact** cria um novo objeto de contato para um hospedado.

  - **Set-CsExUmContact** modifica um objeto de contato existente para o Exchange um hospedado.

O exemplo a seguir cria um objeto de contato de atendente automático:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Este exemplo cria um novo objeto de contato do Exchange UM com o endereço SIP sip:exumaa1@fabrikam.com. O nome do pool onde o serviço registrador do Lync Server 2013 está em execução é RedmondPool.litwareinc.com. A unidade organizacional do Active Directory na qual essas informações serão armazenadas é OU = ExUmContacts, DC = litwareinc, DC = com. O número de telefone do objeto de contato é 2065554567. O parâmetro opcional-AutoAttendant $True especifica que esse objeto é um objeto de contato do atendente automático. Definir o parâmetro-AutoAttendant como false (o padrão) especifica um objeto de contato do acesso do Assinante.

Para obter detalhes sobre os cmdlets New-CsExUmContact e Set-CsExUmContact, consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

