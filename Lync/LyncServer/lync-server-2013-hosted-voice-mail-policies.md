---
title: 'Lync Server 2013: Políticas de correio de voz hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Políticas de correio de voz hospedado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Uma *política de correio de voz hospedada* fornece informações para o aplicativo de roteamento ExUM do Lync Server 2013 sobre onde direcionar chamadas para usuários cujas caixas de correio estão localizadas em um serviço hospedado do Exchange.

<div>


> [!NOTE]  
> As políticas de correio de voz hospedadas são necessárias somente para a integração do Lync Server 2013 com o Exchange UM hospedado. Elas não são necessárias para integração com o Exchange UM local.



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>Escopo da política de caixa postal hospedada

O escopo da política de caixa postal hospedada determina o nível hierárquico no qual a política se aplica. Você pode configurar políticas de caixa postal hospedadas com os seguintes níveis de escopo:

  - A política *global* pode potencialmente afetar todos os usuários na implantação do Lync Server 2013. Se um usuário estiver habilitado para acesso do Exchange UM hospedado e não tiver sido atribuída uma política por usuário e se uma política do site não foi atribuída ao site do usuário, a política global será aplicada. A política global é instalada com o Lync Server 2013. Você pode modificá-la para atender às suas necessidades, mas não pode renomeá-la ou excluí-la.

  - Uma política de *site* pode afetar todos os usuários que estão hospedados no site para o qual a política está definida. Se um usuário estiver configurado para acesso do Exchange UM hospedado e não tiver sido atribuída uma política por usuário, a política do site será aplicada.

  - Uma política *por usuário* pode afetar apenas usuários individuais ou grupos. Para impor uma política por usuário, você deve explicitamente atribuir a política a usuários individuais, grupos e objetos de contato.

<div>


> [!NOTE]  
> Na maioria dos casos, apenas uma política de caixa postal hospedada é necessária. Muitas vezes, você pode modificar a política global para atender a todas as suas necessidades. Se você implantar várias políticas de caixa postal hospedadas, todas essas políticas terão escopo por usuário.



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>Atributos hospedados da política de caixa postal

Uma política de caixa postal define dois atributos que o aplicativo de roteamento ExUM do Lync Server 2013 é inserido na URI de solicitação de uma mensagem de convite enviada para a implementação do Exchange UM hospedada:

  - **Destino:** O nome de domínio totalmente qualificado (FQDN) do serviço do Exchange UM hospedado. Esse valor é usado pelo servidor de borda do Lync Server local para fins de roteamento.
    
    <div>
    

    > [!NOTE]  
    > O FQDN para Exchange Online é exap.um.outlook.com.

    
    </div>

  - **Organização:** O FQDN do locatário no serviço do Exchange UM hospedado que aloja as caixas de correio dos usuários do Lync Server 2013. Uma política de caixa postal pode conter várias organizações. Se mais de uma organização estiver incluída na política, esse atributo deve ser uma lista separada por vírgulas dos locatários do Exchange Server que hospedam suas caixas de correio de usuário do Lync Server 2013.

<div>


> [!NOTE]  
> O administrador de locatário do seu serviço do Exchange UM hospedado fornecerá os valores necessários para as configurações de atributo de destino e organização. Para configurar sua política, você deve executar o cmdlet New-CsHostedVoicemailPolicy ou usar o cmdlet Set-CsHostedVoicemailPolicy para modificar um que existe (por exemplo, a política global).



</div>

Para obter detalhes sobre o gerenciamento de políticas de caixa postal hospedadas, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>Atribuição de política de caixa postal por usuário

Se a sua política de caixa postal hospedada for definida com o escopo por usuário, você deverá atribuí-la explicitamente. Você pode executar o cmdlet Grant-CsHostedVoicemailPolicy para atribuir a política a usuários individuais ou grupos.

Para obter detalhes sobre como atribuir ou remover uma política de correio de voz hospedada por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - Grant CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

