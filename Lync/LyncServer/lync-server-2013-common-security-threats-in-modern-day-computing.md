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

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="95f13-102">Ameaças de segurança comuns no Modern Day Computing</span><span class="sxs-lookup"><span data-stu-id="95f13-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95f13-103">_**Tópico da última modificação:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="95f13-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="95f13-104">Como o Lync Server 2013 é um sistema de comunicação de classe empresarial, você deve estar ciente de ataques comuns de segurança que podem afetar sua infraestrutura e comunicações.</span><span class="sxs-lookup"><span data-stu-id="95f13-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="95f13-105">Chave de Ataque Comprometida</span><span class="sxs-lookup"><span data-stu-id="95f13-105">Compromised-Key Attack</span></span>

<span data-ttu-id="95f13-p101">Uma chave é um código secreto ou um número que é usado para criptografar, descriptografar ou validar uma informação secreta. Há duas chaves sensitivas em uso na chave de infraestrutura pública (PKI) que deve ser considerada: .</span><span class="sxs-lookup"><span data-stu-id="95f13-p101">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information. There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="95f13-108">A chave privada que cada titular do certificado tem</span><span class="sxs-lookup"><span data-stu-id="95f13-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="95f13-109">A chave da sessão que é usada depois da identificação com sucesso e a chave da sessão alterada pelos parceiros de comunicação</span><span class="sxs-lookup"><span data-stu-id="95f13-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="95f13-p102">Um ataque à chave comprometida acontece quando o atacante determina a chave de privacidade ou a chave da sessão. Quando o atacante é bem sucedido nesta determinação da chave, ele pode usá-la para descriptografar dados criptografados sem que o remetente.</span><span class="sxs-lookup"><span data-stu-id="95f13-p102">A compromised-key attack occurs when the attacker determines the private key or the session key. When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="95f13-112">O Lync Server 2013 usa os recursos de PKI no sistema operacional Windows Server para proteger os dados de chave usados para criptografia para as conexões de TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="95f13-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="95f13-113">As chaves usadas para criptografar mídia são trocadas através de conexões TLS.</span><span class="sxs-lookup"><span data-stu-id="95f13-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="95f13-114">Rede de Ataque De Negação de Serviço</span><span class="sxs-lookup"><span data-stu-id="95f13-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="95f13-p104">O ataque *de negação de serviço* ocorre quando o atacante impede o uso da rede normal e função pelos usuários válidos. Isso é feito quando o atacante inunda o serviço com pedidos legítimos que domina o uso do serviço pelos usuários legítimos. Usando um ataque de negação de serviço, o atacante pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="95f13-p104">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users. This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users. By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="95f13-118">Enviar dados inválidos aos aplicativos e serviços que estão funcionando na rede atacada para interromper o funcionamento normal delel.</span><span class="sxs-lookup"><span data-stu-id="95f13-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="95f13-119">Enviar uma grande quantidade de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda devagar aos pedidos legítimos.</span><span class="sxs-lookup"><span data-stu-id="95f13-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="95f13-120">Esconder a evidência dos ataques.</span><span class="sxs-lookup"><span data-stu-id="95f13-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="95f13-121">Impedir os usuários de acessar os recursos de acesso a rede.</span><span class="sxs-lookup"><span data-stu-id="95f13-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="95f13-122">Espionagem (Bisbilhotar, Intrometer)</span><span class="sxs-lookup"><span data-stu-id="95f13-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="95f13-p105">A *Espionagem* pode ocorrer quando um atacante ganha acesso ao caminho dos dados na rede e tem a habilidade para monitorar e ler o tráfego. Isso também é chamado de *bisbilhotar* ou *falsificar*. Se o tráfego está no texto plano, o atacante pode lê-lo quando o atacante ganha acesso ao caminho. Um exemplo é um ataque realizado no controle de um router no caminho dos dados.</span><span class="sxs-lookup"><span data-stu-id="95f13-p105">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called *sniffing* or *snooping*. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="95f13-127">A recomendação e a configuração padrão de tráfego no Microsoft Lync Server 2013 é usar o protocolo de TLS (MTLS) mútuo entre servidores confiáveis e TLS do cliente para o servidor.</span><span class="sxs-lookup"><span data-stu-id="95f13-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="95f13-128">Essa medida protetora poderia dificultar e muito um ataque ou impossibilitar o alcance com o período de tempo no qual tal conversa ocorre.</span><span class="sxs-lookup"><span data-stu-id="95f13-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="95f13-129">TLS autentica todas as partes e criptografa todo tráfego.</span><span class="sxs-lookup"><span data-stu-id="95f13-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="95f13-130">Isso não impede a espionagem, mas o atacante não pode ler o tráfego, a não ser que quebre a criptografia.</span><span class="sxs-lookup"><span data-stu-id="95f13-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="95f13-p107">O protocolo de Relay de Uso Traversal NAT (TURN) não exige o tráfego para ser criptografado e as informações que são enviadas são protegidas pela integridade da mensagem. Mesmo estando abertas apara a espionagem, as informações que são enviadas (o endereço do IP e a porta) podem ser extraídas diretamente dando uma simples olhada nos endereços de saída e de destino dos pacotes. O serviço A/V Edge certifica que os dados são válidos verificando a Integridade da Mensagem da mensagem, usando a chave derivada de poucos itens, incluindo uma senha do TURN, que nunca é enviada em um texto claro. Se o ProtocoIo (SRTP) é usado, o tráfego de mídia também é criptografado.</span><span class="sxs-lookup"><span data-stu-id="95f13-p107">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity. Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets. The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text. If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="95f13-135">Falsificação de ID (endereço de IP de Falsificação)</span><span class="sxs-lookup"><span data-stu-id="95f13-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="95f13-136">A *Falsificação* ocorre quando o atacante determina e usa um endereço IP de uma rede, computador ou componente de rede sem autorização para tal ação.</span><span class="sxs-lookup"><span data-stu-id="95f13-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="95f13-137">Um ataque bem-sucedido permite que o atacante opere como se fosse a entidade normalmente identificada pelo endereço IP.</span><span class="sxs-lookup"><span data-stu-id="95f13-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="95f13-138">Dentro do contexto do Microsoft Lync Server 2013, essa situação entra em cena apenas se um administrador tiver feito o seguinte:</span><span class="sxs-lookup"><span data-stu-id="95f13-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="95f13-139">Conexões configuradas que suportam apenas o Protocolo de Controle de Transmissão (TCP) (o que não é recomendado, porque as comunicações do TCP são descriptografadas).</span><span class="sxs-lookup"><span data-stu-id="95f13-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="95f13-140">Marque os endereços de IP daquelas conexões como hosts confiáveis.</span><span class="sxs-lookup"><span data-stu-id="95f13-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="95f13-141">Este é o menor dos problemas para as conexões de Transport Layer Security (TLS), uma vez que a TLS autentica toda as partes e criptografa todo o tráfego.</span><span class="sxs-lookup"><span data-stu-id="95f13-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="95f13-142">Usar a TLS impede que um atacante falsifique o endereço IP em uma conexão específica (por exemplo, conexões TLS mútuas).</span><span class="sxs-lookup"><span data-stu-id="95f13-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="95f13-143">Mas um invasor ainda pode falsificar o endereço do servidor DNS que o Lync Server 2013 usa.</span><span class="sxs-lookup"><span data-stu-id="95f13-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="95f13-144">No entanto, como a autenticação no Lync é realizada com certificados, um invasor não teria um certificado válido necessário para falsificar uma das partes da comunicação.</span><span class="sxs-lookup"><span data-stu-id="95f13-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="95f13-145">Ataque a intermediário</span><span class="sxs-lookup"><span data-stu-id="95f13-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="95f13-146">Um ataque a intermediários ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que estão se comunicando.</span><span class="sxs-lookup"><span data-stu-id="95f13-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="95f13-147">O invasor pode monitorar e ler o tráfego antes de enviá-lo ao destinatário pretendido.</span><span class="sxs-lookup"><span data-stu-id="95f13-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="95f13-148">Cada usuário presente na comunicação, sem saber, envia e recebe tráfego do invasor pensando estar se comunicando apenas com o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="95f13-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="95f13-149">Isso pode acontecer se um invasor conseguir modificar os Active Directory Domain Services para adicionar o servidor dele como um servidor confiável ou modificar o DNS (Sistema de Nome de Domínio) para fazer com que os clientes se conectem ao invasor no caminho para o servidor.</span><span class="sxs-lookup"><span data-stu-id="95f13-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="95f13-150">Um ataque man-in-Middle também pode ocorrer com o tráfego de mídia entre dois clientes.</span><span class="sxs-lookup"><span data-stu-id="95f13-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="95f13-151">No entanto, no Microsoft Lync Server 2013 o compartilhamento de áudio, vídeo e aplicativos ponto a ponto, os fluxos são criptografados com o SRTP, usando chaves criptográficas que são negociadas entre os pares que estão usando o protocolo SIP (protocolo de iniciação de sessão) em TLS.</span><span class="sxs-lookup"><span data-stu-id="95f13-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="95f13-152">Os servidores como o chat em grupo usam HTTPS para melhorar a segurança do tráfego da Web.</span><span class="sxs-lookup"><span data-stu-id="95f13-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="95f13-153">Ataque por Repetição RTP</span><span class="sxs-lookup"><span data-stu-id="95f13-153">RTP Replay Attack</span></span>

<span data-ttu-id="95f13-p111">Um *ataque por repetição* ocorre quando uma transmissão válida de mídia entre duas partes é interceptada e retransmitida de forma mal-intencionada. O SRTP usado em conexão com um protocolo de sinalização de segurança protege as transmissões contra ataques por repetição, habilitando o receptor a manter um índice de pacotes RTP já recebidos e a comparar cada novo pacote com aqueles já listados no índice.</span><span class="sxs-lookup"><span data-stu-id="95f13-p111">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="95f13-156">Spim</span><span class="sxs-lookup"><span data-stu-id="95f13-156">Spim</span></span>

<span data-ttu-id="95f13-p112">*Spim* é uma mensagem instantânea comercial não solicitada ou pedidos de inscrição de presença. Embora não seja por si só um comprometimento da rede, é, no mínimo, irritante, pois pode reduzir a disponibilidade e a produção de recursos e levar a um comprometimento da rede. Um exemplo disso é quando os usuários fazem "spimming" uns para os outros, por meio de envios de solicitações. Os usuários podem bloquear uns aos outros para evitar isso, mas com a federação, se um ataque spim coordenado for estabelecido, isso poderá ser difícil de superar, a não ser que você desabilite a federação do parceiro.</span><span class="sxs-lookup"><span data-stu-id="95f13-p112">*Spim* is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="95f13-161">Vírus e Worms</span><span class="sxs-lookup"><span data-stu-id="95f13-161">Viruses and Worms</span></span>

<span data-ttu-id="95f13-p113">Um *vírus* é uma unidade de código cujo propósito é reproduzir unidades de códigos adicionais e similares. Para funcionar, um vírus precisa de um host, como um arquivo, email ou programa. Um *worm* é uma unidade de código cujo propósito é reproduzir unidades de códigos adicionais e similares, mas ele não precisa de um host. Os vírus e os worms aparecem principalmente durante transferências de arquivos entre clientes ou quando as URLs são enviadas por outros usuários. Um vírus no seu computador pode, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome.</span><span class="sxs-lookup"><span data-stu-id="95f13-p113">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units. To work, a virus needs a host, such as a file, email, or program. A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host. Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users. If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="95f13-167">Informações de Identificação Pessoal</span><span class="sxs-lookup"><span data-stu-id="95f13-167">Personally Identifiable Information</span></span>

<span data-ttu-id="95f13-168">O Microsoft Lync Server 2013 tem o potencial de divulgar informações por meio de uma rede pública que pode ser vinculada a um indivíduo.</span><span class="sxs-lookup"><span data-stu-id="95f13-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="95f13-169">Os tipos de informações podem ser separados em duas categorias específicas:</span><span class="sxs-lookup"><span data-stu-id="95f13-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="95f13-170">**Dados de presença avançados** Os dados de presença avançados são informações que um usuário pode escolher para compartilhar ou não compartilhar por meio de um link para um parceiro federado ou com contatos em uma organização.</span><span class="sxs-lookup"><span data-stu-id="95f13-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="95f13-171">Esses dados não são compartilhados com usuários em uma rede IM pública.</span><span class="sxs-lookup"><span data-stu-id="95f13-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="95f13-172">As políticas dos clientes e outras configurações de clientes podem dar um certo controle com o administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="95f13-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="95f13-173">No Lync Server 2013, o modo de privacidade de presença avançada pode ser configurado para um usuário individual para impedir que os usuários do Lync que não estejam na lista de contatos do usuário vejam as informações de presença do usuário.</span><span class="sxs-lookup"><span data-stu-id="95f13-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="95f13-174">O modo de privacidade de presença avançada não impede que os usuários do Microsoft Office Communicator 2007 e do Microsoft Office Communicator 2007 R2 vejam as informações de presença do usuário.</span><span class="sxs-lookup"><span data-stu-id="95f13-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="95f13-175">Para obter detalhes, consulte o [que há de novo para os clientes no Lync server 2013](lync-server-2013-what-s-new-for-clients.md) na documentação de introdução e Configurando o [modo de privacidade de presença avançada no Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="95f13-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="95f13-176">**Dados obrigatórios** Dados obrigatórios são necessários para a operação adequada do servidor ou do cliente e não estão sob o controle da administração do cliente ou do sistema.</span><span class="sxs-lookup"><span data-stu-id="95f13-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="95f13-177">Essas informações são necessárias no nível do servidor ou no nível da rede para fins de roteamento, manutenção de estado e sinalização.</span><span class="sxs-lookup"><span data-stu-id="95f13-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="95f13-178">As seguintes listas tabelas de dados são exibidas para a rede pública.</span><span class="sxs-lookup"><span data-stu-id="95f13-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="95f13-179">Dados de Presença Aumentados</span><span class="sxs-lookup"><span data-stu-id="95f13-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f13-180">Dados Divulgados</span><span class="sxs-lookup"><span data-stu-id="95f13-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="95f13-181">Configurações Possíveis</span><span class="sxs-lookup"><span data-stu-id="95f13-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f13-182">Dados Pessoais</span><span class="sxs-lookup"><span data-stu-id="95f13-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="95f13-183">Nome, Título, empresa, Email, Fuso Horário</span><span class="sxs-lookup"><span data-stu-id="95f13-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f13-184">Números de Telefone</span><span class="sxs-lookup"><span data-stu-id="95f13-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="95f13-185">Comercial, Celular, Residencial</span><span class="sxs-lookup"><span data-stu-id="95f13-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f13-186">Informações de Calendário</span><span class="sxs-lookup"><span data-stu-id="95f13-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="95f13-187">Disponível/Ocupado, Aviso de Ausência, Detalhes da Reunião (para aqueles que têm acesso ao seu calendário)</span><span class="sxs-lookup"><span data-stu-id="95f13-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f13-188">Status de Presença</span><span class="sxs-lookup"><span data-stu-id="95f13-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="95f13-189">Ausente, Disponível, Ocupado, Não Perturbe, Offline</span><span class="sxs-lookup"><span data-stu-id="95f13-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="95f13-190">Dados Obrigatórios</span><span class="sxs-lookup"><span data-stu-id="95f13-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f13-191">Dados Divulgados</span><span class="sxs-lookup"><span data-stu-id="95f13-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="95f13-192">Exemplo de Informações</span><span class="sxs-lookup"><span data-stu-id="95f13-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f13-193">Endereço de IP</span><span class="sxs-lookup"><span data-stu-id="95f13-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="95f13-194">Endereço atual do computador ou endereço do NATed</span><span class="sxs-lookup"><span data-stu-id="95f13-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f13-195">URI do SIP</span><span class="sxs-lookup"><span data-stu-id="95f13-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="95f13-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="95f13-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

