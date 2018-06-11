---
title: Guia de segurança para o Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: ''
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Security
description: Guia de segurança para o Skype for Business Online <add description>
ms.openlocfilehash: 3ffe2f3308513d2fccb2bd9f65e4b2e194e2f1cf
ms.sourcegitcommit: 9dc1c9afccb1792611b6e6d60dfcf62302dbde81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19709183"
---
# <a name="skype-for-business-online-and-security"></a>Skype for Business Online e Segurança
O Skype for Business Online (SfBO), como parte do serviço do Office 365, segue todas as práticas recomendadas e os procedimentos de segurança, como segurança de nível de serviço, defesa profunda, controles do cliente dentro do serviço, aumento da segurança e melhores práticas operacionais.  Para obter todos os detalhes, consulte a Central de Confiabilidade do Office 365 (https://products.office.com/en-us/business/office-365-trust-center-security).


### <a name="trustworthy-by-design"></a>Design confiável
O Skype for Business Online foi projetado e desenvolvido em conformidade com o SDL (Ciclo de Vida do Desenvolvimento da Segurança) de computação confiável, descrito em https://www.microsoft.com/en-us/sdl/default.aspx. O primeiro passo para criar um sistema de comunicações unificado mais seguro é o desenvolvimento de modelos de ameaça e teste de cada recurso projetado. Os diversos aperfeiçoamentos relacionados à segurança foram criados de acordo com os processos e práticas de codificação. As ferramentas de construção em tempo detectam invasões de buffer e outras potenciais ameaças antes do código ser checado no produto final. Claro, é impossível detectar todas as ameaças de segurança desconhecidas. Nenhum sistema pode garantir segurança completa. No entanto, como o desenvolvimento do produto adotou os princípios de design seguro desde o início, o Skype for Business Online incorpora tecnologias de segurança padrão do setor como parte fundamental de sua arquitetura. 

### <a name="trustworthy-by-default"></a>Padrão confiável
As comunicações de rede no Skype for Business Online são criptografadas por padrão. Ao exigir que todos os servidores usem certificados e ao usar OAUTH, TLS, protocolo SRTP (Secure Real-Time Transport Protocol) e outras técnicas de criptografia padrão do setor, incluindo criptografia AES (Advanced Encryption Standard) de 256 bits, todos os dados do Skype for Business Online estão protegido na rede.

### <a name="how-sfbo-handles-common-security-threats"></a>Como o SfBO lida com ameaças comuns de segurança
Esta seção identifica as ameaças mais comuns à segurança do serviço do SFBO e aborda como a Microsoft atenua cada ameaça.

### <a name="compromised-key-attack"></a>Ataque à chave comprometida
Uma chave é um código secreto ou um número usado para criptografar, descriptografar ou validar informações secretas. Existem duas chaves sensíveis usadas na PKI (Infraestrutura de chave pública) que devem ser levadas em consideração: a chave particular, que cada proprietário de certificado possui, e a chave da sessão, usada após uma identificação bem-sucedida e após a troca da chave da sessão pelos parceiros de comunicação.  Um ataque à chave comprometida acontece quando o invasor determina a chave particular ou a chave da sessão. Quando o atacante é bem sucedido nesta determinação da chave, ele pode usá-la para descriptografar dados criptografados sem que o remetente.

O Skype for Business Online usa os recursos da PKI no sistema operacional do Windows Server para proteger os dados de chave usados para criptografar as conexões do protocolo TLS (Transport Layer Security). As chaves usadas para criptografias de mídia são trocadas através de conexões do TLS. 

### <a name="network-denial-of-service-attack"></a>Ataque de negação de serviço de rede
O ataque de negação de serviço ocorre quando o invasor impede o uso e o funcionamento normal da rede pelos usuários válidos. Com um ataque de negação de serviço, o invasor pode:
- Enviar dados inválidos aos aplicativos e serviços que estão funcionando na rede atacada para interromper o funcionamento normal.
- Enviar uma grande quantidade de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda devagar aos pedidos legítimos.
- Esconder a evidência dos ataques.
- Impedir que os usuários acessem os recursos da rede.

O SFBO atenua esses ataques ao executar a proteção de rede DDOS do Azure e ao limitar as solicitações dos clientes a partir dos mesmos pontos de extremidade, sub-redes e entidades federadas.

### <a name="eavesdropping"></a>Espionagem
A Espionagem pode ocorrer quando um atacante ganha acesso ao caminho dos dados na rede e tem a habilidade para monitorar e ler o tráfego. Isso também é chamado de detecção ou falsificação. Se o tráfego estiver como texto sem formatação, o invasor poderá lê-lo quando tiver acesso ao caminho. Um exemplo é um ataque realizado ao controlar um roteador no caminho de dados. 

O SfBO usa MTLS (TLS mútuo) para comunicações do servidor no O365 e TLS de clientes do serviço, tornando esse ataque muito difícil ou impossível de ser realizado no período em que uma determinada conversa pode ser atacada. O TLS autentica todas as partes e criptografa todo o tráfego. Isso não impede a espionagem, mas o invasor não pode ler o tráfego, a não ser que quebre a criptografia.

O protocolo TURN é usado para fins de mídia em tempo real.  O protocolo TURN não exige que o tráfego seja criptografado e as informações que ele envia são protegidas pela integridade da mensagem. Mesmo estando vulneráveis para a espionagem, as informações que são enviadas (ou seja, o endereço do IP e a porta) podem ser extraídas simplesmente olhando os endereços de saída e de destino dos pacotes. O serviço do SfBO garante a validade dos dados fazendo a verificação da Integridade de Mensagem da mensagem usando a chave derivada de alguns poucos itens, incluindo uma senha TURN, que nunca é enviada em texto não criptografado. O SRTP é usado para o tráfego de mídia e também é criptografado.

### <a name="identity-spoofing-ip-address-spoofing"></a>Falsificação de identidade (falsificação de endereço IP)
A Falsificação ocorre quando o atacante determina e usa um endereço IP de uma rede, computador ou componente de rede sem autorização para tal ação. Um ataque bem-sucedido permite que o invasor opere como se fosse a entidade normalmente identificada pelo endereço IP. No contexto do Microsoft Lync Server 2010, essa situação ocorre somente se um administrador:
- Configurar conexões que suportam apenas o TCP (Protocolo de Controle de Transmissão), o que não é recomendado, pois as comunicações do TCP são descriptografadas.
- Marque os endereços de IP daquelas conexões como hosts confiáveis. 

Este é o menor dos problemas para as conexões de Transport Layer Security (TLS), uma vez que a TLS autentica toda as partes e criptografa todo o tráfego. O uso do TLS impede que um invasor falsifique o endereço IP em uma conexão específica (por exemplo, conexões de TLS mútuo). Mas um invasor ainda pode falsificar o endereço do servidor DNS que o SfBO utiliza. No entanto, como a autenticação no SfBO é feita com certificados, um invasor não teria um certificado válido necessário para falsificar uma das partes na comunicação.

### <a name="man-in-the-middle-attack"></a>Ataque a intermediários
Um ataque a intermediários ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que estão se comunicando. O invasor pode monitorar e ler o tráfego antes de enviá-lo ao destinatário pretendido. Cada usuário presente na comunicação, sem saber, envia e recebe tráfego do invasor pensando estar se comunicando apenas com o usuário pretendido. Isso pode acontecer se um invasor conseguir modificar os Active Directory Domain Services para adicionar o servidor dele como um servidor confiável ou modificar o DNS (Sistema de Nome de Domínio) para fazer com que os clientes se conectem ao invasor no caminho para o servidor. 

Um ataque a intermediários também pode ocorrer com o tráfego de mídia entre dois clientes, com a diferença que, no SfBO, os fluxos de compartilhamento ponto a ponto de áudio, vídeo e aplicativos são criptografados com SRTP usando chaves criptográficas negociadas entre os pares por meio do protocolo SIP (Session Initiation Protocol) no TLS. 

### <a name="rtp-replay-attack"></a>Ataque de reprodução RTP
Um ataque de reprodução ocorre quando uma transmissão válida de mídia entre duas partes é interceptada e retransmitida de forma mal-intencionada. O SfBO usa o SRTP com um protocolo seguro de sinalização que protege as transmissões contra ataques de reprodução ao habilitar o receptor para manter um índice de pacotes RTP já recebidos e comparar cada novo pacote com aqueles já listados no índice.

### <a name="spim"></a>Spim
Spim é uma mensagem instantânea comercial não solicitada ou solicitações de assinatura de presença. Embora não seja por si só um comprometimento da rede, é, no mínimo, irritante, pois pode reduzir a disponibilidade e a produção de recursos e levar a um comprometimento da rede. Um exemplo disso é quando os usuários fazem "spimming" uns para os outros, por meio de envios de solicitações. Os usuários podem bloquear uns aos outros para evitar isso, mas com a federação, se um ataque spim coordenado for estabelecido, isso poderá ser difícil de superar, a não ser que você desabilite a federação do parceiro.

### <a name="viruses-and-worms"></a>Vírus e worms
Vírus é uma unidade de código cujo propósito é reproduzir unidades de códigos adicionais e semelhantes. Para funcionar, um vírus precisa de um host, como um arquivo, email ou programa. Como um vírus, um worm é uma unidade de código que é codificada para reproduzir unidades de código adicionais semelhantes, mas que, ao contrário de um vírus, não precisa de um host. Vírus e worms aparecem principalmente durante transferências de arquivos entre clientes ou quando os URLs são enviados por outros usuários. Um vírus no seu computador pode, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome.  Práticas recomendadas de segurança padrão para o cliente, como a verificação periódica de vírus, podem atenuar esse problema.  

### <a name="personally-identifiable-information"></a>Informações de identificação pessoal
O SfBO tem o potencial de divulgar informações para uma rede pública capaz de ser vinculada a um indivíduo. Os tipos de informações podem ser separados em duas categorias específicas:
- **Dados de presença avançados**&nbsp;&nbsp;&nbsp;São informações que um usuário pode escolher compartilhar ou não por meio de um link com um parceiro federado ou com contatos em uma organização. Esses dados não são compartilhados com usuários em uma rede de chat público. As políticas de clientes e outras configurações de clientes podem dar um certo controle para o administrador do sistema. No serviço do SfBO, o modo avançado de privacidade de presença pode ser configurado para que um usuário individual impeça usuários do SfBO não presentes na lista de contatos de ver suas informações de presença. 
- **Dados obrigatórios**&nbsp;&nbsp;&nbsp;São dados necessários para a operação adequada do servidor ou do cliente. Essas informações são necessárias no nível do servidor ou no nível da rede para fins de roteamento, manutenção de estado e sinalização.
As tabelas a seguir listam os dados necessários para a operação do SfBO.

***Tabela 1 - Dados avançados de presença***

<!--start table here -->

||||
|:-----|:-----|:-----|
|**Dados**|**Possíveis** **configurações**|
|Dados pessoais |Nome, Cargo, Empresa, Endereço de email, Fuso Horário|
|Números de telefone|Comercial, Celular, Residencial|
|Informações de calendário|Disponível/Ocupado, Aviso de ausência, detalhes da reunião (para quem tiver acesso ao seu calendário)| 
|Status de presença|Ausente, Disponível, Ocupado, Não Incomodar, Offline|
|||||

<!-- end of table -->



***Tabela 2 - Dados obrigatórios***

<!--start table here -->

||||
|:-----|:-----|:-----|
|**linha de cabeçalho 1 col 1** |**linha de cabeçalho 1 col 2** |
|Endereço IP|Endereço atual do computador ou endereço do NATed|
|URI do SIP|<u>david.campbell@contoso.com</u>|
|Nome|David Campbell (conforme definido nos Serviços de Domínio do Active Directory)|
|||||

<!-- end of table -->

### <a name="security-framework-for-sfbo"></a>Estrutura de segurança para SfBO
Este capítulo fornece uma visão geral dos elementos fundamentais que compõem a estrutura de segurança do SfBO da Microsoft. Esses elementos são:
- O Active Directory do Azure (AAD) fornece um único repositório de back-end confiável para contas de usuários. 
- A PKI (Infraestrutura de Chave Pública) utiliza certificados emitidos por CAs (autoridades de certificação) confiáveis para autenticar servidores e garantir a integridade de dados.
- O TLS (Transport Layer Security), HTTPS (HTTPS no SSL) e MTLS (TLS mútuo) possibilitam a autenticação do ponto de extremidade e a criptografia de mensagens de chat. Os fluxos de compartilhamento ponto a ponto de áudio, vídeo e aplicativos são criptografados e têm sua integridade verificada utilizando o SRTP (Secure Real-Time Transport Protocol).
- Protocolos padrão do setor para autenticação do usuário, quando possível.
- O Windows PowerShell fornece recursos de segurança habilitados por padrão para que os usuários não possam executar scripts com facilidade ou sem serem percebidos. <!-- delete the prior bullets? -->

Esses elementos fundamentais de segurança trabalham em conjunto para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma fundação segura para o SfBO.

Os tópicos nesta seção descrevem como cada um desses elementos fundamentais funciona para aprimorar a segurança do serviço do SfBO.

### <a name="azure-active-directory"></a>Active Directory do Azure
O Active Directory do Azure funciona como o serviço de diretório do O365. Ele armazena todas as informações do diretório do usuário e as tarefas de políticas. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infraestrutura de chave pública para SfBO
O serviço do SfBO baseia-se em certificados para autenticação do servidor e para estabelecer uma cadeia de confiança entre clientes e servidores e entre diferentes funções do servidor. A PKI (Infraestrutura de Chave Pública) do Windows Server fornece a infraestrutura para estabelecer e validar essa cadeia de confiança.
Certificados são identificações digitais. Eles identificam um servidor por nome e especificam suas propriedades. Para garantir que as informações de um certificado sejam válidas, o certificado deve ser emitido por uma CA (Autoridade de certificação) na qual os clientes confiem ou por outros servidores que se conectam ao servidor. Se o servidor se conecta apenas com outros clientes e servidores de rede privada, a CA pode ser corporativa. Se o servidor interagir com entidades fora da rede privada, uma AC pública pode ser necessária.

Mesmo se as informações no certificado forem válidas, deve haver uma forma de verificar se o servidor que apresenta o certificado é de fato aquele representado pelo certificado. É nessa etapa que o PKI do Windows entrará.
Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado mantém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar partes aleatórias das informações e as envia ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão pode se assegurar de que o servidor vincula a chave privada ao certificado e, portanto, o servidor é nomeado no certificado

#### <a name="crl-distribution-points"></a>Pontos de distribuição das CRLs (Listas de Certificados Revogados)
O SfBO requer que todos os certificados do servidor contenham um ou mais pontos de distribuição de CRL (Lista de Certificados Revogados). Os pontos de distribuição (CDP) de CRL são locais dos quais as CRLs podem ser baixadas para verificar se o certificado não foi revogado desde sua emissão e se o certificado continua dentro do período de validade. Um ponto de distribuição de CRL pode ser encontrado nas propriedades do certificado como um URL e é uma HTTP segura.  O serviço do SfBO verifica a CRL com cada autenticação de certificado.

#### <a name="enhanced-key-usage"></a>Uso avançado da chave
Todos os componentes do serviço do SfBO exigem que todos os certificados do servidor tenham suporte para EKU (Uso Avançado de Chave) para fins de autenticação do servidor. A configuração do campo do EKU para autenticação do servidor significa que o certificado é válido para fins de autenticação de servidores. Esse EKU é essencial para MTLS. 

#### <a name="tls-and-mtls-for-sfbo"></a>TLS e MTLS para SfBO
Os protocolos TLS e MTLS fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O SfBO usa esses dois protocolos para criar a rede de servidores confiáveis e para garantir que todas as comunicações nessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem no MTLS. As comunicações SIP entre o cliente e o servidor ocorrem no TLS.

O TLS permite que os usuários, por meio do software de cliente, autentiquem os servidores do SfBO aos quais se conectam. Em uma conexão do TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ser emitido por uma AC considerada confiável pelo cliente, e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usa a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem utilizadas na comunicação, assim, apenas o proprietário original do certificado pode utilizar sua chave privada para descriptografar os conteúdos de comunicação. A conexão resultante é confiável e, a partir desse momento, não será desafiada por nenhum outro servidor ou cliente confiável. Nesse contexto, o SSL (protocolo SSL), conforme utilizado com serviços Web, pode ser associado ao protocolo baseado em TLS.

Conexões de servidor para servidor dependem do MTLS (TLS mútuo) para autenticação mútua. Em uma conexão do MTLS, o servidor que cria a mensagem e o servidor que a recebe trocam certificados mutuamente a partir de uma CA confiável. Os certificados comprovam a identidade de cada servidor entre si. No serviço do SfBO, este procedimento é seguido.

TLS e MTLS ajudam a evitar a espionagem e os ataques a intermediários. Em um ataque a intermediários, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor, sem o conhecimento das partes. A especificação de servidores confiáveis da TSL e do SfBO diminuem parcialmente o risco de um ataque a intermediários na camada do aplicativo utilizando uma criptografia de ponta a ponta juntamente com a criptografia de chave pública entre dois pontos de extremidade. Assim, um invasor deve ter um certificado válido e confiável com a chave particular correspondente e emitido em nome do serviço com o qual o cliente esteja se comunicando para descriptografar a comunicação. 

#### <a name="encryption-for-sfbo"></a>Criptografia para SfBO
O SfBO utiliza TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor necessita do MTLS, não importa se o tráfego esteja restrito à rede interna ou se ultrapasse seu perímetro.

A tabela a seguir resume o protocolo usado pelo SfBO.

***Tabela 3 – Proteção de tráfego***

<!--start table here no header -->

|||
|:-----|:-----|:-----|
|**Tipo de tráfego**|**Protegido por**|
|Servidor para servidor|MTLS |
|Cliente para Servidor|TLS|
|Chat e presença|TLS (se configurado para TLS)|
|Compartilhamento de mídia de áudio, vídeo e de área de trabalho|SRTP|
|Compartilhamento de área de trabalho (sinalização)|TLS|
|Webconferência|TLS|
|Download de conteúdo de reunião, download do catálogo de endereços, expansão de grupo de distribuição|HTTPS|
|||

<!-- end of table -->

### <a name="media-encryption"></a>Criptografia de mídia
O tráfego de mídia é criptografado usando SRTP (Secure RTP), um perfil do protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataques de repetição para o tráfego RTP. SRTP usa uma chave da sessão gerada por meio de um gerador de número aleatório seguro e trocada por meio do canal TLS de sinalização. Além disso, a mídia que flui em ambas as direções entre o Servidor de Mediação e seu próximo salto interno também é criptografada usando SRTP. 

O SfBO gera nome de usuário/senhas para acesso seguro a retransmissões de mídia no TURN. As retransmissões de mídia trocam o nome de usuário/senha em um canal SIP protegido por TLS.


### <a name="fips"></a>FIPS
O SfBO usa algoritmos compatíveis com FIPS (Federal Information Processing Standard) para trocas de chave de criptografia. Autenticação do usuário e do cliente 

Um usuário confiável é aquele cujas credenciais foram autenticadas pelo AAD no O365. 

Autenticação é o provisionamento de credenciais do usuário a um servidor ou  serviço confiável. O SfBO usa os protocolos de autenticação a seguir, dependendo do status e da localização do usuário.
- **Autenticação moderna** é a implementação da Microsoft do OAUTH 2.0 para comunicação de cliente para servidor. Ela ativa recursos de segurança como a Autenticação baseada em certificado do O365, Autenticação multifator do O365 e Acesso condicional do O365.  Para usar a MA, o locatário online e os clientes precisam estar habilitados para isso.  Os locatários do SfBO criados após maio de 2017 têm o MA ativado por padrão.  Para locatários criados antes disso, siga as instruções apresentadas aqui para ativá-la.  Todos os clientes a seguir oferecem suporte à MA: cliente Skype for Business 2015 ou 2016, Skype for Business no Mac, cliente Lync 2013, 3PIP IP Phones, iOS e Android. 
- **ID da organização** é usada quando a autenticação moderna não está habilitada (ou não está disponível)
- **Protocolo Digest** para os chamados usuários anônimos. Usuários anônimos são usuários externos que não possuem credenciais reconhecidas do Active Directory, mas que foram convidados para uma conferência no local e possuem uma chave de conferência válida. A autenticação Digest não é usada para nenhuma outra interação do cliente.

A autenticação do SfBO consiste em duas fases:
1. Uma associação de segurança é estabelecida entre o cliente e o servidor.
2. O cliente e o servidor usam a associação de segurança existente para assinar mensagens enviadas e para verificar as mensagens recebidas. Mensagens não autenticadas de um cliente não são aceitas quando uma autenticação está habilitada no servidor.

Uma relação de confiança do usuário é anexada a cada mensagem originária de um usuário, não à identidade do usuário em si. O servidor verifica se há credenciais do usuário válidas em cada mensagem. Se as credenciais do usuário forem válidas, a mensagem não será contestada pelo primeiro servidor que a receber nem por nenhum outro servidor no SfBO.

Usuários com credenciais válidas emitidas por um parceiro federado são confiáveis, porém são opcionalmente impedidos por restrições adicionais de aproveitar toda a gama de privilégios concedidos aos usuários internos.

Para a autenticação de mídia, os protocolos ICE e TURN também utilizam o desafio do Digest conforme descrito no IETF TURN RFC. Para detalhes, veja [[travessia de mídia](#rtp-replay-attack)](#external-user-av-traffic-traversal).

Os certificados do cliente proporcionam um caminho alternativo para que os usuários sejam autenticados pelo SfBO. Em vez de fornecer um nome de usuário e senha, os usuários possuem um certificado e a chave privada correspondente ao certificado exigida para resolver um desafio criptográfico. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Ferramentas de gerenciamento do Windows PowerShell e SfBO
No SfBO, os administradores de TI podem gerenciar seus serviços por meio do Portal de administração do O365 ou usando o TRPS (Tenant Remote PowerShell).  Os administradores do locatário usam a Autenticação moderna para autenticar para o TRPS.

Para configurar o acesso ao SfBO em seu limite de Internet para que o SfBO funcione adequadamente (usuários capazes de participar de reuniões, etc.), os clientes precisam configurar o acesso à Internet deles de modo que seja permitido o tráfego UDP e TCP de saída para serviços na nuvem do SfBO.  Para obter mais detalhes, consulte aqui: https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 


### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 e TCP 443

As portas UDP 3478-3481 e TCP 443 são usadas pelos clientes para solicitar o serviço de Borda A/V. Um cliente usa essas duas portas para atribuir as portas UDP e TCP, respectivamente, para que a parte remota se conecte. Para acessar o serviço de Borda A/V, o cliente deve primeiro ter estabelecido uma sessão de sinalização SIP autenticada com o registrador SFBO para obter as credenciais de autenticação do serviço de Borda A/V. Esses valores são enviados pelo canal de sinalização protegido por TLS e são gerados por computador para atenuar os ataques de dicionário. Os clientes podem, então, usar essas credenciais para a autenticação Digest com o serviço de Borda A/V para atribuir portas para uso em uma sessão de mídia. Uma solicitação inicial de atribuição é enviada pelo cliente e respondida com uma mensagem 401 nonce/desafio do serviço de Borda A/V. O cliente envia uma segunda atribuição contendo o nome de usuário e um hash HMAC (Código de Autenticação de Mensagem com Hash) do nome de usuário e nonce. 

Um mecanismo de número sequencial também é usado para evitar ataques de reprodução. O servidor calcula o HMAC esperado com base em seu próprio conhecimento do nome de usuário e senha. Se os valores do HMAC forem correspondentes, o procedimento de atribuição será executado. Caso contrário, o pacote será descartado. Esse mesmo mecanismo do HMAC também é aplicado às mensagens seguintes nessa sessão de chamada. O tempo de vida desse valor de nome de usuário/senha é de no máximo oito horas, período em que o cliente adquire um novo nome de usuário/senha para as chamadas seguintes.

### <a name="udptcp-50000-59999"></a>UDP/TCP 50.000–59.999
O TCP 50.000 de saída é usado no SfBO, inclusive para compartilhamento de aplicativos e de área de trabalho, além de transferência de arquivos. Os intervalos das portas UDP/TCP de 50.000 a 59.999 são usados ​​para sessões de mídia com parceiros do Microsoft Office Communications Server 2007 que exigem o serviço NAT/firewall transversal do serviço de Borda A/V. Como o serviço de Borda A/V é o único processo que usa essas portas, o tamanho do intervalo das portas não indica uma possível ocorrência de ataque. Uma boa prática de segurança é sempre minimizar o número total de portas ouvintes por meio da não execução de serviços de rede desnecessários. Um serviço de rede que não está em execução não é explorável por um invasor remoto e a possibilidade de ataques ao computador host é reduzida. No entanto, dentro de um único serviço, a redução do número de portas não oferece o mesmo benefício. A exposição do software de serviço de Borda A/V a ataques é a mesma com 10.000 ou 10 portas abertas. A atribuição de portas nesse intervalo é feita aleatoriamente e as portas não atribuídas atualmente não escutam pacotes.
 
### <a name="external-user-av-traffic-traversal"></a>Passagem de tráfego A/V do usuário externo
A habilitação de usuários externos e internos para troca de mídia requer um serviço de Borda de Acesso para lidar com a sinalização SIP necessária para configurar e desativar uma sessão. Isso também requer um serviço de Borda A/V para atuar como um retransmissor para a transferência da mídia. A sequência de chamadas é ilustrada na figura a seguir.

![Sequência de chamadas em Ingresso na Reunião](../images/sfbo-call-sequence-security.png)


    1. Um usuário recebe um email contendo um convite para ingressar em uma reunião no SfBO. O email contém uma chave de conferência e um URL baseado em HTTP vinculado à conferência. Tanto a chave quanto o URL são exclusivos de uma reunião específica.

    O usuário inicia o procedimento de ingresso clicando no URL da reunião presente no email, que inicia um processo de detecção do cliente no computador do usuário.  Se o cliente é detectado, ele é inicializado.  Se não é detectado, ele é redirecionado para o cliente Web.
    2. O cliente do SfBO envia uma SIP INVITE contendo as credenciais do usuário. Um usuário federado ou remoto ingressa em uma conferência usando suas credenciais corporativas. Para um usuário federado, a SIP INVITE é enviada primeiramente para o servidor doméstico, que autentica o usuário e encaminha a INVITE para o SfBO. Um usuário anônimo é obrigado a passar pela autenticação Digest. 

    O SfBO autentica o usuário remoto ou anônimo e notifica o cliente. Conforme mencionado na etapa 2, os usuários federados que ingressam em uma conferência são autenticados pela empresa deles.

    3. O cliente envia uma solicitação INFO para adicionar o usuário à conferência A/V.

    A conferência A/V envia a resposta Adicionar Usuário que contém o token a ser apresentado ao serviço de Borda de Conferência A/V, além de outras informações.

    [Nota] Todo o tráfego SIP anterior fluiu pelo serviço de Borda de Acesso.

    O cliente se conecta ao Servidor de Conferência A/V, que valida o token e envia o proxy da solicitação. Este contém outro token de autorização para o Servidor de Conferência A/V interno. O Servidor de Conferência A/V valida o token de autorização, originalmente emitido por ele no canal SIP, para assegurar que um usuário válido ingresse na conferência.
    
    4. Entre o cliente e o servidor de conferência AV, uma conexão de mídia é negociada e configurada por SRTP.

### <a name="federation-safeguards-for-sfbo"></a>Proteções da federação para o SfBO
A federação fornece à sua organização a capacidade de se comunicar com outras organizações para compartilhar chat e presença. No SfBO, a federação está ativada por padrão.  No entanto, os administradores do locatário têm a capacidade de controlar isso por meio do portal do Administrador do O365.  Veja mais.

## <a name="addressing-threats-to-sfbo-conferences"></a>Como enfrentar ameaças às conferências do SfBO

O SfBO oferece a usuários corporativos a capacidade de criar e ingressar em conferências Web em tempo real. Usuários corporativos também podem convidar usuários externos que não tenham uma conta AAD/O365 para participar dessas reuniões. Usuários empregados por parceiros federados com uma identidade segura e autenticada também podem ingressar em reuniões e podem atuar como apresentadores se forem promovidos para tal atividade. Usuários anônimos não podem criar ou ingressar em uma reunião como apresentadores, mas podem ser promovidos a apresentadores após o ingresso.

A permissão para que usuários externos participem de reuniões no SfBO aumenta muito o valor desse recurso, mas também envolve alguns riscos de segurança. Para lidar com esses riscos, o SfBO oferece as seguintes proteções adicionais:
- As funções do participante determinam privilégios de controle de conferência.
- Os tipos de participantes permitem que você limite o acesso a reuniões específicas.
- Os tipos de reuniões definidos determinam quais tipos de participantes podem ingressar.
- O agendamento das conferências é restrito aos usuários que possuem uma conta AAD e uma licença do SfBO.
- Usuários anônimos, ou seja, não autenticados, que desejem ingressar em uma conferência por telefone discam um dos números de acesso à conferência e, em seguida, são solicitados a inserir a ID da conferência. Usuários anônimos não autenticados também devem registrar seus nomes. O nome gravado identifica os usuários não autenticados na conferência. Os usuários anônimos não são admitidos na conferência até que pelo menos um líder ou usuário autenticado ingresse e não é possível atribuir uma função predefinida.

#### <a name="participant-roles"></a>Funções do participante
Os participantes da reunião dividem-se em três grupos, cada um com seus próprios privilégios e restrições:
- **Organizador** &nbsp;&nbsp; O usuário que cria uma reunião, seja imediatamente seja por agendamento. Um organizador deve ser um usuário corporativo autenticado e ter controle sobre todos os aspectos do usuário final de uma reunião.
- **Apresentador** &nbsp;&nbsp; Um usuário que está autorizado a apresentar informações em uma reunião, usando qualquer mídia suportada. O organizador da reunião, por definição, também é um apresentador e determina quem mais pode ser um apresentador. O organizador pode determinar isso ao agendar uma reunião ou com a reunião já em andamento.
- **Participante** &nbsp;&nbsp; Um usuário que foi convidado a participar de uma reunião, mas não está autorizado a atuar como apresentador.

Um apresentador também pode promover um participante ao papel de apresentador durante a reunião.

#### <a name="participant-types"></a>Tipos de participantes

Os participantes da reunião também são categorizados por local e por credenciais. Você pode usar essas duas características para especificar quais usuários podem ter acesso a reuniões específicas. Os usuários podem ser divididos amplamente nas seguintes categorias:
1.  **Usuários que pertencem ao locatário** &nbsp;&nbsp; Esses usuários têm uma credencial no Active Directory do Azure para o locatário.
    a. Dentro da rede corporativa – Esses usuários ingressam de dentro da rede corporativa.
    b.  Usuários remotos – Esses usuários ingressam de fora da rede corporativa. Podem ser funcionários que estão trabalhando em casa ou em trânsito, entre outros, como funcionários de fornecedores confiáveis que receberam credenciais corporativas em seus termos de serviço. Usuários remotos podem criar e ingressar em conferências, além de atuar como apresentadores.
2.  **Usuários que não pertencem ao locatário**&nbsp;&nbsp;Esses usuários não têm credenciais no Active Directory do Azure para o locatário.
    a.  Usuários federados – Apresentam credenciais válidas com parceiros federados e, portanto, são tratados como autenticados pelo SFBO. Os usuários federados podem ingressar em conferências e ser promovidos a apresentadores depois de ingressarem na reunião, mas não podem criar conferências em empresas com as quais são federados.
    b.  Usuários anônimos – Não têm uma identidade do Active Directory e não são federados com o locatário. 

Dados do cliente mostram que muitas conferências envolvem usuários externos. Esses mesmos clientes também querem garantias sobre a identidade de usuários externos antes de permitir que ingressem em uma conferência. Como a seção a seguir descreve, o SfBO limita o acesso à reunião aos tipos de usuários cuja permissão foi explícita e exige que todos os tipos de usuários apresentem as credenciais apropriadas ao entrarem em uma reunião.

#### <a name="participant-admittance"></a>Admissão do participante
No SfBO, os usuários anônimos são transferidos para uma área de espera chamada lobby. Os apresentadores podem, então, permitir ou rejeitar a participação desses usuários na reunião. Esses usuários são transferidos para o lobby, o líder é notificado e os usuários esperam até que um líder os aceite ou rejeite ou até que a conexão expire. Enquanto estão no lobby, os usuários ouvem música. 

Por padrão, os participantes cujas chamadas vêm do PSTN vão diretamente para a reunião, mas essa opção pode ser alterada para forçar os participantes de discagem a irem para o lobby.  
Os organizadores da reunião controlam se os participantes podem ingressar em uma reunião sem esperar no lobby. Cada reunião pode ser configurada para habilitar o acesso por meio de qualquer um dos métodos a seguir:
- **Apenas eu, o organizador da reunião**&nbsp;&nbsp;Todos, exceto o organizador, devem esperar no lobby até serem admitidos.
- **Pessoas que eu convido da minha empresa**&nbsp;&nbsp;Qualquer pessoa da sua empresa pode entrar diretamente na reunião, mesmo que não seja convidada.
- **Qualquer pessoa da minha organização**&nbsp;&nbsp;Todos os usuários do SfBO no locatário do O365 podem ingressar na reunião sem esperar no lobby, mesmo aqueles que não estejam na lista de distribuição. Todos os outros, incluindo todos os usuários externos e anônimos, devem aguardar no lobby até serem admitidos.
- **Todos**&nbsp;&nbsp;Todas as pessoas (sem restrições) que tenham acesso ao link da reunião podem entrar diretamente.
Quando qualquer método, exceto Apenas o organizador (bloqueado), for especificado, o organizador da reunião também poderá especificar que Pessoas chamando por telefone não precisam ficar no lobby. 

#### <a name="presenter-capabilities"></a>Recursos do apresentador
Os organizadores da reunião controlam se os participantes podem fazer apresentações durante uma reunião. Cada reunião pode ser configurada para limitar os apresentadores de acordo com as seguintes opções:
- **Somente o organizador**&nbsp;&nbsp; Apenas o organizador da reunião pode fazer apresentações.
- **Pessoas da minha empresa**&nbsp;&nbsp; Todos os usuários internos podem fazer apresentações.
- **Todos incluindo pessoas fora da minha empresa**&nbsp;&nbsp; Todos (não há restrições) que ingressam na reunião podem fazer apresentações.
- **Pessoas escolhidas**&nbsp;&nbsp;O organizador da reunião especifica quais usuários podem fazer apresentações, adicionando-os a uma lista de apresentadores.

<!-- need some link? 

## Related topics

-->