---
title: Lync Server 2013 Enterprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924e15aae9590b6148864084aa68924e4c080f7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-04-08_

Com o Enterprise Voice, o Lync Server fornece uma oferta de protocolo VoIP para aprimorar ou substituir sistemas PBX (Private Branch Exchange) tradicionais. Os usuários do Enterprise Voice podem ligar para colegas na sua rede VoIP da organização ou PBX e podem ligar para números tradicionais fora da organização. A solução Enterprise Voice inclui recursos de chamada comuns como resposta, encaminhamento, transferência, retenção, reenvio, lançamento e estacionamento, e Enhanced 9-1-1 (E9-1-1) chamada (E9-1-1 está disponível somente nos Estados Unidos). O Enterprise Voice também oferece suporte a uma ampla variedade de dispositivos IP e USB atuais e antigos.

<div>

## <a name="placing-and-receiving-calls"></a>Fazendo e recebendo chamadas

Usando o Lync, os usuários podem fazer chamadas digitando um nome ou número de telefone no teclado ou usando um teclado de discagem exibido na tela. Os usuários podem iniciar chamadas diretamente da sua lista de Contatos. Você também pode implantar dispositivos do Lync Phone Edition, que são dispositivos de telefone IP autônomos fornecidos por parceiros da Microsoft.

Os usuários podem ter vários dispositivos telefônicos registrados no Lync Server e podem alternar entre eles facilmente.

Os usuários são alertados sobre chamadas recebidas em todos seus dispositivos simultaneamente, com toques personalizados em telefones IP e uma notificação parecida com uma mensagem instantânea no PC.

Os usuários também podem definir um único número de telefone que fica conectado ao telefone de mesa, PC e celular, de modo que possam ser encontrados não importa onde estejam.

</div>

<div>

## <a name="basic-call-features"></a>Recursos básicos de chamada

Durante uma chamada, um usuário pode atender a outras chamadas ou iniciar chamadas de saída, e a chamada ativa atual é colocada automaticamente em espera. As chamadas podem ser transferidas de um usuário para outro, diretamente ou após o primeiro usuário falar em particular com o segundo usuário. Os usuários também podem transferir chamadas para outro dispositivo; por exemplo, eles podem transferir uma chamada ativa para seus celulares enquanto saem de seus escritórios.

</div>

<div>

## <a name="richer-communications"></a>Comunicações mais ricas

Ao falar com outro usuário com o Lync, os usuários podem facilmente adicionar o compartilhamento de texto, vídeo ou área de trabalho à chamada. O recurso do-not-perturbe é integrado às configurações de presença no Lync.

Com a Unificação de mensagens (UM) do Exchange, o Lync e o Lync Server se integram com o Microsoft Exchange Server 2013 e o Microsoft Outlook 2013. Os usuários podem ver se têm novas mensagens de voz na janela do Lync e no email. Enquanto estiverem no email, podem clicar para reproduzir o áudio da caixa postal em uma mensagem de email ou exibir uma transcrição da mensagem de caixa postal.

</div>

<div>

## <a name="advanced-calling-features"></a>Recursos avançados de chamada

O Enterprise Voice também inclui vários recursos de chamadas avançados, como a delegação de chamada do Lync, chamada em equipe, recebimento de chamadas em grupo e grupos de resposta.

A delegação de chamadas do Lync permite que os usuários deleguem o tratamento de chamadas a um **** \> ou mais assistentes, acessando as **configurações de atendimento de chamadas das** **Opções** \> . O representante pode executar diversas tarefas de chamada em nome do usuário, incluindo camadas filtragem de chamadas, realização de chamadas e início de conferências.

<div>


> [!IMPORTANT]  
> Você pode estar procurando outro recurso de nome similar, delegação de calendário do Lync. Ele não exige o recurso Enterprise Voice e permite que os usuários agendem reuniões online do Lync a partir do Outlook. Se você vir aqui procurando essas informações, recomendamos o check-out do <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A> para obter informações sobre como habilitar a sincronização de representante do Exchange.



</div>

A chamada em equipe permite que um usuário tenha chamadas de entrada para ligar simultaneamente os telefones dos colegas de equipe, de forma que qualquer pessoa da equipe possa responder à chamada.

Atendimento de chamadas em grupo, um novo recurso em atualizações cumulativas do Lync Server 2013:2013 de fevereiro, permite que os usuários respondam chamadas de entrada para seus colegas de seus próprios telefones. O recebimento de chamadas de grupo difere da chamada de equipe, principalmente, quando uma chamada de entrada entra apenas no telefone do destinatário, mas qualquer outro usuário pode optar por respondê-lo discando um número de grupo de recebimento de chamada.

Os Grupos de Resposta podem ser definidos para enfileiramento e roteamento inteligente de chamadas aos agentes designados. Entre os usos comuns estão assistência técnica de TI, linde atendimento dos recursos humanos e outros centros de contato internos.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Administração do Enterprise Voice

O Lync Server usa padrões e interfaces publicadas para interoperar com a infraestrutura existente. Ele suporta as opções de gateway e SIP (como tronco SIP) para interconexão com sistemas IP PBX e as redes PSTN, de modo que você possa migrar os usuários para o Enterprise Voice com o tempo, minimizando as interrupções. O Lync Server oferece suporte a codecs tradicionais como G. 711, G. 722 e G. 723.1 para interoperabilidade com as soluções tradicionais de VoIP.

Com o controle de admissão de chamadas (CAC), os administradores podem definir limites na quantidade de tráfego de voz e vídeo do Lync Server transportada em links de rede restritos e especificar a ação a ser tomada se uma nova chamada exceder o limite. As ações poderiam incluir roteamento por um caminho alternativo ou a recusa da chamada.

O Lync Server funciona com aparelhos de filial persistente de terceiros para fornecer serviços de chamada local e conexão com PSTN em filiais, em caso de falha de WAN no site central.

</div>

</div>

<span> </span>

</div>

</div>

</div>

