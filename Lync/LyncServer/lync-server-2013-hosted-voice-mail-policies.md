---
title: 'Lync Server 2013: políticas de caixa postal hospedadas'
description: 'Lync Server 2013: políticas de caixa postal hospedadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57461f4ffd2c6f2cd733dd7ec2c945c9e7b801c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550097"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Políticas de caixa postal hospedada no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

Uma *política de caixa postal hospedada* fornece informações para o aplicativo de roteamento ExUM do Lync Server 2013 sobre onde rotear chamadas para usuários cujas caixas de correio estão localizadas em um serviço do Exchange hospedado.

<div>


> [!NOTE]  
> As políticas de caixa postal hospedadas são necessárias apenas para a integração do Lync Server 2013 com a UM do Exchange hospedada. Elas não são necessárias para integração com UM do Exchange local.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Escopo da política de caixa postal hospedada

O escopo da política de caixa postal hospedada determina o nível hierárquico no qual a política é aplicada. É possível configurar as políticas de caixa postal hospedadas com os seguintes níveis de escopo:

  - A política *global* pode potencialmente afetar todos os usuários na implantação do Lync Server 2013. Se um usuário for habilitado para acesso à UM do Exchange hospedada e não tiver recebido uma política por usuário, e se uma política de site não tiver sido atribuída ao site do usuário, a política global será aplicada. A política global é instalada com o Lync Server 2013. É possível modificá-la para atender a suas necessidades, mas não é possível renomeá-la ou excluí-la.

  - Uma política de *site* pode afetar todos os usuários hospedados no site para o qual a política foi definida. Se um usuário for configurado para receber acesso à UM do Exchange hospedada e não tiver recebido uma política por usuário, a política de site será aplicada.

  - Uma política *por usuário* pode afetar somente usuários ou grupos individuais. Para aplicar uma política por usuário, você precisa atribuir explicitamente a política a usuários individuais, grupos e objetos de contato.

<div>


> [!NOTE]  
> Na maioria dos casos, somente a política de caixa postal hospedada é necessário. É possível modificar com frequência a política global a fim de atender a todas as suas necessidades. Se você implantar múltiplas políticas de caixa postal hospedadas, todas essas políticas terão um escopo por usuário.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Atributos de política de caixa postal hospedada

Uma política de caixa postal define dois atributos que o aplicativo de roteamento ExUM do Lync Server 2013 é inserido no URI de solicitação de uma mensagem de convite que é enviada para a implementação do UM do Exchange hospedado:

  - **Destino:** O FQDN (nome de domínio totalmente qualificado) do serviço UM do Exchange hospedado. Esse valor é usado pelo servidor de borda do Lync Server local para fins de roteamento.
    
    <div>
    

    > [!NOTE]  
    > O FQDN para Exchange Online é exap.um.outlook.com.

    
    </div>

  - **Organização:** O FQDN do locatário no serviço de UM do Exchange hospedado que hospeda as caixas de correio dos usuários do Lync Server 2013. Uma política de caixa postal pode conter várias organizações. Se mais de uma organização estiver incluída na política, esse atributo deve ser uma lista separada por vírgulas dos locatários do Exchange Server que hospedam suas caixas de correio de usuário do Lync Server 2013.

<div>


> [!NOTE]  
> O administrador de inquilino de seu serviço de UM do Exchange hospedada fornecerá os valores necessários para suas configurações de Destino e Organização. Para configurar sua política, você precisa executar o cmdlet New-CsHostedVoicemailPolicy ou usar o cmdlet Set-CsHostedVoicemailPolicy para modificar um que exista (por exemplo, a política global).



</div>

Para obter detalhes sobre o gerenciamento de políticas de caixa postal hospedadas, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Atribuição da política de caixa postal por usuário

Se sua política de caixa postal hospedada for definida com escopo por usuário, será necessária atribuí-la explicitamente. É possível executar o cmdlet Grant-CsHostedVoicemailPolicy a fim de atribuir a política a usuários ou grupos individuais.

Para obter detalhes sobre como atribuir ou remover uma política de caixa postal hospedada por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

