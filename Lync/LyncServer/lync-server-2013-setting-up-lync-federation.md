---
title: 'Lync Server 2013: Configuração de federação do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Configuração de federação do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-03-27_

Se você já tiver implantado o servidor de borda ou servidores de borda, adicionar os recursos de cenários agrupados será encaminhado diretamente. Se você não configurou os servidores de borda, deve primeiro fazer isso. Para obter detalhes, consulte: [planejando o acesso de usuários externos no Lync server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento e [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.

<div>


> [!NOTE]  
> Se você pretende configurar qualquer combinação de agrupamento XMPP, Federação do Lync ou conectividade de mensagens instantâneas públicas, poderá implantá-los simultaneamente ou um de cada vez. Se você configurar as opções por meio do construtor de topologias e do Shell de gerenciamento do Lync Server, execute o assistente de implantação no servidor de borda após configurar as opções para um, dois ou todos os três tipos de Federação, você pode reduzir o número de etapas necessárias.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Configurar a Federação do Lync no construtor de topologias e no assistente de implantação

1.  Em um servidor front-end, abra o construtor de topologias. Expanda Pools de bordas e clique com o botão direito do mouse no seu servidor de borda ou no pool do servidor Selecione Editar propriedades.

2.  Em Editar propriedades em geral, selecione Habilitar Federação para este pool de bordas (porta 5061). Clique em OK.

3.  Clique em ação, selecione topologia, selecione publicar. Quando solicitado em publicar a topologia, clique em Avançar. Quando a publicação estiver concluída, clique em concluir.

4.  No servidor de borda, abra o assistente de implantação do Lync Server. Clique em instalar ou atualizar o Lync Server System e, em seguida, clique em configurar ou remover componentes do Lync Server. Clique em executar novamente.

5.  Em configurar componentes do Lync Server, clique em Avançar. A tela Resumo mostrará as ações conforme elas são executadas. Depois que a implantação for concluída, clique em Exibir log para exibir os arquivos de log disponíveis. Clique em concluir para concluir a implantação.
    
    <div>
    

    > [!IMPORTANT]  
    > Você pode selecionar essa opção, mas somente um pool de bordas ou um servidor de borda em sua organização pode ser publicado externamente para Federação. Todo o acesso de usuários federados, incluindo usuários públicos de mensagens instantâneas (IM), passam pelo mesmo pool de bordas ou servidor de borda única. Por exemplo, se sua implantação inclui um pool de bordas ou um servidor de borda única implantado em Nova York e um implantado em Londres e você habilitar o suporte de Federação no pool de bordas de Nova York ou no servidor de borda único, o tráfego de sinal para usuários federados passará pela Nova York Pool de bordas ou servidor de borda único. Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Configurando a Federação com parceiros

1.  Para configurar uma reunião bem-sucedida com outro Microsoft Lync Server 2013, o Lync Server 2010, o Office Communications Server 2007 R2 ou o Office Communicator 2007, selecione o tipo de Federação na tabela a seguir e defina Registros SRV DNS, host DNS (A ou AAAA para IPv6) e configurar políticas aplicáveis ao tipo de Federação:
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Tipo de Federação</th>
    <th>Registros de DNS</th>
    <th>Definição da política</th>
    <th>Observações</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Domínio de parceiro descoberto</p></td>
    <td><p>Configure o registro SRV do formato _sipfederationtls. _tcp. &lt;nome&gt;de domínio externo em que o valor de porta do registro SRV é TCP 5061 e o <strong>host que oferece esse serviço</strong> é definido como SIP. &lt;nome&gt; do domínio externo – o FQDN do serviço de borda de acesso. Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</a> para obter detalhes sobre como criar o registro SRV</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar ou desabilitar descoberta de parceiros de federação no Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Versões anteriores referenciadas a esse tipo de Federação como <strong>Federação aprimorada aberta</strong>. A criação do registro SRV é necessária para esse tipo de Federação e é permitir que outros parceiros descubram sua Federação.</p></td>
    </tr>
    <tr class="even">
    <td><p>Domínio de parceiro permitido</p></td>
    <td><p>Configure o registro SRV do formato _sipfederationtls. _tcp. &lt;nome&gt;de domínio externo em que o valor de porta do registro SRV é TCP 5061 e o <strong>host que oferece esse serviço</strong> é definido como SIP. &lt;nome&gt; do domínio externo – o FQDN do serviço de borda de acesso. Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</a> para obter detalhes sobre como criar o registro SRV</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Versões anteriores referenciadas a esse tipo de Federação como <strong>Federação aprimorada</strong>. A criação do registro SRV é opcional para esse tipo de Federação e é permitir que outros parceiros descubram sua Federação. É claro que, em seguida, é uma <strong>Federação aprimorada aberta</strong>ou um <strong>domínio de parceiro descoberto</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Servidor parceiro permitido</p></td>
    <td><p>Configurar o nome de domínio SIP e o FQDN do servidor de borda de parceiro como um parceiro de Federação em políticas</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar suprote para domínios externos permitidos no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar suporte para domínios externos bloqueados no Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Esse tipo de Federação é a definição de uma relação de um para um e não permite a descoberta de outros parceiros de Federação. Cada parceiro de Federação é configurado explicitamente. Em versões anteriores, isso era conhecido como <strong>Federação direta</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>Provedor de hospedagem e provedor de mensagens de chat públicas</p></td>
    <td><p>Nenhum requisito de DNS específico é definido para esse tipo de Federação</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Criar ou editar fornecedores SIP públicos federados no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Criar ou editar provedores hospedados federados SIP no Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Esse tipo de Federação define serviços e provedores de hospedagem que você deseja configurar para seus usuários. Os usos típicos incluem a configuração de provedores de IM públicos, como o Windows Live Messenger, o Yahoo! e AOL, bem como provedores de hospedagem como o Lync Online e o Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P>
    > <LI>
    > <P>O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</P>
    > <LI>
    > <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Definir e configurar qualquer host DNS obrigatório (A ou AAAA para IPv6) e Registros SRV DNS

3.  Defina e configure qualquer política usando o painel de controle do Lync Server ou usando o Shell de gerenciamento do Lync Server e os cmdlets apropriados. Para obter detalhes sobre os cmdlets do Shell de gerenciamento do Lync Server, consulte [cmdlets de acesso externo e Federação no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > O LRS (Lync Room System) não mostra o botão ingressar para reuniões enviadas por organizadores em parceiros federados do Lync. Para que um link de ingresso na reunião apareça no LRS, a organização de envio deve habilitar o TNEF usando o seguinte cmdlet:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Observe que isso não é LRS específico. O Outlook e o Lync também não mostraram links de junção nesse caso, pois as propriedades MAPI não são transportadas, mas na caixa do Outlook, o usuário pode abrir o convite da reunião e clicar na URL da reunião. Quando TNEFEnabled está definido como true, o Exchange 2013 não distribui propriedades MAPI, incluindo OnlineMeetingExternalLink, e o botão de junção é mostrado no lembrete.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejando o SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Gerenciamento de Federação e acesso externo ao Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

