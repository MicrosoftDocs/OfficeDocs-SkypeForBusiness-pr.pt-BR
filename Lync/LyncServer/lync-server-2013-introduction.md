---
title: Lync Server 2013 introdução
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b0b6868486f9486758d2a346dd62339d98ed1e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Introdução ao Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

Lync Server 2013 e seu software cliente, como o Lync 2013, permitem que os usuários se conectem de novas maneiras e permaneçam conectados, independentemente do local físico. Lync e Lync Server reúne as diferentes maneiras pelas quais as pessoas se comunicam em uma única interface de cliente, são implantadas como uma plataforma unificada e são administradas por meio de uma única infraestrutura de gerenciamento.

Esta tabela e as seções a seguir ilustram os principais conjuntos de recursos ou *cargas de trabalho*que o Lync Server oferece para seus usuários.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Carga de trabalho</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM e presença</p></td>
<td><p>Mensagens instantâneas (IM) e presença ajudam os usuários a encontrar e se comunicar uns com os outros com eficiência e eficácia.</p>
<p>O IM fornece uma plataforma de mensagens instantâneas com histórico de conversas e oferece suporte à conectividade pública de IM com usuários de redes públicas de IM, como MSN/Windows Live, Yahoo!, AOL e Google Talk.</p>
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
<p>A presença estabelece e exibe a disponibilidade e a disposição pessoais de um usuário para se comunicar através do uso de Estados comuns, como <strong>disponível</strong> ou <strong>ocupado</strong>, bem como Estados mais detalhados, como <strong>reversão</strong> e <strong>não incomodar</strong>. Essas informações de presença avançada permitem que outros usuários façam imediatamente as opções de comunicação efetivas.</p></td>
</tr>
<tr class="even">
<td><p>Conferências</p></td>
<td><p>O Lync Server inclui suporte para conferência de mensagens instantâneas, conferência de áudio, webconferência, conferência de vídeo e compartilhamento de aplicativos, para reuniões programadas e improvisadas. Todos esses tipos de reunião são compatíveis com um único cliente. O Lync Server também oferece suporte à conferência discada para que os usuários de telefones PSTN (rede telefônica pública comutada) possam participar da parte de áudio de conferências.</p>
<p>As conferências podem mudar e aumentar sem problemas em tempo real. Por exemplo, uma única conferência pode começar como apenas mensagens instantâneas entre alguns usuários e escalonar para uma conferência de áudio com compartilhamento de área de trabalho e um público maior de forma instantânea, fácil e sem interromper o fluxo de conversa.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p>O <em>Enterprise Voice</em> é a oferta VoIP (Voice over Internet Protocol) no Lync Server. Ele oferece uma opção de voz para aprimorar ou substituir sistemas PBX (Private Branch Exchange) tradicionais. Além dos recursos de telefonia completos de um IP PBX, o Enterprise Voice é integrado à presença avançada, IM, colaboração e reuniões. Recursos como atendimento de chamada, retenção, retomada, transferência, encaminhamento e sobretroca são suportados diretamente, enquanto as teclas de discagem de velocidade personalizada são substituídas por listas de contatos e o intercomunicador automático é substituído por IM.</p>
<p>O Enterprise Voice oferece suporte à alta disponibilidade por meio do controle de admissão de chamadas (CAC), sustentabilidade do escritório de filial e opções estendidas para resiliência de dados.</p></td>
</tr>
<tr class="even">
<td><p>Suporte para usuários remotos</p></td>
<td><p>Você pode fornecer a funcionalidade completa do Lync Server para usuários que atualmente estão fora dos firewalls da sua organização implantando servidores chamados <em>servidores de borda</em> para fornecer uma conexão para esses usuários remotos. Esses usuários remotos podem se conectar a conferências usando um computador pessoal com o Lync 2013 instalado, o telefone ou uma interface da Web.</p>
<p>A implantação de servidores de borda também permite a <em>Federação</em> com organizações de parceiros ou fornecedores. Uma relação federada permite que os usuários coloquem usuários federados em suas listas de contatos, informações de presença e mensagens instantâneas do Exchange com esses usuários e as convidados para chamadas de áudio, chamadas de vídeo e conferências.</p></td>
</tr>
<tr class="odd">
<td><p>Suporte ao cliente móvel</p></td>
<td><p>Além disso, com os serviços de mobilidade do Lync Server, seus usuários podem acessar a funcionalidade do Lync ao usar os dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia compatíveis e realizar atividades como enviar e receber mensagens instantâneas, exibir contatos e exibição da presença. Além disso, os dispositivos móveis suportam alguns recursos do Enterprise Voice, como clicar para participar de uma conferência, Chamada via Trabalho, acesso a único número, caixa postal e chamadas perdidas. As notificações por push também são suportadas para dispositivos móveis que não dão suporte a aplicativos executados em segundo plano.</p></td>
</tr>
<tr class="even">
<td><p>Integração com outros produtos</p></td>
<td><p>O Lync Server integra-se com vários outros produtos para fornecer outros benefícios aos seus usuários e administradores.</p>
<p>As ferramentas de reunião são integradas ao Outlook para permitir que os organizadores agendem uma reunião ou iniciem uma conferência improvisada com um único clique e facilitem que os participantes ingressem.</p>
<p>As informações de presença são integradas no Outlook e no SharePoint.</p>
<p>A Unificação de mensagens (UM) do Exchange oferece vários recursos de integração. Os usuários podem ver se têm uma nova caixa postal no Lync Server. Eles podem clicar em um botão Executar na mensagem do Outlook para ouvir a caixa postal de áudio ou exibir uma transcrição da caixa postal na mensagem de notificação.</p>
<p>Além disso, a execução do Lync Server 2013 com o Exchange 2013 permite vários novos recursos, como um repositório unificado de contatos, que pode ser acessado por clientes de ambos os produtos, bem como fotos de alta resolução para contatos armazenados no banco de dados do Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Implantação simples</p></td>
<td><p>Para ajudá-lo a planejar e implantar seus servidores e clientes, o Lync Server fornece o construtor de topologias.</p>
<p>O construtor de topologias é um componente de instalação do Lync Server. Use o construtor de topologias para criar, ajustar e publicar sua topologia planejada. Ele também valida sua topologia antes de iniciar as instalações do servidor. Quando você instala o Lync Server em servidores individuais, o programa de instalação implanta o servidor conforme indicado na topologia.</p></td>
</tr>
<tr class="even">
<td><p>Gerenciamento simples</p></td>
<td><p>Depois de implantar o Lync Server, ele oferece as seguintes ferramentas de gerenciamento poderosas e simplificadas:</p>
<ul>
<li><p>Gerenciamento de configuração central, que permite gerenciar alterações centralmente e fazer com que elas sejam replicadas rapidamente para toda a implantação.</p></li>
<li><p>Painel de controle do Lync Server, uma interface gráfica de usuário baseada na Web para administradores. Com esta interface de usuário baseada na Web, os administradores do Lync Server podem gerenciar seus sistemas de qualquer lugar na rede corporativa, sem precisar de software de gerenciamento especializado instalado em seus computadores.</p></li>
<li><p>Ferramenta de gerenciamento de linha de comando do Lync Server Management Shell, que se baseia na interface de linha de comando do Windows PowerShell. Ele fornece um conjunto de comandos avançado para a administração de todos os aspectos do produto e permite que os administradores do Lync Server automatizem tarefas repetitivas usando uma ferramenta familiar.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Enquanto os recursos de mensagens instantâneas e presença são instalados automaticamente em cada implantação do Lync Server, você pode escolher se deseja implantar a conferência, o Enterprise Voice e o acesso de usuários remotos para adaptar sua implantação às necessidades da sua organização.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [IM e presença no Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Conferência no Lync Server 2013](lync-server-2013-conferencing.md)

  - [Enterprise Voice no Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Escalabilidade com Lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

