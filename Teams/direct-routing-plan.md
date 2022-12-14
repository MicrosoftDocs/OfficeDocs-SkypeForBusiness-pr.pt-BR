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
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Saiba como Microsoft Roteamento Direto permite conectar um SBC (Controlador de Borda de Sessão) fornecido pelo cliente com suporte ao Sistema de Telefonia.
ms.openlocfilehash: 811115c23d88ff3ce1b7fa6af8f8757afb33fecf
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392321"
---
# <a name="plan-direct-routing"></a>Planejar o Roteamento Direto

> [!Tip]
> Assista à sessão a seguir para saber mais sobre os benefícios do Roteamento Direto, como planejar e como implantá-lo: [Roteamento Direto no Microsoft Teams](https://aka.ms/teams-direct-routing)

O Roteamento Direto permite conectar um SBC (Controlador de Borda de Sessão) fornecido pelo cliente com suporte ao Sistema de Telefonia. Com esse recurso, você pode configurar a conectividade PSTN (Rede Telefônica Comutada Pública) local com Microsoft cliente do Teams, conforme mostrado no seguinte diagrama: 

![Diagrama mostrando a configuração da conectividade PSTN local.](media/PlanDirectRouting1-PSTNwithTeams.png "Configuração da conectividade PSTN local com Microsoft cliente do Teams")

  > [!NOTE]
  > Skype for Business Online também permite emparelhar um SBC fornecido pelo cliente, mas isso requer uma implantação Skype for Business Server local ou uma edição especial de Skype for Business, chamada Cloud Connector, entre o SBC e o Microsoft Cloud. Esse cenário é conhecido como voz híbrida. Em contraste, o Roteamento Direto permite uma conexão direta entre o SBC com suporte e o Microsoft Cloud.

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [o Roteamento Direto](direct-routing-landing-page.md). 

Com o Roteamento Direto, você pode conectar seu SBC a quase qualquer tronco de telefonia ou interconexão com equipamentos PSTN de terceiros. O Roteamento Direto permite: 

- Use praticamente qualquer tronco PSTN com o Sistema de Telefone. 

- Configure a interoperabilidade entre equipamentos de telefonia de propriedade do cliente, como uma PBX (troca de ramificação privada) de terceiros, dispositivos analógicos e Teams.

Microsoft também oferece soluções de voz na nuvem, como o Plano de Chamada. No entanto, uma solução de voz híbrida pode ser melhor para sua organização se: 

- Microsoft Plano de Chamada não está disponível em seu país. 

- Sua organização requer conexão com dispositivos analógicos de terceiros, call centers e assim por diante. 

- Sua organização tem um contrato existente com uma operadora PSTN.

O Roteamento Direto também dá suporte aos usuários que têm a licença adicional para o Plano de Chamada Microsoft. Para obter mais informações, consulte [Sistema telefônico e planos de chamada](calling-plan-landing-page.md). 

Com o Roteamento Direto, quando os usuários participam de uma conferência agendada, o número de discagem é fornecido pelo serviço Microsoft Audio Conferencing, que requer o licenciamento adequado.  Ao discar, o serviço Microsoft Audio Conferencing coloca a chamada usando recursos de chamada online, o que requer o licenciamento adequado. (Observe que, se um usuário não tiver uma licença de Conferência de Áudio Microsoft, a chamada será roteada por meio do Roteamento Direto.) Para obter mais informações, confira [Reuniões Online com o Teams](https://www.microsoft.com/en-us/microsoft-teams/online-meetings). 
 
Planejar a implantação do Roteamento Direto é fundamental para uma implementação bem-sucedida. Este artigo descreve os requisitos de infraestrutura e licenciamento e fornece informações sobre conectividade SBC: 

- [Requisitos de infraestrutura](#infrastructure-requirements)
- [Licenciamento e outros requisitos](#licensing-and-other-requirements)
- [Nomes de domínio SBC](#sbc-domain-names)
- [Certificado de confiança pública para o SBC](#public-trusted-certificate-for-the-sbc)
- [Sinalização SIP: FQDNs](#sip-signaling-fqdns)
- [Sinalização SIP: portas](#sip-signaling-ports)
- [Tráfego de mídia: intervalos de portas](#media-traffic-port-ranges)
- [Controladores de borda de sessão com suporte (SBCs)](#supported-session-border-controllers-sbcs)

Para obter informações detalhadas sobre como configurar o [Roteamento Direto, consulte Configurar o Roteamento Direto](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
Os requisitos de infraestrutura para os SBCs, domínios e outros requisitos de conectividade de rede com suporte para implantar o Roteamento Direto estão listados na tabela a seguir:  

|Requisito de infraestrutura|Você precisa do seguinte|
|:--- |:--- |
|Controlador de Borda de Sessão (SBC)|Um SBC com suporte. Para obter mais informações, consulte [SBCs com suporte](#supported-session-border-controllers-sbcs).|
|Troncos de telefonia conectados ao SBC|Um ou mais troncos de telefonia conectados ao SBC. Em uma extremidade, o SBC se conecta ao Sistema telefônico por meio do Roteamento Direto. O SBC também pode se conectar a entidades de telefonia de terceiros, como PBXs, Adaptadores de Telefonia Analógica e assim por diante. Qualquer opção de conectividade PSTN conectada ao SBC funcionará. (Para configuração dos troncos PSTN para o SBC, consulte os fornecedores SBC ou provedores de tronco.)|
|Microsoft organização 365|Um Microsoft organização 365 que você usa para abrigar seus usuários do Microsoft Teams e a configuração e conexão com o SBC.|
|Registrador de usuários|O usuário deve ser hospedado no Microsoft 365.<br/>Se sua empresa tiver um ambiente local Skype for Business ou Lync com conectividade híbrida para Microsoft 365, você não poderá habilitar a voz no Teams para um usuário hospedado no local.<br/><br/>Para verificar o registrador de um usuário, use o seguinte cmdlet do PowerShell online Skype for Business:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>A saída do cmdlet deve mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domínios|Um ou mais domínios adicionados às organizações Microsoft 365 ou Office 365.<br/><br/>Observe que você não pode usar o domínio padrão , \*.onmicrosoft.com, que é criado automaticamente para seu locatário.<br/><br/>Para exibir os domínios, você pode usar o seguinte cmdlet do PowerShell online Skype for Business:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obter mais informações sobre domínios e Microsoft 365 ou organizações de Office 365, consulte [Perguntas frequentes sobre domínios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Endereço IP público para o SBC|Um endereço IP público que pode ser usado para se conectar ao SBC. Com base no tipo de SBC, o SBC pode usar NAT.|
|FQDN (Nome de Domínio Totalmente Qualificado) para o SBC|Um FQDN para o SBC, em que a parte de domínio do FQDN é um dos domínios registrados em sua organização Microsoft 365 ou Office 365. Para obter mais informações, consulte [Nomes de domínio SBC](#sbc-domain-names).|
|Entrada DNS pública para o SBC |Uma entrada DNS pública mapeando o SBC FQDN para o Endereço IP público. |
|Certificado de confiança pública para o SBC |Um certificado para o SBC a ser usado para toda a comunicação com o Roteamento Direto. Para obter mais informações, consulte [Certificado de confiança pública para o SBC](#public-trusted-certificate-for-the-sbc).|
|Pontos de conexão para Roteamento Direto |Os pontos de conexão do Roteamento Direto são os três FQDNs a seguir:<br/><br/>`sip.pstnhub.microsoft.com` – FQDN global deve ser testado primeiro.<br/>`sip2.pstnhub.microsoft.com` – FQDN secundário, mapeia geograficamente para a região de segunda prioridade.<br/>`sip3.pstnhub.microsoft.com` – FQDN terciário, mapeia geograficamente para a terceira região de prioridade.<br/><br/>Para obter informações sobre os requisitos de configuração, consulte [Sinalização SIP: FQDNs](#sip-signaling-fqdns).|
|Endereços IP de firewall e portas para mídia de roteamento direto |O SBC se comunica com os seguintes serviços na nuvem:<br/><br/>Proxy SIP, que manipula a sinalização<br/>Processador de Mídia, que manipula a mídia - exceto quando o Bypass de Mídia está ativado<br/><br/>Esses dois serviços têm endereços IP separados no Microsoft Cloud, descritos posteriormente neste documento.<br/><br/>Para obter mais informações, consulte a [seção Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) em [URLs e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges). |
|Perfil de transporte de mídia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Endereços IP de firewall e portas para Microsoft mídia do Teams |Para obter mais informações, consulte [URLs e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licenciamento e outros requisitos 

Os usuários do Roteamento Direto devem ter as seguintes licenças atribuídas no Microsoft 365: 

- sistema telefônico Microsoft
- Microsoft Teams + Skype for Business Plano 2, se incluído no licenciamento
- Microsoft AudioConferência (Leia as anotações e o parágrafo abaixo para obter exemplos específicos sobre quando essa licença é necessária.)

> [!NOTE]
> Skype for Business Plano não deve ser removido de nenhum contrato de licenciamento em que ele esteja incluído. 
> 
> [!IMPORTANT]
> Os usuários GCC High e DoD devem desabilitar qualquer licenciamento de Conferência de Áudio incluído no G5 e aguardar para habilitar qualquer Conferência de Áudio até que o Roteamento Direto tenha sido totalmente configurado. Os usuários devem ter números de telefone discados configurados e um bloco de discagem funcionando antes de habilitar licenças de Conferência de Áudio. Consulte [Conferência de Áudio com Roteamento Direto para GCC High e DoD](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) para obter mais detalhes.


> [!IMPORTANT]
>  Se você quiser adicionar participantes externos a reuniões agendadas, discando para eles ou fornecendo o número discado, a licença de conferência de áudio é necessária.
> Para GCC High e DoD, não atribua uma licença de Conferência de Áudio para usuários do G5. Para usuários do G3, não atribua uma licença de Conferência de Áudio até que o Roteamento Direto esteja totalmente configurado e o usuário tenha um bloco de discagem funcionando.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalonamento de chamadas ad hoc e licença de Conferência de Áudio

Um usuário do Teams pode iniciar uma chamada do Teams-to-PSTN ou do Teams-to-Teams e adicionar um participante PSTN a ele. Esse cenário é chamado de conferência ad hoc. O caminho que a chamada toma depende se o usuário que escala a chamada tem uma licença de Conferência de Áudio Microsoft atribuída ou não:

- **Se o usuário do Teams que escala a chamada tiver uma licença de Conferência de Áudio Microsoft atribuída**, o escalonamento ocorrerá por meio do serviço Microsoft Audio Conferencing. O participante do PSTN remoto que é convidado para a chamada existente recebe uma notificação sobre a chamada de entrada e vê o número da ponte Microsoft atribuída ao usuário do Teams que iniciou o escalonamento.

- **Se o usuário do Teams que escala a chamada não tiver a licença de Conferência de Áudio Microsoft atribuída**, o escalonamento ocorrerá por meio de um Controlador de Borda de Sessão conectado à interface de Roteamento Direto. O participante do PSTN remoto que é convidado para a chamada recebe uma notificação sobre a chamada de entrada e vê o número do usuário do Teams que iniciou o escalonamento. O SBC específico usado para o escalonamento é definido pela política de roteamento do usuário. 

Você deve garantir o seguinte:
 
- CsOnlineVoiceRoutingPolicy é atribuído ao usuário.

- Permitir chamadas privadas está habilitado no nível de locatário do Microsoft Teams.

O Roteamento Direto também dá suporte a usuários licenciados para Microsoft Plano de Chamada. O Sistema de Telefonia com Plano de Chamada pode rotear algumas chamadas usando a interface de Roteamento Direto. No entanto, os números de telefone dos usuários devem ser adquiridos online ou portados para Microsoft.  

A combinação de plano de chamada e conectividade de roteamento direto para o mesmo usuário é opcional, mas pode ser útil. Por exemplo, quando o usuário recebe um plano de chamada Microsoft, mas deseja rotear algumas chamadas usando o SBC. Um dos cenários mais comuns são chamadas para PBXs de terceiros.  Com PBXs de terceiros, todas as chamadas, exceto chamadas para os telefones conectados a esse PBX, são roteadas usando Microsoft Plano de Chamada, mas as chamadas para os telefones conectados a PBXs de terceiros vão para o SBC e, portanto, permanecem na rede corporativa e não no PSTN.

Para obter mais informações sobre o licenciamento do Sistema Telefônico, confira [Obter o máximo das Opções do Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) e [do Plano](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) e [Microsoft licenciamento de complemento do Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

## <a name="supported-end-points"></a>Pontos finais com suporte

Você pode usar como ponto de extremidade:

- Qualquer cliente do Teams.

- Telefones de área comum. Consulte [Configurar telefones de área comum para Microsoft Teams](./set-up-common-area-phones.md). Você não precisa de uma licença de Plano de Chamada ao configurar um telefone de área comum com Roteamento Direto.

- Skype for Business telefones 3PIP. Consulte [Skype for Business suporte a telefones (3PIP) com Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)

## <a name="sbc-domain-names"></a>Nomes de domínio SBC

O nome de domínio SBC deve ser de um dos nomes registrados em Domínios do locatário. Você não pode usar o \*locatário .onmicrosoft.com para o nome FQDN do SBC.

A tabela a seguir mostra exemplos de nomes DNS registrados para o locatário, se o nome pode ser usado como FQDN para o SBC e exemplos de nomes FQDN válidos:

|Nome DNS|Pode ser usado para SBC FQDN|Exemplos de nomes FQDN|
|:--- |:--- |:--- |
contoso.com|Sim|**Nomes válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Não|Não há suporte para o uso de domínios *.onmicrosoft.com para nomes SBC

Suponha que você queira usar um novo nome de domínio. Por exemplo, seu locatário tem contoso.com como um nome de domínio registrado em seu locatário e você deseja usar sbc1.sip.contoso.com. Antes de emparelhar um SBC com o nome sbc1.sip.contoso.com, você deve registrar o nome de domínio sip.contoso.com em Domínios em seu locatário. Se você tentar emparelhar um SBC com sbc1.sip.contoso.com antes de registrar o nome de domínio, receberá o seguinte erro: "Não é possível usar o domínio "sbc1.sip.contoso.com", pois ele não foi configurado para esse locatário."

Depois de adicionar o nome de domínio, você também precisa criar um usuário com o UPN user@sip.contoso.com e atribuir uma licença do Teams. Pode levar até 24 horas para provisionar totalmente o nome de domínio depois que ele é adicionado aos Domínios do seu locatário, um usuário com um novo nome é criado e uma licença é atribuída ao usuário.

É possível que uma empresa tenha vários espaços de endereço SIP em um locatário. Por exemplo, uma empresa pode ter contoso.com como um espaço de endereço SIP e fabrikam.com como o segundo espaço de endereço SIP. Alguns usuários têm user@contoso.com de endereço e alguns usuários têm user@fabrikam.com de endereço. 

O SBC só precisa de um FQDN e pode atender usuários de qualquer espaço de endereço no locatário emparelhado. Por exemplo, um SBC com o nome sbc1.contoso.com pode receber e enviar o tráfego PSTN para usuários com endereços user@contoso.com e user@fabrikam.com desde que esses espaços de endereço SIP sejam registrados no mesmo locatário.  

 > [!NOTE]
 > O SBC FQDN em Serviços de Comunicação do Azure roteamento direto deve ser diferente do SBC FQDN no Roteamento Direto do Teams.
  
## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado de confiança pública para o SBC

Microsoft recomenda que você solicite o certificado para o SBC gerando uma CSR (solicitação de assinatura de certificação). Para obter instruções específicas sobre como gerar um CSR para um SBC, consulte as instruções de interconexão ou a documentação fornecidas pelos fornecedores do SBC.

> [!NOTE]
> A maioria das Autoridades de Certificado (CAs) exige que o tamanho da chave privada seja pelo menos 2048. Tenha isso em mente ao gerar o CSR.

O certificado precisa ter o SBC FQDN como o nome comum (CN) ou o campo SAN (nome alternativo do assunto).

Como alternativa, o Roteamento Direto dá suporte a um curinga na CN e/ou SAN e o curinga precisa estar em conformidade com o [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1) padrão.

Um exemplo seria usar \*o .contoso.com que corresponderia ao sbc.contoso.com do SBC FQDN, mas não corresponderia ao sbc.test.contoso.com.

A interface SIP de roteamento direto só confiará em certificados assinados por CAs (Autoridades de Certificado) que fazem parte do programa de certificado raiz confiável Microsoft. Verifique se o certificado SBC é assinado por uma AC que faz parte do programa e que a extensão EKU (Uso de Chave Estendida) do certificado inclui Autenticação de Servidor.
Saiba mais: [Requisitos do programa – Microsoft programa raiz confiável](/security/trusted-root/program-requirements)
  
[Lista de certificados da AC incluída](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 Para o Roteamento Direto em ambientes GCCH e DoD Office 365, o certificado precisa ser gerado por uma das seguintes autoridades de certificado raiz:

- Ac raiz global do DigiCert
- Ac raiz de EV do DigiCert High Assurance

> [!NOTE]
> Se o suporte ao MTLS (Mutual TLS) estiver habilitado para a conexão do Teams no SBC, você deverá instalar o Baltimore CyberTrust Root e os certificados DigiCert Global Root G2 no Repositório Raiz Confiável do SBC do contexto TLS do Teams. (Isso ocorre porque os certificados de serviço Microsoft usam um desses dois certificados raiz.) Para baixar esses certificados raiz, consulte [Office 365 Cadeias de criptografia](/microsoft-365/compliance/encryption-office-365-certificate-chains). Para obter mais detalhes, confira [Alterações de certificado do Office TLS](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes).

## <a name="sip-signaling-fqdns"></a>Sinalização SIP: FQDNs

O Roteamento Direto é oferecido nos seguintes ambientes:

- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Saiba mais sobre [Office 365 e ambientes do governo dos EUA](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government), como GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft ambientes de GCC 365, Office 365 e Office 365

Os pontos de conexão do Roteamento Direto são os três FQDNs a seguir:

- **sip.pstnhub.microsoft.com** – FQDN global – deve ser julgado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS do Microsoft Azure retornam um endereço IP apontando para o datacenter principal do Azure atribuído ao SBC. A atribuição é baseada em métricas de desempenho dos datacenters e proximidade geográfica com o SBC. O endereço IP retornado corresponde ao FQDN primário.

- **sip2.pstnhub.microsoft.com** – FQDN secundário – mapeia geograficamente para a região de segunda prioridade.

- **sip3.pstnhub.microsoft.com** – FQDN terciário – mapeia geograficamente para a terceira região de prioridade.

Colocar esses três FQDNs em ordem é necessário para:

- Forneça uma experiência ideal (menos carregada e mais próxima do datacenter SBC atribuído consultando o primeiro FQDN).

- Forneça failover quando a conexão de um SBC é estabelecida para um datacenter que está enfrentando um problema temporário. Para obter mais informações, confira [Mecanismo de failover](#failover-mechanism-for-sip-signaling) abaixo.  

As FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com – serão resolvidas em endereços IP das seguintes sub-redes:

- 52.112.0.0/14
- 52.122.0.0/15

Você precisa abrir portas para todos esses intervalos de endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-gcc-dod-environment"></a>Ambiente do Office GCC DoD

O ponto de conexão do Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.dod.teams.microsoft.us** – FQDN global. Como o ambiente Office 365 DoD existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O sip.pstnhub.dod.teams.microsoft.us FQDN será resolvido para um endereço IP da seguinte sub-rede:

- 52.127.64.0/21

Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente do GCC High

O ponto de conexão do Roteamento Direto é o seguinte FQDN:

**sip.pstnhub.gov.teams.microsoft.us** – FQDN global. Como o ambiente GCC High existe apenas nos data centers dos EUA, não há FQDNs secundários e terciários.

O sip.pstnhub.gov.teams.microsoft.us FQDN será resolvido para um endereço IP da seguinte sub-rede:

- 52.127.88.0/21

Você precisa abrir portas para todos esses endereços IP no firewall para permitir o tráfego de entrada e saída de e para os endereços para sinalização.

## <a name="sip-signaling-ports"></a>Sinalização SIP: portas

Você deve usar as seguintes portas para ambientes Microsoft 365 ou Office 365 em que o Roteamento Direto é oferecido:

- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Definido no SBC (para Office 365 a porta GCC High/DoD 5061 deve ser usada)|
SIP/TLS|SBC|SIP Proxy|Definido no SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de failover para sinalização SIP

O SBC faz uma consulta DNS para resolver sip.pstnhub.microsoft.com. Com base no local do SBC e nas métricas de desempenho do datacenter, o datacenter primário é selecionado. Se o datacenter primário tiver um problema, o SBC tentará o sip2.pstnhub.microsoft.com, que se resolve para o segundo datacenter atribuído e, no caso raro, que os datacenters em duas regiões não estão disponíveis, o SBC tenta novamente o último FQDN (sip3.pstnhub.microsoft.com), que fornece o IP do datacenter terciário.

A tabela a seguir resume as relações entre datacenters primários, secundários e terciários:

|Se o datacenter primário for|EMEA|NOAM|ÁSIA|
|:--- |:--- |:--- |:--- |
|O datacenter secundário (sip2.pstnhub.microsoft.com)|NOS|UE|NOS|
|O datacenter terciário (sip3.pstnhub.microsoft.com)|ÁSIA|ÁSIA|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfego de mídia: intervalos de portas

Observe que os requisitos abaixo se aplicam se você quiser implantar o Roteamento Direto sem Bypass de Mídia. Para obter requisitos de firewall para Bypass de Mídia, consulte [Planejar bypass de mídia com Roteamento Direto](./direct-routing-plan-media-bypass.md).

O tráfego de mídia flui de e para um serviço separado no Microsoft Cloud. Os intervalos de endereços IP para tráfego de mídia são os seguintes.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft ambientes de GCC 365, Office 365 e Office 365

- 52.112.0.0/14 (endereços IP de 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (endereços IP de 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>ambiente do DoD Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente do GCC High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de portas (aplicável a todos os ambientes)

O intervalo de portas dos Processadores de Mídia é mostrado na seguinte tabela:

|Tráfego|De|Até|Porta de origem|Porta de destino|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processador de Mídia|SBC|3478-3481 e 49152 – 53247|Definido no SBC|
|UDP/SRTP|SBC|Processador de Mídia|Definido no SBC|3478-3481 e 49152 – 53247|

  > [!NOTE]
  > Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.

## <a name="media-traffic-media-processors-geography"></a>Tráfego de mídia: geografia dos processadores de mídia

O tráfego de mídia flui por meio de componentes chamados processadores de mídia. Os processadores de mídia são colocados nos mesmos datacenters que os proxies SIP:

- NOAM (Centro-Sul dos EUA, dois em datacenters do Oeste dos EUA e leste dos EUA)
- Europa (datacenters do Sul do Reino Unido, França Central, Amsterdã e Dublin)
- Ásia (datacenter de Cingapura)
- Japão (datacenters jp leste e oeste)
- Austrália (datacenters do Leste e Sudeste da UA)
- LATAM (Sul do Brasil)

## <a name="media-traffic-codecs"></a>Tráfego de mídia: Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Perna entre o SBC e o processador de mídia na nuvem ou Microsoft cliente do Teams

Aplica-se a casos de bypass de mídia e casos de não bypass.

A interface de Roteamento Direto na perna entre o Controlador de Borda de Sessão e o Processador de Mídia na Nuvem (sem bypass de mídia) ou entre o cliente do Teams e o SBC (se o Bypass de Mídia habilitado) pode usar os seguintes codecs:

- Bypass sem mídia (SBC para Processador de Mídia na Nuvem): SILK, G.711, G.722, G.729
- Bypass de Mídia (cliente SBC para Teams): SILK, G.711, G.722, G.729

Você pode forçar o uso do codec específico no Controlador de Borda de Sessão excluindo codecs indesejáveis da oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Perna entre Microsoft cliente do Teams e processador de mídia na nuvem

Aplica-se apenas a casos de bypass que não são de mídia. Com o Bypass de Mídia, a mídia flui diretamente entre o cliente do Teams e o SBC.

Na perna entre o Processador de Mídia na Nuvem e Microsoft cliente do Teams, SILK ou G.722 são usados. A escolha do codec nesta perna baseia-se em algoritmos de Microsoft, que levam em consideração vários parâmetros.

  > [!NOTE]
  > Não há suporte para o direcionamento de mídia. Durante uma chamada de Roteamento Direto, se o SBC enviar um novo IP de mídia para o Roteamento Direto do Teams, embora seja negociado na sinalização SIP, a mídia nunca será enviada para o novo endereço IP do Roteamento Direto do Teams.

## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borda de sessão com suporte (SBCs)

Microsoft só dá suporte a SBCs certificados para emparelhar com o Roteamento Direto. Como Enterprise Voice é fundamental para as empresas, Microsoft executa testes intensivos com os SBCs selecionados e trabalha com os fornecedores SBC para garantir que os dois sistemas sejam compatíveis.

Os dispositivos que foram validados são listados como Certificados para Roteamento Direto do Teams. Os dispositivos certificados são garantidos para funcionar em todos os cenários.

Para obter mais informações sobre SBCs com suporte, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).

## <a name="support-boundaries"></a>Limites de suporte

A Microsoft só dá suporte ao Sistema de Telefonia com Roteamento Direto quando usado com dispositivos certificados. Em caso de problemas, você deve entrar em contato com o atendimento ao cliente do fornecedor SBC primeiro. Se necessário, o fornecedor do SBC encaminhará o problema para a Microsoft por meio de canais internos. A Microsoft reserva-se o direito de rejeitar casos de suporte em que um dispositivo não certificado está conectado ao Sistema de Telefonia por meio do Roteamento Direto. Se a Microsoft determinar que o problema de Roteamento Direto de um cliente é com o dispositivo SBC de um fornecedor, o cliente precisará reengajar o fornecedor SBC para obter suporte.

## <a name="see-also"></a>Confira também

[Configurar o Roteamento Direto](direct-routing-configure.md)
