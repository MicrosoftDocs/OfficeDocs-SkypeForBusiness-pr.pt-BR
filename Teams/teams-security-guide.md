---
title: Guia de Segurança do Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Conselhos e informações de segurança para ITAdmins na instalação, configuração e manutenção do Microsoft Teams.
localization_priority: Priority
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
ms.openlocfilehash: 32cbbbc87e6447c3bc49b97b772e2aea4849550f
ms.sourcegitcommit: 1d24b62f41bce4f8d86d6060291af1267f75a2a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209493"
---
> [!IMPORTANT]
> O modelo de serviço do Teams está sujeito a alterações para melhorar a experiência do cliente. Por exemplo, o acesso padrão ou os tempos de expiração do token de atualização podem estar sujeitos a modificações para melhorar a resiliência de desempenho e autenticação para as pessoas que usam o Teams. Quaisquer alterações são feitas com a meta de manter o Teams seguro e confiável por padrão. 
<p>

 # <a name="security-and-microsoft-teams"></a>Segurança e Microsoft Teams

Microsoft Teams, como parte do serviço do Office 365 (M365), segue todas as práticas recomendadas e os procedimentos de segurança, como segurança de nível de serviço, defesa profunda, controles do cliente dentro do serviço, aumento da segurança e melhores práticas operacionais. Para obter todos os detalhes, consulte a [Central de Confiabilidade da Microsoft](https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Confiável por Ddesign

O Teams foi projetado e desenvolvido em conformidade com Microsoft Trustworthy Computing Security Development Lifecycle (SDL), descrito em [Microsoft Trustworthy Computing Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx). O primeiro passo para criar um sistema de comunicações unificado mais seguro é o desenvolvimento de modelos de ameaça e teste de cada recurso projetado. Vários aprimoramentos relacionados à segurança foram incorporados às práticas e processos de codificação. As ferramentas de construção em tempo detectam invasões de buffer e outras potenciais ameaças antes do código ser checado no produto final. É claro que é impossível prever todas as ameaças à segurança desconhecidas e incluí-las no projeto. Nenhum sistema pode garantir a segurança completa. No entanto, porque o desenvolvimento do produto adotou os princípios de design seguro desde o início, o Teams incorpora tecnologias de segurança padrão da indústria como parte fundamental de sua arquitetura.

## <a name="trustworthy-by-default"></a>Confiável por padrão

As comunicações de rede no Teams são criptografadas por padrão. Ao exigir que todos os servidores usem certificados e ao usar OAUTH, TLS, SRTP (Secure Real-Time Transport Protocol), e outras técnicas de criptografia padrão do setor, incluindo a criptografia AES de 256 bits, todos os dados do Teams estão protegidos na rede.

## <a name="how-teams-handles-common-security-threats"></a>Como o Teams lida com ameaças comuns de segurança

Esta seção identifica as ameaças mais comuns à segurança do serviço do Teams e aborda como a Microsoft atenua cada ameaça.

### <a name="compromised-key-attack"></a>Ataque de chave comprometida

O Teams usa os recursos PKI no sistema operacional do Windows Server para proteger os dados-chave usados para criptografar as conexões do Transport Layer Security (TLS). As chaves usadas para criptografar mídia são trocadas através de conexões TLS.

### <a name="network-denial-of-service-attack"></a>Ataque de negação de serviço de rede

O ataque de negação de serviço ocorre quando o invasor impede o uso e o funcionamento normal da rede com usuários válidos. Ao usar um ataque de negação de serviço, o invasor pode:

- Enviar dados inválidos aos aplicativos e serviços que estão funcionando na rede atacada para interromper o funcionamento normal delel.
- Enviar uma grande quantidade de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda devagar aos pedidos legítimos.
- Esconder a evidência dos ataques.
- Impedir os usuários de acessar os recursos de acesso a rede.
O Teams atenua esses ataques ao executar a proteção de rede DDOS do Azure e ao limitar as solicitações dos clientes a partir dos mesmos pontos de extremidade, sub-redes e entidades federadas.

### <a name="eavesdropping"></a>Espionagem

A Espionagem pode ocorrer quando um atacante ganha acesso ao caminho dos dados na rede e tem a habilidade para monitorar e ler o tráfego. Isso também é chamado de bisbilhotar ou falsificar. Se o tráfego está no texto plano, o atacante pode lê-lo quando o atacante ganha acesso ao caminho. Um exemplo é um ataque realizado no controle de um router no caminho dos dados.

O Teams usa TLS (MTLS mútuo) para comunicações do servidor no O365 e TLS de clientes do serviço, tornando esse ataque muito difícil ou impossível de ser realizado no período em que uma determinada conversa pode ser atacada. TLS autentica todas as partes e criptografa todo tráfego. Isso não impede a espionagem, mas o atacante não pode ler o tráfego, a não ser que quebre a criptografia.

O protocolo TURN é usado para fins de mídia em tempo real. O protocolo TURN não exige que o tráfego seja criptografado e as informações que são enviadas são protegidas pela integridade da mensagem. Mesmo estando abertas apara a espionagem, as informações que são enviadas (o endereço do IP e a porta) podem ser extraídas diretamente olhando os endereços de saída e de destino dos pacotes. O serviço do Teams garante que os dados são válidos verificando a Integridade da Mensagem da mensagem, usando a chave derivada de poucos itens, incluindo uma senha do TURN, que nunca é enviada em um texto não criptografado. O SRTP é usado para o tráfego de mídia e também é criptografado.

### <a name="identity-spoofing-ip-address-spoofing"></a>Falsificação de identidade (falsificação de endereço IP)

A Falsificação ocorre quando o atacante determina e usa um endereço IP de uma rede, computador ou componente de rede sem autorização para tal ação. Um ataque bem-sucedido permite que o invasor opere como se o invasor fosse a entidade normalmente identificada pelo endereço IP.

O TLS autentica todos os participantes e criptografa todo o tráfego. Usar o TLS impede que um invasor execute a falsificação do endereço IP em uma conexão específica (por exemplo, conexões TLS mútuas). Um invasor ainda poderia falsificar o endereço do servidor DNS. No entanto, como a autenticação no Teams é feita com certificados, um invasor não teria um certificado válido necessário para falsificar um dos participantes na comunicação.

### <a name="man-in-the-middle-attack"></a>Ataque man-in-the-middle

Um ataque man-in-the-middle ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que estão se comunicando. O invasor pode monitorar e ler o tráfego antes de enviá-lo ao destinatário pretendido. Cada usuário presente na comunicação, sem saber, envia e recebe tráfego do invasor pensando estar se comunicando apenas com o usuário pretendido. Isso pode acontecer se um invasor conseguir modificar os Active Directory Domain Services para adicionar o servidor dele como um servidor confiável ou modificar o DNS (Sistema de Nome de Domínio) para fazer com que os clientes se conectem ao invasor no caminho para o servidor.

Ataques intermediários ao tráfego de mídia entre dois pontos de extremidade participando em compartilhamento de áudio, vídeo e aplicativo do Teams são evitados usando SRTP para criptografar o fluxo de mídia. As chaves criptográficas são negociadas entre os dois pontos de extremidade através de um protocolo de sinalização patenteado (protocolo de Sinalização de Chamada do Teams) que utiliza o canal UDP/TCP criptografado TLS 1.2 e AES-256 (no modo GCM).

### <a name="rtp-replay-attack"></a>Ataque de reprodução de RTP

Um ataque de reprodução ocorre quando uma transmissão de mídia válida entre duas partes é interceptada e retransmitida por motivos mal-intencionados. O Teams usa SRTP com um protocolo de sinalização de segurança que protege as transmissões contra ataques de reprodução, habilitando o receptor a manter um índice de pacotes RTP já recebidos e a comparar cada novo pacote com aqueles já listados no índice.

### <a name="spim"></a>SPIM

O SPIM é um serviço de mensagens instantâneas comerciais não solicitadas ou solicitações de assinatura de presença, como spam, mas na forma de mensagem instantânea. Embora não seja por si só um comprometimento da rede, é, no mínimo, irritante, pois pode reduzir a disponibilidade e a produção de recursos e levar a um comprometimento da rede. Um exemplo disso é quando os usuários fazem "spimming" uns para os outros, por meio de envios de solicitações. Os usuários podem bloquear uns aos outros para evitar isso, mas com a federação, se um ataque spim coordenado for estabelecido, isso poderá ser difícil de superar, a não ser que você desabilite a federação do parceiro.

### <a name="viruses-and-worms"></a>Vírus e Worms

Um vírus é uma unidade de código cujo objetivo é reproduzir outras unidades de código semelhantes. Para trabalhar, um vírus precisa de um host, como um arquivo, um email ou um programa. Como um vírus, um worm é uma unidade de código que é codificada para reproduzir unidades de código adicionais semelhantes, mas que, ao contrário de um vírus, não precisa de um host. Os vírus e os worms aparecem principalmente durante transferências de arquivos entre clientes ou quando as URLs são enviadas por outros usuários. Um vírus no seu computador pode, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome. Práticas recomendadas de segurança padrão para o cliente, como a verificação periódica de vírus, podem atenuar esse problema.

## <a name="security-framework-for-teams"></a>Estrutura de segurança para o Teams

Esta seção oferece uma visão geral dos elementos fundamentais que compõem a estrutura de segurança do Microsoft Teams.

Os principais elementos são:

- O Active Directory do Azure (AAD), que fornece um único repositório de back-end confiável para contas de usuários. As informações do perfil de usuário são armazenadas no AAD pelas ações do Microsoft Graph.
  - Lembre-se de que pode haver vários tokens emitidos, que pode ser visto se rastrear o tráfego de rede. Skype que você pode ver em rastreamentos ao olhar o tráfego de áudio e de chat.
- O protocolo TLS (Transport Layer Security) e o TLS (MTLS) mútuo que criptografam o tráfego de mensagens instantâneas e permitem a autenticação do ponto de extremidade. Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados e a integridade verificada utilizando protocolo SRTP). Você também pode ver o tráfego OAuth em seu rastreamento, principalmente em relação à negociação de permissões durante a mudança entre as guias no Teams, por exemplo, para mover-se de postagens para arquivos. Para obter um exemplo do fluxo OAuth para guias, [consulte este documento](https://docs.microsoft.com/microsoftteams/platform/tabs/how-to/authentication/auth-flow-tab).
- O Teams usa protocolos padrão do setor para autenticação de usuário, sempre que possível.

As seções a seguir abordam algumas das principais tecnologias.

### <a name="azure-active-directory"></a>Azure Active Directory

O Active Directory do Azure funciona como o serviço de diretório do Office 365 (O365). Ele armazena todas as informações do diretório e as atribuições de política do usuário.

#### <a name="crl-distribution-points"></a>Pontos de distribuição CRL

O tráfego do O365 ocorre por canais criptografados por TLS/HTTPS, o que significa que os certificados são usados para a criptografia de todo o tráfego. O Teams requer que todos os certificados de servidor contenham um ou mais pontos de distribuição das Listas de Certificados Revogados (CRLs). Os pontos de distribuição (CDP) de CRL são locais dos quais as CRLs podem ser baixadas para verificar se o certificado não foi revogado desde sua emissão e se o certificado continua dentro do período de validade. Um ponto de distribuição de CRL pode ser encontrado nas propriedades do certificado como uma URL e é normalmente uma HTTP segura. O serviço do Teams verifica a CRL com cada autenticação de certificado.

#### <a name="enhanced-key-usage"></a>Uso Avançado de Chave

Todos os componentes do serviço do Teams exigem que todos os certificados do servidor tenham suporte para EKU (Uso Avançado de Chave) para fins de autenticação do servidor. A configuração do campo do EKU para autenticação do servidor significa que o certificado é válido para fins de autenticação de servidores. Esse EKU é essencial para MTLS.

### <a name="tls-and-mtls-for-teams"></a>TLS e MTLS para o Teams

Os protocolos TLS e MTLS fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O Teams usa esses dois protocolos para criar uma rede de servidores confiáveis e para garantir que todas as comunicações nessa rede sejam criptografadas. Todas as comunicações entre servidores ocorrem no MTLS. Qualquer comunicação SIP ou herdado restante entre o cliente e o servidor ocorrem no TLS.

O TLS permite que os usuários, por meio de seu software cliente, autentiquem os servidores do teams aos quais se conectam. Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ser emitido por uma Autoridade de Certificação (AC) considerada confiável pelo cliente, e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usa a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem utilizadas na comunicação, assim, apenas o proprietário original do certificado pode utilizar sua chave privada para descriptografar os conteúdos de comunicação. A conexão resultante é confiável e, a partir desse momento, não será desafiada por nenhum outro servidor ou cliente confiável.

Conexões de servidor para servidor dependem do MTLS (TLS mútuo) para autenticação mútua. Em uma conexão MTLS, o servidor que cria a mensagem e o servidor que a recebe trocam certificados mutuamente a partir de uma AC confiável. Os certificados comprovam a identidade de cada servidor ao outro. No serviço do Teams, este procedimento é seguido.

O TLS e o MTLS ajudam a evitar a espionagem e os ataques man-in-the Middle. Em um ataque man-in-the-middle, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor, sem o conhecimento dos participantes. As especificações de servidores confiáveis do TLS e do Teams reduzem o risco de um ataque man-in-the middle parcialmente na camada de aplicativos usando criptografia coordenada por meio da criptografia de Chave Pública entre os dois pontos de extremidade. O invasor teria que possuir um certificado válido e confiável com a Chave Privada correspondente e emitido para o nome do serviço ao qual o cliente está solicitando descriptografar a comunicação.

> [!NOTE]
> Os dados do Teams são criptografados em trânsito e em repouso. A Microsoft usa tecnologias padrão do setor, como TLS e SRTP, para criptografar todos os dados em trânsito entre os dispositivos dos usuários e os datacenters da Microsoft e entre os datacenters da Microsoft. Isso inclui mensagens, arquivos, reuniões e outros conteúdos. Os dados corporativos também são criptografados em repouso nos datacenters da Microsoft, de forma que as organizações descriptografem o conteúdo, se necessário, para cumprir suas obrigações de segurança e conformidade, como a Descoberta eletrônica.

### <a name="encryption-for-teams"></a>Criptografia para o Teams

O Teams utiliza o TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor exige o MTLS, independentemente de o tráfego ter sido ajustado à rede interna ou cruzar o perímetro da rede interna.

Esta tabela resume os protocolos usados pelo Teams.

***Criptografia de tráfego***

|||
|:-----|:-----|
|**Tipo de tráfego**|**Criptografado por**|
|Servidor para Servidor|MTLS|
|Cliente para servidor (por exemplo, Mensagens instantâneas e presença)|TLS|
|Fluxos de mídia (por exemplo, Compartilhamento de mídia de áudio e vídeo)|TLS|
|Compartilhamento de mídia de áudio e vídeo|SRTP/TLS|
|Sinalização|TLS|
|||

#### <a name="media-encryption"></a>Criptografia de mídia

O tráfego de mídia é criptografado usando SRTP (Secure RTP), um perfil do protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataques de repetição para o tráfego RTP. SRTP usa uma chave da sessão gerada por meio de um gerador de número aleatório seguro e trocada por meio do canal TLS de sinalização. O tráfego da mídia cliente para cliente é negociado por meio de uma conexão de cliente para o servidor, mas é criptografado usando o SRTP ao ir para cliente direto para o cliente.

O Teams usa um token baseado em credenciais para acesso seguro a retransmissores de mídia por TURN. Media Relays trocam o token por um canal protegido por TLS.

#### <a name="fips"></a>FIPS

O Teams usa algoritmos compatíveis com FIPS (Federal Information Processing Standard) para trocas de chave de criptografia. Para obter mais informações sobre a implementação do FIPS, confira [Publicação 140-2 do padrão FIPS (Federal Information Processing Standard)](https://docs.microsoft.com/microsoft-365/compliance/offering-fips-140-2?view=o365-worldwide).

### <a name="user-and-client-authentication"></a>Autenticação do usuário e do cliente

Um usuário confiável é um com as credenciais autenticadas pelo AAD no Office 365/Microsoft 365.

Autenticação é o provisionamento de credenciais de usuário em um servidor ou serviço confiável. O Teams usa os seguintes protocolos de autenticação, dependendo do status e da localização do usuário.

- **Autenticação moderna (MA)** é a implementação Microsoft do OAUTH 2.0 para comunicação de cliente para servidor. Ela ativa recursos de segurança como a Autenticação multifator do O365 e Acesso condicional do O365. Para usar a MA, tanto o locatário online quanto os clientes precisam ser habilitados para a MA. Os clientes do Teams em PC e dispositivos móveis, bem como no cliente Web, [todos são compatíveis do MA](https://docs.microsoft.com/microsoftteams/sign-in-teams).

> [!NOTE]
> Se você precisar revisar a autenticação e os métodos de autorização do Azure AD, a introdução desse artigo e a sessão “Noções básicas de autenticação no Azure AD”.

A autenticação do Teams é realizada por meio de AAD e OAuth. O processo de autenticação pode ser simplificado para:

- Logon de usuário > Emissão de token > Solicitação posterior usa o token emitido.

As solicitações do cliente ao servidor são autenticadas e autorizadas por meio do AAD com o uso do OAuth. Os usuários com credenciais válidas emitidas por um parceiro federado são confiáveis e passam pelo mesmo processo de usuários nativos. No entanto, outras restrições podem ser colocadas no local por administradores.

Para autenticação de mídia, os protocolos ICE e TURN também utilizam o mecanismo do desafio Digest, conforme descrito no IETF TURN RFC.

### <a name="windows-powershell-and-team-management-tools"></a>Ferramentas de gerenciamento do Teams e Windows PowerShell

No Teams, os administradores de TI podem gerenciar seus serviços por meio do Portal de administração do O365 ou usando o Tenant Remote PowerShell (TRPS). Os administradores de locatário usam autenticação moderna para autenticar o TRPS.

### <a name="configuring-access-to-teams-at-your-internet-boundary"></a>Configuração do acesso ao Teams no seu limite de Internet

Para que o Teams funcione corretamente (para que os usuários possam participar de reuniões, etc.), os clientes devem configurar o acesso à Internet de forma que o tráfego de saída UDP e TCP para os serviços na nuvem do Teams seja permitido. Para obter mais informações, confira [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 e TCP 443

As portas UDP 3478-3481 e TCP 443 são usadas pelos clientes para solicitar o serviço de áudio visuais. Um cliente usa essas duas portas para atribuir as portas UDP e TCP, respectivamente, para permitir esses fluxos de mídia. Os fluxos de mídia nessas portas estão protegidos por uma chave trocada por um canal de sinalização protegido por TLS.

### <a name="udptcp-5000059999-optional"></a>UDP/TCP 50000 – 59.999 (opcional)

Portas em intervalo superior não usam retransmissão de transporte. Como são portas opcionais, você não as encontrará listadas nas URLs e intervalos de endereços IP do Office 365. Isso também significa que o Teams funcionará se essas portas estiverem bloqueadas, devido ao tráfego usando os intervalos de porta 3478-3481 (retransmissão de transporte). Eles são usados para o trânsito de mídia mas, mesmo que estes intervalos sejam desbloqueados, a redução no retardo será mínima (alguns milissegundos). Na maior parte, os problemas com a qualidade de mídia não serão afetados pelo desbloqueio e uso dessas portas. Qualquer investigação desses problemas devem se concentrar em outros lugares.

### <a name="federation-safeguards-for-teams"></a>Proteções de Federação para o Teams

A Federação fornece à sua organização a capacidade de se comunicar com outras organizações para compartilhar mensagens instantâneas e presença. No Teams, a federação está ativada por padrão. No entanto, os administradores de locatários têm a capacidade de controlar isso por meio do portal de administração do O365.

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

O Teams oferece aos usuários corporativos a capacidade de criar e ingressar em reuniões em tempo real. Usuários corporativos também podem convidar usuários externos que não tenham uma conta AAD/Office 365 para participar dessas reuniões. Usuários empregados por parceiros externos com uma identidade segura e autenticada também podem ingressar em reuniões e podem atuar como apresentadores se forem promovidos para tal atividade. Os usuários anônimos não podem criar ou entrar em uma reunião como um apresentador, mas eles podem ser promovidos para o apresentador após entrarem.

Para que os usuários anônimos possam participar de reuniões do Teams, a configuração reuniões dos participantes no centro de administração de Teams deve ser ativada.  

> [!NOTE]
> O termo *usuários anônimos* significa os usuários que não são autenticados no locatário de organizações. Neste contexto, todos os usuários externos são considerados anônimos. Os usuários autenticados incluem usuários locatários e usuários convidados do locatário.

Habilitar os usuários externos a participar de reuniões do Teams pode ser muito útil, mas envolve alguns riscos à segurança. Para lidar com esses riscos, o Teams oferece as seguintes proteções adicionais:

- As funções do participante determinam privilégios de controle de reunião.
- Os tipos de participantes permitem limitar o acesso a reuniões específicas.
- Agendar reuniões é restrito a usuários que têm uma conta do AAD e uma licença do Teams.
- Os usuários anônimos não autenticados que desejem ingressar em uma conferência de discagem discam um dos números de acesso de conferência. Se a configuração "Sempre permitir que os chamadores ignore o lobby" está *Ativada*, eles também deverão esperar até que um apresentador ou usuário autenticado participe da reunião.

Também é possível que um organizador defina as configurações para permitir que os chamadores de discagem sejam a primeira pessoa de uma reunião. Essa configuração é definida nas configurações de videoconferência para os usuários e se aplica a todas as reuniões agendadas pelo usuário.

> [!NOTE]
> Para obter mais informações sobre o convidado e o acesso externo no Teams, confira este [artigo](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations). Ele aborda quais recursos os usuários convidados ou externos podem esperar ver e usar quando fazem logon no Teams.

### <a name="participant-roles"></a>Funções do participante

Os participantes da reunião dividem-se em três grupos, cada um com seus próprios privilégios e restrições:

- **Organizador** o usuário que cria uma reunião, seja improvisado ou por programação. Um organizador deve ser um usuário no locatário autenticado e ter controle sobre todos os aspectos do usuário final de uma reunião.
- **Apresentador** um usuário que está autorizado a apresentar informações em uma reunião, usando qualquer mídia com suporte. O organizador da reunião, por definição, também é um apresentador e determina quem mais pode ser um apresentador. O organizador pode determinar isso ao agendar uma reunião ou com a reunião já em andamento.
- **Participante** um usuário que foi convidado a participar de uma reunião, mas que não está autorizado a atuar como um apresentador.

Um apresentador também pode promover um participante ao papel de apresentador durante a reunião.

### <a name="participant-types"></a>Tipos de participantes

Os participantes da reunião também são categorizados por local e por credenciais. Você pode usar essas duas características para decidir quais usuários podem ter acesso a reuniões específicas. Os usuários podem ser divididos amplamente nas categorias a seguir:

1. **Usuários que não pertencem ao locatário**esses usuários têm credenciais no Active Directory do Azure para o locatário.
    a. *Pessoas na minha organização*esses usuários têm credenciais no Active Directory do Azure para o locatário. *Pessoas na minha organização* – incluem contas de convidado.
    b. *Usuários remotos* – esses usuários estão ingressando de fora da rede corporativa. Podem ser funcionários que estão trabalhando em casa ou em trânsito, entre outros, como funcionários de fornecedores confiáveis que receberam credenciais corporativas em seus termos de serviço. Usuários remotos podem criar e ingressar em reuniões e atuar como apresentadores.
.
2. **Usuários que não pertencem ao locatário** esses usuários não têm credenciais no AD do Azure para o locatário.
    a. *Os usuários federados*– os usuários federados têm credenciais válidas com parceiros federados e são tratados como autenticados pelo Teams, mas ainda são anônimos no locatário do organizador da reunião. Os usuários federados podem ingressar em reuniões e ser promovidos a apresentadores depois de ingressarem na reunião, mas não podem criar reuniões em empresas com as quais são federados.
    b. *Os usuários anônimos* – os usuários anônimos não têm uma identidade do Active Directory e não são federados com o locatário.

Muitas reuniões envolvem usuários externos. Esses mesmos clientes também querem garantias sobre a identidade de usuários externos antes de permitir que ingressem em uma reunião. Como a seção a seguir descreve, o Teams limita o acesso à reunião aos tipos de usuários cuja permissão foi explícita e exige que todos os tipos de usuários apresentem as *credenciais* apropriadas ao entrarem em uma reunião.

### <a name="participant-admittance"></a>Admissão de participantes

No Teams, os usuários anônimos são transferidos para uma área de espera chamada lobby. Os apresentadores podem, então, *permitir ou rejeitar a participação desses usuários na reunião. Quando esses usuários são transferidos para o lobby, o apresentador e os participantes são notificados, e os usuários anônimos devem aguardar até que sejam aceitos ou rejeitados, ou a conexão vai expirar.

Por padrão, os participantes cujas chamadas vêm do PSTN vão diretamente para a reunião, uma vez que um usuário autenticado entra na reunião, mas essa opção pode ser alterada para forçar os participantes de discagem a irem para o lobby.

Os organizadores da reunião controlam se os participantes podem ingressar em uma reunião sem esperar no lobby. Cada reunião pode ser configurada para habilitar o acesso por meio de qualquer um dos métodos a seguir:

Os padrões são:

- *Pessoas na minha organização* – toda pessoa fora da organização espera no lobby até ser admitido.
- *Pessoas da minha organização e organizações confiáveis* – domínios de usuários autenticados e externos do Teams e do Skype for Business que estão na lista de permissão de acesso externo podem ignorar o lobby. Todos os usuários vão esperar no lobby até serem admitidos.
- *Todas as pessoas*– todos os participantes da reunião ignoram o o lobby uma vez que um usuário autenticado entrou em uma reunião. 

### <a name="presenter-capabilities"></a>Recursos do apresentador

Os organizadores da reunião controlam se os participantes podem fazer apresentações durante uma reunião. Cada reunião pode ser configurada para limitar os apresentadores de acordo com as seguintes opções:

- *Pessoas na minha organização* – todos os usuários do locatário, incluindo convidados, podem apresentar
- *Pessoas na minha organização e e organizações confiáveis* – todos os usuários do locatário, incluindo convidados, podem apresentar e domínios usuários externos do Teams e Skype for Business que estão na lista de permissões de acesso externo podem apresentar.  
- *Todas as pessoas* – todos os participantes da reunião são apresentadores.

### <a name="modify-while-meeting-is-running"></a>Modificar enquanto uma reunião está ocorrendo

É possível modificar as opções da reunião enquanto uma reunião está em execução. A alteração, quando salva, irá impactar a reunião em execução dentro de segundos. Também afeta qualquer ocorrência futura da reunião.

## <a name="related-topics"></a>Tópicos relacionados

[As 12 principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)

[Central de Confiabilidade da Microsoft](https://microsoft.com/trustcenter)

[Gerenciar configurações de reunião no Microsoft Teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)

[Otimizar a conectividade do Office 365 para usuários remotos usando a criação de túnel dividido de VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)

- [Implementando a criação de túnel dividido de VPN para Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)
