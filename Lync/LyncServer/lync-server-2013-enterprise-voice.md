---
title: 'Lync Server 2013: Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-04-08_

Com o Enterprise Voice, o Lync Server oferece uma oferta de protocolo de voz (VoIP) autônoma para aprimorar ou substituir sistemas PBX (Private Branch Exchange) tradicionais. Os usuários do Enterprise Voice podem chamar colegas na rede VoIP ou PBX da sua organização, e podem ligar para números de telefone tradicionais fora de sua organização. A solução Enterprise Voice inclui recursos de chamadas comuns, como atender, encaminhar, transferir, suspender, reenvio, lançamento e estacionamento, e 9-1-1 (E9-1-1) de chamadas (E9-1-1 está disponível somente nos Estados Unidos.) O Enterprise Voice também oferece suporte a uma ampla gama de dispositivos IP e USB atuais e mais antigos.

<div>

## <a name="placing-and-receiving-calls"></a>Fazendo e recebendo chamadas

Usando o Lync, os usuários podem fazer chamadas digitando um nome ou número de telefone no teclado ou usando um teclado de discagem exibido na tela. Os usuários também podem iniciar chamadas diretamente da lista de contatos. Você também pode implantar os dispositivos do Lync Phone Edition, que são dispositivos de telefonia IP autônomos fornecidos pelos parceiros da Microsoft.

Os usuários podem ter vários dispositivos telefônicos registrados no Lync Server e podem alternar entre eles facilmente.

Os usuários são alertados sobre chamadas de entrada em todos os seus dispositivos simultaneamente, com toques personalizáveis em dispositivos de telefone IP e uma notificação semelhante a uma mensagem de chat em seu PC.

Os usuários também podem definir um único número de telefone que se conecta ao telefone de mesa, ao PC e ao celular, para que eles possam ser acessados onde quer que estejam.

</div>

<div>

## <a name="basic-call-features"></a>Recursos de chamada básica

Durante uma chamada, um usuário pode atender a chamadas de entrada adicionais ou iniciar chamadas feitas, e a chamada ativa existente é automaticamente colocada em espera. As chamadas podem ser transferidas de um usuário para outro, diretamente ou após o primeiro usuário falar de forma privada com o segundo usuário. Os usuários também podem transferir chamadas para outro dispositivo; por exemplo, eles podem transferir uma chamada ativa para o seu celular à medida que eles orientam a porta do escritório.

</div>

<div>

## <a name="richer-communications"></a>Comunicações mais sofisticadas

Ao conversar com outro usuário com o Lync, os usuários podem facilmente adicionar texto, vídeo ou compartilhamento de área de trabalho à chamada. O recurso do-not-incomodar está integrado às configurações de presença no Lync.

Com o Exchange Unified Messaging (UM), o Lync e o Lync Server se integram com o Microsoft Exchange Server 2013 e o Microsoft Outlook 2013. Os usuários podem ver se têm novas mensagens de voz na janela do Lync e em email. No email, eles podem clicar para reproduzir o áudio da caixa postal em uma mensagem de email ou exibir uma transcrição da mensagem da caixa postal.

</div>

<div>

## <a name="advanced-calling-features"></a>Recursos de chamada avançados

O Enterprise Voice também inclui vários recursos de chamada avançados, como a delegação de chamadas do Lync, a chamada de equipe, a retirada de chamadas em grupo e grupos de resposta.

A delegação de chamadas do Lync permite aos usuários delegar a manipulação de chamadas a um ou mais assistentes acessando **ferramentas** \> **Opções** \> **configurações**de encaminhamento de chamadas. O representante pode executar várias tarefas de chamada em nome do usuário, incluindo chamadas de filtragem, inserção de chamadas e início de conferências.

<div>


> [!IMPORTANT]  
> Você pode estar procurando outro recurso de nome semelhante, delegação de calendário do Lync. Ele não requer o recurso Enterprise Voice e permite que os usuários agendem reuniões online do Lync a partir do Outlook. Se você vir aqui procurando essas informações, recomendamos o check-out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A> para obter informações sobre como habilitar a sincronização de representante do Exchange.



</div>

O recurso de chamada de equipe permite que o usuário tenha chamadas para ligar simultaneamente para os telefones dos colegas de equipe, para que qualquer pessoa da equipe possa atender a chamada.

Recebimento de chamadas em grupo, um novo recurso em atualizações cumulativas para o Lync Server 2013:2013 de fevereiro, permite que os usuários atendam às chamadas recebidas para seus colegas pelos próprios telefones. A retirada de chamadas em grupo é diferente das chamadas de equipe principalmente porque uma chamada recebida só entra no telefone do destinatário, mas qualquer outro usuário pode optar por respondê-la ao discar um número de grupo de recebimento de chamadas.

Os grupos de resposta podem ser configurados para enfileiramento e encaminhamento inteligente de chamadas para agentes designados. Os usos comuns incluem helpdesks de ti, diretas de recursos humanos e outros centros de contato internos.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Administração do Enterprise Voice

O Lync Server usa padrões e interfaces publicadas para interoperar com a infraestrutura existente. Ele é compatível com as opções de gateway e SIP (como entroncamento SIP) para interconexão com sistemas IP PBX e redes PSTN, para que você possa migrar usuários para o Enterprise Voice ao longo do tempo, enquanto minimiza as interrupções. O Lync Server tem suporte para codecs tradicionais como G. 711, G. 722 e G. 723.1 para interoperabilidade com soluções tradicionais de VoIP.

Com o controle de admissão de chamadas (CAC), os administradores podem definir limites para a quantidade de tráfego de voz e vídeo do Lync Server transportados em links de rede restritos e especificam a ação a ser tomada se uma nova chamada excedesse o limite. As ações podem incluir roteamento por um caminho alternativo ou recusando a chamada.

O Lync Server funciona com aparelhos de ramificação externos terceirizados para fornecer serviços de chamadas locais e conexão à PSTN em filiais, em caso de falha de WAN no site central.

</div>

</div>

<span> </span>

</div>

</div>

</div>

