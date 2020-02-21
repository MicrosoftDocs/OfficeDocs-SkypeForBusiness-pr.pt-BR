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
ms.openlocfilehash: b9869f3c903aa7b16529ed72c499a1cb41254634
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="6e976-102">Ameaças comuns à segurança em computação de dia moderno</span><span class="sxs-lookup"><span data-stu-id="6e976-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e976-103">_**Última modificação do tópico:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="6e976-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="6e976-104">Como o Lync Server 2013 é um sistema de comunicação de classe empresarial, você deve estar ciente dos ataques comuns de segurança que podem afetar sua infraestrutura e comunicações.</span><span class="sxs-lookup"><span data-stu-id="6e976-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="6e976-105">Ataque de chave comprometida</span><span class="sxs-lookup"><span data-stu-id="6e976-105">Compromised-Key Attack</span></span>

<span data-ttu-id="6e976-106">Uma chave é um número ou código secreto usado para criptografar, descriptografar ou validar informações secretas.</span><span class="sxs-lookup"><span data-stu-id="6e976-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="6e976-107">Há duas chaves confidenciais em uso na infraestrutura de chave pública (PKI) que devem ser consideradas:.</span><span class="sxs-lookup"><span data-stu-id="6e976-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="6e976-108">A chave privada que cada proprietário do certificado tem</span><span class="sxs-lookup"><span data-stu-id="6e976-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="6e976-109">A chave de sessão usada após uma identificação bem-sucedida e a troca de chaves de sessão pelos parceiros de comunicação</span><span class="sxs-lookup"><span data-stu-id="6e976-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="6e976-110">Um ataque de chave comprometida ocorre quando o invasor determina a chave privada ou a chave de sessão.</span><span class="sxs-lookup"><span data-stu-id="6e976-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="6e976-111">Quando o invasor consegue determinar a chave, ele pode usar a chave para descriptografar os dados criptografados sem o conhecimento do remetente.</span><span class="sxs-lookup"><span data-stu-id="6e976-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="6e976-112">O Lync Server 2013 usa os recursos de PKI no sistema operacional Windows Server para proteger os dados de chave usados para criptografia para as conexões de TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="6e976-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="6e976-113">As chaves usadas para a criptografia de mídia são trocadas por conexões TLS.</span><span class="sxs-lookup"><span data-stu-id="6e976-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="6e976-114">Ataque de negação de serviço da rede</span><span class="sxs-lookup"><span data-stu-id="6e976-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="6e976-115">O *ataque de negação de serviço* ocorre quando o invasor impede o uso normal da rede e funciona por usuários válidos.</span><span class="sxs-lookup"><span data-stu-id="6e976-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="6e976-116">Isso é feito quando o invasor inunda o serviço com solicitações legítimas que sobrecarregam o uso do serviço por usuários legítimos.</span><span class="sxs-lookup"><span data-stu-id="6e976-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="6e976-117">Com o uso de um ataque de negação de serviço, o invasor pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e976-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="6e976-118">Enviar dados inválidos a aplicativos e serviços em execução na rede atacada para interromper seu funcionamento normal.</span><span class="sxs-lookup"><span data-stu-id="6e976-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="6e976-119">Enviar um grande volume de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda lentamente às solicitações legítimas.</span><span class="sxs-lookup"><span data-stu-id="6e976-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="6e976-120">Ocultar a evidência dos ataques.</span><span class="sxs-lookup"><span data-stu-id="6e976-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="6e976-121">Impedir que os usuários acessem os recursos da rede.</span><span class="sxs-lookup"><span data-stu-id="6e976-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="6e976-122">Espionagem (farejamento, espionagem)</span><span class="sxs-lookup"><span data-stu-id="6e976-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="6e976-123">A *espionagem* pode ocorrer quando um invasor obtém acesso ao caminho de dados em uma rede e tem a capacidade de monitorar e ler o tráfego.</span><span class="sxs-lookup"><span data-stu-id="6e976-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="6e976-124">Isso também é chamado de *sniffing* ou *snooping*.</span><span class="sxs-lookup"><span data-stu-id="6e976-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="6e976-125">Se o tráfego estiver em texto sem formatação, o invasor poderá ler o tráfego quando o invasor obtiver acesso ao caminho.</span><span class="sxs-lookup"><span data-stu-id="6e976-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="6e976-126">Um exemplo é um ataque realizado pelo controle de um roteador no caminho de dados.</span><span class="sxs-lookup"><span data-stu-id="6e976-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="6e976-127">A recomendação e a configuração padrão para o tráfego no Microsoft Lync Server 2013 é usar o protocolo de TLS mútuo (MTLS) entre servidores confiáveis e TLS de cliente para servidor.</span><span class="sxs-lookup"><span data-stu-id="6e976-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="6e976-128">Essa medida de proteção tornaria um ataque muito difícil ou impossível de alcançar dentro do período de tempo no qual uma determinada conversa ocorre.</span><span class="sxs-lookup"><span data-stu-id="6e976-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="6e976-129">O TLS autentica todas as partes e criptografa todo o tráfego.</span><span class="sxs-lookup"><span data-stu-id="6e976-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="6e976-130">Isso não impede a espionagem, mas o invasor não pode ler o tráfego, a menos que a criptografia seja interrompida.</span><span class="sxs-lookup"><span data-stu-id="6e976-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="6e976-131">O protocolo passagem usando NAT (ativar/desativar) não determina o tráfego a ser criptografado e as informações que ele está enviando são protegidas pela integridade da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6e976-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="6e976-132">Embora esteja aberto para espionagem, as informações que ele está enviando (ou seja, os endereços IP e a porta) podem ser extraídos diretamente, simplesmente examinando os endereços de origem e de destino dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="6e976-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="6e976-133">O serviço de borda A/V garante que os dados sejam válidos verificando a integridade da mensagem da mensagem usando a chave derivada de alguns itens, incluindo uma senha de ativação, que nunca é enviada em texto não criptografado.</span><span class="sxs-lookup"><span data-stu-id="6e976-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="6e976-134">Se o protocolo SRTP for usado, o tráfego de mídia também será criptografado.</span><span class="sxs-lookup"><span data-stu-id="6e976-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="6e976-135">Falsificação de identidade (falsificação de endereço IP)</span><span class="sxs-lookup"><span data-stu-id="6e976-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="6e976-136">A *falsificação* ocorre quando o atacante determina e usa um endereço IP de uma rede, computador ou componente de rede sem autorização para fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="6e976-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="6e976-137">Um ataque de sucesso permite o invasor operar como se fosse uma entidade identificada normalmente pelo endereço IP.</span><span class="sxs-lookup"><span data-stu-id="6e976-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="6e976-138">Dentro do contexto do Microsoft Lync Server 2013, essa situação só entra em cena se um administrador tiver feito o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e976-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="6e976-139">Configurou conexões que suportam apenas TCP (Protocolo de Controle de Transmissão) (não é recomendado porque as comunicações TCP não são criptografadas).</span><span class="sxs-lookup"><span data-stu-id="6e976-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="6e976-140">Marcou os endereços IPs das conexões como hosts confiáveis.</span><span class="sxs-lookup"><span data-stu-id="6e976-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="6e976-141">Este é menos um problema para conexões TLS (Transport Layer Security), porque a TLS autentica todas as partes e criptografa todo o tráfego.</span><span class="sxs-lookup"><span data-stu-id="6e976-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="6e976-142">Usar o TLS evita que um invasor realize falsificação de endereço IP em uma determinada conexão (por exemplo, conexões TLS mútuas).</span><span class="sxs-lookup"><span data-stu-id="6e976-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="6e976-143">Mas um invasor ainda pode falsificar o endereço do servidor DNS que o Lync Server 2013 usa.</span><span class="sxs-lookup"><span data-stu-id="6e976-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="6e976-144">No entanto, como a autenticação no Lync é realizada com certificados, um invasor não terá um certificado válido necessário para falsificar uma das partes da comunicação.</span><span class="sxs-lookup"><span data-stu-id="6e976-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="6e976-145">Ataque de interceptação</span><span class="sxs-lookup"><span data-stu-id="6e976-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="6e976-146">Um ataque de interceptação ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que estão se comunicando.</span><span class="sxs-lookup"><span data-stu-id="6e976-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="6e976-147">O invasor pode monitorar e ler o tráfego antes de enviá-lo para o destinatário pretendido.</span><span class="sxs-lookup"><span data-stu-id="6e976-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="6e976-148">Cada usuário na comunicação envia o tráfego para e recebe o tráfego do invasor, tudo isso enquanto pensa que eles estão se comunicando apenas com o usuário pretendido.</span><span class="sxs-lookup"><span data-stu-id="6e976-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="6e976-149">Isso pode acontecer quando um invasor pode modificar os serviços de domínio do Active Directory para adicionar seu servidor como um servidor confiável ou modificar o DNS (sistema de nomes de domínio) para fazer com que os clientes se conectem por meio do invasor no servidor.</span><span class="sxs-lookup"><span data-stu-id="6e976-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="6e976-150">Um ataque man-in-Middle também pode ocorrer com o tráfego de mídia entre dois clientes.</span><span class="sxs-lookup"><span data-stu-id="6e976-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="6e976-151">No entanto, no compartilhamento de áudio, vídeo e aplicativos ponto a ponto do Microsoft Lync Server 2013, os fluxos são criptografados com o SRTP, usando chaves criptográficas que são negociadas entre os pares que estão usando o protocolo SIP sobre TLS.</span><span class="sxs-lookup"><span data-stu-id="6e976-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="6e976-152">Servidores como o chat de grupo usam HTTPS para aumentar a segurança do tráfego da Web.</span><span class="sxs-lookup"><span data-stu-id="6e976-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="6e976-153">Ataque de repetição ao RTP</span><span class="sxs-lookup"><span data-stu-id="6e976-153">RTP Replay Attack</span></span>

<span data-ttu-id="6e976-154">Um *ataque de repetição* ocorre quando uma transmissão de mídia válida entre duas partes é interceptada e retransmitida para fins mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="6e976-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="6e976-155">O SRTP usado em conjunto com um protocolo de sinalização seguro protege as transmissões contra ataques de repetição habilitando o receptor a manter um índice de pacotes RTP já recebidos e a comparar cada novo pacote com os já listados no índice.</span><span class="sxs-lookup"><span data-stu-id="6e976-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="6e976-156">Spim</span><span class="sxs-lookup"><span data-stu-id="6e976-156">Spim</span></span>

<span data-ttu-id="6e976-157">O *spim* é uma mensagem instantânea comercial não solicitada ou solicitações de inscrição de presença.</span><span class="sxs-lookup"><span data-stu-id="6e976-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="6e976-158">Embora não seja propriamente um compromisso da rede, essa situação é, no mínimo, irritante, pode reduzir a disponibilidade de recursos e a produção e possivelmente comprometerá a rede.</span><span class="sxs-lookup"><span data-stu-id="6e976-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="6e976-159">Um exemplo disso são os usuários que repassam spims entre si ao enviar solicitações.</span><span class="sxs-lookup"><span data-stu-id="6e976-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="6e976-160">Os usuários podem bloquear uns aos outros para evitar que isso aconteça, mas com a federação, se um ataque de spim coordenado for estabelecido, possivelmente será difícil contornar o problema, a menos que você desabilite a federação do parceiro.</span><span class="sxs-lookup"><span data-stu-id="6e976-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="6e976-161">Vírus e worms</span><span class="sxs-lookup"><span data-stu-id="6e976-161">Viruses and Worms</span></span>

<span data-ttu-id="6e976-162">Um *vírus* é uma unidade de código cujo propósito é reproduzir unidades de código adicionais e semelhantes.</span><span class="sxs-lookup"><span data-stu-id="6e976-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="6e976-163">Para funcionar, um vírus precisa de um host, como um arquivo, um email ou um programa.</span><span class="sxs-lookup"><span data-stu-id="6e976-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="6e976-164">Um *worm* é uma unidade de código cujo propósito é reproduzir unidades de código adicionais e semelhantes, mas não precisa de um host.</span><span class="sxs-lookup"><span data-stu-id="6e976-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="6e976-165">Vírus e worms aparecem principalmente durante transferências de arquivos entre clientes ou quando as URLs são enviadas de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="6e976-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="6e976-166">Se um vírus estiver no seu computador, ele pode, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome.</span><span class="sxs-lookup"><span data-stu-id="6e976-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="6e976-167">Informações de identificação pessoal</span><span class="sxs-lookup"><span data-stu-id="6e976-167">Personally Identifiable Information</span></span>

<span data-ttu-id="6e976-168">O Microsoft Lync Server 2013 tem o potencial de divulgar informações por meio de uma rede pública que possa ser vinculada a um indivíduo.</span><span class="sxs-lookup"><span data-stu-id="6e976-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="6e976-169">Os tipos de informações podem ser classificados em duas categorias específicas:</span><span class="sxs-lookup"><span data-stu-id="6e976-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="6e976-170">**Dados de presença avançados** Os dados de presença avançados são informações que um usuário pode optar por compartilhar ou não compartilhar sobre um link para um parceiro federado ou com contatos em uma organização.</span><span class="sxs-lookup"><span data-stu-id="6e976-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="6e976-171">Esses dados não são compartilhados com usuários em uma rede pública de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="6e976-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="6e976-172">As políticas cliente e outras configurações cliente podem aplicar algum controle com o administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="6e976-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="6e976-173">No Lync Server 2013, o modo de privacidade de presença avançada pode ser configurado para um usuário individual para impedir que os usuários do Lync que não estejam na lista de contatos do usuário vejam as informações de presença do usuário.</span><span class="sxs-lookup"><span data-stu-id="6e976-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="6e976-174">O modo de privacidade de presença avançada não impede que os usuários do Microsoft Office Communicator 2007 e do Microsoft Office Communicator 2007 R2 vejam as informações de presença de um usuário.</span><span class="sxs-lookup"><span data-stu-id="6e976-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="6e976-175">Para obter detalhes, consulte [What ' s New for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) na documentação de introdução e [Configurando o modo de privacidade de presença avançada no Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6e976-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="6e976-176">**Dados obrigatórios** Os dados obrigatórios são necessários para a operação adequada do servidor ou do cliente e não estão sob o controle da administração do cliente ou do sistema.</span><span class="sxs-lookup"><span data-stu-id="6e976-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="6e976-177">Essas são as informações necessárias em um nível de servidor ou de rede para fins de roteamento, manutenção de estado e sinalização.</span><span class="sxs-lookup"><span data-stu-id="6e976-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="6e976-178">As tabelas a seguir listam os dados que são expostos em uma rede pública.</span><span class="sxs-lookup"><span data-stu-id="6e976-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="6e976-179">Dados de presença aprimorados</span><span class="sxs-lookup"><span data-stu-id="6e976-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e976-180">Dados divulgados</span><span class="sxs-lookup"><span data-stu-id="6e976-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="6e976-181">Configurações possíveis</span><span class="sxs-lookup"><span data-stu-id="6e976-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e976-182">Dados pessoais</span><span class="sxs-lookup"><span data-stu-id="6e976-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="6e976-183">Nome, cargo, empresa, endereço de email, fuso horário</span><span class="sxs-lookup"><span data-stu-id="6e976-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e976-184">Números de telefone</span><span class="sxs-lookup"><span data-stu-id="6e976-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="6e976-185">Comercial, Celular, Residencial</span><span class="sxs-lookup"><span data-stu-id="6e976-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e976-186">Informações do calendário</span><span class="sxs-lookup"><span data-stu-id="6e976-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="6e976-187">Disponibilidade, aviso de falta de cidade, detalhes da reunião (para aqueles que têm acesso ao seu calendário)</span><span class="sxs-lookup"><span data-stu-id="6e976-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e976-188">Status de presença</span><span class="sxs-lookup"><span data-stu-id="6e976-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="6e976-189">Ausente, Disponível, Ocupado, Não Incomodar, Offline</span><span class="sxs-lookup"><span data-stu-id="6e976-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="6e976-190">Dados obrigatórios</span><span class="sxs-lookup"><span data-stu-id="6e976-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e976-191">Dados divulgados</span><span class="sxs-lookup"><span data-stu-id="6e976-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="6e976-192">Informações de exemplo</span><span class="sxs-lookup"><span data-stu-id="6e976-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e976-193">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="6e976-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="6e976-194">Endereço real do computador ou endereço NAT</span><span class="sxs-lookup"><span data-stu-id="6e976-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e976-195">SIP URI</span><span class="sxs-lookup"><span data-stu-id="6e976-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="6e976-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6e976-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

