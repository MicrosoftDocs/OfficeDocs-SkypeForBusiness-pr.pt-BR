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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leia este tópico para saber como o roteamento direto do sistema de telefone da Microsoft permite que você conecte um controlador de borda de sessão (SBC) compatível com o cliente ao Microsoft Phone System.
ms.openlocfilehash: d279792315aec17df10f5c1335306147c7080287
ms.sourcegitcommit: eab284e2add7af1b3f3c5f1f77c0a3bbf77857a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41953772"
---
# <a name="plan-direct-routing"></a>Planejar o Roteamento Direto

> [!Tip]
> Assista à sessão a seguir para saber mais sobre os benefícios de roteamento direto, como planejar e como implantá-lo: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing)

O roteamento direto do Microsoft Phone System permite conectar um controlador de borda de sessão (SBC) compatível com o cliente ao Microsoft Phone System.  Com esse recurso, por exemplo, você pode configurar a conectividade PSTN (rede telefônica pública comutada) no local com o cliente do Microsoft Teams, conforme mostrado no diagrama a seguir: 

![Diagrama mostrando a configuração de conectividade PSTN local](media/PlanDirectRouting1-PSTNwithTeams.png "Configuração de conectividade PSTN local com o cliente do Microsoft Teams")

  > [!NOTE]
  > O Skype for Business online também permite que você emparelhe um SBC fornecido pelo cliente, mas isso exige uma implantação local do Skype for Business Server ou uma edição especial do Skype for Business, chamada de conector de nuvem, entre o SBC e a nuvem da Microsoft. Esse cenário é conhecido como voz híbrida. Por outro lado, o roteamento direto permite uma conexão direta entre o SBC compatível e a nuvem da Microsoft. 

Com o roteamento direto, você pode conectar seu SBC a praticamente qualquer tronco de telefonia ou interconexão com equipamento PSTN de terceiros. O roteamento direto permite que você: 

- Usar praticamente qualquer tronco PSTN com o sistema telefônico da Microsoft. 
- Configure a interoperabilidade entre equipamento de telefonia de Propriedade do cliente, como um PBX (Exchange Branch Exchange) de terceiros, dispositivos analógicos e sistema telefônico da Microsoft.

A Microsoft também oferece soluções de voz todas em nuvem, como o plano de chamadas. No entanto, uma solução de voz híbrida pode ser melhor para a sua organização se: 

- O plano de chamadas da Microsoft não está disponível no seu país. 
- Sua organização requer conexão com dispositivos analógicos de terceiros, centros de chamadas e assim por diante. 
- Sua organização tem um contrato existente com uma operadora PSTN.

O roteamento direto também oferece suporte a usuários que têm a licença adicional para o plano de chamadas da Microsoft. Para obter mais informações, consulte [sistema telefônico e planos de chamada](calling-plan-landing-page.md). 

Com o roteamento direto, quando os usuários participam de uma conferência agendada, o número de discagem é fornecido pelo serviço de conferência de áudio da Microsoft, que requer o licenciamento adequado.  Ao discar, o serviço de audioconferência da Microsoft coloca a chamada usando recursos de chamada online, que requer o licenciamento adequado. (Observe que a discagem não roteia pelo roteamento direto.) Para obter mais informações, consulte [reuniões online com o Teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
Planejar a implantação do roteamento direto é essencial para uma implementação bem-sucedida. Este artigo descreve os requisitos de infraestrutura e licença e fornece informações sobre a conectividade SBC: 

- [Requisitos de infraestrutura](#infrastructure-requirements)
- [Licenciamento e outros requisitos](#licensing-and-other-requirements)
- [Nomes de domínio SBC](#sbc-domain-names)
- [Certificado público confiável para o SBC](#public-trusted-certificate-for-the-sbc)
- [Sinalização SIP: FQDNs](#sip-signaling-fqdns)
- [Sinalização SIP: portas](#sip-signaling-ports)
- [Tráfego de mídia: intervalos de porta](#media-traffic-port-ranges)
- [Controladores de borda de sessão com suporte (SBCs)](#supported-session-border-controllers-sbcs)

Para obter informações detalhadas sobre como configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
Os requisitos de infraestrutura para o SBCs, os domínios e outros requisitos de conectividade de rede compatíveis para implantar o roteamento direto estão listados na tabela a seguir:  

|**Requisitos de infraestrutura**|**Você precisa dos seguintes**|
|:--- |:--- |
|Controlador de borda de sessão (SBC)|Um SBC compatível. Para obter mais informações, consulte [SBCS compatível](#supported-session-border-controllers-sbcs).|
|Troncos de telefonia conectados ao SBC|Um ou mais troncos de telefonia conectados ao SBC. Em uma extremidade, o SBC se conecta ao sistema telefônico da Microsoft via roteamento direto. O SBC também pode se conectar a entidades de telefonia de terceiros, como PBXs, adaptadores de telefonia analógicas e assim por diante. Qualquer opção de conectividade PSTN conectada ao SBC funcionará. (Para configuração dos troncos PSTN para o SBC, consulte os fornecedores de SBC ou provedores de tronco.)|
|Locatário do Office 365|Um locatário do Office 365 que você usa para basear seus usuários do Microsoft Teams e a configuração e a conexão com o SBC.|
|Registrador de usuários|O usuário deve estar na home page do Office 365.<br/>Se a sua empresa tiver um ambiente Skype for Business ou Lync local com conectividade híbrida para o Office 365, você não poderá habilitar a voz no Teams para um usuário hospedado no local.<br/><br/>Para verificar o registrador de um usuário, use o seguinte cmdlet do PowerShell do Skype for Business Online:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>A saída do cmdlet deve mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domínios|Um ou mais domínios adicionados a seus locatários do Office 365.<br/><br/>Observe que você não pode usar o domínio padrão \*,. onmicrosoft.com, que é criado automaticamente para o seu locatário.<br/><br/>Para exibir os domínios, você pode usar o seguinte cmdlet do PowerShell do Skype for Business Online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obter mais informações sobre domínios e locatários do Office 365, consulte [perguntas frequentes sobre domínios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Endereço IP público do SBC|Um endereço IP público que pode ser usado para se conectar ao SBC. Com base no tipo de SBC, o SBC pode usar NAT.|
|FQDN (nome de domínio totalmente qualificado) para o SBC|Um FQDN para o SBC, no qual a parte do domínio do FQDN é um dos domínios registrados no seu locatário do Office 365. Para obter mais informações, consulte [nomes de domínio SBC](#sbc-domain-names).|
|Entrada DNS pública para o SBC |Uma entrada DNS pública que associa o endereço IP do SBC ao endereço IP público. |
|Certificado público confiável para o SBC |Um certificado para o SBC ser usado para todas as comunicações com roteamento direto. Para obter mais informações, consulte [certificado público confiável para o SBC](#public-trusted-certificate-for-the-sbc).|
|Pontos de conexão para roteamento direto |Os pontos de conexão para roteamento direto são os três FQDNs a seguir:<br/><br/>`sip.pstnhub.microsoft.com`– O FQDN global deve ser tentado primeiro.<br/>`sip2.pstnhub.microsoft.com`– FQDN secundário, mapas geograficamente para a segunda região de prioridade.<br/>`sip3.pstnhub.microsoft.com`– FQDN (FQDN), que é mapeado geograficamente para a terceira região de prioridade.<br/><br/>Para obter informações sobre os requisitos de configuração, consulte [sinalização SIP: FQDNs](#sip-signaling-fqdns).|
|Endereços IP e portas do firewall para mídia de roteamento direto |O SBC se comunica com os seguintes serviços na nuvem:<br/><br/>Proxy SIP, que manipula a sinalização<br/>Processador de mídia, que manipula mídia-exceto quando a mídia ignorada está ativada<br/><br/>Esses dois serviços têm endereços IP separados no Microsoft Cloud, descritos mais adiante neste documento.<br/><br/>Para obter mais informações, consulte a [seção Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) nas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|Perfil de transporte de mídia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Endereços IP e portas do firewall para mídia do Microsoft Teams |Para obter mais informações, consulte [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licenciamento e outros requisitos 

Os usuários de roteamento direto devem ter as seguintes licenças atribuídas no Office 365: 

- Sistema telefônico da Microsoft. 
- Microsoft Teams + Skype for Business plano 2, se incluído no licenciamento.
- Conferência de áudio da Microsoft (leia as anotações e o parágrafo abaixo para obter exemplos específicos sobre quando a licença é necessária).

> [!NOTE]
> O plano do Skype for Business não deve ser removido de nenhum contrato de licenciamento onde está incluído. 


> [!IMPORTANT]
>  Se você quiser adicionar participantes externos a reuniões agendadas, basta discar para eles ou fornecer o número de discagem, a licença de audioconferência será necessária.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Licença de encaminhamento de chamadas ad hoc e conferência de áudio

Um usuário do teams pode iniciar uma equipe única da PSTN ou do teams para a chamada do Teams e adicionar um participante PSTN a ele. Esse cenário é chamado de conferência ad hoc. O caminho que a chamada leva depende se o usuário que Escalona a chamada tem uma licença de conferência de áudio da Microsoft atribuída ou não:

- Se o usuário do teams que escalonar a chamada tiver uma licença do Microsoft Audio Conferencing atribuída, o escalonamento ocorrerá por meio do serviço de audioconferência da Microsoft. O participante PSTN remoto que é convidado para a chamada existente recebe uma notificação sobre a chamada recebida e vê o número da ponte da Microsoft atribuído ao usuário do teams que iniciou o escalonamento.
- Se o usuário do teams que escalonar a chamada não tiver a licença de conferência de áudio da Microsoft atribuída, o escalonamento ocorrerá por meio de um controlador de borda de sessão conectado à interface de roteamento direto. O participante PSTN remoto que é convidado para a chamada recebe uma notificação sobre a chamada recebida e vê o número do usuário da equipe que iniciou o escalonamento. O SBC específico usado para o escalonamento é definido pela política de roteamento do usuário. 


Além disso, você deve garantir o seguinte:
 
- CsOnlineVoiceRoutingPolicy é atribuído ao usuário. 
- Permitir chamada privada está habilitado no nível do locatário do Microsoft Teams. 

O roteamento direto também oferece suporte a usuários que estão licenciados para o plano de chamadas da Microsoft. Sistema telefônico da Microsoft com plano de chamadas pode rotear algumas chamadas usando a interface de roteamento direto. No entanto, os números de telefone dos usuários devem ser adquiridos online ou portados para a Microsoft.  

A combinação de plano de chamada e a conectividade de roteamento direto para o mesmo usuário é opcional, mas pode ser útil (por exemplo, quando o usuário recebe um plano de chamada da Microsoft, mas quer rotear algumas chamadas usando o SBC). Um dos cenários mais comuns são chamadas para PBXs de terceiros.  Com PBXs de terceiros, todas as chamadas, exceto chamadas para os telefones conectados a essa PBXs, são roteadas usando o plano de chamadas da Microsoft, mas chamadas para os telefones conectados a PBXs de terceiros vão para o SBC e, portanto, permanecer dentro da rede corporativa e não na PSTN. 

Para obter mais informações sobre o licenciamento do sistema telefônico, consulte [obter o máximo do Office com](https://products.office.com/compare-all-microsoft-office-products?tab=2) [as opções de plano](https://technet.microsoft.com/library/office-365-plan-options.aspx)do Office 365 e do Office 365. 

Para obter mais informações sobre o licenciamento do sistema telefônico, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="supported-end-points"></a>Pontos de extremidade compatíveis 

Você pode usar como ponto final:

- Qualquer cliente do teams. 
- Telefones fixos de área comuns. Consulte [Configurar a licença telefônica da área comum para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones). Observação Você não precisa de uma licença de plano de chamada ao configurar um telefone de área comum com roteamento direto.
- Skype for Business 3PIP para telefones. Confira [suporte do Skype for Business para telefones fixos (3PIP) com o Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nomes de domínio SBC

O nome de domínio SBC deve ser de um dos nomes registrados em domínios do locatário. Não é possível usar \*o locatário. onmicrosoft.com para o nome FQDN do SBC.

A tabela a seguir mostra exemplos de nomes DNS registrados para o locatário, se o nome pode ser usado como um FQDN para o SBC e exemplos de nomes de FQDN válidos:

|**Nome DNS**|**Pode ser usado para o FQDN do SBC**|**Exemplos de nomes FQDN**|
|:--- |:--- |:--- |
contoso.com|Sim|**Nomes válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Não|Não há suporte para o uso de domínios *. onmicrosoft.com para nomes SBC

Suponha que você queira usar um novo nome de domínio. Por exemplo, seu locatário tem contoso.com como um nome de domínio registrado em seu locatário e você deseja usar sbc1.sip.contoso.com. Antes de poder emparelhar um SBC com o nome sbc1.sip.contoso.com, você deve registrar o nome de domínio sip.contoso.com em domínios em seu locatário. Se você tentar emparelhar um SBC com sbc1.sip.contoso.com antes de registrar o nome de domínio, você receberá o seguinte erro: "não é possível usar o domínio" sbc1.sip.contoso.com "porque ele não foi configurado para esse locatário."
Depois de adicionar o nome de domínio, você também precisará criar um usuário com user@sip.contoso.com UPN e atribuir uma licença do teams. Pode levar até 24 horas para provisionar completamente o nome de domínio depois que ele é adicionado aos domínios do seu locatário, um usuário com um novo nome é criado e uma licença é atribuída ao usuário. 

É possível que uma empresa possa ter vários espaços de endereço SIP em um locatário. Por exemplo, uma empresa pode ter contoso.com como um espaço de endereço SIP e fabrikam.com como o segundo espaço de endereço SIP. Alguns usuários têm o endereço user@contoso.com e alguns usuários têm o endereço user@fabrikam.com. 

O SBC só precisa de um FQDN e pode atender os usuários de qualquer espaço de endereço no locatário emparelhado. Por exemplo, um SBC com o nome sbc1.contoso.com pode receber e enviar o tráfego PSTN para usuários com endereços user@contoso.com e user@fabrikam.com contanto que esses espaços de endereço SIP sejam registrados no mesmo locatário.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado público confiável para o SBC

A Microsoft recomenda que você solicite o certificado do SBC gerando uma solicitação de assinatura de certificação (CSR). Para obter instruções específicas sobre como gerar um CSR para um SBC, consulte as instruções de interconexão ou documentação fornecidas por seus fornecedores de SBC. 

  > [!NOTE]
  > A maioria das autoridades de certificação (CAs) exige que o tamanho da chave privada seja de pelo menos 2048. Tenha isso em mente ao gerar o CSR.

O certificado precisa ter FQDN do SBC nos campos assunto, nome comum ou nome alternativo do assunto.

Como alternativa, o roteamento direto dá suporte a um caractere curinga na SAN e o caractere curinga precisa estar de acordo com o [http padrão RFC em TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Um exemplo seria usar \*. contoso.com na San, que corresponderia ao FQDN FQDN SBC.contoso.com, mas não corresponde ao SBC.Test.contoso.com.

O certificado precisa ser gerado por uma das seguintes autoridades de certificação raiz:

- AffirmTrust
- Raiz da CA externa addtrust
- Raiz do Baltimore CyberTrust
- Buypass
- Cybertrust
- Classe 3 autoridade de certificação primária pública
- Comodo autoridade de certificação raiz segura
- Alemão Telekom 
- CA raiz global do DigiCert
- CA raiz EV de alta garantia DigiCert
- Confiável
- GlobalSign
- Vá Daddy
- GeoTrust
- Verisign, Inc. 
- Starfield 
- Raiz móvel do Symantec Enterprise para Microsoft 
- SwissSign
- CA de carimbo de data/hora da Thawte
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (alemães Telekom)
- QuoVadis

A Microsoft está trabalhando para adicionar outras autoridades de certificação com base nas solicitações dos clientes. 

## <a name="sip-signaling-fqdns"></a>Sinalização SIP: FQDNs 

O roteamento direto é oferecido nos seguintes ambientes do Office 365:
- Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Saiba mais sobre os [ambientes do Office 365 e do governo dos EUA](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , como GCC, gcc High e DOD.

### <a name="office-365-and-office-365-gcc-environments"></a>Ambientes do Office 365 e do Office 365 GCC

O ponto de conexão para roteamento direto são os três FQDNs a seguir:

- **SIP.pstnhub.Microsoft.com** – FQDN global – deve ser tentado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS do Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC. A atribuição se baseia em métricas de desempenho dos datacenters e da proximidade geográfica com o SBC. O endereço IP retornado corresponde ao FQDN primário.
- **SIP2.pstnhub.Microsoft.com** – FQDN secundário – mapas geograficamente para a segunda região de prioridade.
- **sip3.pstnhub.Microsoft.com** – FQDN (FQDN) – mapas geograficamente para a terceira região de prioridade.

É necessário colocar esses três FQDNs em ordem para:

- Ofereça uma experiência ideal (menos carregada e mais próxima ao datacenter SBC atribuída consultando o primeiro FQDN).
- Fornecer failover quando a conexão de um SBC é estabelecida com um datacenter que está apresentando um problema temporário. Para obter mais informações, consulte o [mecanismo de failover](#failover-mechanism-for-sip-signaling) abaixo.  

Os FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com – serão resolvidos para um dos seguintes endereços IP:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

Você precisa abrir portas para todos esses endereços IP no seu firewall para permitir o recebimento e o tráfego de entrada e saída dos endereços para sinalização.  Se o seu firewall der suporte a nomes DNS, a sip-all.pstnhub.microsoft.com FQDN será resolvida para todos esses endereços IP. 


### <a name="office-365-gcc-dod-environment"></a>Ambiente do Office 365 GCC DoD

O ponto de conexão para roteamento direto é o seguinte FQDN:

**SIP.pstnhub.DoD.Teams.Microsoft.us** – FQDN global. Como o ambiente DoD do Office 365 existe somente nos data centers dos EUA, não há FQDNs secundários e terciários.

A sip.pstnhub.dod.teams.microsoft.us FQDN será resolvida para um dos seguintes endereços IP:

- 52.127.64.33
- 52.127.68.34

Você precisa abrir portas para todos esses endereços IP no seu firewall para permitir o recebimento e o tráfego de entrada e saída dos endereços para sinalização.  Se o seu firewall der suporte a nomes DNS, a sip.pstnhub.dod.teams.microsoft.us FQDN será resolvida para todos esses endereços IP. 

### <a name="office-365-gcc-high-environment"></a>Ambiente High do Office 365 GCC

O ponto de conexão para roteamento direto é o seguinte FQDN:

**SIP.pstnhub.gov.Teams.Microsoft.us** – FQDN global. Como o ambiente High GCC existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

A sip.pstnhub.gov.teams.microsoft.us FQDN será resolvida para um dos seguintes endereços IP:

- 52.127.88.59
- 52.127.92.64

Você precisa abrir portas para todos esses endereços IP no seu firewall para permitir o recebimento e o tráfego de entrada e saída dos endereços para sinalização.  Se o seu firewall der suporte a nomes DNS, a sip.pstnhub.gov.teams.microsoft.us FQDN será resolvida para todos esses endereços IP. 

## <a name="sip-signaling-ports"></a>Sinalização SIP: portas

Você deve usar as seguintes portas para ambientes do Office 365 em que o roteamento direto é oferecido:
- Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|**Traffic**|**De**|**Até**|**Porta de origem**|**Porta de destino**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|Proxy SIP|SBC|1024 – 65535|Definido no SBC (para o Office 365 GCC High/DoD somente as portas 5061 e 5062 devem ser usadas)|
SIP/TLS|SBC|Proxy SIP|Definido no SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de failover para sinalização SIP

O SBC faz uma consulta DNS resolver sip.pstnhub.microsoft.com. Com base na localização do SBC e nas métricas de desempenho do datacenter, o datacenter principal é selecionado. Se o principal do datacenter tiver um problema, o SBC tentará o sip2.pstnhub.microsoft.com, que é resolvido para o segundo datacenter atribuído e, no caso raro, os datacenters em duas regiões não estiverem disponíveis, o SBC repetirá o último FQDN ( sip3.pstnhub.microsoft.com), que fornece o IP do Data Center terciário.

A tabela a seguir resume as relações entre os datacenters primários, secundários e terciários:

|**Se o datacenter principal estiver**|**EMEA**|**NOAM**|**Centro**|
|:--- |:--- |:--- |:--- |
|O datacenter secundário (sip2.pstnhub.microsoft.com)|Junte|FAZ|Junte|
|O datacenter terciário (sip3.pstnhub.microsoft.com)|Centro|Centro|FAZ|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfego de mídia: intervalos de porta
Observe que os requisitos abaixo se aplicam se você deseja implantar o roteamento direto sem bypass de mídia. Para requisitos de firewall para bypass de mídia, consulte [planejar o bypass de mídia com roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass).



O tráfego de mídia flui para e de um serviço separado na nuvem da Microsoft. O intervalo IP para tráfego de mídia é o seguinte.

### <a name="office-365-and-office-365-gcc-environments"></a>Ambientes do Office 365 e do Office 365 GCC

- 52.112.0.0/14 (endereços IP de 52.112.0.1 para 52.115.255.254).

### <a name="office-365-gcc-dod-environment"></a>Ambiente do Office 365 GCC DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Ambiente High do Office 365 GCC

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de porta (aplicável a todos os ambientes)
O intervalo de portas dos processadores de mídia é mostrado na tabela a seguir: 

|**Traffic**|**De**|**Até**|**Porta de origem**|**Porta de destino**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processador de mídia|SBC|49152 – 53247|Definido no SBC|
|UDP/SRTP|SBC|Processador de mídia|Definido no SBC|49152 – 53247|

  > [!NOTE]
  > A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.

## <a name="media-traffic-codecs"></a>Tráfego de mídia: codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Trecho entre o processador de SBC e de mídia em nuvem ou o cliente do Microsoft Teams.
Aplica-se aos dois casos de bypass de mídia e não bypass.

A interface de roteamento direto no trecho entre o controlador de borda de sessão e o processador de mídia de nuvem (sem bypass de mídia) ou entre o cliente de equipes e o SBC (se a mídia ignorada habilitado) pode usar os seguintes codecs:

- Bypass sem mídia (processador SBC para mídia em nuvem): SILK, G. 711, G. 722, G. 729
- Bypass de mídia (SBC para o cliente do Teams): SILK, G. 711, G. 722, G. 729, OPUS

Você pode forçar o uso do codec específico no controlador de borda de sessão, excluindo codecs indesejáveis da oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Trecho entre o cliente do Microsoft Teams e o processador de mídia em nuvem
Aplica-se somente ao caso de bypass sem mídia. Com o bypass de mídia, a mídia flui diretamente entre o cliente de equipe e o SBC.

No trecho entre o processador de mídia da nuvem e o cliente do Microsoft Teams, o SILK ou o G. 722 é usado. A opção de codec nesse trecho é baseada em algoritmos da Microsoft, que levam em consideração vários parâmetros. 


## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borda de sessão com suporte (SBCs)

A Microsoft oferece suporte apenas para SBCs certificado para emparelhar com roteamento direto. Como o Enterprise Voice é essencial para empresas, a Microsoft executa testes intensivos com o SBCs selecionado e trabalha com os fornecedores de SBC para garantir que os dois sistemas sejam compatíveis. 

Os dispositivos que foram validados são listados como certificados para o roteamento direto do teams. Os dispositivos certificados têm a garantia de funcionar em todos os cenários. 

Para obter mais informações sobre o SBCs compatível, consulte [lista de controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Confira também

[Configurar o Roteamento Direto](direct-routing-configure.md)



