---
title: Requisitos de porta e protocolo para servidores
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumo: Revise as considerações de uso da porta antes de implementar Skype para Business Server.'
ms.openlocfilehash: 3de98f096215c8f703f23081d2b102d3d5c9ffac
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838604"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de porta e protocolo para servidores
 
**Resumo:** Revise as considerações de uso da porta antes de implementar Skype para Business Server.
  
Skype para Business Server requer que portas específicas nos firewalls internos e externos estejam abertos. Adicionalmente, se o protocolo IPsec (Internet Protocol security) tiver sido implantado em sua organização, ele deverá estar desabilitado no intervalo de portas usadas para a distribuição de áudio, vídeo e vídeo panorama. 
  
Isso pode parecer desanimador bit em um primeiro momento, o trabalho pesado para o planejamento, isso pode ser feito usando o [Skype para ferramenta de planejamento do Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Depois que você tiver ido pelas perguntas do assistente sobre quais recursos você planeja usar, para cada site que você define você pode exibir o relatório de Firewall dentro do relatório de administração de borda e use as informações na lista para criar regras de yourfirewall. Você também pode fazer ajustes muitos dos nomes e endereços IP usados para obter detalhes consulte [Review o relatório de Firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Lembre-Lembre-se pode exportar o relatório de administração de borda para uma planilha do Excel e o relatório de Firewall será uma das planilhas no arquivo. 
  
Você também pode encontrar as informações nestas tabelas no formulário de diagrama examinando o cartaz de cargas de trabalho de protocolo vinculado do artigo [Technical diagrams for Skype para Business Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Se você estiver implementando Skype para negócios Online (O365) consulte [URLs do Office 365 e intervalos de endereços IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Ambientes híbridos serão necessário fazer referência a este tópico e também a [requisitos de porta e protocolo](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#port-and-protocol-requirements)híbrida.
> - Você pode ter os firewalls de hardware ou software, podemos não exigem modelos específicos ou versões. O que importa é que portas são na lista branca, portanto, o firewall não prejudicar o funcionamento do Skype para Business Server.
  
## <a name="port-and-protocol-details"></a>Detalhes de protocolo e porta

Esta seção resume as portas e protocolos usados pelos servidores, balanceadores de carga e clientes em um Skype para implantação de servidor de negócios.
  
> [!NOTE]
> Quando Skype para Business Server é iniciado, ele abre as portas necessárias no Firewall do Windows. Já deve estar executando o Firewall do Windows em aplicativos mais normais, mas se ele não está sendo usado Skype para Business Server funcionará sem ele. 
  
Para obter detalhes sobre a configuração de firewall para componentes de borda, consulte [cenários de servidor de borda no Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno. 
  
**Portas do servidor necessárias (por Função de servidor)**

|Função de servidor|Nome do serviço|Porta|Protocolo|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Todos os servidores  |Navegador do SQL  |1434  |UDP  |Navegador do SQL para a cópia replicada local do banco de dados do repositório de gerenciamento Central.  |
|Servidores Front-End  |Skype para serviço de front-end Server de negócios  |5060  |TCP  |Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.  |
|Servidores Front-End  |Skype para serviço de front-end Server de negócios  |5061  | TCP (TLS) |Usada pelos servidores Standard Edition e pools de front-ends em todas as comunicações SIP internas entre servidores (MTLS), em comunicações SIP entre o servidor e o cliente (TLS) e em comunicações SIP entre os servidores front-end e os servidores de mediação (MTLS). Também é usada em comunicações com o Monitoring Server.  |
| Servidores Front-End |Skype para serviço de front-end Server de negócios  |444  | HTTPS <br/> TCP  |Usado para comunicação HTTPS entre o foco (o Skype para componente Business Server que gerencia o estado da conferência) e os servidores individuais.  <br/> Essa porta também é usada para comunicação TCP entre servidores Front-End e de aparelhos de filial persistente.  |
|Servidores Front-End  |Skype para serviço de front-end Server de negócios  |135  |DCOM e RPC (controle de procedimento remoto)  |Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.  |
|Servidores Front-End  |Skype para o serviço de conferência de mensagens Instantâneas do servidor de negócios  |5062  |TCP  |Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).  |
|Servidores Front-End  |Skype para serviço de Webconferência de servidor de negócios  |8057  |TCP (TLS)  |Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.  |
|Servidores Front-End  |Skype para serviço de compatibilidade de webconferência Business Server  |8058  |TCP (TLS)  |Usado para escutar conexões do modelo de objeto Persistent Shared (PSOM) do cliente do Live Meeting e de versões anteriores do Skype para Business Server.  |
|Servidores Front-End  |Skype para o serviço de conferência de áudio/vídeo do Business Server  |5063  |TCP  |Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).  |
|Servidores Front-End  |Skype para o serviço de conferência de áudio/vídeo do Business Server  |57501-65535  |TCP/UDP  |Intervalo de porta de mídia usado para videoconferência.  |
|Servidores Front-End  |Skype para serviço de compatibilidade da Web Server Business  |80  |HTTP  |Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.  |
|Servidores Front-End  |Skype para serviço de compatibilidade da Web Server Business  |443  |HTTPS  |Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).  |
|Servidores Front-End  |Skype para serviço de compatibilidade da Web Server Business  |8080  |TCP e HTTP  |Usado pelos componentes da Web para acesso externo.  |
|Servidores Front-End  |Servidor de componentes da Web  |4443  |HTTPS  |Comunicações entre pools de front-end HTTPS (de Proxy Reverso) e HTTPS para conexão de Descoberta automática.  |
|Servidores Front-End  |Servidor de componentes da Web  |8060  |TCP (MTLS)  ||
|Servidores Front-End  |Servidor de componentes da Web  |8061  |TCP (MTLS)  ||
|Servidores Front-End  |Componente dos serviços de mobilidade  |5086  |TCP (MTLS)  |Porta SIP usada pelos processos internos dos Serviços de Mobilidade  |
|Servidores Front-End  |Componente dos serviços de mobilidade  |5087  |TCP (MTLS)  |Porta SIP usada pelos processos internos dos Serviços de Mobilidade  |
|Servidores Front-End  |Componente dos serviços de mobilidade  |443  |HTTPS  ||
|Servidores Front-End  |Skype para o serviço Atendedor de conferência Business Server (conferência discada)  |5064  |TCP  |Usada para solicitações SIP de entrada para conferência discada.  |
|Servidores Front-End  |Skype para o serviço Atendedor de conferência Business Server (conferência discada)  |5072  |TCP  |Usado para solicitações SIP de entrada para Atendedor (discada).  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype para serviço de mediação do servidor de negócios  |5070  |TCP  |Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype para serviço de mediação do servidor de negócios  |5067  |TCP (TLS)  |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype para serviço de mediação do servidor de negócios  |5068  |TCP  |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype para serviço de mediação do servidor de negócios  |5081  |TCP  |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype para serviço de mediação do servidor de negócios  |5082  |TCP (TLS)  |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  |
|Servidores Front-End  |Skype para o serviço de compartilhamento de aplicativos de servidor de negócios  |5065  |TCP  |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  |
|Servidores Front-End  |Skype para o serviço de compartilhamento de aplicativos de servidor de negócios  |49152-65535  |TCP  |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  |
|Servidores Front-End  |Skype para serviço de anúncio de conferência do servidor de negócios  |5073  |TCP  |Usado para solicitações SIP de entrada para o Skype para serviço de anúncio de conferência do servidor de negócios (ou seja, para conferência discada).  |
|Servidores Front-End  |Skype para serviço de estacionamento de chamada do servidor de negócios  |5075  |TCP  |Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.  |
|Servidores Front-End  |Skype para serviço de teste de áudio do servidor de negócios  |5076  |TCP  |Usada para solicitações SIP de entrada para o serviço Teste de Áudio.  |
|Servidores Front-End  |Não aplicável  |5066  |TCP  |Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.  |
|Servidores Front-End  |Skype para serviço de grupo de resposta do servidor de negócios  |5071  |TCP  |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  |
|Servidores Front-End  |Skype para serviço de grupo de resposta do servidor de negócios  |8404  |TCP (MTLS)  |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  |
|Servidores Front-End  |Skype para serviço de política de largura de banda do Business Server  |5080  |TCP  |Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.  |
|Servidores Front-End  |Skype para acesso do servidor de compartilhamento de arquivos do servidor de negócios  |445   |SMB/TCP  | Usado para recuperar o catálogo de endereço, conteúdo da reunião e outros itens armazenados no servidor de compartilhamento de arquivos.  |
|Servidores Front-End  |Skype para serviço de política de largura de banda do Business Server  |448  |TCP  |Usada para controle de admissão de chamada pelo Skype para serviço de política de largura de banda Business Server.  |
|Front servidores End em que reside o repositório de gerenciamento Central  | Skype para o serviço agente replicador mestre do servidor de negócios |445  |TCP  |Usado para enviar dados de configuração do repositório de gerenciamento Central para os servidores que executam o Skype para Business Server.  |
|Todos os servidores  |Navegador do SQL  |1434  |UDP  |Navegador do SQL para cópia local replicada do gerenciamento Central armazenam dados na instância local do SQL Server  |
|Todos os servidores internos  |Vários  |49152-57500  |TCP/UDP  |Intervalo de porta de mídia usada para audioconferência em todos os servidores internos. Usado por todos os servidores que encerram áudio: servidores Front-End (para Skype para o serviço Atendedor de conferência do servidor de negócios, Skype para serviço de anúncio de conferência do servidor de negócios e Skype para o serviço de conferência de áudio/vídeo do Business Server), e Servidor de mediação.  |
|Servidor Office Web Apps  ||443  ||Usada pelo Skype para Business Server para se conectar ao servidor do Office Web Apps.  |
|Diretores  |Skype para serviço de front-end Server de negócios  |5060  |TCP  |Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.  |
|Diretores  |Skype para serviço de front-end Server de negócios  |444  |HTTPS  <br/> TCP  |Comunicação entre servidores entre Front-End e Diretor. Além disso, o certificado de cliente publicar (para servidores Front-End) ou validar se o certificado de cliente já tiver sido publicado.  |
|Diretores  |Skype para serviço de compatibilidade da Web Server Business  |80  |TCP  |Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.  |
|Diretores  |Skype para serviço de compatibilidade da Web Server Business  |443  |HTTPS  |Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).  |
|Diretores  |Skype para serviço de front-end Server de negócios  |5061  |TCP  |Usada para comunicações internas entre os servidores e para conexões do cliente.  |
|Servidores de mediação  |Skype para serviço de mediação do servidor de negócios  |5070  |TCP  |Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.  |
|Servidores de mediação  |Skype para serviço de mediação do servidor de negócios  |5067  |TCP (TLS)  |Usada para solicitações SIP de entrada do gateway PSTN.  |
|Servidores de mediação  |Skype para serviço de mediação do servidor de negócios  |5068  |TCP  |Usada para solicitações SIP de entrada do gateway PSTN.  |
|Servidores de mediação  |Skype para serviço de mediação do servidor de negócios  |5070  |TCP (MTLS)  |Usada para solicitações SIP dos Servidores Front-End.  |
|Servidor de front-end de bate-papo persistente  |SIP de bate-papo persistente  |5041  |TCP (MTLS)  ||
|Servidor de front-end de bate-papo persistente  |Bate-papo persistente do Windows Communication Foundation (WCF)  |881  |TCP (TLS) e TCP (MTLS)  ||
|Servidor de front-end de bate-papo persistente  |Serviço de transferência de arquivos de bate-papo persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX. Embora Skype para Business Server não são mais usa a porta TCP 5060, durante a implantação do controle de chamada remota você criar uma configuração de servidores confiáveis, que associa o FQDN do servidor de linha RCC a porta TCP que o servidor Front-End ou diretor usará para se conectar ao Sistema PBX. Para obter detalhes, consulte o cmdlet **CsTrustedApplicationComputer** no Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.
  
Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.
  
**Portas do balanceador de carga de hardware se estiver usando somente o balanceador de carga de hardware**

|Balanceador de carga|Porta|Protocolo|
|:-----|:-----|:-----|
|Balanceador de carga do Servidor Front-End  |5061  |TCP (TLS)  |
|Balanceador de carga do Servidor Front-End  |444  |HTTPS  |
|Balanceador de carga do Servidor Front-End  |135  |DCOM e RPC (controle de procedimento remoto)  |
|Balanceador de carga do Servidor Front-End  |80  |HTTP  |
|Balanceador de carga do Servidor Front-End  |8080  |Clientes TCP - recuperação de clientes e dispositivos do certificado raiz do servidor Front-End - e dispositivos autenticados por NTLM  |
|Balanceador de carga do Servidor Front-End  |443  |HTTPS  |
|Balanceador de carga do Servidor Front-End  |4443  |HTTPS (do proxy reverso)  |
|Balanceador de carga do Servidor Front-End  |5072  |TCP  |
|Balanceador de carga do Servidor Front-End  |5073  |TCP  |
|Balanceador de carga do Servidor Front-End  |5075  |TCP  |
|Balanceador de carga do Servidor Front-End  |5076  |TCP  |
|Balanceador de carga do Servidor Front-End  |5071  |TCP  |
|Balanceador de carga do Servidor Front-End  |5080  |TCP  |
|Balanceador de carga do Servidor Front-End  |448  |TCP  |
|Balanceador de carga do Servidor de mediação  |5070  |TCP  |
|Balanceador de carga do Servidor Front-End (se o pool também executa o Servidor de mediação)  |5070  |TCP  |
|Balanceador de carga do Diretor  |443  |HTTPS  |
|Balanceador de carga do Diretor  |444  |HTTPS  |
|Balanceador de carga do Diretor  |5061  |TCP  |
|Balanceador de carga do Diretor  |4443  |HTTPS (do proxy reverso)  |
   
Seus pools do Front-End e do Diretor que usam o balanceamento de carga DNS também precisam ter um balanceador de carga de hardware implantado. A tabela a seguir mostra as portas que precisam ser abertas nesses balanceadores de carga de hardware.
  
**Portas do balanceador de carga de hardware se estiver usando o balanceamento de carga DNS**

|Balanceador de carga|Porta|Protocolo|
|:-----|:-----|:-----|
|Balanceador de carga do Servidor Front-End  |80  |HTTP  |
|Balanceador de carga do Servidor Front-End  |443  |HTTPS  |
|Balanceador de carga do Servidor Front-End  |8080  |Clientes TCP - recuperação de clientes e dispositivos do certificado raiz do servidor Front-End - e dispositivos autenticados por NTLM  |
|Balanceador de carga do Servidor Front-End  |4443  |HTTPS (do proxy reverso)  |
|Balanceador de carga do Diretor  |443  |HTTPS  |
|Balanceador de carga do Diretor  |4443  |HTTPS (do proxy reverso)  |

**Portas do cliente necessárias**

|Componente|Porta|Protocolo|Notas|
|:-----|:-----|:-----|:-----|
|Clientes  |67/68  |DHCP  |Usado pelo Skype para Business Server para encontrar o FQDN do registrador (ou seja, se o DNS SRV falhar e as configurações manuais não forem definidas).  |
|Clientes  |443  |TCP (TLS)  |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  |
|Clientes  |443  |TCP (PSOM/TLS)  |Usada para acesso de usuário externo às sessões de webconferência.  |
|Clientes  |443  |TCP (STUN/MSTURN)  |Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)  |
|Clientes  |3478  |UDP (STUN/MSTURN)  |Usada para acesso de usuário externo às sessões de A/V e mídia (UDP)  |
|Clientes  |5061  |TCP (MTLS)  |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  |
|Clientes  |6891-6901  |TCP  |Usado para transferência de arquivos entre Skype para clientes corporativos e antigos clientes.  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de porta de áudio (mínimo de 20 portas necessárias)  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de porta de vídeo (mínimo de 20 portas necessárias).  |
|Clientes  |1024-65535\*  |TCP  |Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).  |
|Clientes  |1024-65535\*  |TCP  |Compartilhamento de aplicativos.  |
|Telefone de área comum Aastra 6721ip  <br/> Telefone de mesa Aastra 6725ip  <br/> Telefone IP HP 4110 (telefone de área comum)  <br/> Telefone IP HP 4120 (telefone de mesa)  <br/> Telefone de área comum IP Polycom CX500  <br/> Telefone de mesa IP Polycom CX600  <br/> Telefone de mesa IP Polycom CX700  <br/> Telefone de conferência IP Polycom CX3000  |67/68  |DHCP  |Usada pelos dispositivos listados para encontrar o Skype para o certificado do servidor de negócios, fornecendo FQDN e FQDN do registrador.  |
   
\*Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (parâmetros ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).
  
> [!NOTE]
> Os programas de instalação de Skype para clientes corporativos criam automaticamente as exceções de firewall necessárias para o sistema operacional no computador cliente. 

> [!NOTE]
> As portas que são usadas para acesso de usuários externos são necessárias para qualquer cenário no qual o cliente deve atravessar do firewall da organização (por exemplo, qualquer comunicações externas ou reuniões hospedadas por outras empresas). 
  
## <a name="ipsec-exceptions"></a>Exceções IPsec

Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorâmico. Essa recomendação existe porque é necessário evitar atrasos na alocação das portas de mídia por causa da negociação IPsec.
  
A tabela a seguir explica as configurações de exceções recomendadas do IPsec. 
  
**Exceções recomendadas do IPsec**

|Nome da regra|IP de origem|IP de destino|Protocolo|Porta de origem|Porta de destino|Requisito de autenticação|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Entrada interna do Servidor de Borda A/V  |Qualquer um  |Interno do Servidor de Borda A/V  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Entrada externa do Servidor de Borda A/V  |Qualquer um  |Externo do Servidor de Borda A/V  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Saída interna do Servidor de Borda A/V  |Interno do Servidor de Borda A/V  |Qualquer um  |UDP &amp; TCP  |Qualquer  |Qualquer um  |Não autenticar  |
|Saída externa do Servidor de Borda A/V  |Externo do Servidor de Borda A/V  |Qualquer um  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Entrada do Servidor de Mediação  |Qualquer um  |Mediação  <br/> Servidor(es)  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Saída do Servidor de Mediação  |Mediação  <br/> Servidor(es)  |Qualquer um  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Entrada do Atendedor de Conferência  |Qualquer um  |Servidor Front-End executando o Atendedor de Conferência  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Saída do Atendedor de Conferência  |Servidor Front-End executando o Atendedor de Conferência  |Qualquer um  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Entrada de Conferência A/V  |Qualquer um  |Servidores Front-End  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Saída de Conferência A/V  |Servidores Front-End  |Qualquer um  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Entrada do Exchange  |Qualquer um  |Unificação de Mensagens do Exchange  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Entrada dos Servidores de Compartilhamento de Aplicativo  |Qualquer um  |Servidores de Compartilhamento de Aplicativos  |TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Saída do Servidor de Compartilhamento de Aplicativos  |Servidores de Compartilhamento de Aplicativos  |Qualquer um  |TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Saída do Exchange  |Unificação de Mensagens do Exchange  |Qualquer um  |UDP e TCP  |Qualquer um  |Qualquer um  |Não autenticar  |
|Clientes  |Qualquer um  |Qualquer um  |UDP  |Intervalo especificado de portas de mídia  |Qualquer um  |Não autenticar  |