---
title: Planejar o Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Saiba como Telefone Microsoft o Roteamento Direto do Sistema permite que você conecte um SBC (Controlador de Borda de Sessão) fornecido pelo cliente com suporte ao Telefone Microsoft System.
ms.openlocfilehash: b8c1c4beb17463dcc7921677529646abf624836c
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331092"
---
# <a name="plan-direct-routing"></a>Planejar o Roteamento Direto

> [!Tip]
> Assista à sessão a seguir para saber mais sobre os benefícios do Roteamento Direto, como planejar e como implantá-la: [Roteamento Direto no Microsoft Teams](https://aka.ms/teams-direct-routing)

Telefone Microsoft o Roteamento Direto do Sistema permite que você conecte um SBC (Controlador de Borda de Sessão) fornecido pelo cliente ao Telefone Microsoft System.  Com esse recurso, por exemplo, você pode configurar a conectividade PSTN (Rede Telefônica Pública Comutada) local com o cliente Microsoft Teams, conforme mostrado no diagrama a seguir: 

![Diagrama mostrando a configuração da conectividade PSTN local.](media/PlanDirectRouting1-PSTNwithTeams.png "Configuração da conectividade PSTN local com Microsoft Teams cliente")

  > [!NOTE]
  > o Skype for Business Online também permite emparelhar um SBC fornecido pelo cliente, mas isso requer uma implantação de Skype for Business Server local ou uma edição especial do Skype for Business, chamado Cloud Connector, entre o SBC e o Microsoft Cloud. Esse cenário é conhecido como voz híbrida. Por outro lado, o Roteamento Direto permite uma conexão direta entre o SBC com suporte e o Microsoft Cloud.

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto](direct-routing-landing-page.md). 

Com o Roteamento Direto, você pode conectar seu SBC a praticamente qualquer tronco de telefonia ou interconectar com equipamento PSTN de terceiros. O Roteamento Direto permite que você: 

- Use praticamente qualquer tronco PSTN com Telefone Microsoft System. 
- Configure a interoperabilidade entre equipamentos de telefonia de propriedade do cliente, como pbx (troca de filial privada) de terceiros, dispositivos analógicos e Telefone Microsoft System.

A Microsoft também oferece soluções de voz all-in-the-cloud, como Plano de Chamadas. No entanto, uma solução de voz híbrida pode ser melhor para sua organização se: 

- O Plano de Chamada da Microsoft não está disponível em seu país. 
- Sua organização exige conexão com dispositivos analógicos de terceiros, call centers e assim por diante. 
- Sua organização tem um contrato existente com uma operadora PSTN.

O Roteamento Direto também dá suporte a usuários que têm a licença adicional para o Plano de Chamadas da Microsoft. Para obter mais informações, [consulte Sistema de Telefonia e Planos de Chamada.](calling-plan-landing-page.md) 

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
|Troncos de telefonia conectados ao SBC|Um ou mais troncos de telefonia conectados ao SBC. Em uma extremidade, o SBC se conecta ao sistema Telefone Microsoft via Roteamento Direto. O SBC também pode se conectar a entidades de telefonia de terceiros, como PBXs, Adaptadores de Telefonia Analógica e assim por diante. Qualquer opção de conectividade PSTN conectada ao SBC funcionará. (Para a configuração dos troncos PSTN para o SBC, consulte os fornecedores SBC ou provedores de tronco.)|
|Microsoft 365 ou Office 365 organização|Uma Microsoft 365 ou Office 365 que você usa para o seu Microsoft Teams usuários e a configuração e a conexão com o SBC.|
|Registrador de usuários|O usuário deve estar Microsoft 365 ou Office 365.<br/>Se sua empresa tiver um ambiente local Skype for Business ou Lync com conectividade híbrida com Microsoft 365 ou Office 365, você não poderá habilitar a voz no Teams para um usuário que está no local.<br/><br/>Para verificar o registrador de um usuário, use o seguinte cmdlet Skype for Business PowerShell Online:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>A saída do cmdlet deve mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domínios|Um ou mais domínios adicionados às organizações Microsoft 365 ou Office 365.<br/><br/>Observe que você não pode usar o domínio padrão, \* .onmicrosoft.com, que é criado automaticamente para seu locatário.<br/><br/>Para exibir os domínios, você pode usar o seguinte cmdlet Skype for Business PowerShell Online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obter mais informações sobre domínios e Microsoft 365 ou Office 365, consulte [Perguntas frequentes sobre domínios.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Endereço IP público do SBC|Um endereço IP público que pode ser usado para se conectar ao SBC. Com base no tipo de SBC, o SBC pode usar NAT.|
|FQDN (Nome de Domínio Totalmente Qualificado) para o SBC|Um FQDN para o SBC, onde a parte de domínio do FQDN é um dos domínios registrados em sua Microsoft 365 ou Office 365 organização. Para obter mais informações, consulte [Nomes de domínio SBC](#sbc-domain-names).|
|Entrada DNS pública para o SBC |Uma entrada DNS pública mapeando o FQDN SBC para o Endereço IP público. |
|Certificado confiável público para o SBC |Um certificado para o SBC a ser usado para toda a comunicação com o Roteamento Direto. Para obter mais informações, consulte [Public trusted certificate for the SBC](#public-trusted-certificate-for-the-sbc).|
|Pontos de conexão para Roteamento Direto |Os pontos de conexão para Roteamento Direto são os três FQDNs a seguir:<br/><br/>`sip.pstnhub.microsoft.com` – O FQDN global deve ser experimentado primeiro.<br/>`sip2.pstnhub.microsoft.com` – FQDN secundário, mapeia geograficamente para a região de segunda prioridade.<br/>`sip3.pstnhub.microsoft.com` – FQDN terciário, mapeia geograficamente para a região de terceira prioridade.<br/><br/>Para obter informações sobre os requisitos de configuração, consulte [Sinalização SIP: FQDNs](#sip-signaling-fqdns).|
|Endereços IP de firewall e portas para mídia de Roteamento Direto |O SBC se comunica com os seguintes serviços na nuvem:<br/><br/>Proxy SIP, que lida com a sinalização<br/>Processador de Mídia, que lida com mídia - exceto quando o Desvio de Mídia está em<br/><br/>Esses dois serviços têm endereços IP separados no Microsoft Cloud, descritos posteriormente neste documento.<br/><br/>Para obter mais informações, consulte a [seção Microsoft Teams em](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [URLs e intervalos de endereços IP.](/office365/enterprise/urls-and-ip-address-ranges) |
|Perfil de Transporte de Mídia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Endereços IP de firewall e portas para Microsoft Teams mídia |Para obter mais informações, [consulte URLs e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licenciamento e outros requisitos 

Os usuários do Roteamento Direto devem ter as seguintes licenças atribuídas Microsoft 365 ou Office 365: 

- Telefone Microsoft System. 
- Microsoft Teams + Skype for Business Plano 2, se incluído no licenciamento.
- Conferência de Áudio da Microsoft (leia as anotações e o parágrafo abaixo para exemplos específicos sobre quando a licença é necessária).

> [!NOTE]
> Skype for Business Plano não deve ser removido de qualquer contrato de licenciamento no qual ele está incluído. 
> 
> [!IMPORTANT]
> GCC usuários High e DoD devem desabilitar qualquer licenciamento de Audioconferência incluído no G5 e aguardar para habilitar qualquer Audioconferência até que o Roteamento Direto seja totalmente configurado. Os usuários devem ter números de telefone discados configurados e um bloco de discagem de trabalho antes de habilbilar licenças de Audioconferência. Consulte [Audioconferência com Roteamento](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) Direto para GCC Alta e DoD para obter mais detalhes.


> [!IMPORTANT]
>  Caso você gostaria de adicionar participantes externos a reuniões agendadas, discando para eles ou fornecendo o número de discagem, a licença de audioconferência é necessária.
> Para GCC Alta e DoD, não atribua uma licença de Audioconferência para usuários do G5.  Para usuários G3, não atribua uma licença de Audioconferência até que o Roteamento Direto seja totalmente configurado e o usuário tenha um bloco de discagem funcionando.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalação de chamada ad hoc e licença de Audioconferência

Um Teams usuário pode iniciar uma chamada um-a-um Teams PSTN ou Teams para Teams e adicionar um participante PSTN a ela. Esse cenário é chamado de conferência ad hoc. O caminho que a chamada leva depende se o usuário que escalona a chamada tem uma licença de Audioconferência da Microsoft atribuída ou não:

- Se o Teams usuário que escalona a chamada tiver uma licença de Audioconferência da Microsoft atribuída, a escalada ocorrerá por meio do serviço de Audioconferência da Microsoft. O participante PSTN remoto que é convidado para a chamada existente recebe uma notificação sobre a chamada de entrada e vê o número da ponte da Microsoft atribuída ao usuário Teams que iniciou a escalação.
- Se o Teams usuário que escalona a chamada não tiver a licença de Audioconferência da Microsoft atribuída, a escalonamento ocorrerá por meio de um Controlador de Borda de Sessão conectado à interface de Roteamento Direto. O participante PSTN remoto que é convidado para a chamada recebe uma notificação sobre a chamada de entrada e vê o número do usuário Teams que iniciou a escalada. O SBC específico usado para a escalonamento é definido pela Política de Roteamento do usuário. 


Além disso, você deve garantir o seguinte:
 
- CsOnlineVoiceRoutingPolicy é atribuído ao usuário. 
- Permitir Chamada Privada está habilitada no nível de locatário para Microsoft Teams. 

O Roteamento Direto também dá suporte a usuários licenciados para o Plano de Chamadas da Microsoft. Telefone Microsoft Sistema com Plano de Chamadas pode rotear algumas chamadas usando a interface de Roteamento Direto. No entanto, os números de telefone dos usuários devem ser adquiridos online ou portados para a Microsoft.  

Misturar o Plano de Chamadas e a conectividade de Roteamento Direto para o mesmo usuário é opcional, mas pode ser útil (por exemplo, quando o usuário recebe um Plano de Chamadas da Microsoft, mas deseja rotear algumas chamadas usando o SBC). Um dos cenários mais comuns são chamadas para PBXs de terceiros.  Com PBXs de terceiros, todas as chamadas, exceto chamadas para os telefones conectados a esse PBXs, são roteados usando o Plano de Chamadas da Microsoft, mas as chamadas para os telefones conectados a PBXs de terceiros vão para o SBC e, portanto, permanecem na rede corporativa e não na PSTN. 

Para obter mais informações sobre Sistema de Telefonia licenciamento, consulte Obter o máximo [de Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) e Opções [de Plano.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 

Para obter mais informações sobre Sistema de Telefonia licenciamento, [consulte Microsoft Teams licenciamento de complemento.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 

## <a name="supported-end-points"></a>Pontos de extremidade com suporte 

Você pode usar como ponto de extremidade:

- Qualquer Teams cliente. 
- Telefones de área comum. Consulte [Configurar a licença Telefone Área](./set-up-common-area-phones.md)Comum para Microsoft Teams . Observe que você não precisa de uma licença de Plano de Chamadas ao configurar uma área comum Telefone com Roteamento Direto.
- Skype for Business telefones 3PIP. Consulte [Skype for Business suporte a telefones (3PIP) com Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nomes de domínio SBC

O nome de domínio SBC deve ser de um dos nomes registrados em Domínios do locatário. Não é possível usar o \* locatário .onmicrosoft.com para o nome FQDN do SBC.

A tabela a seguir mostra exemplos de nomes DNS registrados para o locatário, se o nome pode ser usado como FQDN para o SBC e exemplos de nomes FQDN válidos:

|Nome DNS|Pode ser usado para FQDN SBC|Exemplos de nomes FQDN|
|:--- |:--- |:--- |
contoso.com|Sim|**Nomes válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Não|O uso de domínios *.onmicrosoft.com não é suportado para nomes SBC

Suponha que você queira usar um novo nome de domínio. Por exemplo, seu locatário contoso.com um nome de domínio registrado em seu locatário e você deseja usar sbc1.sip.contoso.com. Antes de poder emparelhar um SBC com o nome sbc1.sip.contoso.com, você deve registrar o nome de domínio sip.contoso.com em Domínios em seu locatário. Se você tentar emparelhar um SBC com sbc1.sip.contoso.com antes de registrar o nome de domínio, receberá o seguinte erro: "Não é possível usar o domínio "sbc1.sip.contoso.com", pois ele não foi configurado para esse locatário."
Depois de adicionar o nome de domínio, você também precisa criar um usuário com upn user@sip.contoso.com e atribuir uma Teams de usuário. Pode levar até 24 horas para provisionar totalmente o nome de domínio depois que ele for adicionado aos domínios do seu locatário, um usuário com um novo nome é criado e uma licença é atribuída ao usuário. 

É possível que uma empresa tenha vários espaços de endereço SIP em um locatário. Por exemplo, uma empresa pode ter contoso.com como um espaço de endereço SIP e fabrikam.com como o segundo espaço de endereço SIP. Alguns usuários têm endereço user@contoso.com e alguns usuários têm endereço user@fabrikam.com. 

O SBC só precisa de um FQDN e pode atender usuários de qualquer espaço de endereço no locatário emparelhado. Por exemplo, um SBC com o nome sbc1.contoso.com pode receber e enviar o tráfego PSTN para usuários com endereços user@contoso.com e user@fabrikam.com desde que esses espaços de endereço SIP sejam registrados no mesmo locatário.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado confiável público para o SBC

A Microsoft recomenda que você solicite o certificado para o SBC gerando uma solicitação de assinatura de certificação (CSR). Para obter instruções específicas sobre como gerar uma CSR para um SBC, consulte as instruções de interconexão ou a documentação fornecida por seus fornecedores SBC. 

  > [!NOTE]
  > A maioria das autoridades de certificados (CAs) exige que o tamanho da chave privada seja pelo menos 2048. Lembre-se disso ao gerar a CSR.

O certificado precisa ter o FQDN SBC como o nome comum (CN) ou o campo nome alternativo do assunto (SAN). O certificado deve ser emitido diretamente de uma autoridade de certificação, não de um provedor intermediário.

Como alternativa, o Roteamento Direto dá suporte a um curinga no CN e/ou SAN, e o curinga precisa estar em conformidade com o [PADRÃO RFC HTTP Sobre TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Um exemplo seria usar .contoso.com que corresponderia ao \* FQDN SBC sbc.contoso.com, mas não corresponderia ao sbc.test.contoso.com.

A interface SIP de Roteamento Direto confiará apenas em certificados assinados pelas Autoridades de Certificados (CAs) que fazem parte do Programa de Certificado Raiz Confiável da Microsoft. Certifique-se de que seu certificado SBC seja assinado por uma AC que faz parte do programa e que a extensão uso de chave estendida (EKU) do certificado inclua Autenticação de Servidor.
Saiba Mais:

[Requisitos do Programa - Programa Raiz Confiável da Microsoft](/security/trusted-root/program-requirements) 
 [Lista de certificados de AC incluída](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

> [!NOTE]
> *Se o suporte a TLS mútuo (MTLS) estiver habilitado para Teams conexão no SBC, você deverá instalar o Certificado Raiz do Baltimore CyberTrust no Armazenamento Raiz Confiável SBC do contexto TLS do Teams. (Isso porque os certificados de serviço da Microsoft usam o certificado raiz de Baltimore.) Para baixar o certificado raiz de Baltimore, consulte [Office 365 Cadeias de criptografia](/microsoft-365/compliance/encryption-office-365-certificate-chains).

## <a name="sip-signaling-fqdns"></a>Sinalização SIP: FQDNs 

O Roteamento Direto é oferecido nos seguintes ambientes:
- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC Alta
- Office 365 DoD

Saiba mais sobre [Office 365 e ambientes](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) do Governo dos EUA, como GCC, GCC Alta e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 ambientes Office 365 GCC ambientes

Os pontos de conexão para Roteamento Direto são os três FQDNs a seguir:

- **sip.pstnhub.microsoft.com** – FQDN Global – deve ser experimentado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC. A atribuição é baseada em métricas de desempenho dos datacenters e proximidade geográfica com o SBC. O endereço IP retornado corresponde ao FQDN principal.
- **sip2.pstnhub.microsoft.com** – FQDN secundário – mapeia geograficamente para a região de segunda prioridade.
- **sip3.pstnhub.microsoft.com** – FQDN terciário – mapeia geograficamente para a região de terceira prioridade.

Colocar esses três FQDNs em ordem é necessário para:

- Forneça uma experiência ideal (menos carregada e mais próxima do datacenter SBC atribuído consultando o primeiro FQDN).
- Forneça failover quando a conexão de um SBC é estabelecida com um datacenter que está enfrentando um problema temporário. Para obter mais informações, consulte [Mecanismo de failover](#failover-mechanism-for-sip-signaling) abaixo.  

Os FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com – serão resolvidos para endereços IP das seguintes sub-redes:

- 52.112.0.0/14
- 52.120.0.0/14

Você precisa abrir portas para todos esses intervalos de endereços IP em seu firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-gcc-dod-environment"></a>Office GCC ambiente do DoD

O ponto de conexão para Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – FQDN Global. Como o Office 365 do DoD existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O FQDN sip.pstnhub.dod.teams.microsoft.us será resolvido para um endereço IP da seguinte sub-rede:

- 52.127.64.0/21

Você precisa abrir portas para todos esses endereços IP no firewall para permitir que o tráfego de entrada e saída entre e os endereços para sinalização.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC ambiente high

O ponto de conexão para Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – FQDN Global. Como o GCC ambiente High existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O FQDN sip.pstnhub.gov.teams.microsoft.us será resolvido para um endereço IP a partir da seguinte sub-rede:

- 52.127.88.0/21

Você precisa abrir portas para todos esses endereços IP no firewall para permitir que o tráfego de entrada e saída entre e os endereços para sinalização.

## <a name="sip-signaling-ports"></a>Sinalização SIP: Portas

Você deve usar as seguintes portas para ambientes Microsoft 365 ou Office 365 onde o Roteamento Direto é oferecido:
- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC Alta
- Office 365 DoD

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Definido no SBC (Para Office 365 GCC somente a porta 5061 high/DoD deve ser usada)|
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
Observe que os requisitos abaixo se aplicam se você quiser implantar o Roteamento Direto sem Bypass de Mídia. Para requisitos de firewall para Bypass de Mídia, consulte [Plan for media bypass with Direct Routing](./direct-routing-plan-media-bypass.md).



O tráfego de mídia flui de e para um serviço separado no Microsoft Cloud. Os intervalos de endereços IP para tráfego de mídia são os seguinte.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 ambientes Office 365 GCC ambientes

- 52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (endereços IP de 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 ambiente do DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC ambiente high

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

O tráfego de mídia flui por meio de componentes chamados processadores de mídia. Processadores de mídia são colocados nos mesmos datacenters que os proxies SIP:

- NOAM (Central Sul dos EUA, dois nos datacenters oeste e leste dos EUA)
- Europa (datacenters do Reino Unido do Sul, Central da França, Amsterdã e Dublin)
- Ásia (datacenter de Cingapura)
- Japão (datacenters JP East e West)
- Austrália (datacenters AU East e Southeast)
- LATAM (Brasil Sul)
- África (Norte da África do Sul)

## <a name="media-traffic-codecs"></a>Tráfego de mídia: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Leg between SBC and Cloud Media Processor or Microsoft Teams client.
Aplica-se a casos de bypass de mídia e não bypass.

A interface de Roteamento Direto na etapa entre o Controlador de Borda de Sessão e o Processador de Mídia na Nuvem (sem bypass de mídia) ou entre o cliente Teams e o SBC (se o Bypass de Mídia estiver habilitado) pode usar os seguintes codecs:

- Bypass sem mídia (SBC para Processador de Mídia na Nuvem): SILK, G.711, G.722, G.729
- Desvio de mídia (SBC para Teams cliente): SILK, G.711, G.722, G.729

Você pode forçar o uso do codec específico no Controlador de Borda de Sessão excluindo codecs indesejáveis da oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg between Microsoft Teams Client and Cloud Media Processor
Aplica-se apenas a caso de desvio de mídia. Com o Desvio de Mídia, a mídia flui diretamente entre o cliente Teams e o SBC.

Na etapa entre o Processador de Mídia na Nuvem e o cliente Microsoft Teams é usado o SILK ou o G.722. A escolha do codec nesta etapa é baseada em algoritmos da Microsoft, que levam em consideração vários parâmetros. 


## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borda de sessão com suporte (SBCs)

A Microsoft só dá suporte a SBCs certificados para emparelhar com Roteamento Direto. Como Enterprise Voice é essencial para empresas, a Microsoft executa testes intensivos com os SBCs selecionados e trabalha com os fornecedores SBC para garantir que os dois sistemas sejam compatíveis. 

Os dispositivos que foram validados são listados como Certificados para Teams Roteamento Direto. Os dispositivos certificados têm garantia de funcionar em todos os cenários. 

Para obter mais informações sobre SBCs com suporte, consulte Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Confira também

[Configurar o Roteamento Direto](direct-routing-configure.md)
