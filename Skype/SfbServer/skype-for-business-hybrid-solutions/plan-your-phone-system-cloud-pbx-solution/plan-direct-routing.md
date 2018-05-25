---
title: Planejar o roteamento direto
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/15/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Leia este tópico para saber como roteamento direto do Microsoft telefone sistema permite que você se conectar a um controlador de borda de sessão (SBC) com suporte, fornecida pelo cliente ao sistema de telefone da Microsoft.
ms.openlocfilehash: 9809c4acb5d80f18dc076b07e81c052caa6fbc0d
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="plan-direct-routing"></a>Planejar o roteamento direto

  > [!NOTE]
  > Esta é uma versão de visualização de roteamento direto do Microsoft Phone System.  Documentação e funcionalidades do produto estão sujeitos a alterações.

Roteamento direto do Microsoft telefone sistema permite que você se conectar a um controlador de borda de sessão (SBC) com suporte, fornecida pelo cliente ao sistema de telefone da Microsoft.  Com esse recurso, por exemplo, você pode configurar a conectividade de PSTN local com o cliente Microsoft Teams, conforme mostrado no diagrama a seguir: 

![Mostra a configuração da conectividade PSTN local com o cliente do Microsoft Teams](../../media/PlanDirectRouting1-PSTNwithTeams.png)

  > [!NOTE]
  > Skype para Business Online também permite que você par um SBC fornecido pelo cliente, mas isso requer um Skype local para a implantação de servidor de negócios ou uma edição especial do Skype para os negócios, chamado conector de nuvem, entre o SBC e o Microsoft Cloud. Este cenário é conhecido como voz híbrida. Por outro lado, o roteamento direto permite que uma conexão direta entre o SBC com suporte e o Microsoft Cloud. 

Com o roteamento direto, você pode conectar seu SBC praticamente qualquer tronco de telefonia ou interconnect com o equipamento de rede de telefônica pública comutada (PSTN) de terceiros. Roteamento direto permite que você: 

- Use praticamente qualquer tronco PSTN com Microsoft Phone System. 
- Configure a interoperabilidade entre o equipamento de telefonia de propriedade do cliente, uma troca de terceiros privada de comutação (PBX), dispositivos analógicos e Microsoft Phone System.

A Microsoft também oferece soluções de voz all nuvem, como planejar a chamada.  No entanto, uma solução híbrida de voz pode ser mais adequada para sua organização se: 

- Chamar plano Microsoft não está disponível em seu país. 
- Sua organização exige conexão para dispositivos analógicos de terceiros, centros de chamada e assim por diante. 
- Sua organização tem um contrato existente com uma operadora de telefonia PSTN.

Roteamento direto também oferece suporte a usuários que têm a licença adicional para o Microsoft chamar plano. Para obter mais informações, consulte [Chamando planos no Office 365](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365) e o [licenciamento e outros requisitos](#licensing-and-other-requirements). 

Com o roteamento direto, quando os usuários participem de uma conferência agendada, o número de discagem é fornecido pelo serviço de conferência de áudio da Microsoft, que requer o licenciamento correto.  Ao fazer chamadas, o serviço de conferência de áudio Microsoft coloca a chamada usando os recursos de chamada online, que requer o licenciamento correto. (Observe que a discagem externa não é roteado por meio de roteamento direto). Para obter mais informações, consulte [Reuniões Online com equipes](https://products.office.com/en-us/microsoft-teams/online-meeting-solutions). 
 
Planejamento da implantação do roteamento direto é fundamental para uma implementação bem-sucedida. Este artigo descreve os requisitos de licenciamento e de infraestrutura e fornece informações sobre conectividade SBC: 

- [Requisitos de infraestrutura](#infrastructure-requirements)
- [Licenciamento e outros requisitos](#licensing-and-other-requirements)
- [Nomes de domínio SBC](#sbc-domain-names)
- [Certificado confiável público para o SBC](#public-trusted-certificate-for-the-sbc)
- [Sinalização SIP: FQDNs e portas de firewall](#sip-signaling-fqdns-and-firewall-ports)
- [Tráfego de mídia: intervalos de endereços IP e porta](#media-traffic-ip-addresses-and-port-ranges)
- [SBCs com suporte](#supported-session-border-controllers-sbcs)

Para obter informações detalhadas sobre como configurar o roteamento direto, consulte [Configurar o roteamento direto](configure-direct-routing.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura
Os requisitos de infraestrutura para os SBCs com suporte, domínios e outros requisitos de conectividade de rede para implantar o roteamento direto estão listados na tabela a seguir:  

|**Requisito de infraestrutura**|**Você precisará dos seguintes itens**|
|:--- |:--- |
|Controlador de borda de sessão (SBC)|Um SBC com suporte. Para obter mais informações, consulte [SBCs suportados](#supported-session-border-controllers-sbcs).|
|Troncos de telefonia conectados ao SBC|Um ou mais troncos de telefonia conectados ao SBC. Em uma extremidade, o SBC conecta-se ao sistema telefônico Microsoft via roteamento direto. O SBC também pode se conectar ao entidades de telefonia de terceiros, como PBXs, adaptadores de telefonia analógico e assim por diante. Qualquer opção de conectividade PSTN conectada ao SBC funcionará. (Observação: configuração de troncos PSTN para SBC, consulte os fornecedores SBC ou provedores de tronco.)|
|Locatário do Office 365|Um locatário do Office 365 que você pode usar para hospedar os usuários Teams da Microsoft e a configuração e a conexão para o SBC.|
|Registrador do usuário|Usuário deve ser hospedado no Office 365.<br/>Se sua empresa tiver Skype um local para o ambiente de negócios ou no Lync com conectividade híbrida para o Office 365, não será possível habilitar voz em equipes para um usuário hospedado no local.<br/><br/>Para verificar o registrador de um usuário, use a seguinte Skype para o cmdlet do PowerShell Online de negócios:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>A saída do cmdlet deve mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domínios|Um ou mais domínios adicionados ao seus locatários do Office 365.<br/><br/>**Observação:** Não é possível utilizar o domínio padrão, *. onmicrosoft.com, que é criado automaticamente para o seu locatário.<br/><br/>Para exibir os domínios, você pode usar o Skype o seguinte cmdlet do PowerShell Online de negócios:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obter mais informações sobre os domínios e locatários do Office 365, consulte [FAQ de domínios](https://support.office.com/en-us/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Endereço IP público para o SBC|Um endereço IP público que pode ser usado para conexão com o SBC. Com base no tipo de SBC, o SBC pode usar NAT.|
|Nome de domínio totalmente qualificado (FQDN) para o SBC|Um FQDN para o SBC, onde a parte de domínio do FQDN é um dos domínios registrados no seu locatário do Office 365. Para obter mais informações, consulte [nomes de domínio SBC](#sbc-domain-names).|
|Entrada DNS pública para o SBC |Uma entrada de DNS pública mapear o FQDN SBC para o endereço IP público. |
|Certificado confiável público para o SBC |Um certificado para o SBC a ser usado para toda a comunicação com o roteamento direto. Para obter mais informações, consulte o [certificado público de confiável para o SBC](#public-trusted-certificate-for-the-sbc).|
|Pontos de Conexão para roteamento direto |Os pontos de conexão para roteamento direto são os FQDNs de três seguintes:<br/><br/>```sip.pstnhub.microsoft.com```– FQDN global, deve ser tentado primeiro.<br/>```sip2.pstnhub.microsoft.com```– FQDN secundário, geograficamente mapeia à segunda região prioridade.<br/>```sip3.pstnhub.microsoft.com```– FQDN terciária, geograficamente mapeia para a região de prioridade de terceiro.<br/><br/>Para obter informações sobre os requisitos de configuração, consulte [a sinalização SIP: FQDNs e portas do firewall](#sip-signaling-fqdns-and-firewall-ports).|
|Endereços IP do firewall e portas de mídia de roteamento direto |O SBC se comunica com os seguintes serviços na nuvem:<br/><br/>Proxy, que trata a sinalização SIP<br/>Processador de mídia, que trata a mídia-, exceto quando o desvio de mídia está ligado<br/><br/>Esses dois serviços tem endereços IP separados no Microsoft Cloud, descrito mais adiante neste documento.<br/><br/>Para obter mais informações, consulte a [seção de equipes da Microsoft](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) em [URLs do Office 365 e intervalos de endereços IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2). |
|Perfil de transporte de mídia|RTP/TCP/SAVP <br/>RTP/UDP/SAVP|
Endereços IP do firewall e portas de mídia Teams da Microsoft |Para obter mais informações, consulte [URLs do Office 365 e intervalos de endereços IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2). |
|||

## <a name="licensing-and-other-requirements"></a>Licenciamento e outros requisitos 

Usuários de roteamento direto devem ter as seguintes licenças atribuídas no Office 365: 

- Skype for Business Online (Plan 2) 
- Sistema telefônico da Microsoft 
- Microsoft Teams 
- Conferência de áudio da Microsoft 

A licença de conferência de áudio é necessária para a adição de participantes externos para reuniões agendadas, discando a eles para acessá-los ou fornecendo o número de discagem. 
 
  > [!NOTE]
  > A licença de E5 inclui o sistema telefônico e audioconferência.   

Além disso, você deve garantir que o seguinte:
 
- CsOnlineVoiceRoutingPolicy é atribuída ao usuário. 
- Permitir que chamar privada está habilitado no nível do locatário for Microsoft Teams. 

Roteamento direto também oferece suporte a usuários que são licenciados para chamar plano Microsoft. Microsoft System de telefone com chamar planejar pode rotear algumas chamadas usando a interface de roteamento direto. No entanto, os números de telefone dos usuários devem ser tanto adquiridos online ou migrados para o Microsoft.  

Combinação de conectividade de chamada planejar e roteamento direto para o mesmo usuário é opcional, mas pode ser útil, por exemplo, quando o usuário é atribuído a um Microsoft chamar planejar mas deseja rotear algumas chamadas via SBC. Um dos cenários mais comuns são chamadas para PBXs de terceiros.  Com terceiros PBXs, todas as chamadas, exceto as chamadas para os telefones conectados a esse PBXs, são roteadas via chamar plano Microsoft; mas chamadas para os telefones conectados a terceiros PBXs ir para o SBC, portanto ficar dentro da rede corporativa e não à PSTN. 

Para obter mais informações sobre o licenciamento do sistema telefônico, consulte [obter o máximo do Office com o Office 365](https://products.office.com/en-us/compare-all-microsoft-office-products?tab=2) e [Opções de planejamento do Office 365](https://technet.microsoft.com/en-us/library/office-365-plan-options.aspx). 

Para obter mais informações sobre o licenciamento do sistema telefônico, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing). 

## <a name="sbc-domain-names"></a>Nomes de domínio SBC

O nome de domínio SBC deve ser um dos nomes registrados no "Domínios" do inquilino. Não é possível usar o *. onmicrosoft.com locatário para o nome FQDN do SBC.

A tabela a seguir mostra exemplos de nomes DNS registrados para o locatário, se o nome pode ser usado como um FQDN para o SBC e exemplos de nomes de FQDN válidos:

|**Nome DNS**|**Pode ser usado para o FQDN de SBC**|**Exemplos de nomes de FQDN**|
|:--- |:--- |:--- |
Contoso.com|Sim|**Nomes válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>Europe.contoso.com|
|Contoso.onmicrosoft.com|Não|**Nome inválido não:**<br/>sbc1.Europe.contoso.com (requer registrando europe.contoso.com de nome de domínio em "Domínios" primeiro)
|

É possível que uma empresa pode ter vários espaços de endereçamento SIP em um locatário. Por exemplo, uma empresa pode ter contoso.com como um espaço de endereço SIP e fabrikam.com como o espaço de endereço SIP segundo. Alguns usuários têm endereço user@contoso.com e alguns usuários têm user@fabrikam.com endereço. 

O SBC só precisa de um FQDN e pode atender usuários de qualquer espaço de endereçamento no locatário emparelhado. Por exemplo, um SBC com o nome de sbc1.contoso.com pode receber e enviar o tráfego PSTN para usuários com endereços user@contoso.com e user@fabrikam.com, desde que esses espaços de endereçamento SIP registrados no mesmo inquilino.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado confiável público para o SBC

A Microsoft recomenda que você solicitou o certificado para o SBC gerando uma certificação da assinatura CSR (solicitação). Para obter instruções específicas sobre gerando uma CSR para um SBC, consulte as instruções interconexão ou a documentação fornecida pelos seus fornecedores SBC. 

  > [!NOTE]
  > A maioria das autoridades de certificação (CAs) exigem o tamanho da chave particular seja pelo menos 2048. Lembre-se ao gerar o CSR.

O certificado precisa ter o SBC FQDN no assunto, nome comum ou campos de nome alternativo da entidade.

Como alternativa, roteamento direto suporta um curinga no nome ou SAN comuns e o caractere curinga precisa para se adequar ao padrão [RFC HTTP sobre TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Um exemplo estaria utilizando *. contoso.com no SAN, que o sbc.contoso.com SBC FQDN encontraria como correspondente, mas não seria coincidirem com sbc.test.contoso.com.

O certificado precisa ser gerado por uma das seguintes autoridades de certificação raiz:

- AddTrust externo da autoridade de certificação raiz
- Raiz do Baltimore CyberTrust
- Buypass
- Autoridade de certificação principal pública classe 3 
- CA de raiz Global DigiCert 
- Entrust
- GlobalSign
- Go Daddy
- VeriSign, Inc. 
- Raiz móvel Symantec Enterprise para Microsoft 
- Carimbo de hora Thawte CA
- Pela Trustwave.
- T-Systems internacional GmbH (marcos Telekom)
- QuoVadis

Microsoft está trabalhando na adição de autoridades de certificação adicionais com base em solicitações dos clientes. 

## <a name="sip-signaling-fqdns-and-firewall-ports"></a>Sinalização SIP: FQDNs e portas de firewall 

O ponto de conexão direta de roteamento são os FQDNs de três seguintes:

- **sip.pstnhub.microsoft.com** – Global FQDN – deve ser tentado primeiro. Quando o SBC envia uma solicitação para resolver esse nome, os servidores DNS da Microsoft Azure retornam um endereço IP apontando para o datacenter do Windows Azure primário atribuído para o SBC. Sobre as métricas de desempenho dos centros de dados e proximidade geográfica com o SBC baseia-se a atribuição. O endereço IP retornado corresponde ao FQDN principal.
- **sip2.pstnhub.microsoft.com** – secundário FQDN – geograficamente mapeia à segunda região prioridade.
- **sip3.pstnhub.microsoft.com** – terciária FQDN – geograficamente mapeia para a região de prioridade de terceiro.

É necessário para colocar esses três FQDNs na ordem:

- Fornecer uma experiência ideal (menos carregada e mais próxima para o datacenter SBC atribuído consultando o FQDN do primeiro).
- Fornece failover quando a conexão de um SBC é estabelecida com um datacenter que está experimentando um problema temporário. Para obter mais informações, consulte o [mecanismo de Failover](#failover-mechanism-for-sip-signaling) abaixo.  

Os FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com – será resolvidos para um dos seguintes endereços IP:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

Você precisará abrir portas para todos esses endereços IP no seu firewall para permitir o tráfego de entrada e saído de e para os endereços de sinalização.  Se seu firewall suporta nomes DNS, o FQDN sip-all.pstnhub.microsoft.com resolve para todos os endereços IP acima.  Você deve usar as seguintes portas:

|**Tráfego**|**De**|**Até**|**Porta de origem**|**Porta de destino**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|Proxy SIP|SBC|1024 – 65535|Definidos no SBC|
SIP/TLS|SBC|Proxy SIP|Definidos no SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de failover para a sinalização SIP

O SBC faz uma consulta DNS para resolver sip.pstnhub.microsoft.com. Com base no local de SBC e as métricas de desempenho do datacenter, o datacenter primário está selecionado. Se datacenter principal apresenta um problema, o SBC tentará sip2.pstnhub.microsoft.com, o que resolve para o segundo datacenter atribuído, e, no caso de rara que data centers em dois regiões não estão disponíveis, o SBC repete o último (do FQDN sip3.pstnhub.microsoft.com), que fornece o IP de datacenter terciário.

A tabela abaixo resume as relações entre data centers terciário principal e secundário:

|**Se for o datacenter primário**|**EMEA**|**NOAM**|**ÁSIA**|
|:--- |:--- |:--- |:--- |
|O datacenter secundário (sip2.pstnhub.microsoft.com)|CONOSCO|UE|CONOSCO|
|O datacenter terciário (sip3.pstnhub.microsoft.com)|ÁSIA|ÁSIA|UE|
|||||

## <a name="media-traffic-ip-addresses-and-port-ranges"></a>Tráfego de mídia: intervalos de endereços IP e porta

O tráfego de mídia flui de e para um serviço separado em que o Microsoft Cloud. O intervalo de IP dos processadores de mídia é mostrado na tabela a seguir:

|**Tráfego**|**De**|**Até**|**Porta de origem**|**Porta de destino**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processador de mídia|SBC|49 152 – 53 247|Definidos no SBC|
|UDP/SRTP|SBC|Processador de mídia|Definidos no SBC|49 152 – 53 247|
|

  > [!NOTE]
  > A Microsoft recomenda pelo menos duas portas por chamada simultânea no SBC.

## <a name="supported-session-border-controllers-sbcs"></a>Suporte para controladores de borda de sessão (SBCs)

Microsoft suporta apenas o SBC certified emparelhar com o roteamento direto. Como Enterprise Voice é fundamental para a empresa, Microsoft executa testes de uso intensivos com os selecionado SBCs e funciona com os fornecedores SBC para garantir que os dois sistemas é compatíveis. 

Os dispositivos que tiverem sido validados são listados como certificado para equipes direto roteamento. Os dispositivos de certificados são garantidos funcionem em todos os cenários. Também é um processo de suporte conjunto entre a Microsoft e os fornecedores SBC estabelecidos.  

Os seguintes fornecedores estiver sendo certified:
- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)
- Faixa de opções (anteriormente Sonus):
   - [Série de borda de SBC](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+SBC+Edge+1000+-+2000+for+Microsoft+Teams+Direct+Routing)
   - [SBC Core série TBD](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)
- ThinkTel: ThinkTel não vende os SBCs para as empresas, mas seu SBC está sendo certified.  
 
## <a name="see-also"></a>Consulte também

[Configurar o roteamento direto](configure-direct-routing.md)


