---
title: Planejar o Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Saiba como o Roteamento Direto do Microsoft Phone System permite conectar um SBC (Controlador de Borda de Sessão) fornecido pelo cliente ao Microsoft Phone System.
ms.openlocfilehash: 77757cf76215dbed0b3ec572b5f1f57120551d86
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923823"
---
# <a name="plan-direct-routing"></a>Planejar o Roteamento Direto

> [!Tip]
> Assista à sessão a seguir para saber mais sobre os benefícios do Roteamento [Direto,](https://aka.ms/teams-direct-routing) como planejar e como implantá-lo: Roteamento Direto no Microsoft Teams

O Roteamento Direto do Sistema De Telefonia do Microsoft Phone permite conectar um SBC (Controlador de Borda de Sessão) fornecido pelo cliente ao Microsoft Phone System.  Com esse recurso, por exemplo, você pode configurar a conectividade PSTN (Rede Telefônica Pública Comutada) local com o cliente do Microsoft Teams, conforme mostrado no diagrama a seguir: 

![Diagrama mostrando a configuração da conectividade PSTN local](media/PlanDirectRouting1-PSTNwithTeams.png "Configuração de conectividade PSTN local com o cliente do Microsoft Teams")

  > [!NOTE]
  > O Skype for Business Online também permite emparelhar um SBC fornecido pelo cliente, mas isso requer uma implantação local do Skype for Business Server ou uma edição especial do Skype for Business, chamada Cloud Connector, entre o SBC e o Microsoft Cloud. Esse cenário é conhecido como voz híbrida. Por outro lado, o Roteamento Direto permite uma conexão direta entre o SBC com suporte e o Microsoft Cloud.

> [!Important]
> A Cloud Connector Edition se desposente em 31 de julho de 2021 juntamente com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [o Roteamento Direto.](direct-routing-landing-page.md) 

Com o Roteamento Direto, você pode conectar seu SBC a quase qualquer tronco de telefonia ou interconectar-se com equipamento PSTN de terceiros. O Roteamento Direto permite que você: 

- Use praticamente qualquer tronco PSTN com o Microsoft Phone System. 
- Configure a interoperabilidade entre o equipamento de telefonia de propriedade do cliente, como um PBX (troca de ramificação privada de terceiros), dispositivos analógicos e o Microsoft Phone System.

A Microsoft também oferece soluções de voz na nuvem, como Plano de Chamada. No entanto, uma solução de voz híbrida pode ser melhor para sua organização se: 

- O Plano de Chamada da Microsoft não está disponível em seu país/região. 
- Sua organização requer conexão com dispositivos analógicos de terceiros, call centers e assim por diante. 
- Sua organização tem um contrato existente com uma operadora PSTN.

O Roteamento Direto também dá suporte aos usuários que têm a licença adicional para o Plano de Chamada da Microsoft. Para obter mais informações, consulte [o Sistema de Telefonia e os Planos de Chamada.](calling-plan-landing-page.md) 

Com o Roteamento Direto, quando os usuários participam de uma conferência agendada, o número de discagem é fornecido pelo serviço de Audioconferência da Microsoft, que exige o licenciamento adequado.  Ao discar, o serviço de Audioconferência da Microsoft coloca a chamada usando recursos de chamada online, o que exige o licenciamento adequado. (Observe que se um usuário não tiver uma licença de Audioconferência da Microsoft, as chamadas passarão pelo Roteamento Direto.) Para obter mais informações, consulte [Reuniões Online com o Teams.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
Planejar sua implantação do Roteamento Direto é fundamental para uma implementação bem-sucedida. Este artigo descreve os requisitos de infraestrutura e licenciamento e fornece informações sobre conectividade SBC: 

- [Requisitos de infraestrutura](#infrastructure-requirements)
- [Licenciamento e outros requisitos](#licensing-and-other-requirements)
- [Nomes de domínio SBC](#sbc-domain-names)
- [Certificado público confiável para o SBC](#public-trusted-certificate-for-the-sbc)
- [Sinalização SIP: FQDNs](#sip-signaling-fqdns)
- [Sinalização SIP: Portas](#sip-signaling-ports)
- [Tráfego de mídia: Intervalos de portas](#media-traffic-port-ranges)
- [SBCs (Controladores de Borda de Sessão) com suporte](#supported-session-border-controllers-sbcs)

Para obter informações detalhadas sobre como configurar o Roteamento Direto, consulte [Configurar Roteamento Direto.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
Os requisitos de infraestrutura para os SBCs, domínios e outros requisitos de conectividade de rede para implantar o Roteamento Direto estão listados na tabela a seguir:  

|Requisito de infraestrutura|Você precisa do seguinte|
|:--- |:--- |
|Controlador de Borda de Sessão (SBC)|Um SBC com suporte. Para obter mais informações, consulte [SBCs com suporte.](#supported-session-border-controllers-sbcs)|
|Troncos de telefonia conectados ao SBC|Um ou mais troncos de telefonia conectados ao SBC. Em uma extremidade, o SBC conecta-se ao Sistema Telefônico Microsoft por meio de Roteamento Direto. O SBC também pode se conectar a entidades de telefonia de terceiros, como PBXs, Adaptadores de Telefonia Analógica e assim por diante. Qualquer opção de conectividade PSTN conectada ao SBC funcionará. (Para configuração dos troncos PSTN para o SBC, consulte os fornecedores SBC ou provedores de tronco.)|
|Microsoft 365 ou organização do Office 365|Uma organização do Microsoft 365 ou do Office 365 que você usa para seus usuários do Microsoft Teams e a configuração e a conexão com o SBC.|
|Registrador de usuários|O usuário deve estar no Microsoft 365 ou no Office 365.<br/>Se sua empresa tiver um ambiente local do Skype for Business ou do Lync com conectividade híbrida com o Microsoft 365 ou o Office 365, você não poderá habilitar a voz no Teams para um usuário instalado no local.<br/><br/>Para verificar o registrador de um usuário, use o seguinte cmdlet do PowerShell do Skype for Business Online:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>A saída do cmdlet deve mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domínios|Um ou mais domínios adicionados às suas organizações do Microsoft 365 ou office 365.<br/><br/>Observe que você não pode usar o domínio padrão, \* .onmicrosoft.com, que é criado automaticamente para seu locatário.<br/><br/>Para exibir os domínios, você pode usar o seguinte cmdlet do PowerShell do Skype for Business Online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obter mais informações sobre domínios e organizações do Microsoft 365 ou do Office 365, consulte [Perguntas frequentes sobre Domínios.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Endereço IP público do SBC|Um endereço IP público que pode ser usado para se conectar ao SBC. Com base no tipo de SBC, o SBC pode usar NAT.|
|FQDN (Nome de Domínio Totalmente Qualificado) para o SBC|Um FQDN para o SBC, onde a parte de domínio do FQDN é um dos domínios registrados em sua organização do Microsoft 365 ou do Office 365. Para obter mais informações, consulte [os nomes de domínio SBC.](#sbc-domain-names)|
|Entrada DNS pública para o SBC |Uma entrada DNS pública mapeando o FQDN SBC para o Endereço IP público. |
|Certificado público confiável para o SBC |Um certificado para que o SBC seja usado para toda a comunicação com o Roteamento Direto. Para obter mais informações, consulte [Certificado confiável público para o SBC.](#public-trusted-certificate-for-the-sbc)|
|Pontos de conexão para Roteamento Direto |Os pontos de conexão para Roteamento Direto são os três FQDNs a seguir:<br/><br/>`sip.pstnhub.microsoft.com` – O FQDN global deve ser tentado primeiro.<br/>`sip2.pstnhub.microsoft.com` – FQDN secundário, mapeia geograficamente a região de segunda prioridade.<br/>`sip3.pstnhub.microsoft.com` – FQDN terciário, mapeia geograficamente a região de terceira prioridade.<br/><br/>Para obter informações sobre requisitos de configuração, consulte [Sinalização SIP: FQDNs.](#sip-signaling-fqdns)|
|Endereços IP de firewall e portas para mídia de Roteamento Direto |O SBC se comunica aos seguintes serviços na nuvem:<br/><br/>Proxy SIP, que lida com a sinalização<br/>Processador de Mídia, que lida com mídia , exceto quando o Bypass de Mídia está em<br/><br/>Esses dois serviços têm endereços IP separados no Microsoft Cloud, descritos posteriormente neste documento.<br/><br/>Para obter mais informações, consulte a seção [do Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) em [URLs e intervalos de endereços IP.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|Perfil de Transporte de Mídia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Endereços IP de firewall e portas para mídia do Microsoft Teams |Para obter mais informações, consulte [URLs e intervalos de endereços IP.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>Licenciamento e outros requisitos 

Os usuários do Roteamento Direto devem ter as seguintes licenças atribuídas no Microsoft 365 ou no Office 365: 

- Microsoft Phone System. 
- Microsoft Teams + Skype for Business Plano 2, se incluído no licenciamento.
- Audioconferência da Microsoft (leia as anotações e o parágrafo abaixo para ver exemplos específicos sobre quando a licença é necessária).

> [!NOTE]
> O Plano Skype for Business não deve ser removido de qualquer contrato de licenciamento no qual ele está incluído. 


> [!IMPORTANT]
>  Caso você gostaria de adicionar participantes externos a reuniões agendadas, discando para eles ou fornecendo o número de discagem, a licença de audioconferência é necessária.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Licença de escalação de chamada e audioconferência ad hoc

Um usuário do Teams pode iniciar uma chamada entre duas equipes para PSTN ou Teams ao Teams e adicionar um participante PSTN a ele. Esse cenário é chamado de conferência ad hoc. O caminho que a chamada leva depende se o usuário que escalona a chamada tem uma licença de Audioconferência da Microsoft atribuída ou não:

- Se o usuário do Teams que escalona a chamada tiver uma licença de Audioconferência da Microsoft atribuída, a escalação acontecerá por meio do serviço de Audioconferência da Microsoft. O participante PSTN remoto que é convidado para a chamada existente recebe uma notificação sobre a chamada recebida e vê o número da ponte da Microsoft atribuída ao usuário do Teams que iniciou a escalação.
- Se o usuário do Teams que escala a chamada não tiver a licença de AudioConferência da Microsoft atribuída, a escalação acontecerá por meio de um Controlador de Borda de Sessão conectado à interface de Roteamento Direto. O participante PSTN remoto que é convidado para a chamada recebe uma notificação sobre a chamada recebida e vê o número do usuário do Teams que iniciou a escalação. O SBC específico usado para a escalação é definido pela Política de Roteamento do usuário. 


Além disso, você deve garantir o seguinte:
 
- O CsOnlineVoiceRoutingPolicy é atribuído ao usuário. 
- Permitir Chamada Privada está habilitado no nível do locatário do Microsoft Teams. 

O Roteamento Direto também dá suporte a usuários licenciados para o Plano de Chamada da Microsoft. O Microsoft Phone System com Plano de Chamada pode rotear algumas chamadas usando a interface de Roteamento Direto. No entanto, os números de telefone dos usuários devem ser adquiridos online ou portados para a Microsoft.  

Misturar a conectividade de Plano de Chamada e Roteamento Direto para o mesmo usuário é opcional, mas pode ser útil (por exemplo, quando o usuário recebe um Plano de Chamada da Microsoft, mas deseja rotear algumas chamadas usando o SBC). Um dos cenários mais comuns é as chamadas para PBXs de terceiros.  Com PBXs de terceiros, todas as chamadas, exceto chamadas para os telefones conectados a esse PBXs, são roteados usando o Plano de Chamada da Microsoft, mas as chamadas para os telefones conectados a PBXs de terceiros vão para o SBC e, portanto, permanecem dentro da rede corporativa e não do PSTN. 

Para obter mais informações sobre licenciamento do Sistema de [Telefonia,](https://products.office.com/compare-all-microsoft-office-products?tab=2) consulte Obter o máximo das Opções do Office [e do Plano.](https://technet.microsoft.com/library/office-365-plan-options.aspx) 

Para obter mais informações sobre licenciamento do Sistema de Telefonia, consulte o licenciamento [de complementos do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 

## <a name="supported-end-points"></a>Pontos de extremidade com suporte 

Você pode usar como ponto de extremidade:

- Qualquer cliente do Teams. 
- Telefones de área comuns. Consulte [Configurar a licença de Telefone de Área Comum do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones) Observe que você não precisa de uma licença do Plano de Chamada ao configurar um Telefone de Área Comum com Roteamento Direto.
- Telefones 3PIP do Skype for Business. Consulte [o suporte para telefones Skype for Business (3PIP) com o Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nomes de domínio SBC

O nome de domínio SBC deve ser de um dos nomes registrados em Domínios do locatário. Você não pode usar o \* locatário .onmicrosoft.com para o nome FQDN do SBC.

A tabela a seguir mostra exemplos de nomes DNS registrados para o locatário, se o nome pode ser usado como FQDN para o SBC e exemplos de nomes FQDN válidos:

|Nome DNS|Pode ser usado para FQDN SBC|Exemplos de nomes FQDN|
|:--- |:--- |:--- |
contoso.com|Sim|**Nomes válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Não|Não há suporte para onmicrosoft.com domínios *.onmicrosoft.com para nomes SBC

Suponha que você queira usar um novo nome de domínio. Por exemplo, seu locatário contoso.com como um nome de domínio registrado em seu locatário e você deseja usar sbc1.sip.contoso.com. Antes de poder emparelhar um SBC com o nome sbc1.sip.contoso.com, você deve registrar o nome de domínio sip.contoso.com em Domínios em seu locatário. Se você tentar emparelhar um SBC com o sbc1.sip.contoso.com antes de registrar o nome de domínio, receberá o seguinte erro: "Não é possível usar o domínio "sbc1.sip.contoso.com" porque ele não foi configurado para este locatário".
Depois de adicionar o nome de domínio, você também precisa criar um usuário com upn user@sip.contoso.com e atribuir uma licença do Teams. Pode levar até 24 horas para provisionar totalmente o nome de domínio depois que ele é adicionado aos Domínios do seu locatário, um usuário com um novo nome é criado e uma licença é atribuída ao usuário. 

É possível que uma empresa tenha vários espaços de endereço SIP em um locatário. Por exemplo, uma empresa pode ter contoso.com como um espaço de endereço SIP e fabrikam.com como o segundo espaço de endereço SIP. Alguns usuários têm endereço user@contoso.com e alguns têm endereço user@fabrikam.com. 

O SBC só precisa de um FQDN e pode atender os usuários de qualquer espaço de endereço no locatário emparelhado. Por exemplo, um SBC com o nome sbc1.contoso.com pode receber e enviar o tráfego PSTN para usuários com endereços user@contoso.com e user@fabrikam.com desde que esses espaços de endereço SIP sejam registrados no mesmo locatário.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado público confiável para o SBC

A Microsoft recomenda que você solicite o certificado para o SBC gerando uma solicitação de assinatura de certificação (CSR). Para obter instruções específicas sobre como gerar uma CSR para um SBC, consulte as instruções de interconexão ou a documentação fornecida por seus fornecedores SBC. 

  > [!NOTE]
  > A maioria das Autoridades de Certificação (CAs) exige que o tamanho da chave privada seja pelo menos 2048. Lembre-se disso ao gerar a CSR.

O certificado precisa ter o FQDN SBC como o nome comum (CN) ou o campo san (nome alternativo do assunto). O certificado deve ser emitido diretamente de uma autoridade de certificação, não de um provedor intermediário.

Como alternativa, o Roteamento Direto dá suporte a um caractere curinga no CN e/ou SAN, e o caractere curinga precisa estar em conformidade com o [padrão RFC HTTP sobre TLS.](https://tools.ietf.org/html/rfc2818#section-3.1) Um exemplo seria usar .contoso.com que corresponderia ao \* FQDN SBC sbc.contoso.com, mas não corresponderia ao sbc.test.contoso.com.

O certificado precisa ser gerado por uma das seguintes autoridades de certificação raiz:

- ResstruçãoDaTrust
- AddTrust External CA Root
- Raiz cybertrust de CyberTrust*
- Buypass
- Cybertrust
- Autoridade de Certificação Pública Primária de Classe 3
- Comodo Secure Root CA
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- Confiar
- GlobalSign
- Go Daddy
- Geotrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Raiz móvel da Symantec Enterprise para Microsoft 
- SwissSign
- Ca Descongelar Data/Hora
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Para Roteamento Direto nos ambientes GCCH e DoD do Office 365, o certificado precisa ser gerado por uma das seguintes autoridades de certificação raiz:
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *Se o suporte a MTLS (Mutual TLS) estiver habilitado para a conexão do Teams no SBC, você deverá instalar o Certificado Raiz CyberTrust de CyberTrust do SBC no Armazenamento Raiz Confiável SBC do contexto TLS do Teams. (Isso porque os certificados de serviço da Microsoft usam o certificado raiz de Baltimore.) Para baixar o certificado raiz de Baltimore, consulte as cadeias de [criptografia do Office 365.](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)

A Microsoft está trabalhando para adicionar mais autoridades de certificação com base em solicitações de clientes. 

## <a name="sip-signaling-fqdns"></a>Sinalização SIP: FQDNs 

O Roteamento Direto é oferecido nos seguintes ambientes:
- Microsoft 365 ou Office 365
- Cc do Office 365
- Office 365 GCC High
- Office 365 DoD

Saiba mais sobre [ambientes do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) e do Governo dos EUA, como GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambientes do Microsoft 365, Office 365 e Office 365 GCC

Os pontos de conexão para Roteamento Direto são os três FQDNs a seguir:

- **sip.pstnhub.microsoft.com** – FQDN Global – deve ser tentado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS do Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC. A atribuição se baseia nas métricas de desempenho dos datacenters e da proximidade geográfica do SBC. O endereço IP retornado corresponde ao FQDN principal.
- **sip2.pstnhub.microsoft.com** – FQDN Secundário – mapeia geograficamente a região de segunda prioridade.
- **sip3.pstnhub.microsoft.com** – FQDN terciário – mapeia geograficamente a região de terceira prioridade.

É necessário colocar esses três FQDNs em ordem para:

- Forneça uma experiência ideal (menos carregada e mais próxima do datacenter SBC atribuído consultando o primeiro FQDN).
- Forneça failover quando a conexão de um SBC for estabelecida com um datacenter que esteja enfrentando um problema temporário. Para obter mais informações, consulte o [mecanismo failover](#failover-mechanism-for-sip-signaling) abaixo.  

Os FQDNs ( sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com – serão resolvidos para um dos seguintes endereços IP:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.  Se o firewall for compatível com  nomes DNS, a sip-all.pstnhub.microsoft.com FQDN será resolvida para todos esses endereços IP. 

> [!IMPORTANT]
>  Como parte da expansão do Roteamento Direto do Teams e melhoria do serviço, implantamos novas instâncias de infraestrutura de Roteamento Direto na Austrália. Isso se reflete em dois endereços IP adicionais (52.114.16.74 e 52.114.20.29) para os quais os seguintes FQDNs serão resolvidos para clientes australianos – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com. Você precisa adicionar esses dois endereços IP (52.114.16.74 e 52.114.20.29) às suas LISTAS de Controle de Acesso IP (ACLs) e abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-365-gcch-and-dod-environment"></a>Ambiente GCCH e DoD do Office 365

O ponto de conexão do Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – FQDN global. Como o ambiente do Office 365 DoD existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O FQDN sip.pstnhub.dod.teams.microsoft.us será resolvido em um dos seguintes endereços IP:

- 52.127.64.33
- 52.127.68.34

Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-365-gcc-high-environment"></a>Ambiente do Office 365 GCC High

O ponto de conexão do Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – FQDN global. Como o ambiente GCC High existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O FQDN sip.pstnhub.gov.teams.microsoft.us será resolvido em um dos seguintes endereços IP:

- 52.127.88.59
- 52.127.92.64

Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização. Se o firewall for compatível com  nomes DNS, a sip-all.pstnhub.gov.teams.microsoft.us FQDN será resolvida para todos esses endereços IP. Esse FQDN também pode ser usado como FQDN Federado para classificação de chamada de entrada.

## <a name="sip-signaling-ports"></a>Sinalização SIP: Portas

Você deve usar as seguintes portas para ambientes do Microsoft 365 ou office 365 nos quais o Roteamento Direto é oferecido:
- Microsoft 365 ou Office 365
- Cc do Office 365
- Office 365 GCC High
- Office 365 DoD

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|Sbc|1024 – 65535|Definido no SBC (para o Office 365 GCC High/DoD apenas a porta 5061 deve ser usada)|
SIP/TLS|Sbc|SIP Proxy|Definido no SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de failover para Sinalização SIP

O SBC faz uma consulta DNS para resolver sip.pstnhub.microsoft.com. Com base no local SBC e nas métricas de desempenho do datacenter, o datacenter principal é selecionado. Se o datacenter principal tiver um problema, o SBC tentará o sip2.pstnhub.microsoft.com, que é resolvido para o segundo datacenter atribuído e, no caso raro em que os datacenters em duas regiões não estão disponíveis, o SBC recupera o último FQDN (sip3.pstnhub.microsoft.com), que fornece o IP do datacenter terciário.

A tabela a seguir resume as relações entre datacenters primários, secundários e terciários:

|Se o datacenter principal for|EMEA|Noam|Ásia|
|:--- |:--- |:--- |:--- |
|O datacenter secundário (sip2.pstnhub.microsoft.com)|Nos|Ue|Nos|
|O datacenter terciário (sip3.pstnhub.microsoft.com)|Ásia|Ásia|Ue|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfego de mídia: Intervalos de portas
Observe que os requisitos a seguir se aplicam se você quiser implantar o Roteamento Direto sem Bypass de Mídia. Para requisitos de firewall para Bypass de Mídia, consulte Plano de [bypass de mídia com Roteamento Direto.](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)



O tráfego de mídia flui de e para um serviço separado no Microsoft Cloud. Os intervalos de endereços IP para tráfego de mídia são os próximos.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambientes do Microsoft 365, Office 365 e Office 365 GCC

- 52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (endereços IP de 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Ambiente de DoD do Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Ambiente do Office 365 GCC High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de portas (aplicável a todos os ambientes)
O intervalo de portas dos Processadores de Mídia é mostrado na tabela a seguir: 

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processador de Mídia|Sbc|3478-3481 e 49152 – 53247|Definido no SBC|
|UDP/SRTP|Sbc|Processador de Mídia|Definido no SBC|3478-3481 e 49152 – 53247|

  > [!NOTE]
  > A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.


## <a name="media-traffic-media-processors-geography"></a>Tráfego de mídia: Geografia dos processadores de mídia

O tráfego de mídia flui por meio de componentes chamados processadores de mídia. Os processadores de mídia são colocados nos mesmos datacenters que os proxies SIP. Além disso, há processadores de mídia adicionais para otimizar o fluxo de mídia. Por exemplo, não temos um componente proxy SIP agora na Austrália (fluxos SIP via Cingapura ou Hong Kong), mas temos o processador de mídia localmente na Austrália. A necessidade dos processadores de mídia localmente é ditada pela latência que encontramos enviando tráfego de longa distância, por exemplo, da Austrália para Cingapura ou Hong Kong. Embora a latência no exemplo de tráfego fluindo da Austrália para Hong Kong ou Cingapura seja aceitável para preservar uma boa qualidade de chamada para o tráfego SIP, para tráfego de mídia em tempo real, não é.

Local dos processadores de mídia:

Locais onde o proxy SIP e os componentes do processador de mídia foram implantados:
- EUA (dois datacenters do oeste dos EUA e do leste dos EUA)
- Europa (datacenters de Dublin e Amsterdã)
- Ásia (datacenters de Cingapura e Hong Kong)

Locais onde apenas processadores de mídia são implantados (fluxos SIP por meio do datacenter mais próximo listado acima):
- Japão (datacenters jp leste e oeste)
- Austrália (datacenters leste e sudeste da AU)




## <a name="media-traffic-codecs"></a>Tráfego de mídia: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Leg between SBC and Cloud Media Processor or Microsoft Teams client.
Aplica-se ao caso de bypass de mídia e casos não ignorados.

A interface roteamento direto na parte entre o Controlador de Borda de Sessão e o Processador de Mídia na Nuvem (sem bypass de mídia) ou entre o cliente do Teams e o SBC (se Bypass de Mídia habilitado) pode usar os seguintes codecs:

- Bypass sem mídia (SBC para processador de mídia na nuvem): SILK, G.711, G.722, G.729
- Bypass de Mídia (SBC para cliente do Teams): SILK, G.711, G.722, G.729

Você pode forçar o uso do codec específico no Controlador de Borda de Sessão excluindo codecs indesejáveis da oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg between Microsoft Teams Client and Cloud Media Processor
Aplica-se somente a caso de bypass de fora da mídia. Com o Bypass de Mídia, a mídia flui diretamente entre o cliente do Teams e o SBC.

Na etapa entre o Processador de Mídia na Nuvem e o cliente Microsoft Teams, SILK ou G.722 é usado. A escolha do codec nesta etapa se baseia nos algoritmos da Microsoft, que levam em consideração vários parâmetros. 


## <a name="supported-session-border-controllers-sbcs"></a>SBCs (Controladores de Borda de Sessão) com suporte

A Microsoft só dá suporte a SBCs certificados para emparelhar com o Roteamento Direto. Como o Enterprise Voice é fundamental para empresas, a Microsoft executa testes intensivos com os SBCs selecionados e trabalha com os fornecedores SBC para garantir que os dois sistemas sejam compatíveis. 

Os dispositivos que foram validados são listados como Certificados para Roteamento Direto do Teams. Os dispositivos certificados têm a garantia de funcionar em todos os cenários. 

Para obter mais informações sobre SBCs com suporte, consulte Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Confira também

[Configurar o Roteamento Direto](direct-routing-configure.md)
