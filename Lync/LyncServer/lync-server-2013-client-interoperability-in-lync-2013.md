---
title: 'Lync Server 2013: interoperabilidade do cliente no Lync 2013'
description: 'Lync Server 2013: interoperabilidade do cliente no Lync 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549607"
---
# <a name="client-interoperability-in-lync-2013"></a>Interoperabilidade do cliente no Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-03-04_

Este tópico discute a capacidade dos clientes do Microsoft Lync Server 2013 de coexistir e interagir com clientes de versões anteriores do Lync Server e Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Compatibilidade de servidor e cliente

A tabela a seguir exibe as combinações com suporte de versões de cliente e de servidor. Esta tabela indica se é permitido entrar quando o cliente tenta se conectar ao servidor indicado. O Lync Server 2013 oferece suporte à versão anterior do cliente. Além disso, ao contrário de versões anteriores, o Lync Server 2010 oferece suporte aos novos clientes do Lync 2013. Isso permite que as organizações que estão atualizando do Lync Server 2010 distribuem novos clientes independentemente das atualizações do Lync Server.


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
<td><p>Não suportado</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="even">
<td><p>Chat de grupo do Lync 2010</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Não Supported3</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="odd">
<td><p>Aplicativo Lync da Windows Store</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
</tbody>
</table>


1Para obter detalhes, consulte [migração do Lync Server 2010, chat de grupo ou Office Communications Server 2007 R2 Group Chat to Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, a funcionalidade de chat de grupo estava disponível com o servidor de chat de grupo, um aplicativo confiável de terceiros para o Lync Server 2010. Os clientes do Lync 2013 não são compatíveis com o Lync Server 2010, o chat de grupo.

o 3Lync Web App 2013 agora fornece uma experiência de reunião completa, incluindo áudio e vídeo do computador e é considerado como substituto para o participante do Lync 2010. Lync 2010 o participante se conectará ao Lync Server 2013 somente quando você estiver usando um navegador sem suporte (Internet Explorer 6 ou Internet Explorer 7) e Windows XP.

os recursos de presença e IM do 4The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não. Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para a interoperabilidade de presença e de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.

5 para obter limitações, consulte "suporte de recurso de conferência para clientes do Lync 2013 no Lync Server 2010 reuniões", mais adiante neste tópico.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interoperabilidade entre clientes

Com a versão 2013 do Lync Server, várias versões do cliente podem interagir perfeitamente nos cenários de ponto a ponto e de conferência. Esta seção discute a disponibilidade de recursos quando os usuários interagem com outros usuários, que estejam usando versões diferentes de clientes e servidores.

<div>

## <a name="peer-to-peer-feature-support"></a>Suporte ao recurso ponto a ponto

Recursos ponto a ponto são suportados para usuários que estão hospedados em versões diferentes do servidor e que estejam usando versões de cliente diferentes. A experiência do usuário final e os recursos disponíveis são consistentes com os recursos do cliente do usuário e a versão do servidor em que o usuário entrou. Em outras palavras:

  - Se um usuário estiver conectado ao Lync Server 2013 com um cliente mais antigo, o usuário terá a mesma experiência para a qual ele é usado. Nenhum dos novos recursos introduzidos no Lync Server 2013 estará disponível até que o cliente do usuário seja atualizado. Os exemplos incluem visualização de galeria de vídeo, vídeo HD, compartilhamento do PowerPoint atualizado e a opção de ativar o áudio e vídeo de todos os participantes na entrada da reunião. Os novos recursos são descritos em [novos recursos de conferência no Lync Server 2013](lync-server-2013-new-conferencing-features.md) e [o que há de novo para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Se um usuário estiver conectado ao Lync Server 2010 com um cliente do Lync 2013, todos os novos recursos não suportados pelo Lync Server 2010 não estarão disponíveis até que o usuário seja movido para o Lync Server 2013.

A tabela a seguir compara a disponibilidade de recursos em sessões ponto a ponto nas quais o cliente está conectado ao Lync Server 2013 ou ao Lync Server 2010.

<div>


> [!NOTE]  
> Lync Web App e Lync 2010 o participante são clientes somente da reunião e não estão incluídos nesta tabela.



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
<th>Sistema de Mensagens Instantâneas</th>
<th>Presença</th>
<th>Voz</th>
<th>Vídeo</th>
<th>Compartilhamento de Aplicativos</th>
<th>Transferência de Arquivos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Yes1</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>Rede pública de IM (AOL, Yahoo!)</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Mensagens instantâneas públicas (MSN, Windows Live Messenger)</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
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
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de desligamento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>..</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário, por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual não será renovado.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de IM e voz.</P></LI></UL>



</div>

1 no Office Communicator 2007 R2, somente o compartilhamento de área de trabalho (e não o compartilhamento de programas) está disponível.

<div>


> [!NOTE]  
> O compartilhamento de área de trabalho entre o Office Communicator 2007 R2 e o Skype for Business 2015 não pode ser iniciado a partir do cliente mais recente quando a interface de usuário do cliente do Skype for Business 2015 é imposta.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Suporte de recurso de conferência para clientes do Lync 2013 nas reuniões do Lync Server 2010

Quando os usuários ingressam em reuniões do Lync Server 2010 com um cliente do Lync 2013, eles têm acesso aos recursos do cliente do Lync 2013 com as seguintes exceções:

  - Nas opções de gerenciamento de **participantes** , que podem ser acessadas apontando para o ícone pessoas na janela da reunião, a opção **sem im de reunião** não funciona.

  - O modo de exibição de galeria não funciona em videoconferências. O usuário vê apenas o alto-falante ativo em vez de todos os alto-falantes. Na lista de opções de **escolha um layout, o modo de** exibição de **Galeria** não está disponível

  - A lista de participantes é exibida por padrão em videoconferências.

  - Ao clicar com o botão direito do mouse em um usuário na lista de participantes, as opções **bloquear o gerenciamento do participante de vídeo** e **fixar na Galeria** não estarão disponíveis.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Suporte de recurso de conferência nas reuniões do Lync Server 2013

O Lync Server 2013 fornece novos recursos de conferência que ficam disponíveis para os usuários depois que suas contas são movidas para o Lync Server 2013 e entram no cliente Lync 2013. Os exemplos incluem visualização de galeria de vídeo, vídeo HD, compartilhamento do PowerPoint e a opção para desativar o áudio e vídeo de todos os participantes na entrada da reunião. Os novos recursos são descritos em [novos recursos de conferência no Lync Server 2013](lync-server-2013-new-conferencing-features.md) e [o que há de novo para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Nas reuniões do Lync Server 2013, determinados recursos de conferência têm suporte para usuários hospedados em diferentes versões do servidor e que usam diferentes clientes e versões de cliente. Quando os clientes ingressam em uma reunião do Lync Server 2013, os usuários têm acesso aos recursos e funcionalidades mostrados nesta tabela.


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
<th>Mensagens instantâneas ponto a ponto</th>
<th>Voz</th>
<th>Vídeo</th>
<th>Compartilhamento de Aplicativos</th>
<th>PowerPoint</th>
<th>Transferência de arquivos</th>
<th>Quadro de comunicações</th>
<th>Sondagem</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim2</p></td>
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

3 se a reunião foi agendada no Lync Server 2013 e slides do PowerPoint foram carregados por um cliente do Lync 2013, os usuários do Lync 2010 têm acesso somente para exibição aos slides. Por outro lado, se os slides do PowerPoint foram carregados por um usuário do Lync 2010, os usuários do Lync Server 2013 poderão exibir e slides e, se o servidor do Office Web Apps estiver configurado, acessar novos recursos, como exibição de alta resolução, animações, transições de slides e vídeo incorporado. Para obter mais informações, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

os recursos de presença e IM do 4The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não. Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para a interoperabilidade de presença e de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Suporte a suplemento de agendamento

O suporte do servidor a vários suplementos de agendamento é consistente com a compatibilidade de versão do servidor e cliente. Em geral, os seguintes suplementos de agendamento têm suporte no Lync Server 2013. No entanto, versões anteriores de suplementos não fornecem novos recursos de suplemento do Lync 2013, como a opção para desativar o áudio e o vídeo de todos os participantes na entrada da reunião.

  - **Suplemento de reunião online para Lync 2013**     Oferece os mesmos recursos que o suplemento de reunião online para o Lync 2010, com a adição de controles sem som de participantes, que permitem que os organizadores de reunião agendem conferências com áudio e vídeo de participante sem som por padrão. Administradores também podem personalizar convites de reunião da organização incluindo um logotipo personalizado, uma URL da equipe de suporte, uma URL de aviso de isenção legal ou um texto de rodapé personalizado.

  - **Suplemento de reunião online para Lync 2010**     Fornece agendamento para reuniões do Lync e remove a capacidade de agendar conferências do Office Live Meeting.

  - Suplemento de conferência **do Office Communicator 2007 R2**     Fornece agendamento para conferências do Office Live Meeting e conferências do Office Communicator 2007 R2. 

<div>


> [!NOTE]  
> As conferências do Live Meeting não podem ser agendadas no Lync Server 2013.



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
<td><p>Suplemento de reunião online para Lync 2013 (pode ser usado com o Office 2013, Outlook 2010 e Outlook 2007)</p></td>
<td><p>Com suporte</p></td>
<td><p>Suportado (novos recursos de suplemento não disponíveis)</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="even">
<td><p>Agendador da Web do Lync 2013</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="odd">
<td><p>Suplemento de Reunião Online para Lync 2010</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="even">
<td><p>Suplemento de Conferência do Office Communicator 2007 R2</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Suporte para entrar em reuniões

Todos os clientes com suporte do Lync Server 2013 têm permissão para ingressar em reuniões do Lync 2013. Como o Lync Web App é um componente da Web do servidor, em casos em que o Lync Web App é usado para ingressar em uma reunião do Lync Server 2013, a versão mais recente do Lync Web App é sempre usada.

Os clientes do Lync 2013 podem ingressar em reuniões hospedadas no Lync 2010 e no Office Communications Server 2007 R2 com funcionalidade escalada. Recursos em reuniões são limitados pela versão do servidor em que a reunião está hospedada.

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos de aplicativo do Lync Windows Store para Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Novos recursos de conferência no Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[O que há de novo para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

