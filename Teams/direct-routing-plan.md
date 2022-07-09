---
title: Planejar o Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
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
description: Saiba como o Roteamento Direto da Microsoft permite que você conecte um SBC (Controlador de Borda de Sessão) fornecido pelo cliente com suporte ao Sistema de Telefonia.
ms.openlocfilehash: fd5f2733fc11511e6cfc2e646c0bb78aff26b522
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695054"
---
# <a name="plan-direct-routing"></a>Planejar o Roteamento Direto

> [!Tip]
> Assista à sessão a seguir para saber mais sobre os benefícios do Roteamento Direto, como planejar e como implantá-lo: Roteamento Direto [no Microsoft Teams](https://aka.ms/teams-direct-routing)

O Roteamento Direto permite que você conecte um SBC (Controlador de Borda de Sessão) fornecido pelo cliente com suporte ao Sistema de Telefonia. Com esse recurso, você pode configurar a conectividade PSTN (Rede Telefônica Pública Comunada) local com o cliente do Microsoft Teams, conforme mostrado no diagrama a seguir: 

![Diagrama mostrando a configuração da conectividade PSTN local.](media/PlanDirectRouting1-PSTNwithTeams.png "Configuração da conectividade PSTN local com o cliente do Microsoft Teams")

  > [!NOTE]
  > O Skype for Business Online também permite emparelhar um SBC fornecido pelo cliente, mas isso requer uma implantação do Skype for Business Server local ou uma edição especial do Skype for Business, chamada Cloud Connector, entre o SBC e o Microsoft Cloud. Esse cenário é conhecido como voz híbrida. Por outro lado, o Roteamento Direto permite uma conexão direta entre o SBC com suporte e o Microsoft Cloud.

> [!Important]
> O Cloud Connector Edition será desativado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto](direct-routing-landing-page.md). 

Com o Roteamento Direto, você pode conectar seu SBC a praticamente qualquer tronco de telefonia ou interconexão com equipamentos PSTN de terceiros. O Roteamento Direto permite que você: 

- Use praticamente qualquer tronco PSTN com o Sistema de Telefonia. 

- Configure a interoperabilidade entre o equipamento de telefonia de propriedade do cliente, como uma PBX (troca de filial privada) de terceiros, dispositivos analógicos e Teams.

A Microsoft também oferece soluções de voz na nuvem, como Plano de Chamadas. No entanto, uma solução de voz híbrida pode ser melhor para sua organização se: 

- O Plano de Chamadas da Microsoft não está disponível em seu país. 

- Sua organização requer conexão com dispositivos analógicos de terceiros, call centers e assim por diante. 

- Sua organização tem um contrato existente com uma operadora PSTN.

O Roteamento Direto também dá suporte a usuários que têm a licença adicional para o Plano de Chamadas da Microsoft. Para obter mais informações, consulte [Sistema de Telefonia e Planos de Chamadas](calling-plan-landing-page.md). 

Com o Roteamento Direto, quando os usuários participam de uma conferência agendada, o número de discagem é fornecido pelo serviço de Audioconferência da Microsoft, que exige o licenciamento adequado.  Ao discar, o serviço de Audioconferência da Microsoft coloca a chamada usando recursos de chamada online, o que exige o licenciamento adequado. (Observe que, se um usuário não tiver uma licença de Audioconferência da Microsoft, a chamada será roteada pelo Roteamento Direto.) Para obter mais informações, consulte [Reuniões Online com o Teams](https://www.microsoft.com/en-us/microsoft-teams/online-meetings). 
 
Planejar a implantação do Roteamento Direto é fundamental para uma implementação bem-sucedida. Este artigo descreve os requisitos de infraestrutura e licenciamento e fornece informações sobre a conectividade SBC: 

- [Requisitos de infraestrutura](#infrastructure-requirements)
- [Licenciamento e outros requisitos](#licensing-and-other-requirements)
- [Nomes de domínio SBC](#sbc-domain-names)
- [Certificado confiável público para o SBC](#public-trusted-certificate-for-the-sbc)
- [Sinalização SIP: FQDNs](#sip-signaling-fqdns)
- [Sinalização SIP: portas](#sip-signaling-ports)
- [Tráfego de mídia: intervalos de portas](#media-traffic-port-ranges)
- [Controladores de borda de sessão com suporte (SBCs)](#supported-session-border-controllers-sbcs)

Para obter informações detalhadas sobre como configurar o Roteamento Direto, consulte [Configurar Roteamento Direto](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
Os requisitos de infraestrutura para os SBCs, domínios e outros requisitos de conectividade de rede com suporte para implantar o Roteamento Direto estão listados na tabela a seguir:  

|Requisito de infraestrutura|Você precisa do seguinte|
|:--- |:--- |
|Controlador de Borda de Sessão (SBC)|Um SBC com suporte. Para obter mais informações, consulte [SBCs com suporte](#supported-session-border-controllers-sbcs).|
|Troncos de telefonia conectados ao SBC|Um ou mais troncos de telefonia conectados ao SBC. Em uma extremidade, o SBC se conecta ao Sistema de Telefonia por meio do Roteamento Direto. O SBC também pode se conectar a entidades de telefonia de terceiros, como PBXs, Adaptadores de Telefonia Analógica e assim por diante. Qualquer opção de conectividade PSTN conectada ao SBC funcionará. (Para obter a configuração dos troncos PSTN para o SBC, consulte os fornecedores SBC ou provedores de tronco.)|
|Organização do Microsoft 365|Uma organização do Microsoft 365 que você usa para conectar seus usuários do Microsoft Teams e a configuração e a conexão com o SBC.|
|Registrador de usuários|O usuário deve estar hospedado no Microsoft 365.<br/>Se sua empresa tiver um ambiente Skype for Business ou Lync local com conectividade híbrida com o Microsoft 365, você não poderá habilitar a voz no Teams para um usuário hospedado no local.<br/><br/>Para verificar o registrador de um usuário, use o seguinte cmdlet Skype for Business Online do PowerShell:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>A saída do cmdlet deve mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domínios|Um ou mais domínios adicionados às suas organizações microsoft 365 ou Office 365.<br/><br/>Observe que você não pode usar o domínio padrão, \*.onmicrosoft.com, que é criado automaticamente para seu locatário.<br/><br/>Para exibir os domínios, você pode usar o seguinte cmdlet Skype for Business Online do PowerShell:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obter mais informações sobre domínios e microsoft 365 ou Office 365, consulte [perguntas frequentes sobre domínios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Endereço IP público para o SBC|Um endereço IP público que pode ser usado para se conectar ao SBC. Com base no tipo de SBC, o SBC pode usar NAT.|
|FQDN (Nome de Domínio Totalmente Qualificado) para o SBC|Um FQDN para o SBC, em que a parte de domínio do FQDN é um dos domínios registrados em sua organização microsoft 365 ou Office 365. Para obter mais informações, consulte [nomes de domínio SBC](#sbc-domain-names).|
|Entrada DNS pública para o SBC |Uma entrada DNS pública que mapeia o FQDN SBC para o endereço IP público. |
|Certificado confiável público para o SBC |Um certificado para o SBC a ser usado para toda a comunicação com o Roteamento Direto. Para obter mais informações, consulte [Certificado confiável público para o SBC](#public-trusted-certificate-for-the-sbc).|
|Pontos de conexão para Roteamento Direto |Os pontos de conexão para o Roteamento Direto são os três FQDNs a seguir:<br/><br/>`sip.pstnhub.microsoft.com` – O FQDN global deve ser tentado primeiro.<br/>`sip2.pstnhub.microsoft.com` – FQDN secundário, mapeado geograficamente para a segunda região de prioridade.<br/>`sip3.pstnhub.microsoft.com` – FQDN terciário, mapeado geograficamente para a terceira região de prioridade.<br/><br/>Para obter informações sobre os requisitos de configuração, [consulte Sinalização SIP: FQDNs](#sip-signaling-fqdns).|
|Portas e endereços IP do firewall para mídia de Roteamento Direto |O SBC se comunica com os seguintes serviços na nuvem:<br/><br/>Proxy SIP, que manipula a sinalização<br/>Processador de mídia, que manipula mídia , exceto quando o Bypass de Mídia está ativado<br/><br/>Esses dois serviços têm endereços IP separados no Microsoft Cloud, descritos posteriormente neste documento.<br/><br/>Para obter mais informações, consulte a [seção do Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) em [URLs e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges). |
|Perfil de Transporte de Mídia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Portas e endereços IP do firewall para mídia do Microsoft Teams |Para obter mais informações, consulte [URLs e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licenciamento e outros requisitos 

Os usuários do Roteamento Direto devem ter as seguintes licenças atribuídas no Microsoft 365: 

- Sistema de Telefonia da Microsoft
- Microsoft Teams + Skype for Business Plano 2, se incluído no licenciamento
- Audioconferência da Microsoft (leia as anotações e o parágrafo abaixo para obter exemplos específicos sobre quando essa licença é necessária.)

> [!NOTE]
> Skype for Business Plano não deve ser removido de nenhum contrato de licenciamento em que ele esteja incluído. 
> 
> [!IMPORTANT]
> Os usuários do GCC High e do DoD devem desabilitar qualquer licenciamento de Audioconferência incluído no G5 e aguardar para habilitar qualquer Audioconferência até que o Roteamento Direto seja totalmente configurado. Os usuários devem ter números de telefone discados configurados e um teclado de discagem funcional antes de habilitar licenças de Audioconferência. Consulte [Audioconferência com Roteamento Direto para GCC High e DoD](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) para obter mais detalhes.


> [!IMPORTANT]
>  Se você quiser adicionar participantes externos a reuniões agendadas, seja discando para eles ou fornecendo o número de discagem, a licença de audioconferência será necessária.
> Para GCC High e DoD, não atribua uma licença de Audioconferência para usuários do G5. Para usuários do G3, não atribua uma licença de Audioconferência até que o Roteamento Direto esteja totalmente configurado e o usuário tenha um teclado de discagem funcional.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalonamento de chamadas ad hoc e licença de Audioconferência

Um usuário do Teams pode iniciar uma chamada do Teams para PSTN ou do Teams para Teams e adicionar um participante PSTN a ele. Esse cenário é chamado de conferência ad hoc. O caminho que a chamada usa depende se o usuário que escalona a chamada tem uma licença de Audioconferência da Microsoft atribuída ou não:

- **Se o usuário do Teams que escalona a** chamada tiver uma licença de Audioconferência da Microsoft atribuída, o escalonamento ocorrerá por meio do serviço de Audioconferência da Microsoft. O participante PSTN remoto que é convidado para a chamada existente recebe uma notificação sobre a chamada de entrada e vê o número da ponte da Microsoft atribuída ao usuário do Teams que iniciou o escalonamento.

- **Se o usuário do Teams** que escalona a chamada não tiver a licença de Audioconferência da Microsoft atribuída, o escalonamento ocorrerá por meio de um Controlador de Borda de Sessão conectado à interface de Roteamento Direto. O participante PSTN remoto que é convidado para a chamada recebe uma notificação sobre a chamada de entrada e vê o número do usuário do Teams que iniciou o escalonamento. O SBC específico usado para o escalonamento é definido pela política de roteamento do usuário. 

Você deve garantir o seguinte:
 
- CsOnlineVoiceRoutingPolicy é atribuído ao usuário. 

- Permitir Chamada Privada está habilitado no nível do locatário do Microsoft Teams. 

O Roteamento Direto também dá suporte a usuários licenciados para o Plano de Chamadas da Microsoft. O Sistema de Telefonia com Plano de Chamadas pode rotear algumas chamadas usando a interface de Roteamento Direto. No entanto, os números de telefone dos usuários devem ser adquiridos online ou portados para a Microsoft.  

Misturar o Plano de Chamadas e a conectividade de Roteamento Direto para o mesmo usuário é opcional, mas pode ser útil. Por exemplo, quando o usuário recebe um Plano de Chamada da Microsoft, mas deseja rotear algumas chamadas usando o SBC. Um dos cenários mais comuns são chamadas para PBXs de terceiros.  Com PBXs de terceiros, todas as chamadas, exceto chamadas para os telefones conectados a esse PBX, são roteados usando o Plano de Chamadas da Microsoft, mas as chamadas para os telefones conectados a PBXs de terceiros vão para o SBC e, portanto, permanecem dentro da rede corporativa e não do PSTN. 

Para obter mais informações sobre o licenciamento do Sistema de Telefonia, confira [Obter o máximo](https://products.office.com/compare-all-microsoft-office-products?tab=2) das Opções do Office e [do Plano](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) e [do licenciamento de complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="supported-end-points"></a>Pontos de extremidade com suporte 

Você pode usar como um ponto de extremidade:

- Qualquer cliente do Teams. 

- Telefones de área comuns. Consulte [Configurar Telefones de Área Comum para o Microsoft Teams](./set-up-common-area-phones.md). Você não precisa de uma licença de Plano de Chamada ao configurar um Telefone de Área Comum com Roteamento Direto.

- Skype for Business telefones 3PIP. Consulte [Skype for Business suporte a telefones (3PIP) com o Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nomes de domínio SBC

O nome de domínio SBC deve ser de um dos nomes registrados em Domínios do locatário. Você não pode usar o \*locatário .onmicrosoft.com para o nome FQDN do SBC.

A tabela a seguir mostra exemplos de nomes DNS registrados para o locatário, se o nome pode ser usado como um FQDN para o SBC e exemplos de nomes FQDN válidos:

|Nome DNS|Pode ser usado para FQDN SBC|Exemplos de nomes de FQDN|
|:--- |:--- |:--- |
contoso.com|Sim|**Nomes válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Não|Não há suporte para o uso de domínios *.onmicrosoft.com para nomes SBC

Suponha que você queira usar um novo nome de domínio. Por exemplo, seu locatário contoso.com como um nome de domínio registrado em seu locatário e você deseja usar sbc1.sip.contoso.com. Antes de emparelhar um SBC com o nome sbc1.sip.contoso.com, você deve registrar o nome de domínio sip.contoso.com domínios em seu locatário. Se você tentar emparelhar um SBC com o sbc1.sip.contoso.com antes de registrar o nome de domínio, receberá o seguinte erro: "Não é possível usar o domínio "sbc1.sip.contoso.com", pois ele não foi configurado para este locatário."
Depois de adicionar o nome de domínio, você também precisa criar um usuário com upn user@sip.contoso.com e atribuir uma licença do Teams. Pode levar até 24 horas para provisionar totalmente o nome de domínio depois que ele é adicionado aos Domínios do seu locatário, um usuário com um novo nome é criado e uma licença é atribuída ao usuário. 

É possível que uma empresa tenha vários espaços de endereço SIP em um locatário. Por exemplo, uma empresa pode ter contoso.com como um espaço de endereço SIP e fabrikam.com como o segundo espaço de endereço SIP. Alguns usuários têm endereço user@contoso.com e alguns usuários têm endereço user@fabrikam.com. 

O SBC só precisa de um FQDN e pode atender aos usuários de qualquer espaço de endereço no locatário emparelhado. Por exemplo, um SBC com o nome sbc1.contoso.com pode receber e enviar o tráfego PSTN para usuários com endereços user@contoso.com e user@fabrikam.com, desde que esses espaços de endereço SIP sejam registrados no mesmo locatário.  

 > [!NOTE]
 > O FQDN do SBC Serviços de Comunicação do Azure roteamento direto deve ser diferente do FQDN SBC no Roteamento Direto do Teams.
  
## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado confiável público para o SBC

A Microsoft recomenda que você solicite o certificado para o SBC gerando uma CSR (solicitação de assinatura de certificação). Para obter instruções específicas sobre como gerar uma CSR para um SBC, consulte as instruções de interconexão ou a documentação fornecida por seus fornecedores SBC. 

> [!NOTE]
> A maioria das autoridades de certificação (ACs) exige que o tamanho da chave privada seja pelo menos 2048. Tenha isso em mente ao gerar a CSR.

O certificado precisa ter o FQDN SBC como o CN (nome comum) ou o campo SAN (nome alternativo da entidade).

Como alternativa, o Roteamento Direto dá suporte a um curinga no CN e/ou SAN, e o curinga precisa estar em conformidade com o [HTTP RFC padrão via TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Um exemplo seria usar \*.contoso.com que corresponderia ao FQDN SBC sbc.contoso.com, mas não corresponderia ao sbc.test.contoso.com.

A interface SIP de Roteamento Direto confiará apenas em certificados assinados por autoridades de certificação (ACs) que fazem parte do Programa de Certificado Raiz Confiável da Microsoft. Verifique se o certificado SBC foi assinado por uma AC que faz parte do programa e se a extensão EKU (Uso Estendido de Chave) do certificado inclui a Autenticação de Servidor.
Saiba mais: [Requisitos de Programa – Programa Raiz Confiável da Microsoft](/security/trusted-root/program-requirements)
  
[Lista de Certificados de Autoridade de Certificação incluída](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 Para roteamento direto Office 365 ambientes GCCH e DoD, o certificado precisa ser gerado por uma das seguintes autoridades de certificação raiz:

- AC raiz global digiCert
- DigiCert High Assurance EV Root CA

> [!NOTE]
> Se o suporte MTLS (Mutual TLS) estiver habilitado para a conexão do Teams no SBC, você deverá instalar os certificados Baltimore CyberTrust Root e DigiCert Global Root G2 no Repositório Raiz Confiável SBC do contexto TLS do Teams. (Isso ocorre porque os certificados de serviço da Microsoft usam um desses dois certificados raiz.) Para baixar esses certificados raiz, consulte [Office 365 de criptografia](/microsoft-365/compliance/encryption-office-365-certificate-chains). Para obter mais detalhes, consulte [Alterações de certificado TLS do Office](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes).

## <a name="sip-signaling-fqdns"></a>Sinalização SIP: FQDNs 

O Roteamento Direto é oferecido nos seguintes ambientes:

- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Saiba mais sobre [Office 365 e ambientes do Governo](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) dos EUA, como GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambientes do Microsoft 365, Office 365 e Office 365 GCC

Os pontos de conexão para o Roteamento Direto são os três FQDNs a seguir:

- **sip.pstnhub.microsoft.com** – FQDN Global – deve ser tentado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS do Microsoft Azure retornam um endereço IP apontando para o datacenter primário do Azure atribuído ao SBC. A atribuição se baseia nas métricas de desempenho dos datacenters e na proximidade geográfica com o SBC. O endereço IP retornado corresponde ao FQDN primário.

- **sip2.pstnhub.microsoft.com** – FQDN secundário – mapeia geograficamente para a segunda região de prioridade.

- **sip3.pstnhub.microsoft.com** – FQDN terciário – mapeia geograficamente para a região de terceira prioridade.

Colocar esses três FQDNs em ordem é necessário para:

- Forneça uma experiência ideal (menos carregado e mais próximo do datacenter SBC atribuído consultando o primeiro FQDN).

- Forneça failover quando a conexão de um SBC for estabelecida com um datacenter que esteja enfrentando um problema temporário. Para obter mais informações, consulte o [mecanismo de failover](#failover-mechanism-for-sip-signaling) abaixo.  

Os FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com – serão resolvidos para endereços IP das seguintes sub-redes:

- 52.112.0.0/14
- 52.120.0.0/14

Você precisa abrir portas para todos esses intervalos de endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-gcc-dod-environment"></a>Ambiente do Office GCC DoD

O ponto de conexão para o Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – FQDN global. Como o Office 365 do DoD existe somente nos data centers dos EUA, não há FQDNs secundários e terciários.

O FQDN sip.pstnhub.dod.teams.microsoft.us será resolvido para um endereço IP da seguinte sub-rede:

- 52.127.64.0/21

Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High

O ponto de conexão para o Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – FQDN global. Como o ambiente GCC High existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O FQDN sip.pstnhub.gov.teams.microsoft.us será resolvido para um endereço IP da seguinte sub-rede:

- 52.127.88.0/21

Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

## <a name="sip-signaling-ports"></a>Sinalização SIP: portas

Você deve usar as seguintes portas para ambientes do Microsoft 365 ou Office 365 em que o Roteamento Direto é oferecido:

- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Definido no SBC (para a Office 365 GCC High/DoD somente a porta 5061 deve ser usada)|
SIP/TLS|SBC|SIP Proxy|Definido no SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de failover para sinalização SIP

O SBC faz uma consulta DNS para resolver sip.pstnhub.microsoft.com. Com base no local SBC e nas métricas de desempenho do datacenter, o datacenter primário é selecionado. Se o datacenter primário apresentar um problema, o SBC tentará o sip2.pstnhub.microsoft.com, que é resolvido para o segundo datacenter atribuído e, no caso raro em que os datacenters em duas regiões não estão disponíveis, o SBC tentará novamente o último FQDN (sip3.pstnhub.microsoft.com), que fornece o IP do datacenter terciário.

A tabela a seguir resume as relações entre datacenters primários, secundários e terciários:

|Se o datacenter primário for|EMEA|NOAM|ÁSIA|
|:--- |:--- |:--- |:--- |
|O datacenter secundário (sip2.pstnhub.microsoft.com)|NOS|UE|NOS|
|O datacenter terciário (sip3.pstnhub.microsoft.com)|ÁSIA|ÁSIA|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfego de mídia: intervalos de portas
Observe que os requisitos abaixo se aplicam se você quiser implantar o Roteamento Direto sem Bypass de Mídia. Para requisitos de firewall para Bypass de Mídia, consulte [Plan for media bypass with Direct Routing](./direct-routing-plan-media-bypass.md).

O tráfego de mídia flui de e para um serviço separado no Microsoft Cloud. Os intervalos de endereços IP para tráfego de mídia são os seguintes.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambientes do Microsoft 365, Office 365 e Office 365 GCC

- 52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (endereços IP de 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 do DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de portas (aplicável a todos os ambientes)
O intervalo de portas dos Processadores de Mídia é mostrado na tabela a seguir: 

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processador de mídia|SBC|3478-3481 e 49152 – 53247|Definido no SBC|
|UDP/SRTP|SBC|Processador de mídia|Definido no SBC|3478-3481 e 49152 – 53247|

  > [!NOTE]
  > A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.


## <a name="media-traffic-media-processors-geography"></a>Tráfego de mídia: geografia dos processadores de mídia

O tráfego de mídia flui por meio de componentes chamados processadores de mídia. Os processadores de mídia são colocados nos mesmos datacenters que os proxies SIP:

- NOAM (Centro-Sul dos EUA, dois datacenters no Oeste dos EUA e Leste dos EUA)
- Europa (Sul do Reino Unido, França Central, Amsterdã e dublin datacenters)
- Ásia (datacenter de Singapura)
- Japão (datacenters leste e oeste de JP)
- Austrália (datacenters do Leste dos EUA e sudeste)
- LATAM (Sul do Brasil)
- África (Norte da África do Sul)

## <a name="media-traffic-codecs"></a>Tráfego de mídia: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Segmento entre o SBC e o Processador de Mídia de Nuvem ou o cliente do Microsoft Teams

Aplica-se a maiúsculas e minúsculas de bypass de mídia e casos que não são de bypass.

A interface de Roteamento Direto no segmento entre o Controlador de Borda da Sessão e o Processador de Mídia de Nuvem (sem bypass de mídia) ou entre o cliente do Teams e o SBC (se o Bypass de Mídia estiver habilitado) pode usar os seguintes codecs:

- Bypass de não mídia (SBC para processador de mídia de nuvem): SILK, G.711, G.722, G.729
- Bypass de mídia (SBC para cliente do Teams): SILK, G.711, G.722, G.729

Você pode forçar o uso do codec específico no Controlador de Borda de Sessão excluindo codecs indesejáveis da oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Segmento entre o Cliente do Microsoft Teams e o Processador de Mídia de Nuvem

Aplica-se somente a maiúsculas e minúsculas que não são de bypass de mídia. Com o Bypass de Mídia, a mídia flui diretamente entre o cliente do Teams e o SBC.

No segmento entre o Processador de Mídia de Nuvem e o cliente do Microsoft Teams, o SILK ou o G.722 é usado. A opção de codec nessa etapa é baseada em algoritmos da Microsoft, que levam em consideração vários parâmetros. 

  > [!NOTE]
  > Não há suporte para o direcionamento de mídia. Durante uma chamada de Roteamento Direto, se o SBC enviar um novo IP de mídia para o Roteamento Direto do Teams, embora seja negociado na sinalização SIP, a mídia nunca será enviada para o novo endereço IP do Roteamento Direto do Teams.

## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borda de sessão com suporte (SBCs)

A Microsoft só dá suporte a SBCs certificados para emparelhar com o Roteamento Direto. Como Enterprise Voice é essencial para empresas, a Microsoft executa testes intensivos com os SBCs selecionados e trabalha com os fornecedores SBC para garantir que os dois sistemas sejam compatíveis. 

Os dispositivos que foram validados são listados como Certificados para Roteamento Direto do Teams. Os dispositivos certificados têm a garantia de funcionar em todos os cenários. 

Para obter mais informações sobre SBCs com suporte, consulte [Controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Confira também

[Configurar o Roteamento Direto](direct-routing-configure.md)
