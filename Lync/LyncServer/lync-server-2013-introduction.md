---
title: 'Lync Server 2013: Introdução'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Introdução ao Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

O Lync Server 2013 e o software cliente, como o Lync 2013, permitem que os usuários se conectem de novas maneiras e permaneçam conectados, independentemente de sua localização física. O Lync e o Lync Server reúne as diferentes maneiras pelas quais as pessoas se comunicam em uma única interface de cliente, são implantadas como uma plataforma unificada e são administradas por meio de uma única infraestrutura de gerenciamento.

Esta tabela e as seções a seguir ilustram os principais conjuntos de recursos ou *cargas de trabalho*que o Lync Server fornece para seus usuários.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Redução</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM e presença</p></td>
<td><p>O recurso de mensagens instantâneas (IM) e a presença ajudam os usuários a encontrarem e se comunicar uns com os outros com eficiência e eficácia.</p>
<p>As mensagens instantâneas fornecem uma plataforma de mensagens instantâneas com histórico de conversas e aceita conectividade de mensagens de chat públicas com usuários de redes públicas de mensagens instantâneas, como MSN/Windows Live, Yahoo!, AOL e Google Talk.</p>
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
<p>A presença estabelece e exibe a disponibilidade pessoal do usuário e a disposição para se comunicar por meio do uso de Estados comuns, como <strong>disponível</strong> ou <strong>ocupado</strong>, bem como Estados mais detalhados, como voltados para o <strong>momento</strong> e não <strong>incomodar </strong>. Essas informações de presença avançada permitem que outros usuários façam imediatamente opções de comunicação eficazes.</p></td>
</tr>
<tr class="even">
<td><p>Conferência</p></td>
<td><p>O Lync Server inclui suporte para conferências de mensagens de chat, videoconferências, webconferência, videoconferência e compartilhamento de aplicativos, para reuniões programadas e improvisadas. Todos esses tipos de reunião são compatíveis com um único cliente. O Lync Server também oferece suporte à conferência discada para que os usuários de telefones PSTN (rede telefônica pública comutada) possam participar na parte de áudio de conferências.</p>
<p>As conferências podem alterar e crescer perfeitamente em tempo real. Por exemplo, uma conferência única pode começar como apenas mensagens instantâneas entre alguns usuários e encaminhar para uma videoconferência com compartilhamento de área de trabalho e um público maior, de modo rápido e sem interromper o fluxo de conversa.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p>O <em>Enterprise Voice</em> é a oferta de protocolo de voz pela Internet (VoIP) no Lync Server. Ele fornece uma opção de voz para aprimorar ou substituir sistemas PBX (Private Branch Exchange) tradicionais. Além dos recursos de telefonia completos de um IP PBX, o Enterprise Voice é integrado com presença avançada, mensagens instantâneas, colaboração e reuniões. Recursos como atendimento de chamada, retenção, retomada, transferência, encaminhar e encaminhar são suportados diretamente, enquanto as teclas de discagem rápida personalizada são substituídas por listas de contatos e os intercomunicados automáticos são substituídos por mensagens instantâneas.</p>
<p>O Enterprise Voice dá suporte à alta disponibilidade por meio do controle de admissão de chamadas (CAC), à sustentabilidade do escritório da filial e às opções estendidas para resiliência de dados.</p></td>
</tr>
<tr class="even">
<td><p>Suporte a usuários remotos</p></td>
<td><p>Você pode fornecer a funcionalidade completa do Lync Server para usuários que atualmente estão fora dos firewalls da sua organização implantando servidores chamados de <em>servidores de borda</em> para fornecer uma conexão para esses usuários remotos. Esses usuários remotos podem se conectar a conferências usando um computador pessoal com o Lync 2013 instalado, o telefone ou uma interface da Web.</p>
<p>A implantação de servidores de borda também permite que você se <em>agrupe</em> com organizações de parceiros ou fornecedores. Uma relação federada permite que os usuários coloquem usuários federados em suas listas de contatos, troque informações de presença e mensagens de chat com esses usuários e as convidem para chamadas de áudio, chamadas com vídeo e conferências.</p></td>
</tr>
<tr class="odd">
<td><p>Suporte ao cliente móvel</p></td>
<td><p>Além disso, com os serviços de mobilidade do Lync Server, seus usuários podem acessar a funcionalidade do Lync ao usar dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia e executar tais atividades como enviar e receber mensagens instantâneas, ver contatos, e ver a presença. Além disso, os dispositivos móveis dão suporte a alguns recursos de voz empresarial, como o clique para ingressar em uma conferência, fazer chamadas pelo trabalho, por um único número, por correio de voz e chamadas perdidas. Também há suporte para notificações por push em dispositivos móveis que não dão suporte a aplicativos executados em segundo plano.</p></td>
</tr>
<tr class="even">
<td><p>Integração com outros produtos</p></td>
<td><p>O Lync Server integra-se com vários outros produtos para fornecer benefícios adicionais aos seus usuários e administradores.</p>
<p>As ferramentas de reunião são integradas ao Outlook para permitir que os organizadores agendem uma reunião ou iniciem uma conferência improvisada com um único clique e facilitem que os participantes ingressem.</p>
<p>As informações de presença são integradas ao Outlook e ao SharePoint.</p>
<p>O Exchange Unified Messaging (UM) fornece vários recursos de integração. Os usuários podem ver se têm uma nova caixa postal no Lync Server. Eles podem clicar no botão reproduzir na mensagem do Outlook para ouvir a caixa postal de áudio ou exibir uma transcrição da caixa postal na mensagem de notificação.</p>
<p>Além disso, a execução do Lync Server 2013 com o Exchange 2013 permite vários novos recursos, como um repositório de contatos unificado que pode ser acessado por clientes de ambos os produtos, bem como fotos de alta resolução para os contatos armazenados no banco de dados do Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Implantação simples</p></td>
<td><p>Para ajudar você a planejar e implantar seus servidores e clientes, o Lync Server fornece o construtor de topologias.</p>
<p>O construtor de topologias é um componente de instalação do Lync Server. Você usa o construtor de topologias para criar, ajustar e publicar sua topologia planejada. Ele também valida sua topologia antes de começar as instalações do servidor. Quando você instala o Lync Server em servidores individuais, o programa de instalação implanta o servidor conforme direcionado na topologia.</p></td>
</tr>
<tr class="even">
<td><p>Gerenciamento simples</p></td>
<td><p>Depois de implantar o Lync Server, ele oferece as seguintes ferramentas de gerenciamento poderosas e otimizadas:</p>
<ul>
<li><p>Gerenciamento de configuração central, que permite que você gerencie as alterações de forma centralizada e faça com que elas sejam replicadas rapidamente para toda a implantação.</p></li>
<li><p>Painel de controle do Lync Server, uma interface gráfica do usuário baseada na Web para administradores. Com essa interface do usuário baseada na Web, os administradores do Lync Server podem gerenciar seus sistemas de qualquer lugar da rede corporativa, sem precisar de um software de gerenciamento especializado instalado em seus computadores.</p></li>
<li><p>Ferramenta de gerenciamento de linha de comando do Shell de gerenciamento do Lync Server, que se baseia na interface de linha de comando do Windows PowerShell. Ele fornece um conjunto de comandos avançados para a administração de todos os aspectos do produto e permite que os administradores do Lync Server automatizem tarefas repetitivas usando uma ferramenta conhecida.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Enquanto os recursos de mensagem instantânea e presença são instalados automaticamente em toda a implantação do Lync Server, você pode escolher se deseja implantar o acesso de conferência, do Enterprise Voice e do usuário remoto para ajustar a implantação às necessidades da sua organização.

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

