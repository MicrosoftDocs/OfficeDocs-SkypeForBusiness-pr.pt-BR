---
title: 'Lync Server 2013: configuração de Federação do Lync'
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
ms.openlocfilehash: ce06c67e3c7e90f8e1170edb82e515f66be7a2ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Configurando a Federação do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-03-27_

Se o servidor de borda já foi implantado nos servidores, a adição dos recursos de cenários federados é o próximo passo. Se os servidores de borda ainda não foram definidos, faça isso primeiro. Para obter detalhes, consulte: [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento e [implantação de acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.

<div>


> [!NOTE]  
> Se você pretende instalar uma combinação de federação XMPP, federação do Lync ou uma conectividade pública de mensagens instantâneas, é possível implantá-las simultaneamente ou uma de cada vez. Se configurar as opções com o Construtor de Topologias e o shell de gerenciamento do Lync Server e executar o Assistente de implantação no servidor de borda depois de configurar as opções para um, dois ou todos os três tipos de federação, será possível reduzir o número de etapas necessárias.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Instalando a federação do Lync no Construtor de Topologias e o Assistente de implantação

1.  Em um servidor front-end, abra o Construtor de Topologias. Expanda os pools de borda e clique com o botão direito do mouse no servidor de borda ou pool de servidores de borda. Selecione Editar propriedades.

2.  Em Editar Propriedades, sob Geral, selecione Habilitar Federação para este pool de borda (Porta 5061). Clique em OK.

3.  Clique em Ação, selecione Topologia, selecione Publicar. Quando a mensagem sobre Publicar a topologia surgir, clique em Próxima. Quando Publicar for concluído, clique em Concluir.

4.  No servidor de borda, abra o Assistente de Implantação do Lync Server. Clique em Instalar ou Atualizar Sistema do Lync Server; em seguida, clique em Instalação ou Remover Componentes do Lync Server. Clique em Executar Novamente.

5.  Em Instalar Componentes do Lync Server, clique em Avançar. A tela de resumo mostrará as ações conforme forem executadas. Depois que a implantação estiver concluída, clique em Exibir Log para exibir os arquivos de log disponíveis. Clique em Concluir para concluir a implantação.
    
    <div>
    

    > [!IMPORTANT]  
    > É possível selecionar esta opção, mas apenas um pool de borda ou servidor de borda de sua organização pode ser publicado externamente para federação. Todo o acesso de usuários federados, inclusive usuários públicos de IM (mensagens instantâneas), atravessa o mesmo pool de borda ou servidor de borda único. Por exemplo, se sua implantação contém um pool de borda ou servidor de borda único implantado em Nova Iorque e outro implantado um Londres e você habilita o suporte à federação no pool de borda ou servidor de borda único de Nova Iorque, o tráfego do sinal para os usuários federados atravessará o pool de borda ou servidor de borda único de Nova Iorque. Isso é verdadeiro até mesmo para comunicações com os usuários de Londres, embora um usuário interno de Londres que liga para um usuário federado do Nova Iorque use um pool ou servidor de borda de Londres para o tráfego de áudio/vídeo.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Configurando a federação com parceiros

1.  Para configurar uma federação bem-sucedida com outro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 ou Office Communicator 2007, selecione o tipo de Federação da tabela a seguir e defina Registros SRV DNS, host DNS (A ou AAAA para IPv6) e configurar políticas aplicáveis ao tipo de Federação:
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Tipo de federação</th>
    <th>Registros DNS</th>
    <th>Definição de política</th>
    <th>Observações</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Domínio do parceiro descoberto</p></td>
    <td><p>Configure o registro SRV do formato _sipfederationtls. _tcp. &lt;nome&gt;de domínio externo onde o valor de porta para o registro SRV é TCP 5061 e o <strong>host que oferece esse serviço</strong> é definido como SIP. &lt;nome&gt; do domínio externo – o FQDN do serviço de borda de acesso. Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte à borda no Lync Server 2013</a> para obter detalhes sobre como criar o registro SRV</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>As versões anteriores se referiam a esse tipo de federação como <strong>Federação avançada aberta</strong>. A criação do registro SRV é obrigatória para esse tipo de federação e serve para permitir que outros parceiros descubram sua federação.</p></td>
    </tr>
    <tr class="even">
    <td><p>Domínio de parceiro permitido</p></td>
    <td><p>Configure o registro SRV do formato _sipfederationtls. _tcp. &lt;nome&gt;de domínio externo onde o valor de porta para o registro SRV é TCP 5061 e o <strong>host que oferece esse serviço</strong> é definido como SIP. &lt;nome&gt; do domínio externo – o FQDN do serviço de borda de acesso. Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte à borda no Lync Server 2013</a> para obter detalhes sobre como criar o registro SRV</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Versões anteriores mencionadas nesse tipo de Federação como <strong>Federação aprimorada</strong>. A criação do registro SRV é opcional para esse tipo de federação e serve para permitir que outros parceiros descubram sua federação. Isso é obviamente uma <strong>Federação avançada aberta</strong> ou um <strong>Domínio de parceiro descoberto</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Servidor de parceiro permitido</p></td>
    <td><p>Configurar o nome de domínio SIP e o FQDN do servidor de borda de parceiro como um parceiro de Federação em políticas</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar suporte para domínios externos permitidos no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar suporte para domínios externos bloqueados no Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Esse tipo de federação é a definição de uma relação um-para-um e não permite a descoberta de outros parceiros de federação. Cada parceiro de federação é configurado explicitamente. Nas versões anteriores, isso era conhecido como <strong>Federação direta</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>Hospedando provedor e provedor de IM público</p></td>
    <td><p>Nenhum requisito específico de DNS é definido para esse tipo de federação</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Criar ou editar provedores federados SIP públicos no Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Criar ou editar provedores federados SIP hospedados Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Esse tipo de federação define os provedores de serviços e hospedagem que você deseja configurar para seus usuários. Os usos mais comuns incluem a configuração de provedores de IM públicos como Windows Live Messenger, Yahoo! e AOL, bem como provedores de hospedagem como o Lync Online e o Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P>
    > <LI>
    > <P>O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</P>
    > <LI>
    > <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Defina e configure todos os hosts DNS exigidos (A ou AAAA para IPv6) e registros SRV de DNS

3.  Defina e configure qualquer política usando o painel de controle do Lync Server ou usando o Shell de gerenciamento do Lync Server e os cmdlets apropriados. Para obter detalhes sobre os cmdlets do Shell de gerenciamento do Lync Server, confira [cmdlets de Federação e acesso externo no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > O Lync Room System (LRS) não mostra o botão ingressar para reuniões enviadas por organizadores em parceiros federados do Lync. Para que um link de ingresso na reunião apareça no LRS, a organização de envio deve habilitar o TNEF usando o seguinte cmdlet:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Observe que isso não é LRS específico. O Outlook e o Lync também não mostraram links de ingresso nesse caso, pois as propriedades MAPI não são transportadas, mas no caso do Outlook, o usuário pode abrir o convite da reunião e clicar na URL da reunião. Quando TNEFEnabled é definido como true, o Exchange 2013 não distribui propriedades MAPI, incluindo OnlineMeetingExternalLink e o botão de associação será mostrado no lembrete.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento para SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Gerenciamento de Federação e acesso externo ao Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

