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
description: Saiba como o Roteamento Direto do Sistema de Telefonia do Microsoft Phone permite que você conecte um Controlador de Borda de Sessão (SBC) fornecido pelo cliente com suporte ao Microsoft Phone System.
ms.openlocfilehash: 858d57fb210765a1223a68527b0aa1b37bf7800b
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836988"
---
# <a name="plan-direct-routing"></a>Planejar o Roteamento Direto

> [!Tip]
> Assista à sessão a seguir para saber mais sobre os benefícios do Roteamento [Direto,](https://aka.ms/teams-direct-routing) como planejar e como implantá-la: Roteamento Direto no Microsoft Teams

O Roteamento Direto do Sistema do Microsoft Phone permite que você conecte um SBC (Controlador de Borda de Sessão) fornecido pelo cliente ao Microsoft Phone System.  Com esse recurso, por exemplo, você pode configurar a conectividade PSTN (Rede Telefônica Pública Comutada) local com o cliente do Microsoft Teams, conforme mostrado no diagrama a seguir: 

![Diagrama mostrando a configuração da conectividade PSTN local](media/PlanDirectRouting1-PSTNwithTeams.png "Configuração da conectividade PSTN local com o cliente do Microsoft Teams")

  > [!NOTE]
  > O Skype for Business Online também permite que você emparelhe um SBC fornecido pelo cliente, mas isso requer uma implantação local do Skype for Business Server ou uma edição especial do Skype for Business, chamada Cloud Connector, entre o SBC e o Microsoft Cloud. Esse cenário é conhecido como voz híbrida. Por outro lado, o Roteamento Direto permite uma conexão direta entre o SBC com suporte e o Microsoft Cloud.

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](direct-routing-landing-page.md) 

Com o Roteamento Direto, você pode conectar seu SBC a praticamente qualquer tronco de telefonia ou interconectar com equipamento PSTN de terceiros. O Roteamento Direto permite que você: 

- Use praticamente qualquer tronco PSTN com o Microsoft Phone System. 
- Configure a interoperabilidade entre equipamentos de telefonia de propriedade do cliente, como pbx (troca de filial privada de terceiros), dispositivos analógicos e Sistema de Telefonia da Microsoft.

A Microsoft também oferece soluções de voz all-in-the-cloud, como Plano de Chamadas. No entanto, uma solução de voz híbrida pode ser melhor para sua organização se: 

- O Plano de Chamada da Microsoft não está disponível em seu país. 
- Sua organização exige conexão com dispositivos analógicos de terceiros, call centers e assim por diante. 
- Sua organização tem um contrato existente com uma operadora PSTN.

O Roteamento Direto também dá suporte a usuários que têm a licença adicional para o Plano de Chamadas da Microsoft. Para obter mais informações, consulte [Sistema de Telefonia e Planos de Chamadas.](calling-plan-landing-page.md) 

Com o Roteamento Direto, quando os usuários participam de uma conferência agendada, o número de discagem é fornecido pelo serviço de Audioconferência da Microsoft, que exige o licenciamento adequado.  Ao discar, o serviço de Audioconferência da Microsoft coloca a chamada usando recursos de chamada online, o que exige o licenciamento adequado. (Observe que, se um usuário não tiver uma licença de Audioconferência da Microsoft, a chamada será roteado pelo Roteamento Direto.) Para obter mais informações, consulte [Online Meetings with Teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
Planejar sua implantação de Roteamento Direto é fundamental para uma implementação bem-sucedida. Este artigo descreve os requisitos de infraestrutura e licenciamento e fornece informações sobre a conectividade SBC: 

- [Requisitos de infraestrutura](#infrastructure-requirements)
- [Licenciamento e outros requisitos](#licensing-and-other-requirements)
- [Nomes de domínio SBC](#sbc-domain-names)
- [Certificado confiável público para o SBC](#public-trusted-certificate-for-the-sbc)
- [Sinalização SIP: FQDNs](#sip-signaling-fqdns)
- [Sinalização SIP: Portas](#sip-signaling-ports)
- [Tráfego de mídia: intervalos de porta](#media-traffic-port-ranges)
- [Controladores de borda de sessão com suporte (SBCs)](#supported-session-border-controllers-sbcs)

Para obter informações detalhadas sobre como configurar o Roteamento Direto, consulte [Configure Direct Routing](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
Os requisitos de infraestrutura para os SBCs, domínios e outros requisitos de conectividade de rede com suporte para implantar o Roteamento Direto estão listados na tabela a seguir:  

|Requisito de infraestrutura|Você precisa do seguinte|
|:--- |:--- |
|Controlador de Borda de Sessão (SBC)|Um SBC com suporte. Para obter mais informações, consulte [SBCs com suporte](#supported-session-border-controllers-sbcs).|
|Troncos de telefonia conectados ao SBC|Um ou mais troncos de telefonia conectados ao SBC. Em uma extremidade, o SBC se conecta ao Sistema de Telefonia Microsoft por meio de Roteamento Direto. O SBC também pode se conectar a entidades de telefonia de terceiros, como PBXs, Adaptadores de Telefonia Analógica e assim por diante. Qualquer opção de conectividade PSTN conectada ao SBC funcionará. (Para a configuração dos troncos PSTN para o SBC, consulte os fornecedores SBC ou provedores de tronco.)|
|Organização do Microsoft 365 ou Office 365|Uma organização do Microsoft 365 ou do Office 365 que você usa para a casa dos usuários do Microsoft Teams e a configuração e a conexão com o SBC.|
|Registrador de usuários|O usuário deve estar em casa no Microsoft 365 ou no Office 365.<br/>Se a sua empresa tiver um ambiente local do Skype for Business ou do Lync com conectividade híbrida com o Microsoft 365 ou o Office 365, você não poderá habilitar a voz no Teams para um usuário instalado no local.<br/><br/>Para verificar o registrador de um usuário, use o seguinte cmdlet do PowerShell do Skype for Business Online:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>A saída do cmdlet deve mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domínios|Um ou mais domínios adicionados às suas organizações do Microsoft 365 ou Office 365.<br/><br/>Observe que você não pode usar o domínio padrão, \* .onmicrosoft.com, que é criado automaticamente para seu locatário.<br/><br/>Para exibir os domínios, você pode usar o seguinte cmdlet do PowerShell do Skype for Business Online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obter mais informações sobre domínios e organizações do Microsoft 365 ou Office 365, consulte [Perguntas frequentes sobre domínios.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Endereço IP público do SBC|Um endereço IP público que pode ser usado para se conectar ao SBC. Com base no tipo de SBC, o SBC pode usar NAT.|
|FQDN (Nome de Domínio Totalmente Qualificado) para o SBC|Um FQDN para o SBC, onde a parte de domínio do FQDN é um dos domínios registrados em sua organização do Microsoft 365 ou office 365. Para obter mais informações, consulte [Nomes de domínio SBC](#sbc-domain-names).|
|Entrada DNS pública para o SBC |Uma entrada DNS pública mapeando o FQDN SBC para o Endereço IP público. |
|Certificado confiável público para o SBC |Um certificado para o SBC a ser usado para toda a comunicação com o Roteamento Direto. Para obter mais informações, consulte [Public trusted certificate for the SBC](#public-trusted-certificate-for-the-sbc).|
|Pontos de conexão para Roteamento Direto |Os pontos de conexão para Roteamento Direto são os três FQDNs a seguir:<br/><br/>`sip.pstnhub.microsoft.com` – O FQDN global deve ser experimentado primeiro.<br/>`sip2.pstnhub.microsoft.com` – FQDN secundário, mapeia geograficamente para a região de segunda prioridade.<br/>`sip3.pstnhub.microsoft.com` – FQDN terciário, mapeia geograficamente para a região de terceira prioridade.<br/><br/>Para obter informações sobre os requisitos de configuração, consulte [Sinalização SIP: FQDNs](#sip-signaling-fqdns).|
|Endereços IP de firewall e portas para mídia de Roteamento Direto |O SBC se comunica com os seguintes serviços na nuvem:<br/><br/>Proxy SIP, que lida com a sinalização<br/>Processador de Mídia, que lida com mídia - exceto quando o Desvio de Mídia está em<br/><br/>Esses dois serviços têm endereços IP separados no Microsoft Cloud, descritos posteriormente neste documento.<br/><br/>Para obter mais informações, consulte a seção [Microsoft Teams em](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [URLs e intervalos de endereços IP.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|Perfil de Transporte de Mídia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Endereços IP de firewall e portas para mídia do Microsoft Teams |Para obter mais informações, [consulte URLs e intervalos de endereços IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licenciamento e outros requisitos 

Os usuários do Roteamento Direto devem ter as seguintes licenças atribuídas no Microsoft 365 ou no Office 365: 

- Microsoft Phone System. 
- Microsoft Teams + Skype for Business Plan 2, se incluído no licenciamento.
- Conferência de Áudio da Microsoft (leia as anotações e o parágrafo abaixo para exemplos específicos sobre quando a licença é necessária).

> [!NOTE]
> O Plano do Skype for Business não deve ser removido de nenhum contrato de licenciamento no qual ele está incluído. 
> 
> [!IMPORTANT]
> Os usuários do GCC High e do DoD devem desabilitar qualquer licenciamento de Audioconferência incluído no G5 e aguardar para habilitar qualquer Audioconferência até que o Roteamento Direto seja totalmente configurado. Os usuários devem ter números de telefone discados configurados e um bloco de discagem de trabalho antes de habilbilar licenças de Audioconferência. Consulte [Audioconferência com Roteamento Direto para GCC High e DoD](https://docs.microsoft.com/microsoftteams/audio-conferencing-with-direct-routing-for-gcch-and-dod) para obter mais detalhes.


> [!IMPORTANT]
>  Caso você gostaria de adicionar participantes externos a reuniões agendadas, discando para eles ou fornecendo o número de discagem, a licença de audioconferência é necessária.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalação de chamada ad hoc e licença de Audioconferência

Um usuário do Teams pode iniciar uma chamada do Teams um-a-um para PSTN ou Teams para o Teams e adicionar um participante PSTN a ele. Esse cenário é chamado de conferência ad hoc. O caminho que a chamada leva depende se o usuário que escalona a chamada tem uma licença de Audioconferência da Microsoft atribuída ou não:

- Se o usuário do Teams que escalona a chamada tiver uma licença de Audioconferência da Microsoft atribuída, a escalada ocorrerá por meio do serviço de Audioconferência da Microsoft. O participante PSTN remoto que é convidado para a chamada existente recebe uma notificação sobre a chamada de entrada e vê o número da ponte da Microsoft atribuída ao usuário do Teams que iniciou a escalada.
- Se o usuário do Teams que escalona a chamada não tiver a licença de Audioconferência da Microsoft atribuída, a escalação ocorrerá por meio de um Controlador de Borda de Sessão conectado à interface de Roteamento Direto. O participante PSTN remoto que é convidado para a chamada recebe uma notificação sobre a chamada de entrada e vê o número do usuário do Teams que iniciou a escalação. O SBC específico usado para a escalonamento é definido pela Política de Roteamento do usuário. 


Além disso, você deve garantir o seguinte:
 
- CsOnlineVoiceRoutingPolicy é atribuído ao usuário. 
- Permitir Chamada Privada está habilitada no nível de locatário para o Microsoft Teams. 

O Roteamento Direto também dá suporte a usuários licenciados para o Plano de Chamadas da Microsoft. O Sistema de Telefonia da Microsoft com Plano de Chamadas pode rotear algumas chamadas usando a interface de Roteamento Direto. No entanto, os números de telefone dos usuários devem ser adquiridos online ou portados para a Microsoft.  

Misturar o Plano de Chamadas e a conectividade de Roteamento Direto para o mesmo usuário é opcional, mas pode ser útil (por exemplo, quando o usuário recebe um Plano de Chamadas da Microsoft, mas deseja rotear algumas chamadas usando o SBC). Um dos cenários mais comuns são chamadas para PBXs de terceiros.  Com PBXs de terceiros, todas as chamadas, exceto chamadas para os telefones conectados a esse PBXs, são roteados usando o Plano de Chamadas da Microsoft, mas as chamadas para os telefones conectados a PBXs de terceiros vão para o SBC e, portanto, permanecem na rede corporativa e não na PSTN. 

Para obter mais informações sobre o licenciamento do Sistema de Telefonia, consulte [Obter o máximo de Opções](https://products.office.com/compare-all-microsoft-office-products?tab=2) do Office e Do [Plano.](https://technet.microsoft.com/library/office-365-plan-options.aspx) 

Para obter mais informações sobre licenciamento do Sistema de Telefonia, consulte [Licenciamento de complemento do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 

## <a name="supported-end-points"></a>Pontos de extremidade com suporte 

Você pode usar como ponto de extremidade:

- Qualquer cliente do Teams. 
- Telefones de área comum. Consulte [Configurar a licença de Telefone de Área Comum do Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones). Observe que você não precisa de uma licença de Plano de Chamadas ao configurar um Telefone de Área Comum com Roteamento Direto.
- Telefones Skype for Business 3PIP. Consulte o suporte a telefones [do Skype for Business (3PIP) com o Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nomes de domínio SBC

O nome de domínio SBC deve ser de um dos nomes registrados em Domínios do locatário. Não é possível usar o \* locatário .onmicrosoft.com para o nome FQDN do SBC.

A tabela a seguir mostra exemplos de nomes DNS registrados para o locatário, se o nome pode ser usado como FQDN para o SBC e exemplos de nomes FQDN válidos:

|Nome DNS|Pode ser usado para FQDN SBC|Exemplos de nomes FQDN|
|:--- |:--- |:--- |
contoso.com|Sim|**Nomes válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Não|O uso de domínios *.onmicrosoft.com não é suportado para nomes SBC

Suponha que você queira usar um novo nome de domínio. Por exemplo, seu locatário contoso.com um nome de domínio registrado em seu locatário e você deseja usar sbc1.sip.contoso.com. Antes de poder emparelhar um SBC com o nome sbc1.sip.contoso.com, você deve registrar o nome de domínio sip.contoso.com em Domínios em seu locatário. Se você tentar emparelhar um SBC com sbc1.sip.contoso.com antes de registrar o nome de domínio, receberá o seguinte erro: "Não é possível usar o domínio "sbc1.sip.contoso.com", pois ele não foi configurado para esse locatário."
Depois de adicionar o nome de domínio, você também precisa criar um usuário com upn user@sip.contoso.com e atribuir uma licença do Teams. Pode levar até 24 horas para provisionar totalmente o nome de domínio depois que ele for adicionado aos domínios do seu locatário, um usuário com um novo nome é criado e uma licença é atribuída ao usuário. 

É possível que uma empresa tenha vários espaços de endereço SIP em um locatário. Por exemplo, uma empresa pode ter contoso.com como um espaço de endereço SIP e fabrikam.com como o segundo espaço de endereço SIP. Alguns usuários têm endereço user@contoso.com e alguns usuários têm endereço user@fabrikam.com. 

O SBC só precisa de um FQDN e pode atender usuários de qualquer espaço de endereço no locatário emparelhado. Por exemplo, um SBC com o nome sbc1.contoso.com pode receber e enviar o tráfego PSTN para usuários com endereços user@contoso.com e user@fabrikam.com desde que esses espaços de endereço SIP sejam registrados no mesmo locatário.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado confiável público para o SBC

A Microsoft recomenda que você solicite o certificado para o SBC gerando uma solicitação de assinatura de certificação (CSR). Para obter instruções específicas sobre como gerar uma CSR para um SBC, consulte as instruções de interconexão ou a documentação fornecida por seus fornecedores SBC. 

  > [!NOTE]
  > A maioria das autoridades de certificados (CAs) exige que o tamanho da chave privada seja pelo menos 2048. Lembre-se disso ao gerar a CSR.

O certificado precisa ter o FQDN SBC como o nome comum (CN) ou o campo nome alternativo do assunto (SAN). O certificado deve ser emitido diretamente de uma autoridade de certificação, não de um provedor intermediário.

Como alternativa, o Roteamento Direto dá suporte a um curinga no CN e/ou SAN, e o curinga precisa estar em conformidade com o [PADRÃO RFC HTTP Sobre TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Um exemplo seria usar .contoso.com que corresponderia ao \* FQDN SBC sbc.contoso.com, mas não corresponderia ao sbc.test.contoso.com.

O certificado precisa ser gerado por uma das seguintes autoridades de certificado raiz:

- AffirmTrust
- Raiz de AC externa addTrust
- Raiz da CyberTrust de Baltimore*
- Buypass
- Cybertrust
- Autoridade de Certificação Primária Pública de Classe 3
- Comodo Secure Root CA
- Deutsche Telekom 
- AC Raiz Global digiCert
- AC raiz do EV de Alta Garantia digiCert
- Confia
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Symantec Enterprise Mobile Root para Microsoft 
- SwissSign
- CA de data/hora de descongelar
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Para roteamento direto em ambientes GCCH e DoD do Office 365, o certificado precisa ser gerado por uma das seguintes autoridades de certificado raiz:
- AC Raiz Global digiCert
- AC raiz do EV de Alta Garantia digiCert

> [!NOTE]
> *Se o suporte MTLS (Mutual TLS) estiver habilitado para a conexão do Teams no SBC, você deverá instalar o Certificado Raiz de Baltimore CyberTrust no Armazenamento Raiz Confiável SBC do contexto TLS do Teams. (Isso porque os certificados de serviço da Microsoft usam o certificado raiz de Baltimore.) Para baixar o certificado raiz de Baltimore, consulte Cadeias de criptografia [do Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains).

A Microsoft está trabalhando na adição de autoridades de certificação adicionais com base em solicitações de clientes. 

## <a name="sip-signaling-fqdns"></a>Sinalização SIP: FQDNs 

O Roteamento Direto é oferecido nos seguintes ambientes:
- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Saiba mais sobre [ambientes do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) e do Governo dos EUA, como GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambientes do Microsoft 365, Office 365 e Office 365 GCC

Os pontos de conexão para Roteamento Direto são os três FQDNs a seguir:

- **sip.pstnhub.microsoft.com** – FQDN Global – deve ser experimentado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS do Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC. A atribuição é baseada em métricas de desempenho dos datacenters e proximidade geográfica com o SBC. O endereço IP retornado corresponde ao FQDN principal.
- **sip2.pstnhub.microsoft.com** – FQDN secundário – mapeia geograficamente para a região de segunda prioridade.
- **sip3.pstnhub.microsoft.com** – FQDN terciário – mapeia geograficamente para a região de terceira prioridade.

Colocar esses três FQDNs em ordem é necessário para:

- Forneça uma experiência ideal (menos carregada e mais próxima do datacenter SBC atribuído consultando o primeiro FQDN).
- Forneça failover quando a conexão de um SBC é estabelecida com um datacenter que está enfrentando um problema temporário. Para obter mais informações, consulte [Mecanismo de failover](#failover-mechanism-for-sip-signaling) abaixo.  

Os FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com – serão resolvidos para um dos seguintes endereços IP:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

Você precisa abrir portas para todos esses endereços IP no firewall para permitir que o tráfego de entrada e saída entre e os endereços para sinalização.  Se o firewall dá suporte a nomes DNS, o FQDN **sip-all.pstnhub.microsoft.com** resolvido para todos esses endereços IP. 

> [!IMPORTANT]
>  Como parte da expansão do Roteamento Direto do Teams e melhoria do serviço, implantamos novas instâncias da infraestrutura de Roteamento Direto na Austrália. Isso se reflete em dois endereços IP adicionais (52.114.16.74 e 52.114.20.29) para os quais os seguintes FQDNs serão resolvidos para clientes australianos – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com. Você precisa adicionar esses dois endereços IP (52.114.16.74 e 52.114.20.29) às suas ACLs (Listas de Controle de Acesso IP) e abrir portas para todos esses endereços IP em seu firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-365-gcch-and-dod-environment"></a>Ambiente GCCH e DoD do Office 365

O ponto de conexão para Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – FQDN Global. Como o ambiente do DoD do Office 365 existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O FQDN sip.pstnhub.dod.teams.microsoft.us será resolvido para um dos seguintes endereços IP:

- 52.127.64.33
- 52.127.68.34

Você precisa abrir portas para todos esses endereços IP no firewall para permitir que o tráfego de entrada e saída entre e os endereços para sinalização.

### <a name="office-365-gcc-high-environment"></a>Ambiente do Office 365 GCC High

O ponto de conexão para Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – FQDN Global. Como o ambiente GCC High existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O FQDN sip.pstnhub.gov.teams.microsoft.us será resolvido para um dos seguintes endereços IP:

- 52.127.88.59
- 52.127.92.64

Você precisa abrir portas para todos esses endereços IP no firewall para permitir que o tráfego de entrada e saída entre e os endereços para sinalização. Se o firewall for compatível com nomes DNS, o FQDN **sip-all.pstnhub.gov.teams.microsoft.us** resolvido para todos esses endereços IP. Esse FQDN também pode ser usado como FQDN Federado para classificação de chamada de entrada.

## <a name="sip-signaling-ports"></a>Sinalização SIP: Portas

Você deve usar as seguintes portas para ambientes do Microsoft 365 ou Office 365 nos quais o Roteamento Direto é oferecido:
- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Definido no SBC (Para o Office 365 GCC High/DoD somente a porta 5061 deve ser usada)|
SIP/TLS|SBC|SIP Proxy|Definido no SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de failover para Sinalização SIP

O SBC faz uma consulta DNS para resolver sip.pstnhub.microsoft.com. Com base no local SBC e nas métricas de desempenho do datacenter, o datacenter principal é selecionado. Se o datacenter principal tiver um problema, o SBC tentará o sip2.pstnhub.microsoft.com, que é resolvido para o segundo datacenter atribuído e, no caso raro de datacenters em duas regiões não estar disponíveis, o SBC tentará novamente o último FQDN (sip3.pstnhub.microsoft.com), que fornece o IP do datacenter terciário.

A tabela abaixo resume as relações entre datacenters primários, secundários e terciários:

|Se o datacenter principal for|EMEA|NOAM|ÁSIA|
|:--- |:--- |:--- |:--- |
|O datacenter secundário (sip2.pstnhub.microsoft.com)|EUA|UE|EUA|
|O datacenter terciário (sip3.pstnhub.microsoft.com)|ÁSIA|ÁSIA|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfego de mídia: intervalos de porta
Observe que os requisitos abaixo se aplicam se você quiser implantar o Roteamento Direto sem Bypass de Mídia. Para requisitos de firewall para Bypass de Mídia, consulte [Plan for media bypass with Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass).



O tráfego de mídia flui de e para um serviço separado no Microsoft Cloud. Os intervalos de endereços IP para tráfego de mídia são os seguinte.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambientes do Microsoft 365, Office 365 e Office 365 GCC

- 52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (endereços IP de 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Ambiente do Office 365 DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Ambiente do Office 365 GCC High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de portas (aplicável a todos os ambientes)
O intervalo de portas dos Processadores de Mídia é mostrado na tabela a seguir: 

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processador de Mídia|SBC|3478-3481 e 49152 – 53247|Definido no SBC|
|UDP/SRTP|SBC|Processador de Mídia|Definido no SBC|3478-3481 e 49152 – 53247|

  > [!NOTE]
  > A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.


## <a name="media-traffic-media-processors-geography"></a>Tráfego de mídia: Geografia dos processadores de mídia

O tráfego de mídia flui por meio de componentes chamados processadores de mídia. Os processadores de mídia são colocados nos mesmos datacenters que os proxies SIP. Além disso, há processadores de mídia adicionais para otimizar o fluxo de mídia. Por exemplo, não temos um componente proxy SIP agora na Austrália (fluxos SIP via Cingapura ou Hong Kong), mas temos o processador de mídia localmente na Austrália. A necessidade dos processadores de mídia localmente é ditada pela latência que vivenciamos enviando tráfego de longa distância, por exemplo, da Austrália para Cingapura ou Hong Kong. Embora a latência no exemplo de tráfego fluindo da Austrália para Hong Kong ou Cingapura seja aceitável para preservar uma boa qualidade de chamada para o tráfego SIP, para tráfego de mídia em tempo real não é.

Local dos processadores de mídia:

Locais onde os componentes de proxy SIP e processador de mídia implantados:
- EUA (dois datacenters do Leste Dos EUA e oeste dos EUA)
- Europa (datacenters de Amsterdã e Dublin)
- Ásia (datacenters de Cingapura e Hong Kong)

Locais onde apenas processadores de mídia são implantados (fluxos SIP por meio do datacenter mais próximo listado acima):
- Japão (datacenters JP East e West)
- Austrália (datacenters AU East e Southeast)




## <a name="media-traffic-codecs"></a>Tráfego de mídia: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Leg between SBC and Cloud Media Processor or Microsoft Teams client.
Aplica-se a casos de bypass de mídia e não bypass.

A interface de Roteamento Direto na etapa entre o Controlador de Borda de Sessão e o Processador de Mídia na Nuvem (sem bypass de mídia) ou entre o cliente do Teams e o SBC (se Bypass de Mídia habilitado) pode usar os seguintes codecs:

- Bypass sem mídia (SBC para Processador de Mídia na Nuvem): SILK, G.711, G.722, G.729
- Bypass de Mídia (cliente SBC para Teams): SILK, G.711, G.722, G.729

Você pode forçar o uso do codec específico no Controlador de Borda de Sessão excluindo codecs indesejáveis da oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg between Microsoft Teams Client and Cloud Media Processor
Aplica-se apenas a caso de desvio de mídia. Com o Desvio de Mídia, a mídia flui diretamente entre o cliente do Teams e o SBC.

Na etapa entre o Processador de Mídia na Nuvem e o cliente do Microsoft Teams, é usado o SILK ou o G.722. A escolha do codec nesta etapa é baseada em algoritmos da Microsoft, que levam em consideração vários parâmetros. 


## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borda de sessão com suporte (SBCs)

A Microsoft só dá suporte a SBCs certificados para emparelhar com Roteamento Direto. Como Enterprise Voice é essencial para empresas, a Microsoft executa testes intensivos com os SBCs selecionados e trabalha com os fornecedores SBC para garantir que os dois sistemas sejam compatíveis. 

Os dispositivos que foram validados estão listados como Certificados para Roteamento Direto do Teams. Os dispositivos certificados têm garantia de funcionar em todos os cenários. 

Para obter mais informações sobre SBCs com suporte, consulte Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Confira também

[Configurar o Roteamento Direto](direct-routing-configure.md)
