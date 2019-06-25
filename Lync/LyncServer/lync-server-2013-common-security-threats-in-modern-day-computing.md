---
title: 'Lync Server 2013: ameaças comuns de segurança na computação do dia moderno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2446ee0755f4544f17f6c04c6059d70576a466f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Ameaças de segurança comuns no Modern Day Computing

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-09-10_

Como o Lync Server 2013 é um sistema de comunicação de classe empresarial, você deve estar ciente de ataques comuns de segurança que podem afetar sua infraestrutura e comunicações.

<div>

## <a name="compromised-key-attack"></a>Chave de Ataque Comprometida

Uma chave é um código secreto ou um número que é usado para criptografar, descriptografar ou validar uma informação secreta. Há duas chaves sensitivas em uso na chave de infraestrutura pública (PKI) que deve ser considerada: .

  - A chave privada que cada titular do certificado tem

  - A chave da sessão que é usada depois da identificação com sucesso e a chave da sessão alterada pelos parceiros de comunicação

Um ataque à chave comprometida acontece quando o atacante determina a chave de privacidade ou a chave da sessão. Quando o atacante é bem sucedido nesta determinação da chave, ele pode usá-la para descriptografar dados criptografados sem que o remetente.

O Lync Server 2013 usa os recursos de PKI no sistema operacional Windows Server para proteger os dados de chave usados para criptografia para as conexões de TLS (Transport Layer Security). As chaves usadas para criptografar mídia são trocadas através de conexões TLS.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Rede de Ataque De Negação de Serviço

O ataque *de negação de serviço* ocorre quando o atacante impede o uso da rede normal e função pelos usuários válidos. Isso é feito quando o atacante inunda o serviço com pedidos legítimos que domina o uso do serviço pelos usuários legítimos. Usando um ataque de negação de serviço, o atacante pode fazer o seguinte:

  - Enviar dados inválidos aos aplicativos e serviços que estão funcionando na rede atacada para interromper o funcionamento normal delel.

  - Enviar uma grande quantidade de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda devagar aos pedidos legítimos.

  - Esconder a evidência dos ataques.

  - Impedir os usuários de acessar os recursos de acesso a rede.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Espionagem (Bisbilhotar, Intrometer)

A *Espionagem* pode ocorrer quando um atacante ganha acesso ao caminho dos dados na rede e tem a habilidade para monitorar e ler o tráfego. Isso também é chamado de *bisbilhotar* ou *falsificar*. Se o tráfego está no texto plano, o atacante pode lê-lo quando o atacante ganha acesso ao caminho. Um exemplo é um ataque realizado no controle de um router no caminho dos dados.

A recomendação e a configuração padrão de tráfego no Microsoft Lync Server 2013 é usar o protocolo de TLS (MTLS) mútuo entre servidores confiáveis e TLS do cliente para o servidor. Essa medida protetora poderia dificultar e muito um ataque ou impossibilitar o alcance com o período de tempo no qual tal conversa ocorre. TLS autentica todas as partes e criptografa todo tráfego. Isso não impede a espionagem, mas o atacante não pode ler o tráfego, a não ser que quebre a criptografia.

O protocolo de Relay de Uso Traversal NAT (TURN) não exige o tráfego para ser criptografado e as informações que são enviadas são protegidas pela integridade da mensagem. Mesmo estando abertas apara a espionagem, as informações que são enviadas (o endereço do IP e a porta) podem ser extraídas diretamente dando uma simples olhada nos endereços de saída e de destino dos pacotes. O serviço A/V Edge certifica que os dados são válidos verificando a Integridade da Mensagem da mensagem, usando a chave derivada de poucos itens, incluindo uma senha do TURN, que nunca é enviada em um texto claro. Se o ProtocoIo (SRTP) é usado, o tráfego de mídia também é criptografado.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Falsificação de ID (endereço de IP de Falsificação)

A *Falsificação* ocorre quando o atacante determina e usa um endereço IP de uma rede, computador ou componente de rede sem autorização para tal ação. Um ataque bem-sucedido permite que o atacante opere como se fosse a entidade normalmente identificada pelo endereço IP. Dentro do contexto do Microsoft Lync Server 2013, essa situação entra em cena apenas se um administrador tiver feito o seguinte:

  - Conexões configuradas que suportam apenas o Protocolo de Controle de Transmissão (TCP) (o que não é recomendado, porque as comunicações do TCP são descriptografadas).

  - Marque os endereços de IP daquelas conexões como hosts confiáveis.

Este é o menor dos problemas para as conexões de Transport Layer Security (TLS), uma vez que a TLS autentica toda as partes e criptografa todo o tráfego. Usar a TLS impede que um atacante falsifique o endereço IP em uma conexão específica (por exemplo, conexões TLS mútuas). Mas um invasor ainda pode falsificar o endereço do servidor DNS que o Lync Server 2013 usa. No entanto, como a autenticação no Lync é realizada com certificados, um invasor não teria um certificado válido necessário para falsificar uma das partes da comunicação.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Ataque a intermediário

Um ataque a intermediários ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que estão se comunicando. O invasor pode monitorar e ler o tráfego antes de enviá-lo ao destinatário pretendido. Cada usuário presente na comunicação, sem saber, envia e recebe tráfego do invasor pensando estar se comunicando apenas com o usuário pretendido. Isso pode acontecer se um invasor conseguir modificar os Active Directory Domain Services para adicionar o servidor dele como um servidor confiável ou modificar o DNS (Sistema de Nome de Domínio) para fazer com que os clientes se conectem ao invasor no caminho para o servidor. Um ataque man-in-Middle também pode ocorrer com o tráfego de mídia entre dois clientes. No entanto, no Microsoft Lync Server 2013 o compartilhamento de áudio, vídeo e aplicativos ponto a ponto, os fluxos são criptografados com o SRTP, usando chaves criptográficas que são negociadas entre os pares que estão usando o protocolo SIP (protocolo de iniciação de sessão) em TLS. Os servidores como o chat em grupo usam HTTPS para melhorar a segurança do tráfego da Web.

</div>

<div>

## <a name="rtp-replay-attack"></a>Ataque por Repetição RTP

Um *ataque por repetição* ocorre quando uma transmissão válida de mídia entre duas partes é interceptada e retransmitida de forma mal-intencionada. O SRTP usado em conexão com um protocolo de sinalização de segurança protege as transmissões contra ataques por repetição, habilitando o receptor a manter um índice de pacotes RTP já recebidos e a comparar cada novo pacote com aqueles já listados no índice.

</div>

<div>

## <a name="spim"></a>Spim

*Spim* é uma mensagem instantânea comercial não solicitada ou pedidos de inscrição de presença. Embora não seja por si só um comprometimento da rede, é, no mínimo, irritante, pois pode reduzir a disponibilidade e a produção de recursos e levar a um comprometimento da rede. Um exemplo disso é quando os usuários fazem "spimming" uns para os outros, por meio de envios de solicitações. Os usuários podem bloquear uns aos outros para evitar isso, mas com a federação, se um ataque spim coordenado for estabelecido, isso poderá ser difícil de superar, a não ser que você desabilite a federação do parceiro.

</div>

<div>

## <a name="viruses-and-worms"></a>Vírus e Worms

Um *vírus* é uma unidade de código cujo propósito é reproduzir unidades de códigos adicionais e similares. Para funcionar, um vírus precisa de um host, como um arquivo, email ou programa. Um *worm* é uma unidade de código cujo propósito é reproduzir unidades de códigos adicionais e similares, mas ele não precisa de um host. Os vírus e os worms aparecem principalmente durante transferências de arquivos entre clientes ou quando as URLs são enviadas por outros usuários. Um vírus no seu computador pode, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome.

</div>

<div>

## <a name="personally-identifiable-information"></a>Informações de Identificação Pessoal

O Microsoft Lync Server 2013 tem o potencial de divulgar informações por meio de uma rede pública que pode ser vinculada a um indivíduo. Os tipos de informações podem ser separados em duas categorias específicas:

  - **Dados de presença avançados** Os dados de presença avançados são informações que um usuário pode escolher para compartilhar ou não compartilhar por meio de um link para um parceiro federado ou com contatos em uma organização. Esses dados não são compartilhados com usuários em uma rede IM pública. As políticas dos clientes e outras configurações de clientes podem dar um certo controle com o administrador do sistema. No Lync Server 2013, o modo de privacidade de presença avançada pode ser configurado para um usuário individual para impedir que os usuários do Lync que não estejam na lista de contatos do usuário vejam as informações de presença do usuário. O modo de privacidade de presença avançada não impede que os usuários do Microsoft Office Communicator 2007 e do Microsoft Office Communicator 2007 R2 vejam as informações de presença do usuário. Para obter detalhes, consulte o [que há de novo para os clientes no Lync server 2013](lync-server-2013-what-s-new-for-clients.md) na documentação de introdução e Configurando o [modo de privacidade de presença avançada no Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) na documentação de implantação.

  - **Dados obrigatórios** Dados obrigatórios são necessários para a operação adequada do servidor ou do cliente e não estão sob o controle da administração do cliente ou do sistema. Essas informações são necessárias no nível do servidor ou no nível da rede para fins de roteamento, manutenção de estado e sinalização.

As seguintes listas tabelas de dados são exibidas para a rede pública.

### <a name="enhanced-presence-data"></a>Dados de Presença Aumentados

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dados Divulgados</th>
<th>Configurações Possíveis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dados Pessoais</p></td>
<td><p>Nome, Título, empresa, Email, Fuso Horário</p></td>
</tr>
<tr class="even">
<td><p>Números de Telefone</p></td>
<td><p>Comercial, Celular, Residencial</p></td>
</tr>
<tr class="odd">
<td><p>Informações de Calendário</p></td>
<td><p>Disponível/Ocupado, Aviso de Ausência, Detalhes da Reunião (para aqueles que têm acesso ao seu calendário)</p></td>
</tr>
<tr class="even">
<td><p>Status de Presença</p></td>
<td><p>Ausente, Disponível, Ocupado, Não Perturbe, Offline</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>Dados Obrigatórios

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dados Divulgados</th>
<th>Exemplo de Informações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endereço de IP</p></td>
<td><p>Endereço atual do computador ou endereço do NATed</p></td>
</tr>
<tr class="even">
<td><p>URI do SIP</p></td>
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

