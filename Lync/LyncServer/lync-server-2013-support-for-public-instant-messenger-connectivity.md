---
title: Suporte do Lync Server 2013 para conectividade de mensagem instantânea pública
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c89cc911411095034385f7b8ebbe01edddcd20c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Suporte para conectividade de mensagem instantânea pública no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Suporte para conectividade de mensagem instantânea pública

Este artigo fornece informações sobre o suporte para a PIC (conectividade pública de IM). A PIC é um recurso do Microsoft Lync que permite que as organizações habilitem seus usuários do Lync para se conectar com usuários de determinados serviços de mensagens instantâneas (IM) públicas por meio de seus clientes e identidades do Lync.

Os usuários finais se beneficiam da capacidade de se conectar com clientes, parceiros e fornecedores em termos de seus termos. Ele se beneficia do suporte a um único cliente de comunicação em tempo real, mantendo os recursos de controle, conformidade e arquivamento do Lync. Lync-conectividade do Skype, [disponível publicamente em maio de 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), depende do herdado que o Lync/Office Communications Server (OCS)/Live Communications Server (LCs) primeiro estabeleceu com a PIC na conexão com o MSN/Windows Live, AOL e Yahoo.Para obter mais informações sobre o Lync-conectividade com o Skype, consulte a [conectividade do Lync](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx). A Federação com o Windows Live, o AOL e o Yahoo são cada um deles em um caminho até o fim da vida útil.Esta página documenta o status de cada serviço.

Para usar a PIC, os clientes precisam ativar o serviço para cada provedor de serviço de mensagens de chat públicas. Os requisitos e os detalhes de como fazer isso dependem do provedor de serviços de mensagens instantâneas e do programa de licenciamento subjacente do cliente.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

A Microsoft colocou o Windows Live Messenger e o Skype juntos. Em abril de 2013, os usuários do Messenger migraram para o Skype quando entrarem. Os clientes do Lync que confiam na Federação com o Messenger continuarão a ser capazes de se comunicar com seus contatos do Messenger, mesmo depois que esses contatos forem atualizados para o Skype. Não há nada que os administradores do Lync ou os usuários finais do Lync precisem fazer para manter a continuidade do serviço, e o gerenciamento dessa funcionalidade no Lync permanece o mesmo que para comunicações com o Messenger. 

Quando os usuários do Messenger se conectarem ao Skype usando suas contas da Microsoft (ou seja, as mesmas credenciais usadas para o Messenger) todos os seus contatos do Messenger-incluindo contatos federados do Lync-siga-os no Skype. O compartilhamento de presença e mensagens instantâneas entre o Skype e o Lync para estes contatos está disponível. 

Lync-conectividade do Skype-adição de contato, compartilhamento de presença, mensagens instantâneas e chamadas de áudio entre o Lync e usuários do Skype – também está disponível para todos os clientes do Lync.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Instant\! e mensagem instantânea do AOL

Federação com o Yahoo\! e a AOL estão em um caminho para o fim da vida para os clientes do Lync (e do Office Communications Server). A capacidade da Microsoft de fornecer a cada um desses serviços tem o suporte contingente no Yahoo\! e a AOL, e os acordos subjacentes deles estão prestes a ser enrolados. Para o Yahoo\! e AOL, o serviço continuará até de junho de 2014.

  - O **Yahoo** -Service continuará até junho de 2014, e os clientes continuarão precisando ser licenciados com a licença de assinatura de usuário da conectividade de im pública do Microsoft Lync ("pic USL").A partir de 1º de setembro de 2012, a PIC USL, não está mais disponível para compra de contratos novos ou renovadores.Os clientes com licenças compradas antes desta data poderão continuar a federar-se com o Yahoo\! até o anterior da data de encerramento do serviço ou o prazo de expiração da licença.Leia [o comunicado](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) no blog da equipe do Lync.Os clientes que têm licenças de PIC em contratos que vão até 30 de junho de 2014 receberão um crédito em proporção ao valor dos pagamentos que abrangem o período de 30 de junho de 2014.

  - A **AOL** – em 30 de junho de 2014, o serviço de conectividade de IM ("pic") do Lync não estará mais disponível.Para limitar a interrupção do cliente quando o serviço terminar, descontinuamos o provisionamento de domínios adicionais do cliente. Até 30 de junho de 2014, os clientes não precisam fazer nada para continuar a dar suporte às comunicações federadas com o AIM. Além dessa data (ou para clientes que queiram provisionar domínios adicionais nesse meio tempo), um serviço substituto está disponível diretamente na AOL. Para obter mais informações sobre o novo serviço da AOL, consulte [estabelecendo Federação direta com AIM](http://aimenterprise.aol.com/pic.php)  (abre a nova página no AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Resumo do provedor de mensagens de chat públicas

A tabela a seguir fornece um resumo dos provedores de serviços públicos de mensagens instantâneas, recursos de Federação com o Lync e requisitos de licenciamento.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Provedor de serviço público de mensagens instantâneas</th>
<th>Recursos federados</th>
<th>Requisitos de licenciamento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Mensagens instantâneas, presença, áudio</p></td>
<td><p>Licenças de acesso para cliente do Lync Server, plano do Lync Online 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Mensagens instantâneas, presença, áudio/vídeo</p></td>
<td><p>Licenças de acesso para cliente do Lync Server (com suporte desde que o WLM esteja no mercado)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Mensagens instantâneas, presença</p></td>
<td><p>Licenças de acesso para cliente do Lync Server; compatível até junho de 2014 para clientes atuais.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Mensagens instantâneas, presença</p></td>
<td><p>Requer licença de assinatura de usuário de conectividade de mensagem pública adicional do Microsoft Lync ("PIC USL"), além de licenças de acesso para cliente do Lync Server. A partir da lista de preços de setembro de 2012, o PIC USL não está mais disponível para compra. Os clientes com licenças ativas podem continuar a federar-se com o Yahoo! Messenger até a data de encerramento do serviço em 30 de junho de 2014.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

