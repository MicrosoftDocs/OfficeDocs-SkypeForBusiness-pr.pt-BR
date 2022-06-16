---
title: Guia de segurança para visão geral do Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 04/12/2022
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Consultoria e aprendizados de segurança para administradores de IT na instalação, configuração e manutenção Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e5dcee1e45ec191853f088887e7ed36f8e3fbc6
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103198"
---
# <a name="security-and-microsoft-teams"></a>Segurança e Microsoft Teams

> [!IMPORTANT]
> O modelo de serviço do Teams está sujeito a alterações para melhorar as experiências do cliente. Por exemplo, o acesso padrão ou os tempos de expiração do token de atualização podem estar sujeitos a modificações para melhorar a resiliência de desempenho e autenticação para as pessoas que usam o Teams. Quaisquer alterações são feitas com a meta de manter o Teams seguro e confiável por padrão.

O Microsoft Teams, como parte dos serviços do Microsoft 365 e do Office 365, segue todas as práticas recomendadas de segurança e procedimentos, como segurança em nível de serviço por meio de defesa aprofundada, controles do cliente dentro do serviço, proteção de segurança e práticas recomendadas operacionais. Para obter detalhes completos, consulte a [Central de Confiabilidade da Microsoft](https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Confiável por natureza

O Teams foi projetado e desenvolvido em conformidade com o SDL (Security Development Lifecycle) da Microsoft, que é descrito em [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx). A primeira etapa na criação de um sistema de comunicações unificadas mais seguro foi criar modelos de ameaças e testar cada recurso conforme ele foi projetado. Várias melhorias relacionadas à segurança foram criadas no processo de codificação e nas práticas. As ferramentas de tempo de compilação detectam estouros de buffer e outras possíveis ameaças à segurança antes que o código seja conferido ao produto final. É impossível projetar contra todas as ameaças de segurança desconhecidas. Nenhum sistema pode garantir a segurança completa. No entanto, como o desenvolvimento de produtos adotou princípios de design seguros desde o início, o Teams incorpora tecnologias de segurança padrão do setor como uma parte fundamental de sua arquitetura.

## <a name="trustworthy-by-default"></a>Confiável por padrão

As comunicações de rede no Teams são criptografadas por padrão. Ao exigir que todos os servidores usem certificados e usando OAUTH, Transport Layer Security (TLS) e Secure Real-Time Transport Protocol (SRTP), todos os dados do Teams são protegidos na rede.

## <a name="how-teams-handles-common-security-threats"></a>Como o Teams lida com ameaças comuns de segurança

Esta seção identifica as ameaças mais comuns à segurança do serviço do Teams e aborda como a Microsoft atenua cada ameaça.

### <a name="compromised-key-attack"></a>Ataque de chave comprometida

O Teams usa os recursos de PKI no sistema operacional Windows Server para proteger os dados de chave usados para criptografia para as conexões TLS. As chaves usadas para criptografias de mídia são trocadas por conexões TLS.

### <a name="network-denial-of-service-attack"></a>Ataque de negação de serviço de rede

Um ataque de negação de serviço distribuído (DDOS) ocorre quando o invasor impede o uso normal da rede e funciona por usuários válidos. Usando um ataque de negação de serviço, o invasor pode:

- Enviar dados inválidos aos aplicativos e serviços que estão funcionando na rede atacada para interromper o funcionamento normal delel.
- Enviar uma grande quantidade de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda devagar aos pedidos legítimos.
- Esconder a evidência dos ataques.
- Impedir os usuários de acessar os recursos de acesso a rede.

O Teams atenua esses ataques ao executar a proteção de rede DDOS do Azure e ao limitar as solicitações dos clientes a partir dos mesmos pontos de extremidade, sub-redes e entidades federadas.

### <a name="eavesdropping"></a>Espionagem

A interceptação ocorre quando um invasor obtém acesso ao caminho de dados em uma rede e tem a capacidade de monitorar e ler o tráfego. A interceptação também é chamada de detecção ou espionagem. Se o tráfego estiver em texto sem formatação, o invasor poderá ler o tráfego quando o invasor obtiver acesso ao caminho. Um exemplo é um ataque executado controlando um roteador no caminho de dados.

O Teams usa TLS mútuo (MTLS) e OAuth de Servidor para Servidor (S2S) (entre outros protocolos) para comunicações de servidor no Microsoft 365 e no Office 365 e também usa TLS de clientes para o serviço. Todo o tráfego na rede é criptografado.

Esses métodos de comunicação tornam a interceptação difícil ou impossível de alcançar dentro do período de uma única conversa. O TLS autentica todos os participantes e criptografa todo o tráfego. Embora o TLS não impeça a interceptação, o invasor não pode ler o tráfego, a menos que a criptografia seja interrompida.

O protocolo *Traversal Using Relays around NAT*(TURN) é usado para fins de mídia em tempo real. O protocolo TURN não exige que o tráfego seja criptografado e as informações que ele envia são protegidas pela integridade da mensagem. Embora ele esteja aberto à interceptação, as informações que ele envia, ou seja, endereços IP e porta, podem ser extraídas diretamente examinando os endereços de origem e de destino dos pacotes. O serviço Teams garante que os dados sejam válidos verificando a integridade da mensagem usando a chave derivada de alguns itens, incluindo uma senha TURN, que nunca é enviada em texto não criptografado. O SRTP é usado para tráfego de mídia e também é criptografado.

### <a name="identity-spoofing-ip-address-spoofing"></a>Falsificação de identidade (falsificação de endereço IP)

A falsificação ocorre quando o invasor identifica e usa um endereço IP de um componente de rede, computador ou rede sem ter autorização para fazer isso. Um ataque bem-sucedido permite que o invasor opere como se o invasor for a entidade normalmente identificada pelo endereço IP.

O TLS autentica todas as partes e criptografa todo o tráfego. O uso do TLS impede que um invasor execute falsificação de endereço IP em uma conexão específica (por exemplo, conexões TLS mútuas). Um invasor ainda pode falsificar o endereço do servidor Sistema de Nomes de Domínio (DNS). No entanto, como a autenticação no Teams é executada com certificados, um invasor não teria um certificado válido necessário para falsificar uma das partes na comunicação.

### <a name="man-in-the-middle-attack"></a>Ataque Man-in-the-Middle

Um ataque man-in-the-middle ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que estão se comunicando. O invasor pode monitorar e ler o tráfego antes de enviá-lo ao destinatário pretendido. Cada usuário presente na comunicação, sem saber, envia e recebe tráfego do invasor pensando estar se comunicando apenas com o usuário pretendido. Esse cenário pode acontecer se um invasor puder modificar os Serviços de Domínio do Active Directory para adicionar o servidor dele como um servidor confiável ou modificar a configuração DNS ou usar outros meios para fazer com que os clientes se conectem através do invasor no caminho para o servidor.

Ataques man-in-the-middle no tráfego de mídia entre dois pontos de extremidade que participam do compartilhamento de áudio, vídeo e aplicativo do Teams são impedidos usando o *Protocolo em Tempo Real Seguro* (SRTP) para criptografar o fluxo de mídia. As chaves criptográficas são negociadas entre os dois pontos de extremidade através de um protocolo de sinalização proprietário (protocolo de Sinalização de Chamada do Teams) que utiliza o canal UDP/TCP criptografado TLS 1.2 e AES-256 (no modo GCM).

### <a name="real-time-transport-protocol-rtp-replay-attack"></a>Ataque de repetição do protocolo RTP

Um ataque de reprodução ocorre quando uma transmissão de mídia válida entre duas partes é interceptada e retransmitida por motivos mal-intencionados. O Teams usa o SRTP com um protocolo de sinalização de segurança que protege as transmissões contra ataques de reprodução, habilitando o receptor a manter um índice de pacotes RTP já recebidos e a comparar cada novo pacote com aqueles já listados no índice.

### <a name="spim"></a>SPIM

SPIM são mensagens instantâneas comerciais não solicitadas ou solicitações de assinatura de presença, como spam, mas em formato de mensagem instantânea. Embora não seja por si só um comprometimento da rede, é, no mínimo, inconveniente, pode reduzir a disponibilidade e a produção de recursos e possivelmente levar a um comprometimento da rede. Um exemplo são os usuários que fazem "spimming" uns aos outros enviando solicitações. Os usuários podem bloquear uns aos outros para evitar o spimming, mas, com a federação, se um ator mal-intencionado estabelecer um ataque SPIM coordenado, poderá ser difícil de superar, a menos que você desabilite a federação do parceiro.

### <a name="viruses-and-worms"></a>Vírus e Worms

Um vírus é uma unidade de código cuja finalidade é reproduzir mais unidades de código semelhantes. Para funcionar, um vírus precisa de um host, como um arquivo, email ou programa. Como um vírus, um worm é uma unidade de código que reproduz mais unidades de código semelhantes, mas que, ao contrário de um vírus, não precisa de um host. Vírus e worms aparecem principalmente durante transferências de arquivos entre clientes ou quando URLs são enviadas de outros usuários. Se um vírus estiver em seu computador, ele poderá, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome. As práticas recomendadas de segurança do cliente padrão, como verificar periodicamente se há vírus, podem atenuar esse problema.

## <a name="security-framework-for-teams"></a>Estrutura de segurança para o Teams

O Teams endossa ideias de segurança como Confiança Zero e princípios de acesso com Privilégios mínimos. Esta seção oferece uma visão geral dos elementos fundamentais que compõem a estrutura de segurança do Microsoft Teams.

Os principais elementos são:

- O Active Directory do Azure (Azure AD) que fornece um único repositório de back-end confiável às contas dos usuários. As informações de perfil do usuário são armazenadas no Azure AD pelas ações do Microsoft Graph.
  - Pode haver vários tokens emitidos que você pode ver se rastrear seu tráfego de rede. Incluindo tokens do Skype que você pode ver em rastreamentos ao examinar o tráfego de chat e áudio.
- O protocolo TLS criptografa o canal em movimento. A autenticação ocorre usando TLS mútuo (MTLS), com base em certificados ou usando a autenticação Serviço a serviço baseada no Azure AD.
- Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados e a integridade verificada utilizando protocolo SRTP).
- Você verá o tráfego OAuth em seu rastreamento, especialmente em torno de trocas de token e negociação de permissões ao alternar entre guias no Teams, por exemplo, para mover de Postagens para Arquivos. Para obter um exemplo do fluxo OAuth para guias, [consulte este documento](/microsoftteams/platform/tabs/how-to/authentication/auth-flow-tab).
- O Teams usa protocolos padrão do setor para autenticação de usuário, sempre que possível.

As seções a seguir abordam algumas das principais tecnologias.

### <a name="azure-active-directory"></a>Azure Active Directory

O Active Directory do Azure funciona como o serviço de diretório do Microsoft 365 e do Office 365. Ele armazena todas as informações de diretório de usuários e aplicativos e atribuições de política.

### <a name="traffic-encryption-in-teams"></a>Criptografia de tráfego no Teams

Esta tabela mostra os principais Tipos de tráfego e qual protocolo é usado para criptografia.

|**Tipo de tráfego**|**Criptografado por**|
|:-----|:-----|
|Servidor para Servidor|TLS (com MTLS ou OAuth de Serviço a Serviço)|
|Cliente para servidor, por exemplo, mensagens instantâneas e presença|TLS|
|Fluxos de mídia, por exemplo, compartilhamento de áudio e vídeo de mídia|TLS|
|Compartilhamento de mídia de áudio e vídeo|SRTP/TLS|
|Sinalização|TLS|
|Criptografia avançada de cliente para cliente (por exemplo, chamadas de criptografia de ponta a ponta)|SRTP/DTLS|
|||

#### <a name="certificate-revocation-list-crl-distribution-points"></a>Pontos de Distribuição da Lista de Certificados Revogados (CRL)

Microsoft 365 e o tráfego do Office 365 ocorrem em canais criptografados TLS/HTTPS, o que significa que os certificados são usados para criptografia de todo o tráfego. O Teams exige que todos os certificados de servidor contenham um ou mais pontos de distribuição da CRL. Os pontos de distribuição de CRL (CDPs) são locais dos quais as CRLs podem ser baixadas para verificar se o certificado não foi revogado desde a hora em que foi emitido e se o certificado ainda está dentro do período de validade. Um ponto de distribuição da CRL é notado nas propriedades do certificado como uma URL e é HTTP seguro. O serviço Teams verifica a CRL com cada autenticação de certificado.

#### <a name="enhanced-key-usage"></a>Uso Avançado de Chave

Todos os componentes do serviço Teams exigem todos os certificados de servidor para dar suporte ao Uso Avançado de Chave (EKU) para autenticação de servidor. Configurar o campo EKU para autenticação de servidor significa que o certificado é válido para autenticar servidores. Esse EKU é essencial para o MTLS.

#### <a name="tls-for-teams"></a>TLS para Teams

**Os dados do Teams são criptografados em trânsito e em repouso no serviços da Microsoft, entre serviços e entre clientes e serviços.** A Microsoft usa tecnologias padrão do setor, como TLS e SRTP, para criptografar todos os dados em trânsito. Os dados em trânsito incluem mensagens, arquivos, reuniões e outros conteúdos. Os dados corporativos também são criptografados em repouso no serviços da Microsoft para que as organizações possam descriptografar o conteúdo, se necessário, para atender às obrigações de segurança e conformidade por meio de métodos como a Descoberta Eletrônica. Para obter mais informações sobre criptografia Microsoft 365, consulte [Criptografia no Microsoft 365](/microsoft-365/compliance/encryption)

Os fluxos de dados TCP são criptografados usando TLS e protocolos OAuth MTLS e OAuth de Serviço a serviço fornecem comunicações autenticadas de ponto de extremidade entre serviços, sistemas e clientes. O Teams usa esses protocolos para criar uma rede de sistemas confiáveis e garantir que toda a comunicação pela rede seja criptografada.

Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ter sido emitido por uma AC (Autoridade de Certificação) que também é confiável para o cliente e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usará a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem usadas para a comunicação, para que somente o proprietário original do certificado possa usar sua chave privada para descriptografar o conteúdo da comunicação. A conexão resultante é confiável e, a partir desse ponto, não é desafiada por outros servidores ou clientes confiáveis.

O uso do TLS ajuda a evitar ataques de interceptação e man-in-the-middle. Em um ataque man-in-the-middle, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor sem o conhecimento de nenhuma das partes. O TLS e a especificação do Teams de servidores confiáveis reduz o risco de um ataque man-in-the-middle parcialmente na camada do aplicativo usando a criptografia que é coordenada usando a criptografia de Chave Pública entre os dois pontos de extremidade. Um invasor teria que ter um certificado válido e confiável com a chave privada correspondente e emitida para o nome do serviço ao qual o cliente está se comunicando para descriptografar a comunicação.

#### <a name="encryption-in-teams-and-microsoft-365"></a>Criptografia no Teams e no Microsoft 365

Há várias camadas de criptografia em trabalho dentro Microsoft 365. A criptografia do Teams funciona com o restante da criptografia do Microsoft 365 para proteger o conteúdo da sua organização. Este artigo descreve tecnologias de criptografia específicas para o Teams. Para uma visão geral sobre criptografia Microsoft 365, consulte [Criptografia no Microsoft 365](/microsoft-365/compliance/encryption).

#### <a name="media-encryption"></a>Criptografia de mídia

Os fluxos de chamada no Teams são baseados no modelo de oferta e resposta [Protocolo de Descrição de Sessão (SDP) RFC 8866](https://datatracker.ietf.org/doc/html/rfc8866) via HTTPS. Depois que o receptor aceita uma chamada, o chamador e o receptor concordam com os parâmetros da sessão.

O tráfego de mídia é criptografado e flui entre o receptor e o chamador usando RTP seguro (SRTP), um perfil do Protocolo de Transporte em Tempo Real (RTP) que fornece confidencialidade, autenticação e proteção contra ataques de repetição para o tráfego RTP. SRTP usa uma chave da sessão gerada por meio de um gerador de número aleatório seguro e trocada por meio do canal TLS de sinalização. Na maioria dos casos, o tráfego de mídia cliente para cliente é negociado por meio da sinalização de conexão de cliente para servidor e é criptografado usando SRTP ao ir diretamente de cliente para cliente.

Em fluxos normais de chamada, a negociação da chave de criptografia ocorre por meio do canal de sinalização de chamada. Em uma chamada criptografada de ponta a ponta, o fluxo de sinalização é o mesmo de uma chamada Teams normal. No entanto, o Teams usa DTLS para derivar uma chave de criptografia com base em certificados por chamada gerados em ambos os pontos de extremidade do cliente. Como o DTLS deriva a chave com base nos certificados do cliente, a chave é opaca para a Microsoft. Quando ambos os clientes concordam com a chave, a mídia começa a fluir usando essa chave de criptografia negociada por DTLS por SRTP.

Para proteger contra um ataque man-in-the-middle entre o receptor e o chamador, o Teams deriva um código de segurança de 20 dígitos das impressões digitais SHA-256 dos certificados de chamada do chamador e do ponto de extremidade do chamador. O receptor e o chamador podem validar os códigos de segurança de 20 dígitos lendo-os uns para os outros para ver se eles correspondem. Se os códigos não corresponderem, a conexão entre o receptor e o chamador foi interceptada por um ataque man-in-the-middle. Se a chamada tiver sido comprometida, os usuários poderão encerrar a chamada manualmente.

O Teams usa um token baseado em credenciais para acesso seguro a retransmissores de mídia por TURN. Media Relays trocam o token por um canal protegido por TLS.

### <a name="federal-information-processing-standard-fips"></a>FIPS (Federal Information Processing Standard)

O Teams usa algoritmos compatíveis com FIPS para trocas de chaves de criptografia. Para obter mais informações sobre a implementação do FIPS, confira [Publicação 140-2 do padrão FIPS (Federal Information Processing Standard)](/microsoft-365/compliance/offering-fips-140-2).

### <a name="user-and-client-authentication"></a>Autenticação do usuário e do cliente

Um usuário confiável é aquele cujas credenciais foram autenticadas pelo Azure AD no Microsoft 365 ou no Office 365.

A autenticação é o provisionamento de credenciais de usuário em um servidor ou serviço confiável. O Teams usa os seguintes protocolos de autenticação, dependendo do status e da localização do usuário.

- **Autenticação moderna (MA)** é a implementação Microsoft do OAUTH 2.0 para comunicação de cliente para servidor. Ela ativa recursos de segurança como a autenticação multifatorial e o Acesso Condicional. Para usar a MA, tanto o locatário online quanto os clientes precisam habilitar a MA. Os clientes do Teams em PC e dispositivos móveis, bem como no cliente Web, [são compatíveis com a MA](./sign-in-teams.md).

> [!NOTE]
> Se você quiser mais informações sobre os métodos de autorização do Azure AD, a introdução desse artigo e a sessão “Noções básicas de autenticação no Azure AD”.

A autenticação do Teams é realizada pelo Azure AD e pelo OAuth. O processo de autenticação pode ser simplificado para:

- O usuário entra > ocorre a emissão de token > próxima solicitação usa o token emitido.

As solicitações de cliente para servidor são autenticadas e autorizadas pelo Azure AD com o uso do OAuth. Os usuários com credenciais válidas emitidas por um parceiro federado são confiáveis e passam pelo mesmo processo de usuários nativos. No entanto, outras restrições podem ser colocadas no local por administradores.

Para autenticação de mídia, os protocolos ICE e TURN também utilizam o mecanismo do desafio Digest, conforme descrito no IETF TURN RFC.

### <a name="windows-powershell-and-team-management-tools"></a>Ferramentas de gerenciamento do Teams e Windows PowerShell

No Teams, os administradores de TI podem gerenciar seu serviço por meio do Centro de administração do Microsoft 365 ou usando o Tenant Remote PowerShell (TRPS). Os administradores de locatário usam autenticação moderna para autenticar no TRPS.

### <a name="configuring-access-to-teams-at-your-internet-boundary"></a>Configurando o acesso Teams no limite da Internet

Para que o Teams funcione corretamente, por exemplo, para que os usuários possam ingressar em reuniões, os clientes precisam configurar o acesso à Internet de modo que o tráfego UDP e TCP de saída para serviços na nuvem do Teams seja permitido. Para obter mais informações, consulte [URLs e intervalos de endereços IP do Office 365](/office365/enterprise/urls-and-ip-address-ranges).

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 e TCP 443

As portas UDP 3478-3481 e TCP 443 são usadas pelos clientes para solicitar o serviço de áudio visuais. Um cliente usa essas duas portas para atribuir as portas UDP e TCP, respectivamente, para permitir esses fluxos de mídia. Os fluxos de mídia nessas portas estão protegidos por uma chave trocada por um canal de sinalização protegido por TLS.

### <a name="federation-safeguards-for-teams"></a>Proteções de federação para Teams

A Federação fornece à sua organização a capacidade de se comunicar com outras organizações para compartilhar mensagens instantâneas e presença. No Teams, a federação está ativada por padrão. No entanto, os administradores de locatários têm a capacidade de controlar a federação por meio do Centro de administração do Microsoft 365.

## <a name="addressing-threats-to-teams-meetings"></a>Enfrentando ameaças em reuniões do Teams

Essas são as duas opções para controlar quem chega nas reuniões do Teams e quem terá acesso às informações apresentadas.

1. Você pode controlar quem entra em suas reuniões nas configurações de **lobby**.</p>

    |As opções de configuração "Quem pode ignorar o lobby" disponíveis na página Opções de reunião   |Os tipos de usuário ingressam diretamente na reunião  |Tipos de usuário indo para o lobby   |
    |---------|---------|---------|
    |Pessoas da minha organização     |  - No locatário  </br>- Convidado do locatário         |  - Federado</br>  - Anônimo</br>  - Discagem PSTN</br>     |
    |Pessoas da minha organização e organizações confiáveis      |  - No locatário</br> - Convidado do locatário</br> - Federado</br>        |  - Anônimo</br>  - Discagem PSTN</br>      |
    |Todos      |   - No locatário</br>  - Convidado do locatário</br>  - Federado anônimo</br>  - Discagem PSTN</br>       |         |

2. A segunda forma é por meio de **reuniões estruturadas** (onde os apresentadores podem fazer isso em relação a tudo o que deve ser feito e os participantes têm uma experiência controlada). Depois de ingressar em uma reunião estruturada, os apresentadores controlam o que os participantes podem fazer na reunião. </p>

    |Ações  |Apresentadores  |Participantes  |
    |---------|---------|---------|
    |Falar e compartilhar seus vídeos     |   Y      |   Y      |
    |Participar do chat da reunião     |   Y    |    Y     |
    |Alterar as configurações das opções de reunião     |   Y      |  N       |
    |Ativar mudo de outros participantes| Y | N |
    |Remover outros participantes      |  Y       |   N      |
    |Compartilhar conteúdo     |     Y    |     N    |
    |Admitir outros participantes do lobby|  Y       |   N      |
    |Tornar outros participantes apresentadores ou participantes     |   Y      | N        |
    |Iniciar ou parar gravação      |     Y    |    N     |
    |Assumir o controle quando outro participante compartilhar um PowerPoint     |  Y         | N        |

O Teams oferece aos usuários corporativos a capacidade de criar e ingressar em reuniões em tempo real. Os usuários corporativos também podem convidar usuários externos que não possuem uma conta do Azure AD, do Microsoft 365 ou do Office 365 para participar dessas reuniões. Usuários empregados por parceiros externos com uma identidade segura e autenticada também podem ingressar em reuniões e podem atuar como apresentadores se forem promovidos para tal atividade. Os usuários anônimos não podem criar ou ingressar em uma reunião como apresentador, mas podem ser promovidos a apresentadores após ingressarem.

Para que os usuários anônimos possam participar de reuniões do Teams, a configuração reuniões dos participantes no centro de administração de Teams deve ser ativada.

> [!NOTE]
> O termo *usuários anônimos* significa os usuários que não são autenticados no locatário de organizações. Neste contexto, todos os usuários externos são considerados anônimos. Os usuários autenticados incluem usuários locatários e usuários convidados do locatário.

Habilitar os usuários externos a participar de reuniões do Teams pode ser útil, mas envolve alguns riscos à segurança. Para lidar com esses riscos, o Teams usa as seguintes proteções:

- As funções do participante determinam privilégios de controle de reunião.
- Os tipos de participantes permitem limitar o acesso a reuniões específicas.
- Agendar reuniões é restrito a usuários que têm uma conta do AAD e uma licença do Teams.
- Os usuários anônimos não autenticados que desejem ingressar em uma conferência de discagem discam um dos números de acesso de conferência. Se a configuração "Sempre permitir que os chamadores ignore o lobby" está *Ativada*, eles também deverão esperar até que um apresentador ou usuário autenticado participe da reunião.

  > [!CAUTION]
  > Se você não quiser que usuários Anônimos (usuários não convidados explicitamente) ingressem em uma reunião, você precisará garantir que **Usuários anônimos podem participar de uma reunião** esteja definido como **Desativado** na seção de **Participantes** da reunião.

Também é possível que um organizador defina as configurações para permitir que os chamadores de discagem sejam a primeira pessoa de uma reunião. Essa configuração é definida nas configurações de videoconferência para os usuários e se aplica a todas as reuniões agendadas pelo usuário.

> [!NOTE]
> Para obter mais informações sobre o convidado e o acesso externo no Teams, confira este [artigo](./communicate-with-users-from-other-organizations.md). Ele aborda quais recursos os usuários convidados ou externos podem esperar ver e usar quando fazem logon no Teams. <p> Se você estiver gravando reuniões e deseja ver uma matriz de permissões ao acessar o conteúdo, consulte [esse artigo](./tmr-meeting-recording-change.md) e a sua matriz.

### <a name="participant-roles"></a>Funções de participante

Os participantes da reunião dividem-se em três grupos, cada um com seus próprios privilégios e restrições:

- **Organizador** o usuário que cria uma reunião, seja improvisado ou por programação. Um organizador deve ser um usuário no locatário autenticado e ter controle sobre todos os aspectos do usuário final de uma reunião.
- **Apresentador** um usuário que está autorizado a apresentar informações em uma reunião, usando qualquer mídia com suporte. O organizador da reunião, por definição, também é um apresentador e determina quem mais pode ser um apresentador. O organizador pode determinar isso ao agendar uma reunião ou com a reunião já em andamento.
- **Participante** um usuário que foi convidado a participar de uma reunião, mas que não está autorizado a atuar como um apresentador.

Um apresentador também pode promover um participante ao papel de apresentador durante a reunião.

### <a name="participant-types"></a>Tipos de participantes

Os participantes da reunião também são categorizados por local e por credenciais. Você pode usar essas duas características para decidir quais usuários podem ter acesso a reuniões específicas. Os usuários podem ser divididos amplamente nas categorias a seguir:

- **Usuários que pertencem ao locatário**. Esses usuários têm uma credencial Azure Active Directory para o locatário.

    *Pessoas na minha organização* esses usuários têm credenciais no Active Directory do Azure para o locatário. *Pessoas na minha organização* – incluem contas de convidado.

    *Usuários remotos* – esses usuários estão ingressando de fora da rede corporativa. Podem ser funcionários que estão trabalhando em casa ou em trânsito, entre outros, como funcionários de fornecedores confiáveis que receberam credenciais corporativas em seus termos de serviço. Usuários remotos podem criar e ingressar em reuniões e atuar como apresentadores.

- **Usuários que não pertencem ao locatário**. Esses usuários não têm credenciais no Azure AD para o locatário.

    *Usuários Federados* - os usuários federados têm credenciais válidas com parceiros federados e são tratados como autenticados pelo Teams, mas ainda são externos ao locatário do organizador da reunião. Os usuários federados podem ingressar em reuniões e ser promovidos a apresentadores depois de ingressarem na reunião, mas não podem criar reuniões em empresas com as quais são federados.

    *Os usuários anônimos* – os usuários anônimos não têm uma identidade do Active Directory e não são federados com o locatário.

Muitas reuniões envolvem usuários externos. Esses mesmos clientes também querem garantias sobre a identidade de usuários externos antes de permitir que ingressem em uma reunião. Como a seção a seguir descreve, o Teams limita o acesso à reunião aos tipos de usuários cuja permissão foi explícita e exige que todos os tipos de usuários apresentem as *credenciais* apropriadas ao entrarem em uma reunião.

### <a name="participant-admittance"></a>Participação do participante

> [!CAUTION]
> Se você não quiser que usuários Anônimos (usuários não convidados explicitamente) ingressem em uma reunião, você precisará garantir que a opção **Usuários anônimos podem participar de uma reunião** esteja definida como **Desativado** na seção de **Participantes** da reunião.

No Teams, os usuários anônimos são transferidos para uma área de espera chamada lobby. Os apresentadores podem, então, *permitir ou rejeitar a participação desses usuários na reunião. Quando esses usuários são transferidos para o lobby, o apresentador e os participantes são notificados, e os usuários anônimos devem aguardar até que sejam aceitos ou rejeitados, ou a conexão vai expirar.

Por padrão, os participantes cujas chamadas vêm do PSTN vão diretamente para a reunião, uma vez que um usuário autenticado entra na reunião, mas essa opção pode ser alterada para forçar os participantes de discagem a irem para o lobby.

Os organizadores da reunião controlam se os participantes podem ingressar em uma reunião sem esperar no lobby. Cada reunião pode ser configurada para habilitar o acesso por meio de qualquer um dos métodos a seguir:

Os padrões são:

- *Pessoas na minha organização* – toda pessoa fora da organização espera no lobby até ser admitido.
- *Pessoas em minha organização, organizações confiáveis e convidados* - Usuários autenticados dentro da organização, incluindo usuários convidados e usuários de organizações confiáveis, ingressam na reunião diretamente sem esperar no lobby. Os usuários anônimos aguardam o lobby.
- *Todas as pessoas*– todos os participantes da reunião ignoram o o lobby uma vez que um usuário autenticado entrou em uma reunião. 

### <a name="presenter-capabilities"></a>Recursos do apresentador

Os organizadores da reunião controlam se os participantes podem fazer apresentações durante uma reunião. Cada reunião pode ser configurada para limitar os apresentadores de acordo com as seguintes opções:

- *Pessoas na minha organização* – todos os usuários do locatário, incluindo convidados, podem apresentar
- *Pessoas na minha organização e organizações confiáveis* – todos os usuários do locatário, incluindo convidados, podem apresentar e domínios usuários externos do Teams e Skype for Business que estão na lista de permissões de acesso externo podem apresentar.  
- *Todas as pessoas* – todos os participantes da reunião são apresentadores.

### <a name="modify-while-meeting-is-running"></a>Modificar enquanto uma reunião está ocorrendo

Você pode modificar as opções de reunião enquanto uma reunião está em andamento. A alteração, quando salva, será perceptível na reunião em execução em segundos. Ele também afeta quaisquer ocorrências futuras da reunião.

## <a name="related-topics"></a>Tópicos relacionados

[As 12 principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](/microsoft-365/security/top-security-tasks-for-remote-work)

[Central de Confiabilidade da Microsoft](https://microsoft.com/trustcenter)

[Gerenciar configurações de reunião no Microsoft Teams](./meeting-settings-in-teams.md)

[Otimize a conectividade do Microsoft 365 ou do Office 365 dos usuários remotos usando o túnel dividido da VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)

- [Implementando o túnel dividido de VPN](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

[Gravações de reunião no Teams, onde as gravações são armazenadas e quem pode acessá-las](./tmr-meeting-recording-change.md)
