---
title: 'Lync Server 2013: Gerenciando de federação e acesso externo ao Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8eb4dcf6a690e2bab7b834624fb0f695e3e770e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Gerenciando de federação e acesso externo ao Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

Implantar um servidor de borda ou um pool de bordas é o primeiro passo para dar suporte a usuários externos. Para obter detalhes sobre a implantação de servidores de borda, consulte Implantando o [acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.

Após a instalação e a configuração da implantação interna do Lync Server 2013, os usuários internos em sua organização podem colaborar com outros usuários internos que tenham contas SIP nos serviços de domínio Active Directory (AD DS). A colaboração pode incluir o envio e o recebimento de mensagens instantâneas e a atualização do status de presença e a participação em conferências (também conhecidas como "reuniões"). Você habilita e configura o acesso de usuários externos para controlar se os usuários externos com suporte podem colaborar com usuários internos do Lync Server. Os usuários externos podem incluir usuários remotos da implantação, usuários federados (incluindo usuários com suporte de provedores de serviços de mensagens instantâneas públicas), Federação do XMPP e participantes anônimos em conferências.

Se a sua implantação incluía a instalação de um servidor de borda do Lync Server 2013 ou um pool de bordas, o escopo dos possíveis tipos de comunicação será amplamente expandido com várias opções para acesso de usuário externo, comunicação com membros de outros domínios federados SIP Provedores federados SIP e usuários federados XMPP. Depois de configurar o servidor de borda ou o pool de bordas, habilite os tipos de acesso de usuário externo que você deseja fornecer e configure as políticas para controlar o acesso externo. No Lync Server 2013, habilite e configure o acesso de usuários externos e políticas usando o painel de controle do Lync Server, o Shell de gerenciamento do Lync Server ou ambos, de acordo com os requisitos da tarefa. Para obter detalhes sobre essas ferramentas de gerenciamento, consulte [Ferramentas administrativas do Lync server 2013](lync-server-2013-lync-server-administrative-tools.md) na documentação de operações, [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) na documentação de operações e [instalar o Lync Server 2013 ferramentas administrativas ](lync-server-2013-install-lync-server-administrative-tools.md)na documentação de operações.

<div>


> [!IMPORTANT]  
> Ao projetar sua configuração e políticas para acesso de usuário externo, você deve entender a precedência de políticas e como as políticas são aplicadas. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.



</div>

Por padrão, nenhuma política é configurada para dar suporte ao acesso externo do usuário, incluindo acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o acesso de usuário externo à sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo com suporte para cada política. Isso inclui as seguintes políticas de acesso externo:

  - **Política global a**   política global é criada quando você implanta seus servidores de borda. Por padrão, nenhuma opção de acesso de usuário externo está habilitada na política global. Para dar suporte ao acesso de usuário externo no nível global, configure a política global para dar suporte a um ou mais tipos de opções de acesso de usuário externo. A política global aplica-se a todos os usuários em sua organização, mas políticas de site e políticas de usuário substituem a política global. Se você excluir a política global, não a removerá. Em vez disso, redefina-o para a configuração padrão.

  - **Política de site**   você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos. A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site. Por exemplo, se você habilitar o acesso de usuário remoto na política global, poderá especificar uma política de site que desabilite o acesso de usuário remoto para um site específico. Por padrão, uma política de site é aplicada a todos os usuários do site, mas você pode atribuir uma política de usuário a um usuário para substituir a configuração de política do site.

  - **Política de usuário**   você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte para acesso de usuário remoto a usuários específicos. A configuração na política de usuário substitui a política global e do site, mas somente para os usuários específicos aos quais a política de usuário está atribuída. Por exemplo, se você habilitar o acesso de usuário remoto na política global e na política do site, poderá especificar uma política de usuário que desabilite o acesso de usuário remoto e atribua essa política de usuário a usuários específicos. Se você criar uma política de usuário, deverá aplicá-la a um ou mais usuários antes de entrar em vigor.

Para determinar quais configurações de configuração e quais diretivas você precisa criar ou editar, consulte os seguintes pontos de decisão:

**Você deseja permitir que usuários internos e externos do seu domínio possam colaborar usando mensagens instantâneas, conferências da Web e áudio/vídeo?**

Defina as configurações conforme detalhado nos tópicos [Configurar políticas para controlar o acesso de usuários remotos no Lync server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)e [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Deseja permitir que usuários anônimos participem e sejam convidados para conferências hospedadas pelos usuários na sua implantação?**

Defina as configurações como detalhados no tópico [atribuir políticas de conferência para dar suporte a usuários anônimos no Lync server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [criar ou modificar uma política de conferência no Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e [configurações de política de conferência referência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**Deseja permitir que os usuários se comuniquem com os contatos do domínio federado do SIP?**

Defina as configurações conforme detalhado nos tópicos [Configurar políticas para controlar o acesso de usuários federados no Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [habilitar ou desabilitar a conectividade de mensagens de chat públicas e Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)e [gerenciar domínios federados SIP para seu organização no Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Se você habilitou a comunicação com domínios de Federação SIP, deseja habilitar comunicações com contatos de parceiro federado do XMPP?**

Defina as configurações conforme detalhado no tópico [Configurar políticas para controlar o acesso de usuários federados do XMPP no Lync server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) e [gerenciar XMPP parceiros federados no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Se você tiver habilitado a comunicação com domínios federados SIP, deseja habilitar a descoberta automática de Federação SIP?**

Defina as configurações conforme detalhado no tópico [habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Se você habilitou a comunicação com domínios de Federação SIP, deseja habilitar o envio de um aviso de isenção de responsabilidade a contatos federados notificando que você usa o arquivamento e que as comunicações podem ser arquivadas?**

Defina as configurações conforme detalhado no tópico [habilitar ou desabilitar o envio de uma isenção de arquivamento para parceiros federados no Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que permitem a comunicação com provedores públicos, como Windows Live Messenger, AOL e\!Yahoo?**

Defina as configurações conforme detalhado nos tópicos Configurando [políticas para controlar o acesso de usuários públicos no Lync server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[habilitar ou desabilitar a conectividade de mensagens de chat públicas e a Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)e [criar ou editar Public SIP Federated provedores no Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

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

**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que sejam provedores que executam o Microsoft Office 365, o Microsoft Lync Online e o Microsoft Lync Online 2010?**

Defina as configurações conforme detalhado nos tópicos [criar ou editar provedores federados SIP públicos no Lync server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [habilitar ou desabilitar a conectividade de mensagens de chat públicas e a Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) e [criar ou editar provedores federados SIP hospedados Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**A implantação está configurada em um domínio dividido (também conhecido como híbrido), no qual alguns usuários têm o servidor primário em uma implantação local e outros usuários estão configurados com um servidor primário em um ambiente online?**

Defina as configurações conforme detalhado nos tópicos [Configurar políticas para controlar o acesso de usuários federados no Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [habilitar ou desabilitar a conectividade de mensagens de chat públicas e Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) e [criar ou editar o SIP federado federado provedores Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

Se preferir uma tabela que liste os requisitos:


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Guia em Federação e acesso externo (na horizontal) Federação ou tipo de acesso externo (down)</th>
<th>Política de Acesso Externo</th>
<th>Configuração de borda de acesso</th>
<th>Domínios federados SIP</th>
<th>Provedores Federados SIP</th>
<th>Parceiro federado do XMPP</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuários remotos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurar políticas para controle de acesso de usuário remoto no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar ou desabilitar acesso de usuário remoto no Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Contatos federados SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar acesso de usuário federado no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar ou desabilitar descoberta de parceiros de federação no Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Gerenciar domínios SIP federados para sua organização no Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP contatos federados</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar acesso de usuário federado no Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Gerenciar parceiros XMPP federados no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Dividir domínio/usuários híbridos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar acesso de usuário federado no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Criar ou editar provedores hospedados federados SIP no Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contatos do serviço público de mensagens instantâneas</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurar políticas para controlar o acesso de usuário público no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Criar ou editar fornecedores SIP públicos federados no Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Acesso de usuário anônimo a reuniões e conferências</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Atribuir políticas de conferência para suporte de usuários anônimos no Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Você também deve considerar as seguintes configurações de configuração em políticas de conferência: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">criar ou modificar uma política de conferência no Lync server 2013</A> e <A href="lync-server-2013-conferencing-policy-settings-reference.md">a referência de configurações de política de conferência para o Lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Você pode definir as configurações de acesso de usuário externo, incluindo as políticas que deseja usar para controlar o acesso de usuários externos, mesmo que você não tenha habilitado o acesso de usuários externos para a sua organização. No entanto, as políticas e outras configurações que você configura estão em vigor apenas quando você tem acesso de usuário externo habilitado para sua organização. Os usuários externos não podem se comunicar com os usuários da sua organização quando o acesso ao usuário externo estiver desabilitado ou se nenhuma política de acesso externo do usuário estiver configurada para dar suporte a ele.

Sua implantação de borda autentica os tipos de usuários externos (exceto para usuários anônimos, que são autenticados pela ID de conferência e uma chave de usuário que é enviada para o participante anônimo quando você cria os participantes da conferência e convida) e os controles acesso com base em como você configura o suporte de borda. Para controlar a comunicação, você pode configurar uma ou mais políticas e definir configurações que definem como os usuários dentro e fora da sua implantação se comunicam uns com os outros. As políticas e configurações incluem a política global padrão para acesso ao usuário externo, além das políticas de site e de usuário que você pode criar e configurar para habilitar um ou mais tipos de acesso de usuários externos para sites ou usuários específicos.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Gerenciar política de acesso externo no Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Gerenciar configuração da borda de acesso para sua organização no Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Gerenciar domínios SIP federados para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Gerenciar fornecedores SIP federados para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Gerenciar parceiros XMPP federados no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configurando o suporte de Federação para um cliente do Lync Online no Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

