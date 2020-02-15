---
title: 'Lync Server 2013: ameaças de segurança comuns em computação de dia moderno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb78e03f67f7ceffbbfc401403f4025d3004fb00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Ameaças comuns à segurança em computação de dia moderno

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-09-10_

Como o Lync Server 2013 é um sistema de comunicação de classe empresarial, você deve estar ciente dos ataques comuns de segurança que podem afetar sua infraestrutura e comunicações.

<div>

## <a name="compromised-key-attack"></a>Ataque de chave comprometida

Uma chave é um número ou código secreto usado para criptografar, descriptografar ou validar informações secretas. Há duas chaves confidenciais em uso na infraestrutura de chave pública (PKI) que devem ser consideradas:.

  - A chave privada que cada proprietário do certificado tem

  - A chave de sessão usada após uma identificação bem-sucedida e a troca de chaves de sessão pelos parceiros de comunicação

Um ataque de chave comprometida ocorre quando o invasor determina a chave privada ou a chave de sessão. Quando o invasor consegue determinar a chave, ele pode usar a chave para descriptografar os dados criptografados sem o conhecimento do remetente.

O Lync Server 2013 usa os recursos de PKI no sistema operacional Windows Server para proteger os dados de chave usados para criptografia para as conexões de TLS (Transport Layer Security). As chaves usadas para a criptografia de mídia são trocadas por conexões TLS.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Ataque de negação de serviço da rede

O *ataque de negação de serviço* ocorre quando o invasor impede o uso normal da rede e funciona por usuários válidos. Isso é feito quando o invasor inunda o serviço com solicitações legítimas que sobrecarregam o uso do serviço por usuários legítimos. Com o uso de um ataque de negação de serviço, o invasor pode fazer o seguinte:

  - Enviar dados inválidos a aplicativos e serviços em execução na rede atacada para interromper seu funcionamento normal.

  - Enviar um grande volume de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda lentamente às solicitações legítimas.

  - Ocultar a evidência dos ataques.

  - Impedir que os usuários acessem os recursos da rede.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Espionagem (farejamento, espionagem)

A *espionagem* pode ocorrer quando um invasor obtém acesso ao caminho de dados em uma rede e tem a capacidade de monitorar e ler o tráfego. Isso também é chamado de *sniffing* ou *snooping*. Se o tráfego estiver em texto sem formatação, o invasor poderá ler o tráfego quando o invasor obtiver acesso ao caminho. Um exemplo é um ataque realizado pelo controle de um roteador no caminho de dados.

A recomendação e a configuração padrão para o tráfego no Microsoft Lync Server 2013 é usar o protocolo de TLS mútuo (MTLS) entre servidores confiáveis e TLS de cliente para servidor. Essa medida de proteção tornaria um ataque muito difícil ou impossível de alcançar dentro do período de tempo no qual uma determinada conversa ocorre. O TLS autentica todas as partes e criptografa todo o tráfego. Isso não impede a espionagem, mas o invasor não pode ler o tráfego, a menos que a criptografia seja interrompida.

O protocolo passagem usando NAT (ativar/desativar) não determina o tráfego a ser criptografado e as informações que ele está enviando são protegidas pela integridade da mensagem. Embora esteja aberto para espionagem, as informações que ele está enviando (ou seja, os endereços IP e a porta) podem ser extraídos diretamente, simplesmente examinando os endereços de origem e de destino dos pacotes. O serviço de borda A/V garante que os dados sejam válidos verificando a integridade da mensagem da mensagem usando a chave derivada de alguns itens, incluindo uma senha de ativação, que nunca é enviada em texto não criptografado. Se o protocolo SRTP for usado, o tráfego de mídia também será criptografado.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Falsificação de identidade (falsificação de endereço IP)

A *falsificação* ocorre quando o atacante determina e usa um endereço IP de uma rede, computador ou componente de rede sem autorização para fazê-lo. Um ataque de sucesso permite o invasor operar como se fosse uma entidade identificada normalmente pelo endereço IP. Dentro do contexto do Microsoft Lync Server 2013, essa situação só entra em cena se um administrador tiver feito o seguinte:

  - Configurou conexões que suportam apenas TCP (Protocolo de Controle de Transmissão) (não é recomendado porque as comunicações TCP não são criptografadas).

  - Marcou os endereços IPs das conexões como hosts confiáveis.

Este é menos um problema para conexões TLS (Transport Layer Security), porque a TLS autentica todas as partes e criptografa todo o tráfego. Usar o TLS evita que um invasor realize falsificação de endereço IP em uma determinada conexão (por exemplo, conexões TLS mútuas). Mas um invasor ainda pode falsificar o endereço do servidor DNS que o Lync Server 2013 usa. No entanto, como a autenticação no Lync é realizada com certificados, um invasor não terá um certificado válido necessário para falsificar uma das partes da comunicação.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Ataque de interceptação

Um ataque de interceptação ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que estão se comunicando. O invasor pode monitorar e ler o tráfego antes de enviá-lo para o destinatário pretendido. Cada usuário na comunicação envia o tráfego para e recebe o tráfego do invasor, tudo isso enquanto pensa que eles estão se comunicando apenas com o usuário pretendido. Isso pode acontecer quando um invasor pode modificar os serviços de domínio do Active Directory para adicionar seu servidor como um servidor confiável ou modificar o DNS (sistema de nomes de domínio) para fazer com que os clientes se conectem por meio do invasor no servidor. Um ataque man-in-Middle também pode ocorrer com o tráfego de mídia entre dois clientes. No entanto, no compartilhamento de áudio, vídeo e aplicativos ponto a ponto do Microsoft Lync Server 2013, os fluxos são criptografados com o SRTP, usando chaves criptográficas que são negociadas entre os pares que estão usando o protocolo SIP sobre TLS. Servidores como o chat de grupo usam HTTPS para aumentar a segurança do tráfego da Web.

</div>

<div>

## <a name="rtp-replay-attack"></a>Ataque de repetição ao RTP

Um *ataque de repetição* ocorre quando uma transmissão de mídia válida entre duas partes é interceptada e retransmitida para fins mal-intencionados. O SRTP usado em conjunto com um protocolo de sinalização seguro protege as transmissões contra ataques de repetição habilitando o receptor a manter um índice de pacotes RTP já recebidos e a comparar cada novo pacote com os já listados no índice.

</div>

<div>

## <a name="spim"></a>Spim

O *spim* é uma mensagem instantânea comercial não solicitada ou solicitações de inscrição de presença. Embora não seja propriamente um compromisso da rede, essa situação é, no mínimo, irritante, pode reduzir a disponibilidade de recursos e a produção e possivelmente comprometerá a rede. Um exemplo disso são os usuários que repassam spims entre si ao enviar solicitações. Os usuários podem bloquear uns aos outros para evitar que isso aconteça, mas com a federação, se um ataque de spim coordenado for estabelecido, possivelmente será difícil contornar o problema, a menos que você desabilite a federação do parceiro.

</div>

<div>

## <a name="viruses-and-worms"></a>Vírus e worms

Um *vírus* é uma unidade de código cujo propósito é reproduzir unidades de código adicionais e semelhantes. Para funcionar, um vírus precisa de um host, como um arquivo, um email ou um programa. Um *worm* é uma unidade de código cujo propósito é reproduzir unidades de código adicionais e semelhantes, mas não precisa de um host. Vírus e worms aparecem principalmente durante transferências de arquivos entre clientes ou quando as URLs são enviadas de outros usuários. Se um vírus estiver no seu computador, ele pode, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome.

</div>

<div>

## <a name="personally-identifiable-information"></a>Informações de identificação pessoal

O Microsoft Lync Server 2013 tem o potencial de divulgar informações por meio de uma rede pública que possa ser vinculada a um indivíduo. Os tipos de informações podem ser classificados em duas categorias específicas:

  - **Dados de presença avançados** Os dados de presença avançados são informações que um usuário pode optar por compartilhar ou não compartilhar sobre um link para um parceiro federado ou com contatos em uma organização. Esses dados não são compartilhados com usuários em uma rede pública de mensagens instantâneas. As políticas cliente e outras configurações cliente podem aplicar algum controle com o administrador do sistema. No Lync Server 2013, o modo de privacidade de presença avançada pode ser configurado para um usuário individual para impedir que os usuários do Lync que não estejam na lista de contatos do usuário vejam as informações de presença do usuário. O modo de privacidade de presença avançada não impede que os usuários do Microsoft Office Communicator 2007 e do Microsoft Office Communicator 2007 R2 vejam as informações de presença de um usuário. Para obter detalhes, consulte [What ' s New for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) na documentação de introdução e [Configurando o modo de privacidade de presença avançada no Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) na documentação de implantação.

  - **Dados obrigatórios** Os dados obrigatórios são necessários para a operação adequada do servidor ou do cliente e não estão sob o controle da administração do cliente ou do sistema. Essas são as informações necessárias em um nível de servidor ou de rede para fins de roteamento, manutenção de estado e sinalização.

As tabelas a seguir listam os dados que são expostos em uma rede pública.

### <a name="enhanced-presence-data"></a>Dados de presença aprimorados

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dados divulgados</th>
<th>Configurações possíveis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dados pessoais</p></td>
<td><p>Nome, cargo, empresa, endereço de email, fuso horário</p></td>
</tr>
<tr class="even">
<td><p>Números de telefone</p></td>
<td><p>Comercial, Celular, Residencial</p></td>
</tr>
<tr class="odd">
<td><p>Informações do calendário</p></td>
<td><p>Disponibilidade, aviso de falta de cidade, detalhes da reunião (para aqueles que têm acesso ao seu calendário)</p></td>
</tr>
<tr class="even">
<td><p>Status de presença</p></td>
<td><p>Ausente, Disponível, Ocupado, Não Incomodar, Offline</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>Dados obrigatórios

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dados divulgados</th>
<th>Informações de exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endereço IP</p></td>
<td><p>Endereço real do computador ou endereço NAT</p></td>
</tr>
<tr class="even">
<td><p>SIP URI</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

