---
title: 'Lync Server 2013: gerenciar política de acesso externo para sua organização'
description: 'Lync Server 2013: gerenciar política de acesso externo para sua organização.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f0bb0e6764f67403065187c62debef13c77fcc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558407"
---
# <a name="manage-external-access-policy-in-lync-server-2013"></a>Gerenciar política de acesso externo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso externo que terão suporte na sua organização.

Por padrão, não há políticas configuradas para suportar o acesso de usuário externo, incluindo o acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o suporte de acesso de usuário externo para sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo suportado para cada política. Os escopos da política a seguir estão disponíveis para criação e configuração. Por padrão, a política global é criada, mas não pode ser excluída.

  - **Política global**   A política global é criada quando você implanta seus Servidores de Borda. Por padrão, nenhuma opção de acesso do usuário externo está habilitada na política global. Para suportar o acesso do usuário externo a nível global, você deve configurar a política global para suportar um ou mais tipos de opções de acesso do usuário externo. A política global se aplica a todos os usuários na sua organização, mas as políticas locais e as políticas de usuário substituem a política global. Ao excluir a política global, ela não é removida. Ao invés, é redefinida para a configuração padrão.

  - **Política de site**   Você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos. A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política. Por exemplo, se você ativar o acesso de usuário remoto na política global, pode especificar uma política de local que o desative para um local específico. Por padrão, a política de local é aplicada a todos os usuários do local, mas você pode atribuir uma política de usuário para substituir a configuração da política de local.

  - **Política de usuário**   Você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte ao acesso de usuário remoto a usuários específicos. A configuração da política de usuário substitui a política global e a do local, mas apenas para usuários específicos aos quais a política de usuário é atribuída. Por exemplo, se você ativar o acesso de usuário remoto na política global e na de local, deve especificar uma política de usuário que a desative e depois atribuir essa política de usuário a usuários específicos. Se você criar uma política de usuário, deve aplicá-la a um ou mais usuários antes que ela surta efeito.

<div>


> [!IMPORTANT]  
> As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.



</div>

Essas opções incluem os seguintes tipos de acesso externo:

  - **Habilitar comunicações com usuários federados**   Habilite esta opção se desejar oferecer suporte para o acesso de usuários a domínios parceiros federados. Essa configuração configura a capacidade de os usuários se comunicarem com outros domínios federados SIP, bem como provedores hospedados como o Microsoft 365. Selecionar essa configuração permite que você selecione a opção para permitir a comunicação com domínios XMPP federados.
    
    Como opção, você pode selecionar **Permitir comunicações com parceiros XMPP federados** se você primeiro selecionar **Permitir comunicações com usuários federados**. A federação XMPP é uma federação com organizações que utilizam o XMPP (extensible messaging and presence protocol).
    
    <div>
    

    > [!NOTE]  
    > Se você habilitar a Federação XMPP, também deverá optar por implantar a <STRONG>Federação XMPP</STRONG> na seção configuração de pools de borda do construtor de topologias. A configuração da Federação do XMPP implanta um proxy do XMPP no servidor de borda e um Gateway XMPP no servidor de front-end.

    
    </div>

  - **Habilitar comunicações com usuários**     remotos Habilite essa opção se quiser que os usuários em sua organização que estejam fora do firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server pela Internet.

  - **Habilitar comunicações com usuários públicos**     Habilite essa opção se quiser que usuários internos possam se comunicar com contatos do provedor de mensagens instantâneas públicos, como os fornecidos pelo Windows Live, Yahoo \! e America Online (AOL).
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P>
    > <LI>
    > <P>O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</P>
    > <LI>
    > <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> Além de habilitar o suporte ao acesso de usuário externo, você também deve configurar políticas para controlar o uso do acesso de usuário externo na organização antes de qualquer tipo de acesso de usuário externo estar disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A>.



</div>

**Para exibir políticas de acesso externo usando os cmdlets do Windows PowerShell**

  - Você pode visualizar as políticas de acesso externo usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsExternalAccessPolicy** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Para exibir informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de Gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsExternalAccessPolicy
    
    Esse comando retornará informações parecidas com:
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configurar políticas para controlar o acesso de usuário federado do XMPP no Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configurar políticas para controlar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Redefinindo ou excluindo políticas de acesso de usuário externo no Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

