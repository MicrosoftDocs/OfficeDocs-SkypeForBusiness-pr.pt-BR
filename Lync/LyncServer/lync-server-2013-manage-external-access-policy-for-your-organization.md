---
title: 'Lync Server 2013: Gerenciar política de acesso externo para sua organização'
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
ms.openlocfilehash: e9ade02d1c7a3eae1d65cd62ba69684129105dce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Gerenciar política de acesso externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

Após implantar um ou mais servidores de borda, você deve habilitar os tipos de acesso externo que terão suporte para a sua organização.

Por padrão, não há políticas configuradas para dar suporte a acesso externo a usuários, incluindo acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o acesso de usuário externo à sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo com suporte para cada política. Os seguintes escopos de política estão disponíveis para criação e configuração. Por padrão, a política global é criada, mas não pode ser excluída.

  - **Política global a**   política global é criada quando você implanta seus servidores de borda. Por padrão, nenhuma opção de acesso de usuário externo está habilitada na política global. Para dar suporte ao acesso de usuário externo no nível global, configure a política global para dar suporte a um ou mais tipos de opções de acesso de usuário externo. A política global aplica-se a todos os usuários em sua organização, mas políticas de site e políticas de usuário substituem a política global. Se você excluir a política global, não a removerá. Em vez disso, redefina-o para a configuração padrão.

  - **Política de site**   você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos. A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site. Por exemplo, se você habilitar o acesso de usuário remoto na política global, poderá especificar uma política de site que desabilite o acesso de usuário remoto para um site específico. Por padrão, uma política de site é aplicada a todos os usuários do site, mas você pode atribuir uma política de usuário a um usuário para substituir a configuração de política do site.

  - **Política de usuário**   você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte para acesso de usuário remoto a usuários específicos. A configuração na política de usuário substitui a política global e do site, mas somente para os usuários específicos aos quais a política de usuário está atribuída. Por exemplo, se você habilitar o acesso de usuário remoto na política global e na política do site, poderá especificar uma política de usuário que desabilite o acesso de usuário remoto e atribua essa política de usuário a usuários específicos. Se você criar uma política de usuário, deverá aplicá-la a um ou mais usuários antes de entrar em vigor.

<div>


> [!IMPORTANT]  
> As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.



</div>

Essas opções incluem os seguintes tipos de acesso externo:

  - **Habilitar comunicações com usuários**   federados habilitá-lo se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados. Essa configuração define a capacidade dos usuários de se comunicarem com outros domínios federados do SIP, bem como provedores hospedados como o Microsoft Office 365. Selecionar essa configuração permite que você selecione a opção para permitir a comunicação com domínios federados XMPP.
    
    Como opção, você pode selecionar **habilitar comunicações com parceiros federados do XMPP** se selecionar **habilitar comunicações com usuários federados**. A Federação do XMPP é uma federação com organizações que usam Extensible Messaging and Presence Protocol (XMPP).
    
    <div>
    

    > [!NOTE]  
    > Se você habilitar a Federação do XMPP, também deverá selecionar para implantar a <STRONG>Federação do XMPP</STRONG> na seção configuração de pools de borda do construtor de topologias. A configuração para a Federação do XMPP implanta um proxy XMPP no servidor de borda e um Gateway XMPP no servidor front-end.

    
    </div>

  - **Habilitar comunicações com usuários**   remotos habilite essa opção se você quiser que os usuários em sua organização que estão fora do seu firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server pela Internet.

  - **Habilitar comunicações com usuários**   públicos habilite essa opção se você quiser que os usuários internos possam se comunicar com contatos públicos do provedor de mensagens de chat, como aqueles fornecidos pelo\!Windows Live, Yahoo e America Online (AOL).
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P>
    > <LI>
    > <P>O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</P>
    > <LI>
    > <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> Além de habilitar o suporte ao acesso do usuário externo, você também deve configurar políticas para controlar o uso do acesso de usuários externos em sua organização antes que qualquer tipo de acesso de usuário externo esteja disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A>.



</div>

**Para exibir as políticas de acesso externo usando cmdlets do Windows PowerShell**

  - Você pode exibir as políticas de acesso externo usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsExternalAccessPolicy** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.
    
    Para ver as informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsExternalAccessPolicy
    
    Este comando retorna informações semelhantes para o seguinte:
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar políticas para controlar acesso de usuário federado no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Configurar políticas para controle de acesso de usuário remoto no Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Configurar políticas para controlar o acesso de usuário público no Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Atribuir uma política de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Redefinindo ou excluindo políticas de acesso de usuário externo no Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

