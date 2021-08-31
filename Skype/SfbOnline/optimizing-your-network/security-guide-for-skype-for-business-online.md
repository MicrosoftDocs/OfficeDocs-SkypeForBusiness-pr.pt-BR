---
title: Guia de segurança para o Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Security
description: Guia de segurança para o Skype for Business Online <add description>
ms.openlocfilehash: 85084e3bc675aaadf190b2c486bfe3d6adcb684c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728436"
---
# <a name="security-and-skype-for-business-online"></a>Segurança e Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online (SfBO), como parte dos serviços Microsoft 365 e Office 365, segue todas as práticas recomendadas e procedimentos de segurança, como segurança no nível de serviço por meio de defesa aprofundada, controles do cliente dentro do serviço, segurança e práticas recomendadas operacionais. Para obter detalhes completos, consulte a Central de Confiações da Microsoft ( https://microsoft.com/trustcenter) .

## <a name="trustworthy-by-design"></a>Confiável por Ddesign
O Skype for Business Online foi projetado e desenvolvido em conformidade com o SDL (Ciclo de Vida do Desenvolvimento da Segurança) de computação confiável, descrito em https://www.microsoft.com/sdl/default.aspx. O primeiro passo para criar um sistema de comunicações unificado mais seguro é o desenvolvimento de modelos de ameaça e teste de cada recurso projetado. Vários aprimoramentos relacionados à segurança foram incorporados às práticas e processos de codificação. As ferramentas de construção em tempo detectam invasões de buffer e outras potenciais ameaças antes do código ser checado no produto final. É claro que é impossível prever todas as ameaças à segurança desconhecidas e incluí-las no projeto. Nenhum sistema pode garantir a segurança completa. No entanto, como o desenvolvimento de produtos adotou princípios de design seguro desde o início, o Skype for Business Online incorpora tecnologias de segurança padrão do setor como uma parte fundamental de sua arquitetura. 

## <a name="trustworthy-by-default"></a>Confiável por padrão
As comunicações de rede no Skype for Business Online são criptografadas por padrão. Ao exigir que todos os servidores usem certificados e usando OAUTH, TLS, Protocolo de Transporte seguro Real-Time (SRTP) e outras técnicas de criptografia padrão do setor, incluindo a criptografia AES (Advanced Encryption Standard) de 256 bits, todos os dados Skype for Business Online são protegidos na rede.

## <a name="how-sfbo-handles-common-security-threats"></a>Como o SfBO lida com ameaças comuns de segurança
Esta seção identifica as ameaças mais comuns à segurança do Serviço SfBO e como a Microsoft reduz cada ameaça.

### <a name="compromised-key-attack"></a>Chave de Ataque Comprometida
Uma chave é um código secreto ou um número que é usado para criptografar, descriptografar ou validar uma informação secreta. Existem duas chaves sensíveis usadas na PKI (Infraestrutura de chave pública) que devem ser levadas em consideração: a chave particular, que cada proprietário de certificado possui, e a chave da sessão, usada após uma identificação bem-sucedida e após a troca da chave da sessão pelos parceiros de comunicação. Um ataque à chave comprometida acontece quando o atacante determina a chave de privacidade ou a chave da sessão. Quando o atacante é bem sucedido nesta determinação da chave, ele pode usá-la para descriptografar dados criptografados sem que o remetente.

Skype for Business Online usa os recursos PKI no sistema operacional Windows Server para proteger os dados principais usados para criptografia para as conexões TLS (Transport Layer Security). As chaves usadas para criptografar mídia são trocadas através de conexões TLS. 

### <a name="network-denial-of-service-attack"></a>Ataque de negação de serviço de rede
O ataque de negação de serviço ocorre quando o invasor impede o uso e o funcionamento normal da rede com usuários válidos. Ao usar um ataque de negação de serviço, o invasor pode:
- Enviar dados inválidos aos aplicativos e serviços que estão funcionando na rede atacada para interromper o funcionamento normal delel.
- Enviar uma grande quantidade de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda devagar aos pedidos legítimos.
- Esconder a evidência dos ataques.
- Impedir os usuários de acessar os recursos de acesso a rede.

O SfBO atenua esses ataques executando a proteção de rede do Azure DDOS e a abrandando solicitações de cliente dos mesmos pontos de extremidade, sub-redes e entidades federadas.

### <a name="eavesdropping"></a>Espionagem
A Espionagem pode ocorrer quando um atacante ganha acesso ao caminho dos dados na rede e tem a habilidade para monitorar e ler o tráfego. Isso também é chamado de bisbilhotar ou falsificar. Se o tráfego está no texto plano, o atacante pode lê-lo quando o atacante ganha acesso ao caminho. Um exemplo é um ataque realizado no controle de um router no caminho dos dados. 

O SfBO usa TLS mútuo (MTLS) para comunicações de servidor em Microsoft 365 ou Office 365 e TLS de clientes para o serviço, tornando esse ataque muito difícil de ser alcançado no período em que uma determinada conversa poderia ser atacada. O TLS autentica todos os participantes e criptografa todo o tráfego. Isso não impede a espionagem, mas o atacante não pode ler o tráfego, a não ser que quebre a criptografia.

O protocolo TURN é usado para fins de mídia em tempo real. O protocolo TURN não exige que o tráfego seja criptografado e as informações que são enviadas são protegidas pela integridade da mensagem. Mesmo estando abertas apara a espionagem, as informações que são enviadas (o endereço do IP e a porta) podem ser extraídas diretamente olhando os endereços de saída e de destino dos pacotes. O serviço SfBO garante que os dados são válidos verificando a Integridade da Mensagem da mensagem usando a chave derivada de alguns itens, incluindo uma senha TURN, que nunca é enviada em texto claro. O SRTP é usado para o tráfego de mídia e também é criptografado.

### <a name="identity-spoofing-ip-address-spoofing"></a>Falsificação de identidade (falsificação de endereço IP)
A Falsificação ocorre quando o atacante determina e usa um endereço IP de uma rede, computador ou componente de rede sem autorização para tal ação. Um ataque bem-sucedido permite que o invasor opere como se o invasor fosse a entidade normalmente identificada pelo endereço IP. No contexto do Microsoft Lync Server 2010, essa situação só entra em jogo se um administrador tiver feito os dois seguintes:
- Conexões configuradas que suportam apenas o Protocolo de Controle de Transmissão (TCP) (o que não é recomendado, porque as comunicações do TCP são descriptografadas).
- Marque os endereços de IP daquelas conexões como hosts confiáveis. 

Este é o menor dos problemas para as conexões de Transport Layer Security (TLS), uma vez que a TLS autentica toda as partes e criptografa todo o tráfego. Usar a TLS impede que um atacante falsifique o endereço IP em uma conexão específica (por exemplo, conexões TLS mútuas). Mas um invasor ainda pode fazer a cópia do endereço do servidor DNS que o SfBO usa. No entanto, como a autenticação no SfBO é executada com certificados, um invasor não teria um certificado válido necessário para esbocar uma das partes na comunicação.

### <a name="man-in-the-middle-attack"></a>Ataque a intermediário
Um ataque a intermediários ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que estão se comunicando. O invasor pode monitorar e ler o tráfego antes de enviá-lo ao destinatário pretendido. Cada usuário presente na comunicação, sem saber, envia e recebe tráfego do invasor pensando estar se comunicando apenas com o usuário pretendido. Isso pode acontecer se um invasor conseguir modificar os Active Directory Domain Services para adicionar o servidor dele como um servidor confiável ou modificar o DNS (Sistema de Nome de Domínio) para fazer com que os clientes se conectem ao invasor no caminho para o servidor. 

Um ataque a intermediários também pode ocorrer com o tráfego de mídia entre dois clientes, com a diferença que, no SfBO, os fluxos de compartilhamento ponto a ponto de áudio, vídeo e aplicativos são criptografados com SRTP usando chaves criptográficas negociadas entre os pares por meio do protocolo SIP (Session Initiation Protocol) no TLS. 

### <a name="rtp-replay-attack"></a>Ataque de reprodução de RTP
Um ataque de reprodução ocorre quando uma transmissão de mídia válida entre duas partes é interceptada e retransmitida por motivos mal-intencionados. O SfBO usa o SRTP em conjunto com um protocolo de sinalização seguro que protege as transmissões contra ataques de repetição, permitindo que o receptor mantenha um índice de pacotes RTP já recebidos e compare cada novo pacote com aqueles já listados no índice.

### <a name="spim"></a>SPIM
Spim é uma mensagem instantânea comercial não solicitada ou pedidos de inscrição de presença. Embora não seja por si só um comprometimento da rede, é, no mínimo, irritante, pois pode reduzir a disponibilidade e a produção de recursos e levar a um comprometimento da rede. Um exemplo disso é quando os usuários fazem "spimming" uns para os outros, por meio de envios de solicitações. Os usuários podem bloquear uns aos outros para evitar isso, mas com a federação, se um ataque spim coordenado for estabelecido, isso poderá ser difícil de superar, a não ser que você desabilite a federação do parceiro.

### <a name="viruses-and-worms"></a>Vírus e Worms
Um vírus é uma unidade de código cujo objetivo é reproduzir outras unidades de código semelhantes. Para funcionar, um vírus precisa de um hospedeiro, como um arquivo, email ou programa. Assim como um vírus, um worm é uma unidade de código que é codificada para reproduzir unidades de código semelhantes, mas que, ao contrário de um vírus, não precisa de um hospedeiro. Os vírus e worms aparecem principalmente durante as transferências de arquivos entre clientes ou quando URLs são enviados de outros usuários. Se houver um vírus em seu computador, ele pode, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome. As práticas recomendadas de segurança padrão para o cliente, como a verificação periódica de vírus, podem atenuar esse problema. 

## <a name="personally-identifiable-information"></a>Informações de Identificação Pessoal
O SfBO tem o potencial de divulgar informações por meio de uma rede pública que pode ser vinculada a um indivíduo. Os tipos de informações podem ser separados em duas categorias específicas:
- **Dados de presença aprimorados** &nbsp; &nbsp; &nbsp; Dados de presença aprimorados são informações que um usuário pode optar por compartilhar ou não por meio de um link para um parceiro federado ou com contatos dentro de uma organização. Esses dados não são compartilhados com usuários em uma rede IM pública. As políticas dos clientes e outras configurações de clientes podem dar um certo controle com o administrador do sistema. No serviço SfBO, o modo de privacidade de presença aprimorado pode ser configurado para um usuário individual para impedir que os usuários SfBO que não estão na lista de Contatos do usuário possam ver as informações de presença do usuário. 
- **Dados obrigatórios**&nbsp;&nbsp;&nbsp;São dados necessários para a operação adequada do servidor ou do cliente. Essas informações são necessárias no nível do servidor ou no nível da rede para fins de roteamento, manutenção de estado e sinalização.
As tabelas a seguir listam os dados necessários para a operação do SfBO.

***Tabela 1 - Dados avançados de presença***

<!--start table here -->



| **Dados**             | **Possíveis** **configurações**                                                                  |
|:---------------------|:-------------------------------------------------------------------------------------------|
| Dados Pessoais        | Nome, Título, Empresa, Endereço de Email, Fuso Horário                                             |
| Números de Telefone    | Comercial, Celular, Residencial                                                                         |
| Informações de Calendário | Aviso gratuito/ocupado, aviso de saída, detalhes da reunião (para aqueles que têm acesso ao calendário) |
| Status de Presença      | Ausente, Disponível, Ocupado, Não Perturbe, Offline                                             |
|                      |                                                                                            |

<!-- end of table -->

***Tabela 2 - Dados obrigatórios***

<!--start table here -->


| **Dados**             | **Possíveis** **configurações**                                                                  |
|:---------------------|:-------------------------------------------------------------------------------------------|
| Endereço de IP   | Endereço atual do computador ou endereço do NATed                     |
| URI do SIP      | <u>david.campbell@contoso.com</u>                               |
| Nome         | David Campbell (conforme definido nos Serviços de Domínio do Active Directory) |
|              |                                                                 |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Estrutura de segurança para SfBO
Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Microsoft SfBO. Esses elementos são:
- O Active Directory do Azure (AAD) fornece um único repositório de back-end confiável para contas de usuários. 
- A PKI (infraestrutura de chave pública) usa certificados emitidos por autoridades de certificação confiáveis (CAs) para autenticar servidores e garantir a integridade dos dados.
- A segurança da camada de transporte (TLS), HTTPS sobre SSL (HTTPS) e TLS mútuo (MTLS) possibilitam a autenticação de ponto de extremidade e criptografia IM. Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados e a integridade verificada utilizando protocolo SRTP).
- Protocolos padrão do setor para autenticação do usuário, onde possível.

Os tópicos nesta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança do serviço SfBO.
 
### <a name="azure-active-directory"></a>Azure Active Directory
O Active Directory do Azure funciona como o serviço de diretório do Microsoft 365 e do Office 365. Ele armazena todas as informações do diretório e as atribuições de política do usuário. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infraestrutura de chave pública para SfBO
O serviço SfBO depende de certificados para autenticação de servidor e para estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor. A PKI (Infraestrutura de Chave Pública) do Windows Server fornece a infraestrutura para estabelecer e validar essa cadeia de confiança.
Certificados são identificações digitais. Eles identificam um servidor por nome e especificam suas propriedades. Para garantir que as informações em um certificado sejam válidas, o certificado deve ser emitido por uma Autoridade de Certificação (CA) confiável por clientes ou outros servidores que se conectam ao servidor. Se o servidor se conectar apenas com outros clientes e servidores de rede privada, a AC pode ser uma AC corporativa. Se o servidor interagir com entidades fora da rede privada, uma AC pública pode ser necessária.

Mesmo se as informações no certificado forem válidas, deve haver uma forma de verificar se o servidor que apresenta o certificado é de fato aquele representado pelo certificado. É nessa etapa que o PKI do Windows entrará.
Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado mantém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar partes aleatórias das informações e as envia ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão pode se assegurar de que o servidor vincula a chave privada ao certificado e, portanto, o servidor é nomeado no certificado

#### <a name="crl-distribution-points"></a>Pontos de distribuição CRL
O SfBO exige que todos os certificados de servidor contenham um ou mais pontos de distribuição de CRL (Lista de Revogação de Certificados). Os pontos de distribuição (CDP) de CRL são locais dos quais as CRLs podem ser baixadas para verificar se o certificado não foi revogado desde sua emissão e se o certificado continua dentro do período de validade. Um ponto de distribuição de CRL pode ser encontrado nas propriedades do certificado como uma URL e é normalmente uma HTTP segura. O serviço do SfBO verifica a CRL com cada autenticação de certificado.

#### <a name="enhanced-key-usage"></a>Uso Avançado de Chave
Todos os componentes do serviço do SfBO exigem que todos os certificados do servidor tenham suporte para EKU (Uso Avançado de Chave) para fins de autenticação do servidor. A configuração do campo do EKU para autenticação do servidor significa que o certificado é válido para fins de autenticação de servidores. Esse EKU é essencial para MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS e MTLS para SfBO
Os protocolos TLS e MTLS fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O SfBO usa esses dois protocolos para criar a rede de servidores confiáveis e para garantir que todas as comunicações dessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem no MTLS. As comunicações SIP entre o cliente e o servidor ocorrem no TLS.

O TLS permite que os usuários, por meio de seu software cliente, autententem os servidores SfBO aos quais se conectam. Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ser emitido por uma AC considerada confiável pelo cliente, e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usa a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem utilizadas na comunicação, assim, apenas o proprietário original do certificado pode utilizar sua chave privada para descriptografar os conteúdos de comunicação. A conexão resultante é confiável e, a partir desse momento, não será desafiada por nenhum outro servidor ou cliente confiável. Nesse contexto, a Secure Sockets Layer (SSL), conforme utilizada com serviços os Web, pode ser associada ao protocolo baseado em TLS.

Conexões de servidor para servidor dependem do MTLS (TLS mútuo) para autenticação mútua. Em uma conexão MTLS, o servidor que cria a mensagem e o servidor que a recebe trocam certificados mutuamente a partir de uma AC confiável. Os certificados comprovam a identidade de cada servidor ao outro. No serviço do SfBO, este procedimento é seguido.

O TLS e MTLS ajudam a evitar a espionagem e ataques a intermediários. Em um ataque a intermediários, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor, sem o conhecimento das partes. A especificação do TLS e do SfBO de servidores confiáveis reduz o risco de um ataque man-in-the-middle parcialmente na camada do aplicativo usando criptografia de ponta a ponta coordenada usando a criptografia chave pública entre os dois pontos de extremidade, e um invasor teria que ter um certificado válido e confiável com a chave privada correspondente e emitido para o nome do serviço ao qual o cliente está se comunicando para descriptografar a comunicação. 

### <a name="encryption-for-sfbo"></a>Criptografia para SfBO
O SfBO usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor exige o MTLS, independentemente de o tráfego ter sido ajustado à rede interna ou cruzar o perímetro da rede interna.

A tabela a seguir resume o protocolo usado pelo SfBO.

***Tabela 3 – Proteção de tráfego***

<!--start table here with header -->




|**Tipo de tráfego**|**Protegido por**|
|:-----|:-----|
|Servidor para Servidor|MTLS|
|Cliente para Servidor|TLS|
|Mensagens instantâneas e presença|TLS (se configurado para TLS)|
|Compartilhamento de mídia de áudio, vídeo e de área de trabalho|SRTP|
|Compartilhamento de área de trabalho (sinalização)|TLS|
|Webconferência|TLS|
|Download de conteúdo de reunião, download do catálogo de endereços, expansão de grupo de distribuição|HTTPS|
|||

<!-- end of table -->

#### <a name="media-encryption"></a>Criptografia de mídia
O tráfego de mídia é criptografado usando SRTP (Secure RTP), um perfil do protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataques de repetição para o tráfego RTP. SRTP usa uma chave da sessão gerada por meio de um gerador de número aleatório seguro e trocada por meio do canal TLS de sinalização. Além disso, a mídia que flui em ambas as direções entre o Servidor de Mediação e seu próximo salto interno também é criptografada usando SRTP. 

O SfBO gera nome de usuário/senhas para acesso seguro a retransmissões de mídia no TURN. As retransmissões de mídia trocam o nome de usuário/senha em um canal SIP protegido por TLS.

#### <a name="fips"></a>FIPS
O SfBO usa algoritmos compatíveis com FIPS (Federal Information Processing Standard) para trocas de chave de criptografia. 

### <a name="user-and-client-authentication"></a>Autenticação do usuário e do cliente 
Um usuário confiável é aquele cujas credenciais foram autenticadas pelo AAD Microsoft 365 ou Office 365. 

Autenticação é o provisionamento de credenciais de usuário em um servidor ou serviço confiável. O SfBO usa os seguintes protocolos de autenticação, dependendo do status e do local do usuário.
- **Autenticação moderna** é a implementação da Microsoft do OAUTH 2.0 para comunicação de cliente para servidor. Ele habilita recursos de segurança, como Autenticação Baseada em Certificado, Autenticação Multifacional e Acesso Condicional. Para usar a MA, o locatário online e os clientes precisam estar habilitados para isso. Os locatários do SfBO criados após maio de 2017 têm o MA ativado por padrão. Para locatários criados antes disso, siga as instruções apresentadas aqui para ativá-la. Todos os clientes a seguir oferecem suporte à MA: cliente Skype for Business 2015 ou 2016, Skype for Business no Mac, cliente Lync 2013, 3PIP IP Phones, iOS e Android. 
- **A ID da** organização é usada quando a Autenticação Moderna não está habilitada (ou não está disponível).
- **Protocolo Digest** para os chamados usuários anônimos. Usuários anônimos são usuários externos que não possuem credenciais reconhecidas do Active Directory, mas que foram convidados para uma conferência no local e possuem uma chave de conferência válida. A autenticação Digest não é usada para nenhuma outra interação do cliente.

A autenticação SfBO consiste em duas fases:
1. Uma associação de segurança é estabelecida entre o cliente e o servidor.
2. O cliente e o servidor usam a associação de segurança existente para assinar mensagens enviadas e para verificar as mensagens recebidas. Mensagens não autenticadas de um cliente não são aceitas quando uma autenticação está habilitada no servidor.

Uma marca da confiança do usuário é anexada a cada mensagem originária de um usuário, não à identidade do usuário em si. O servidor verifica se há credenciais de usuário válidas em cada mensagem. Se as credenciais do usuário são válidas, a mensagem não será desafiada apenas pelo primeiro servidor a recebê-la, mas por todos os outros servidores no SfBO.

Usuários com credenciais válidas emitidas por um parceiro federado são confiáveis, porém são opcionalmente impedidos por restrições adicionais de aproveitar toda a gama de privilégios concedidos aos usuários internos.

Para autenticação de mídia, os protocolos ICE e TURN também utilizam o mecanismo do desafio Digest, conforme descrito no IETF TURN RFC. Para obter detalhes, consulte [media traversal](#external-user-av-traffic-traversal).

Os certificados de cliente fornecem uma maneira alternativa para que os usuários sejam autenticados pelo SfBO. Em vez de fornecer um nome de usuário e senha, os usuários possuem um certificado e a chave privada correspondente ao certificado exigida para resolver um desafio criptográfico. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Ferramentas de gerenciamento do Windows PowerShell e SfBO
No SfBO, os administradores de TI podem gerenciar seus serviços por meio do Portal de administração do O365 ou usando o TRPS (Tenant Remote PowerShell). Os administradores de locatário usam autenticação moderna para autenticar o TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configuração do acesso ao SfBO no seu limite de Internet
Para que o SfBO funcione corretamente (usuários capazes de participar de reuniões etc.), os clientes precisam configurar seu acesso à Internet para que o tráfego UDP e TCP de saída para serviços na nuvem SfBO seja permitido. Para obter mais detalhes, consulte aqui: https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 e TCP 443

As portas UDP 3478-3481 e TCP 443 são usadas pelos clientes para solicitar o serviço de Borda A/V. Um cliente usa essas duas portas para atribuir as portas UDP e TCP, respectivamente, para que a parte remota se conecte. Para acessar o serviço de Borda A/V, o cliente deve primeiro ter estabelecido uma sessão de sinalização SIP autenticada com o registrador SfBO para obter credenciais de autenticação de serviço de Borda A/V. Esses valores são enviados pelo canal de sinalização protegido por TLS e são gerados por computador para atenuar os ataques de dicionário. Os clientes podem, então, usar essas credenciais para a autenticação Digest com o serviço de Borda A/V para atribuir portas para uso em uma sessão de mídia. Uma solicitação inicial de atribuição é enviada pelo cliente e respondida com uma mensagem 401 nonce/desafio do serviço de Borda A/V. O cliente envia uma segunda atribuição contendo o nome de usuário e um hash HMAC (Código de Autenticação de Mensagem com Hash) do nome de usuário e nonce. 

Um mecanismo de número sequencial também é usado para evitar ataques de reprodução. O servidor calcula o HMAC esperado com base em seu próprio conhecimento do nome de usuário e senha. Se os valores do HMAC forem correspondentes, o procedimento de atribuição será executado. Caso contrário, o pacote será descartado. Esse mesmo mecanismo do HMAC também é aplicado às mensagens seguintes nessa sessão de chamada. O tempo de vida desse valor de nome de usuário/senha é de no máximo oito horas, período em que o cliente adquire um novo nome de usuário/senha para as chamadas seguintes.

### <a name="udptcp-5000059999"></a>UDP/TCP 50.000-59.999
O TCP 50.000 de saída é usado no SfBO, inclusive para compartilhamento de aplicativos e de área de trabalho, além de transferência de arquivos. Os intervalos das portas UDP/TCP de 50.000 a 59.999 são usados ​​para sessões de mídia com parceiros do Microsoft Office Communications Server 2007 que exigem o serviço NAT/firewall transversal do serviço de Borda A/V. Como o serviço de Borda A/V é o único processo que usa essas portas, o tamanho do intervalo das portas não indica uma possível ocorrência de ataque. Uma boa prática de segurança é sempre minimizar o número total de portas ouvintes por meio da não execução de serviços de rede desnecessários. Um serviço de rede que não está em execução não é explorável por um invasor remoto e a possibilidade de ataques ao computador host é reduzida. No entanto, dentro de um único serviço, a redução do número de portas não oferece o mesmo benefício. A exposição do software de serviço de Borda A/V a ataques é a mesma com 10.000 ou 10 portas abertas. A atribuição de portas nesse intervalo é feita aleatoriamente e as portas não atribuídas atualmente não escutam pacotes.

### <a name="external-user-av-traffic-traversal"></a>Passagem de tráfego A/V do usuário externo
A habilitação de usuários externos e internos para troca de mídia requer um serviço de Borda de Acesso para lidar com a sinalização SIP necessária para configurar e desativar uma sessão. Isso também requer um serviço de Borda A/V para atuar como um retransmissor para a transferência da mídia. A sequência de chamadas é ilustrada na figura a seguir.


![Sequência de chamada no Meeting Join.](media/sfbo-call-sequence-security.png) 

1. Um usuário recebe um email contendo um convite para ingressar em uma reunião no SfBO. O email contém uma chave de conferência e um URL baseado em HTTP vinculado à conferência. Tanto a chave quanto a URL são exclusivas de uma reunião específica.<p>O usuário inicia o procedimento de ingresso clicando no URL da reunião presente no email, que inicia um processo de detecção do cliente no computador do usuário. Se o cliente é detectado, ele é inicializado. Se não é detectado, ele é redirecionado para o cliente Web.<p/>
2. O cliente do SfBO envia uma SIP INVITE contendo as credenciais do usuário. Um usuário federado ou remoto instala uma conferência usando suas credenciais corporativas. Para um usuário federado, a SIP INVITE é enviada primeiramente para o servidor doméstico, que autentica o usuário e encaminha a INVITE para o SfBO. Um usuário anônimo é obrigado a passar pela autenticação Digest.<p>O SfBO autentica o usuário remoto ou anônimo e notifica o cliente. Conforme mencionado na etapa 2, os usuários federados que ingressam em uma conferência são autenticados pela empresa deles.<p/>

3. O cliente envia uma solicitação INFO para adicionar o usuário à conferência A/V.

    As conferências A/V enviam uma resposta Adicionar Usuário que contém o token para apresentar ao serviço de Borda de Conferência A/V entre outras informações.

    [Observação]  Todo o tráfego SIP anterior fluiu pelo serviço de Borda de Acesso.

    O cliente se conecta ao Servidor de Conferência A/V, que valida o token e envia o proxy da solicitação. Este contém outro token de autorização para o Servidor de Conferência A/V interno. O Servidor de Conferência A/V valida o token de autorização, originalmente emitido por ele no canal SIP, para assegurar que um usuário válido ingresse na conferência.

4. Entre o cliente e o Servidor de Conferência A/V, uma conexão de mídia é negociada e configurada pelo SRTP.
5. Um usuário recebe um email contendo um convite para ingressar em uma reunião no SfBO. O email contém uma chave de conferência e um URL baseado em HTTP vinculado à conferência. Tanto a chave quanto a URL são exclusivas de uma reunião específica.

### <a name="federation-safeguards-for-sfbo"></a>Proteções de Federação para SfBO
A federação fornece à sua organização a capacidade de se comunicar com outras organizações para compartilhar chat e presença. No SfBO, a federação está ativada por padrão. No entanto, os administradores de locatários têm a capacidade de controlar isso por meio do Microsoft 365 ou Office 365 de administração. Veja mais.

## <a name="addressing-threats-to-sfbo-conferences"></a>Como enfrentar ameaças às conferências do SfBO

O SfBO oferece a usuários corporativos a capacidade de criar e ingressar em conferências Web em tempo real. Enterprise os usuários também podem convidar usuários externos que não têm uma conta AAD, Microsoft 365 ou Office 365 para participar dessas reuniões. Usuários empregados por parceiros federados com uma identidade segura e autenticada também podem ingressar em reuniões e podem atuar como apresentadores se forem promovidos para tal atividade. Usuários anônimos não podem criar ou ingressar em uma reunião como apresentadores, mas podem ser promovidos a apresentadores após o ingresso.

A permissão para que usuários externos participem de reuniões no SfBO aumenta muito o valor desse recurso, mas também envolve alguns riscos de segurança. Para lidar com esses riscos, o SfBO oferece as seguintes proteções adicionais:
- As funções do participante determinam privilégios de controle de conferência.
- Os tipos de participantes permitem que você limite o acesso a reuniões específicas.
- Os tipos de reuniões definidos determinam quais tipos de participantes podem ingressar.
- O agendamento das conferências é restrito aos usuários que possuem uma conta AAD e uma licença do SfBO.
- Anônimos, ou seja, não autenticados, os usuários que querem ingressar em uma conferência discada discam um dos números de acesso à conferência e, em seguida, são solicitados a inserir a ID da conferência. Os usuários anônimos não autenticados também têm que registrar o seu nome. O nome gravado identifica os usuários não autenticados na conferência. Os usuários anônimos não são admitidos na conferência até que pelo menos um líder ou usuário autenticado ingresse e não é possível atribuir uma função predefinida.

### <a name="participant-roles"></a>Funções do participante
Os participantes da reunião dividem-se em três grupos, cada um com seus próprios privilégios e restrições:
-  &nbsp; Organizer &nbsp; O usuário que cria uma reunião, seja por improviso ou agendamento. Um organizador deve ser um usuário empresarial autenticado e tem controle sobre todos os aspectos do usuário final de uma reunião.
-  &nbsp; Apresentador &nbsp; Um usuário autorizado a apresentar informações em uma reunião, usando qualquer mídia com suporte. O organizador da reunião, por definição, também é um apresentador e determina quem mais pode ser um apresentador. O organizador pode determinar isso ao agendar uma reunião ou com a reunião já em andamento.
-  &nbsp; Participante &nbsp; Um usuário que foi convidado para participar de uma reunião, mas que não está autorizado a atuar como apresentador.

Um apresentador também pode promover um participante ao papel de apresentador durante a reunião.

### <a name="participant-types"></a>Tipos de participantes

Os participantes da reunião também são categorizados por local e por credenciais. Você pode usar essas duas características para especificar quais usuários podem ter acesso a reuniões específicas. Os usuários podem ser divididos amplamente nas seguintes categorias:
1.  **Usuários que pertencem ao locatário** &nbsp; &nbsp; Esses usuários têm uma credencial Azure Active Directory para o locatário.<br/>
    a. *Dentro da corpnet* – Esses usuários estão participando de dentro da rede corporativa.<br/>b. *Usuários remotos* – esses usuários estão ingressando de fora da rede corporativa. Podem ser funcionários que estão trabalhando em casa ou em trânsito, entre outros, como funcionários de fornecedores confiáveis que receberam credenciais corporativas em seus termos de serviço. Usuários remotos podem criar e ingressar em conferências, além de atuar como apresentadores.
2.  **Usuários que não pertencem ao locatário**&nbsp;&nbsp;Esses usuários não têm credenciais no Active Directory do Azure para o locatário.<br/>a. *Usuários federados* - Os usuários federados possuem credenciais válidas com parceiros federados e, portanto, são tratados como autenticados pelo SfBO. Os usuários federados podem ingressar em conferências e ser promovidos a apresentadores depois de ingressarem na reunião, mas não podem criar conferências em empresas com as quais são federados.<br/>b. *Os usuários anônimos* – os usuários anônimos não têm uma identidade do Active Directory e não são federados com o locatário. 

Os dados do cliente mostram que muitas conferências envolvem usuários externos. Esses mesmos clientes também querem garantias sobre a identidade de usuários externos antes de permitir que ingressem em uma conferência. Como a seção a seguir descreve, o SfBO limita o acesso à reunião aos tipos de usuários cuja permissão foi explícita e exige que todos os tipos de usuários apresentem as credenciais apropriadas ao entrarem em uma reunião.

### <a name="participant-admittance"></a>Admissão do participante
No SfBO, os usuários anônimos são transferidos para uma área de espera chamada lobby. Os apresentadores podem, então, permitir ou rejeitar a participação desses usuários na reunião. Esses usuários são transferidos para o lobby, o líder é notificado e os usuários esperam até que um líder os aceite ou rejeite ou até que a conexão expire. Enquanto estão no lobby, os usuários ouvem música. 

Por padrão, os participantes cujas chamadas vêm do PSTN vão diretamente para a reunião, mas essa opção pode ser alterada para forçar os participantes de discagem a irem para o lobby.  
Os organizadores da reunião controlam se os participantes podem ingressar em uma reunião sem esperar no lobby. Cada reunião pode ser configurada para habilitar o acesso por meio de qualquer um dos métodos a seguir:
- **Apenas eu, o organizador da reunião**&nbsp;&nbsp;Todos, exceto o organizador, devem esperar no lobby até serem admitidos.
- **Pessoas que eu convido da minha empresa**&nbsp;&nbsp;Qualquer pessoa da sua empresa pode entrar diretamente na reunião, mesmo que não seja convidada.
- **Qualquer pessoa da minha organização** &nbsp; &nbsp; Todos os usuários SfBO no Microsoft 365 ou Office 365 locatário podem participar da reunião sem esperar no lobby, mesmo que aqueles que não estão na lista de distribuição. Todos os outros, incluindo todos os usuários externos e anônimos, devem aguardar no lobby até serem admitidos.
- **Qualquer pessoa** &nbsp; &nbsp; Qualquer pessoa (não há restrições) que tenha acesso ao link da reunião entra diretamente na reunião.
Quando qualquer método, exceto Apenas o organizador (bloqueado), for especificado, o organizador da reunião também poderá especificar que Pessoas chamando por telefone não precisam ficar no lobby. 

### <a name="presenter-capabilities"></a>Recursos do apresentador
Os organizadores da reunião controlam se os participantes podem fazer apresentações durante uma reunião. Cada reunião pode ser configurada para limitar os apresentadores de acordo com as seguintes opções:
- **Somente organizador** &nbsp; &nbsp; Somente o organizador da reunião pode apresentar.
- **Pessoas da minha empresa** &nbsp; &nbsp; Todos os usuários internos podem apresentar.
- **Todos, incluindo pessoas de fora da minha empresa** &nbsp; &nbsp; Todos (não há restrições) que ingressarem na reunião podem apresentar.
- **Pessoas escolhidas**&nbsp;&nbsp;O organizador da reunião especifica quais usuários podem apresentar algo, adicionando-os a uma lista de apresentadores.

## <a name="related-topics"></a>Tópicos relacionados
[Central de Confiabilidade da Microsoft](https://microsoft.com/trustcenter)

