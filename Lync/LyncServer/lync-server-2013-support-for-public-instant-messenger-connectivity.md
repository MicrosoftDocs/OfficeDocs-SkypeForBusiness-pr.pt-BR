---
title: Lync Server 2013 suporte para conectividade pública de mensagens instantâneas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c6f21e6a58b9130ab93f827f14aad4bd09cbb33
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Suporte para conectividade pública do Messenger no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Suporte para conectividade pública do Messenger

Este artigo fornece informações sobre o suporte para a PIC (conectividade de IM pública). O PIC é um recurso do Microsoft Lync que permite às organizações habilitar seus usuários do Lync a se conectarem com usuários de determinados serviços de mensagens instantâneas (IM) públicos através de seus clientes e identidades do Lync.

Os usuários finais se beneficiam da capacidade de se conectar com clientes, parceiros e fornecedores em seus termos. Ele se beneficia do suporte a um único cliente de comunicação em tempo real, mantendo os recursos de controle, conformidade e arquivamento do Lync. A conectividade Lync-Skype, [publicamente disponível em maio de 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), depende do herdado que o Lync/Office Communications Server (OCS)/Live Communications Server (LCs) primeiro estabeleceu com a PIC na conexão com o MSN/Windows Live, AOL e Yahoo.Para obter mais informações sobre a conectividade Lync-Skype, consulte [Lync-Skype Connectivity](http://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx). A Federação com o Windows Live, AOL e Yahoo é cada uma em um caminho voltado ao fim da vida útil.Esta página documenta o status de cada serviço.

Para usar a PIC, os clientes precisam ativar o serviço para cada provedor de serviços públicos de IM. Os requisitos e detalhes sobre como fazer isso dependem do provedor de serviços de mensagens instantâneas e do programa de licenciamento subjacente do cliente.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

A Microsoft colocou o Windows Live Messenger e o Skype juntos. Em abril de 2013, os usuários do Messenger migraram para o Skype durante a entrada. Os clientes do Lync que dependem da Federação com o Messenger continuarão a ser capazes de se comunicar com seus contatos do Messenger, mesmo depois que os contatos são atualizados para o Skype. Não há nada que os administradores do Lync ou os usuários finais do Lync precisem fazer para manter a continuidade de serviço, e o gerenciamento desse recurso no Lync permanece o mesmo que para comunicações com o Messenger. 

Quando os usuários do Messenger entram no Skype usando suas contas da Microsoft (ou seja, as mesmas credenciais usadas para o Messenger) todos os contatos do Messenger-incluindo contatos federados do Lync-siga-os para o Skype. O compartilhamento de presença e mensagens instantâneas entre o Skype e o Lync para esses contatos estão disponíveis. 

Lync-conectividade do Skype-contato adicionando, compartilhamento de presença, mensagens instantâneas e chamadas de áudio entre usuários do Lync e do Skype – agora está disponível para todos os clientes do Lync.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Instant\! e AOL Instant Messenger

Federação com Yahoo\! e a AOL estão em um caminho voltado para o fim da vida útil para os clientes do Lync (e o Office Communications Server). A capacidade da Microsoft de fornecer a cada um desses serviços tem o suporte contingente no Yahoo\! e AOL, e os acordos subjacentes deles estão para baixo. Para o Yahoo\! e AOL, o serviço continuará até junho de 2014.

  - O **Yahoo** -Service continuará até junho de 2014, e os clientes continuarão a ser licenciados com a licença de assinatura de usuário da conectividade de im pública do Microsoft Lync ("pic USL").A partir de 1º de setembro de 2012, a PIC USL, não está mais disponível para compra de contratos novos ou de renovação.Os clientes com licenças adquiridas antes desta data poderão continuar a se federar com o Yahoo\! até o anterior da data de desligamento do serviço ou de sua validade da licença.Leia [o comunicado](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) no blog da equipe do Lync.Os clientes que têm licenças de PIC em acordos que vão além de 30 de junho de 2014 receberão um crédito em proporção à quantidade de pagamentos que abrangem o período de tempo após 30 de junho de 2014.

  - A **AOL** em 30 de junho de 2014, o serviço de conectividade de IM ("pic") do Lync não estará mais disponível.Para limitar a interrupção do cliente quando o serviço é encerrado, descontinuamos o provisionamento de domínios de clientes adicionais. Até 30 de junho de 2014, os clientes não precisam fazer nada para continuar a suportar comunicações federadas com o AIM. Além dessa data (ou para clientes que desejam provisionar domínios adicionais por enquanto), um serviço substituto está disponível diretamente na AOL. Para obter mais informações sobre o novo serviço da AOL, consulte [establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (abre a nova página no AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Resumo do provedor de IM público

A tabela a seguir fornece um resumo dos provedores de serviços públicos de mensagens instantâneas, recursos de Federação com Lync e requisitos de licenciamento.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Provedor de serviços públicos de IM</th>
<th>Recursos federados</th>
<th>Requisitos de licenciamento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>IM, presença, áudio</p></td>
<td><p>Licenças de acesso para cliente do Lync Server, Lync Online Plan 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>IM, presença, áudio/vídeo</p></td>
<td><p>Licenças de acesso para cliente do Lync Server (com suporte desde que o WLM esteja no mercado)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM, presença</p></td>
<td><p>Licenças de acesso para cliente do Lync Server; com suporte até junho de 2014 para clientes existentes.</p></td>
</tr>
<tr class="even">
<td><p>Toolbar</p></td>
<td><p>IM, presença</p></td>
<td><p>Requer a licença de assinatura de usuário de conectividade pública de IM ("PIC USL") adicional do Microsoft Lync Server, além de licenças de acesso para cliente do Lync Server. A partir da lista de preços de setembro de 2012, o PIC USL não está mais disponível para compra. Clientes com licenças ativas podem continuar a federar com o Yahoo! Messenger até a data de encerramento do serviço em 30 de junho de 2014.</p></td>
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

