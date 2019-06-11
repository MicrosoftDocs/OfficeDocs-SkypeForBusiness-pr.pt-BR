---
title: 'Lync Server 2013: Interoperabilidade do Cliente no Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Interoperabilidade do Cliente no Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-03-04_

Este tópico discute a capacidade dos clientes do Microsoft Lync Server 2013 de coexistência e interação com clientes de versões anteriores do Lync Server e do Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Compatibilidade do servidor e do cliente

A tabela a seguir mostra as combinações de versões de servidor e versões de cliente com suporte. Esta tabela indica se há suporte para entrada quando o cliente tenta se conectar ao servidor indicado. O Lync Server 2013 dá suporte à versão anterior do cliente. Além disso, ao contrário das versões anteriores, o Lync Server 2010 oferece suporte aos novos clientes do Lync 2013. Isso permite que as organizações que estão fazendo a atualização do Lync Server 2010 para distribuir novos clientes independentemente das atualizações do Lync Server.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Com suporte</p></td>
<td><p>Supported5</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Compatível </p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Compatível </p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Compatível </p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="even">
<td><p>Chat de Grupo do Lync 2010</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Sem suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Não Supported3</p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Compatível </p></td>
<td><p>Compatível</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>Sem suporte</p></td>
<td><p>Compatível </p></td>
<td><p>Compatível</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Sem suporte</p></td>
<td><p>Compatível </p></td>
<td><p>Compatível</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Sem suporte</p></td>
<td><p>Compatível </p></td>
<td><p>Compatível</p></td>
</tr>
<tr class="odd">
<td><p>Aplicativo Lync Windows Store</p></td>
<td><p>Compatível </p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
</tbody>
</table>


1Para obter detalhes, confira [migrar do Lync Server 2010, chat em grupo ou Office Communications Server 2007 R2 Grupo chat para o Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, a funcionalidade do chat em grupo estava disponível com o servidor de chat em grupo, um aplicativo confiável de terceiros para o Lync Server 2010. Os clientes do Lync 2013 não são compatíveis com o Lync Server 2010, o chat em grupo.

o 3Lync Web App 2013 agora oferece uma experiência completa na reunião, incluindo áudio e vídeo do computador, e é considerado como substituto para o participante do Lync 2010. O Lync 2010 se conectará ao Lync Server 2013 somente quando você estiver usando um navegador sem suporte (Internet Explorer 6 ou Internet Explorer 7) e Windows XP.

os recursos de presença e de mensagem instantânea do 4The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não são. Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para presença e interoperabilidade de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.

5 para obter limitações, consulte "recurso de conferência de suporte para clientes do Lync 2013 no Lync Server 2010 reuniões" mais adiante neste tópico.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interoperabilidade entre clientes

Com o lançamento do Lync Server 2013, várias versões de cliente podem interagir perfeitamente em cenários ponto a ponto e conferência. Esta seção discute a disponibilidade de recursos quando os usuários interagem com outros usuários que usam versões diferentes de clientes e servidores.

<div>

## <a name="peer-to-peer-feature-support"></a>Suporte a recursos ponto a ponto

Os recursos ponto a ponto são suportados para os usuários que são hospedados em diferentes versões do servidor e quem está usando versões diferentes do cliente. A experiência do usuário final e os recursos disponíveis são consistentes com os recursos do cliente do usuário e a versão do servidor ao qual o usuário está conectado. Em outras palavras:

  - Se um usuário estiver conectado ao Lync Server 2013 com um cliente mais antigo, o usuário terá a mesma experiência para a qual ele é usado. Nenhum dos novos recursos introduzidos no Lync Server 2013 estará disponível até que o cliente do usuário seja atualizado. Exemplos incluem modo de exibição de galeria de vídeos, vídeo em HD, compartilhamento do PowerPoint atualizado e a opção de ativar o áudio e o vídeo dos participantes após a entrada da reunião. Os novos recursos estão descritos nos [novos recursos de conferência do Lync server 2013](lync-server-2013-new-conferencing-features.md) e novidades [para clientes do Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Se um usuário estiver conectado ao Lync Server 2010 com um cliente do Lync 2013, todos os novos recursos não suportados pelo Lync Server 2010 ficarão indisponíveis até que o usuário seja movido para o Lync Server 2013.

A tabela a seguir compara a disponibilidade de recursos em sessões ponto a ponto nas quais o cliente está conectado ao Lync Server 2013 ou ao Lync Server 2010.

<div>


> [!NOTE]  
> O Lync Web App e o Lync 2010 participantes são somente clientes de reunião e não estão incluídos nesta tabela.



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente</th>
<th>Mensagens instantâneas</th>
<th>Presença</th>
<th>Voz</th>
<th>Vídeo</th>
<th>Compartilhamento de Aplicativos</th>
<th>Transferência de arquivos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
<td><p>Yes1</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>MENSAGEM de chat pública (AOL, Yahoo!)</p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>MENSAGEM de chat pública (MSN, Windows Live Messenger)</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de desligamento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário e por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. O recurso da Microsoft para fornecer esse serviço tem o apoio acordado do Yahoo!, o contrato subjacente para o qual não será renovado.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de mensagens instantâneas e de voz.</P></LI></UL>



</div>

1 no Office Communicator 2007 R2, somente o compartilhamento de área de trabalho (e não o compartilhamento de programas) está disponível.

<div>


> [!NOTE]  
> O compartilhamento de área de trabalho entre o Office Communicator 2007 R2 e o Skype for Business 2015 não pode ser iniciado a partir do cliente mais recente quando a interface do usuário do cliente do Skype for Business 2015 é imposta.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Suporte do recurso de conferência para clientes do Lync 2013 no Lync Server 2010 reuniões

Quando os usuários ingressam em reuniões do Lync Server 2010 com um cliente Lync 2013, eles têm acesso aos recursos do cliente Lync 2013 com as seguintes exceções:

  - Nas opções de gerenciamento de **participantes** , que podem ser acessadas apontando para o ícone pessoas na janela da reunião, a opção **nenhuma mensagem instantânea de reunião** não funciona.

  - O modo de exibição de galeria não funciona em videoconferências. O usuário vê apenas o alto-falante ativo em vez de todos os alto-falantes. Na lista de opções **escolher um layout** , o **modo de exibição Galeria** não está disponível

  - A lista de participantes é exibida por padrão em videoconferências.

  - Ao clicar com o botão direito do mouse em um usuário na lista de participantes, o botão **bloquear as opções de gerenciamento de participantes do vídeo** e **fixar em Galeria** não estará disponível.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Suporte do recurso de conferência nas reuniões do Lync Server 2013

O Lync Server 2013 oferece novos recursos de conferência que se tornam disponíveis para os usuários após suas contas serem movidos para o Lync Server 2013 e que entram com o cliente Lync 2013. Os exemplos incluem modo de exibição de galeria de vídeo, vídeo em alta definição, compartilhamento de PowerPoint e opção para desativar o áudio e o vídeo dos participantes após a entrada da reunião. Os novos recursos estão descritos nos [novos recursos de conferência do Lync server 2013](lync-server-2013-new-conferencing-features.md) e novidades [para clientes do Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Em reuniões do Lync Server 2013, determinados recursos de conferência têm suporte para os usuários que são hospedados em diferentes versões do servidor e quem usa diferentes clientes e versões do cliente. Quando os clientes ingressam em uma reunião do Lync Server 2013, os usuários têm acesso aos recursos e funcionalidades mostrados nessa tabela.


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente</th>
<th>Mensagem instantânea ponto a ponto</th>
<th>Voz</th>
<th>Vídeo</th>
<th>Compartilhamento de Aplicativos</th>
<th>PowerPoint</th>
<th>Transferência de arquivos</th>
<th>Quadro de comunicações</th>
<th>Poll</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Yes2</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Yes3</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1 no Office Communicator 2007 R2, somente o compartilhamento de área de trabalho (e não o compartilhamento de programas) está disponível.

2 o Lync Server 2013 usa um mecanismo atualizado para carregar arquivos do PowerPoint. Os usuários do Lync Web App que ingressarem em uma reunião originalmente agendada no Lync Server 2010 podem exibir e navegar em apresentações do PowerPoint, mas não podem carregar arquivos do PowerPoint.

3 se a reunião tiver sido agendada nos slides do Lync Server 2013 e do PowerPoint foram carregadas por um cliente do Lync 2013, os usuários do Lync 2010 terão acesso somente para exibição aos slides. Por outro lado, se os slides do PowerPoint foram carregados por um usuário do Lync 2010, os usuários do Lync Server 2013 poderão exibir e os slides e, se o Office Web Apps estiver configurado, acessar novos recursos, como exibição de resolução mais alta, animações, transições de slides e vídeo inserido. Para obter mais informações, consulte Configurando [a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

os recursos de presença e de mensagem instantânea do 4The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não são. Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para presença e interoperabilidade de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Agendando o suporte ao suplemento

O suporte do servidor para os vários suplementos de agendamento é consistente com a compatibilidade de versão do servidor e do cliente. Em geral, os seguintes suplementos de agendamento são suportados no Lync Server 2013. No entanto, as versões anteriores dos suplementos não fornecem novos recursos de suplemento do Lync 2013, como a opção de ativar o áudio e o vídeo dos participantes após a entrada da reunião.

  - **O suplemento de reunião online para o Lync 2013**   oferece os mesmos recursos que o suplemento de reunião online do Lync 2010, com a adição de controles de desativação de participantes, que permitem que os organizadores da reunião agendem conferências com áudio e vídeo de participantes com mudo ativado assume. Os administradores também podem personalizar os convites para reunião da organização adicionando um logotipo personalizado, uma URL de suporte, uma URL de isenção de responsabilidade legal ou texto de rodapé personalizado.

  - **O suplemento de reunião online para o Lync 2010**   fornece agendamento para reuniões do Lync e remove a funcionalidade de agendar conferências do Office Live Meeting.

  - **O suplemento de conferência do Office Communicator 2007 R2**   fornece agendamento para conferências do Office Live Meeting e do Office Communicator 2007 R2. 

<div>


> [!NOTE]  
> Não é possível agendar conferências do Live Meeting no Lync Server 2013.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente de agendamento</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Suplemento de reunião online do Lync 2013 (pode ser usado com o Office 2013, o Outlook 2010 e o Outlook 2007)</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte (novos recursos de suplemento não disponíveis)</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="even">
<td><p>Agendador da Web do Lync 2013</p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="odd">
<td><p>Suplemento de Reunião Online para Lync 2010</p></td>
<td><p>Compatível </p></td>
<td><p>Com suporte</p></td>
<td><p>Sem suporte</p></td>
</tr>
<tr class="even">
<td><p>Suplemento de conferência do Office Communicator 2007 R2</p></td>
<td><p>Sem suporte</p></td>
<td><p>Compatível </p></td>
<td><p>Compatível</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Suporte para ingressar em reuniões

Todos os clientes aos quais o Lync Server 2013 dá suporte têm permissão para ingressar em reuniões do Lync 2013. Como o Lync Web App é um componente da Web do servidor, em casos em que o Lync Web App é usado para ingressar em uma reunião do Lync Server 2013, a versão mais recente do Lync Web App é sempre usada.

Os clientes do Lync 2013 podem ingressar em reuniões hospedadas no Lync 2010 e no Office Communications Server 2007 R2 com funcionalidade reduzida. Os recursos na reunião são limitados pela versão do servidor na qual a reunião está hospedada.

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos do aplicativo Lync da Windows Store para o Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Novos recursos de conferência no Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Novidades para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

