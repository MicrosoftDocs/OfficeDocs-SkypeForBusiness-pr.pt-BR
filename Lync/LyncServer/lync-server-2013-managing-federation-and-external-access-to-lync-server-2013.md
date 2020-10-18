---
title: 'Lync Server 2013: gerenciamento de Federação e acesso externo ao Lync Server 2013'
description: 'Lync Server 2013: gerenciamento de Federação e acesso externo ao Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d389c7490fd1884631ed2fc184d590eb42141b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574917"
---
# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Gerenciamento de Federação e acesso externo ao Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

Implantar um Servidor de borda ou um pool de Borda é a primeira etapa para suportar usuários externos. Para obter detalhes sobre como implantar servidores de borda, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.

Após instalar e configurar sua implantação interna do Lync Server 2013, os usuários internos da sua organização podem colaborar com outros usuários internos que possuem contas SIP em seus serviços de domínio Active Directory (AD DS). A colaboração pode incluir o envio e recebimento de mensagens instantâneas e a atualização do status de presença e participação nas conferências (também conhecido como "reuniões). Você habilita e configura o acesso de usuário externo para controlar se os usuários externos compatíveis podem colaborar com usuários internos do Lync Server. Os usuários externos podem incluir usuários remotos da sua implantação, usuários federados (incluindo usuários suportados de provedores de serviço de mensagem instantânea (IM) pública, federação XMPP e participantes anônimos em conferências.

Se sua implantação incluiu a instalação de um servidor de borda do Lync Server 2013 ou um pool de borda, o escopo de possíveis tipos de comunicação é amplamente expandido com várias opções para acesso de usuário externo, comunicação com membros de outros domínios federados SIP, provedores federados SIP e usuários federados XMPP. Após configurar o servidor de borda ou o pool de borda, habilite os tipos de acesso de usuário externo que você deseja fornecer e configure as políticas para controlar o acesso externo. No Lync Server 2013, você habilita e configura o acesso de usuário externo e políticas usando o painel de controle do Lync Server, o Shell de gerenciamento do Lync Server ou ambos, com base nos requisitos de tarefa. Para obter detalhes sobre essas ferramentas de gerenciamento, consulte [Lync server 2013 Administrative Tools](lync-server-2013-lync-server-administrative-tools.md) na documentação operações, [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) na documentação operações e [instalar as ferramentas administrativas do Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md) na documentação operações.

<div>


> [!IMPORTANT]  
> Ao projetar sua configuração e políticas para acesso do usuário externo, você deve compreender a precedência das políticas e como as políticas são aplicadas. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.



</div>

Por padrão, nenhuma política está configurada para oferecer suporte ao acesso de usuários externos, incluindo acesso de usuários remotos, acesso de usuários federados, mesmo se você já tiver habilitado o suporte ao acesso de usuários externos na sua organização. Para controlar o uso do acesso de usuários externos, configure uma ou mais políticas, especificando o tipo de acesso de usuários externos com suporte para cada política. Isso inclui as seguintes políticas de acesso externo:

  - **Política global**   A política global é criada quando você implanta seus Servidores de Borda. Por padrão, nenhuma opção de acesso do usuário externo está habilitada na política global. Para suportar o acesso do usuário externo a nível global, você deve configurar a política global para suportar um ou mais tipos de opções de acesso do usuário externo. A política global se aplica a todos os usuários na sua organização, mas as políticas locais e as políticas de usuário substituem a política global. Ao excluir a política global, ela não é removida. Ao invés, é redefinida para a configuração padrão.

  - **Política de site**   Você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos. A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política. Por exemplo, se você ativar o acesso de usuário remoto na política global, pode especificar uma política de local que o desative para um local específico. Por padrão, a política de local é aplicada a todos os usuários do local, mas você pode atribuir uma política de usuário para substituir a configuração da política de local.

  - **Política de usuário**   Você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte ao acesso de usuário remoto a usuários específicos. A configuração da política de usuário substitui a política global e a do local, mas apenas para usuários específicos aos quais a política de usuário é atribuída. Por exemplo, se você ativar o acesso de usuário remoto na política global e na de local, deve especificar uma política de usuário que a desative e depois atribuir essa política de usuário a usuários específicos. Se você criar uma política de usuário, deve aplicá-la a um ou mais usuários antes que ela surta efeito.

Para determinar quais definições de configurações e quais políticas você precisa criar ou editar, consulte os seguintes pontos de decisão:

**Deseja permitir que usuários internos e externos do seu domínio possam colaborar usando mensagem instantânea, conferência da Web e Áudio/Vídeo?**

Defina as configurações conforme detalhado nos tópicos [Configure Policies para controlar o acesso de usuários remotos no Lync server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)e [habilite ou desabilite a Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Deseja permitir que usuários anônimos participem e sejam convidados para conferências hospedadas por usuários em sua implantação?**

Defina as configurações conforme detalhado no tópico [atribuir políticas de conferência para dar suporte a usuários anônimos no Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [criar ou modificar uma política de conferência no Lync Server 2013 e na](lync-server-2013-create-or-modify-a-conferencing-policy.md) [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**Deseja permitir que os usuários se comuniquem com contatos do Domínio Federado SIP?**

Defina as configurações conforme detalhado nos tópicos [Configure Policies to Control Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [habilitar ou desabilitar a Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)e [gerenciar domínios federados SIP para sua organização no](lync-server-2013-manage-sip-federated-domains-for-your-organization.md) Lync Server 2013

**Se você habilitou a comunicação com Domínios Federados SIP, deseja habilitar comunicações com contatos do Parceiro Federado XMPP?**

Defina as configurações, conforme detalhado no tópico [Configure Policies to Control XMPP Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) e [Manage XMPP Federated Partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Se você habilitou a comunicação com domínios federados SIP, deseja habilitar a descoberta automática de Federação SIP?**

Defina as configurações conforme detalhado no tópico [habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Se você habilitou a comunicação com Domínios Federados SIP, você não desejam habilitar o envio de uma declaração para contatos Federados notificando-os que você usa o arquivamento e as comunicações podem ser arquivadas?**

Defina as configurações conforme detalhado no tópico [habilitar ou desabilitar o envio de um aviso de isenção de arquivamento para parceiros federados no Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que permitem a comunicação com provedores públicos, como o Windows Live Messenger, AOL e Yahoo \! ?**

Defina as configurações, conforme detalhado nos tópicos [Configure Policies to Control Public User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[habilitar ou desabilitar a Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)e [criar ou editar provedores públicos SIP federados no Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

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

**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que estejam executando o Microsoft 365, o Microsoft Lync Online e o Microsoft Lync Online 2010?**

Defina as configurações conforme detalhado nos tópicos [criar ou editar provedores federados SIP públicos no Lync server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [habilitar ou desabilitar Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) e [criar ou editar provedores federados SIP hospedados Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**Sua implantação está configurada em um domínio dividido (também conhecido como híbrido), onde alguns usuários possuem seus servidor inicial em uma implantação local e outros usuários configurados com um servidor inicial em um ambiente online?**

Definir as configurações conforme detalhado nos tópicos [Configure Policies to Control Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [habilitar ou desabilitar a Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) e [criar ou editar provedores federados SIP hospedados do Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

Se você prefere uma tabela que lista os requisitos:


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
<th>Guia em Federação e acesso externo (em toda) Federação ou tipo de acesso externo (down)</th>
<th>Política de Acesso Externo</th>
<th>Configuração de Borda de Acesso</th>
<th>Domínios Federados SIP</th>
<th>Provedores Federados SIP</th>
<th>Parceiro Federado XMPP</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuários Remotos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurar políticas para controlar o acesso de usuário remoto no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Contatos Federados SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Gerenciar domínios federados SIP para sua organização no Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contatos Federados XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configurar políticas para controlar o acesso de usuário federado do XMPP no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Gerenciar parceiros federados do XMPP no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Domínio Dividido/Usuários Híbridos</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Criar ou editar provedores federados SIP hospedados Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contatos de Serviço de IM Público</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Criar ou editar provedores federados SIP públicos no Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Acesso do usuário anônimo para reuniões e conferências</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Atribuir políticas de conferência para dar suporte a usuários anônimos no Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Você também deve considerar as seguintes definições de configuração em políticas de conferência: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">criar ou modificar uma política de conferência na</A> <A href="lync-server-2013-conferencing-policy-settings-reference.md">referência de configurações de política de conferência do Lync Server 2013 e do Lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


É possível definir configurações de acesso de usuário externo, incluindo qualquer política que deseja usar para controlar o acesso de usuário externo, mesmo se não habilitou o acesso de usuário externo para sua organização. No entanto, as políticas e outras configurações definidas entram em vigor apenas quando você habilitou acesso de usuário externo para sua organização. Os usuários externos não podem se comunicar com os usuários da sua organização quando o acesso de usuário externo está desabilitado ou se nenhuma política de acesso do usuário externo está configurada para suporá-lo.

Sua implantação de borda autentica os tipos de usuário externos (exceto usuários anônimos que são autenticados pelo ID da conferência e uma chave de passe enviada ao participante anônimo ao criar a conferência e convidar os participantes) e controla o acesso com base em como você configura seu suporte de borda. Para poder controlar as comunicações, é possível configurar uma ou mais políticas e definir outras configurações que definem como os usuários dentro e fora da sua implantação se comunicam entre si. As políticas e configurações incluem a política global padrão para acesso de usuário externo, além de políticas local e do usuário que podem ser criadas e configuradas para habilitar um ou mais tipos de acesso de usuário externo para locais ou usuários específicos.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Gerenciar política de acesso externo no Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Gerenciar a configuração de borda de acesso para sua organização no Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Gerenciar domínios federados SIP para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Gerenciar provedores federados SIP para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Gerenciar parceiros federados do XMPP no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configurando o suporte de Federação para um cliente do Lync Online no Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

