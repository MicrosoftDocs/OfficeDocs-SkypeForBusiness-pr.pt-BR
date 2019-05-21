---
title: Requisitos de protocolo e porta para servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumo: revise as considerações de uso da porta antes de implementar o Skype for Business Server.'
ms.openlocfilehash: 613067d90da4fb06811ca1497c83237019b3c021
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297019"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de protocolo e porta para servidores
 
**Resumo:** Examine as considerações de uso de porta antes de implementar o Skype for Business Server.
  
O Skype for Business Server exige a abertura de portas específicas em firewalls externos e internos. Adicionalmente, se o protocolo IPsec (Internet Protocol security) tiver sido implantado em sua organização, ele deverá estar desabilitado no intervalo de portas usadas para a distribuição de áudio, vídeo e vídeo panorama. 
  
Embora isso possa parecer um pouco assustador à primeira vez, o trabalho pesado para planejar isso pode ser feito usando a [ferramenta de planejamento do Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Depois de conhecer as perguntas do assistente sobre quais recursos você planeja usar, para cada site que você definir, poderá exibir o relatório do firewall no relatório de administração de borda e usar as informações listadas ali para criar regras de yourfirewall. Você também pode fazer ajustes para muitos dos nomes e endereços IP usados, para obter detalhes, consulte [analisar o relatório do firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Lembre-se de que você pode exportar o relatório de administração de borda para uma planilha do Excel, e o relatório de firewall será uma das planilhas no arquivo. 
  
Você também pode encontrar as informações dessas tabelas na forma de diagramas ao analisar o artigo cargas de trabalho de protocolo vinculadas dos [diagramas técnicos do artigo do Skype for Business Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Se você estiver implementando o Skype for Business online (O365), consulte [URLs e intervalos de endereços IP do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Ambientes híbridos precisarão fazer referência a este tópico e também [planejar a conectividade híbrida](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Você pode ter firewalls de hardware ou software, não exigimos modelos ou versões específicas. O que é importante que as portas são brancas para que o firewall não prejudique o funcionamento do Skype for Business Server.
  
## <a name="port-and-protocol-details"></a>Detalhes de protocolo e porta

Esta seção resume as portas e os protocolos usados por servidores, balanceadores de carga e clientes em uma implantação do Skype for Business Server.
  
> [!NOTE]
> Quando o Skype for Business Server for iniciado, ele abrirá as portas necessárias no firewall do Windows. O Firewall do Windows já deve estar em execução na maioria dos aplicativos normais, mas se ele não estiver sendo usado, o Skype for Business Server funcionará sem ele. 
  
Para obter detalhes sobre a configuração de firewall para componentes Edge, consulte [cenários do servidor de borda no Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno. 
  
**Portas do servidor necessárias (por Função de servidor)**

|Função de servidor|Nome do serviço|Porta|Protocolo|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Todos os servidores  |Navegador do SQL  |1434  |UDP  |Navegador do SQL para a cópia replicada local do banco de dados do repositório de gerenciamento central.  |
|Servidores Front-End  |Serviço de front-end do Skype for Business Server  |5060  |TCP  |Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.  |
|Servidores Front-End  |Serviço de front-end do Skype for Business Server  |5061  | TCP (TLS) |Usada pelos servidores Standard Edition e pools de front-ends em todas as comunicações SIP internas entre servidores (MTLS), em comunicações SIP entre o servidor e o cliente (TLS) e em comunicações SIP entre os servidores front-end e os servidores de mediação (MTLS). Também é usada em comunicações com o Monitoring Server.  |
| Servidores Front-End |Serviço de front-end do Skype for Business Server  |444  | HTTPS <br/> TCP  |Usado para comunicação HTTPS entre o foco (o componente do servidor do Skype for Business que gerencia o estado da conferência) e os servidores individuais.  <br/> Essa porta também é usada para comunicação TCP entre aparelhos de ramificação sobreviventes e servidores front-end.  |
|Servidores Front-End  |Serviço de front-end do Skype for Business Server  |135  |DCOM e RPC (controle de procedimento remoto)  |Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.  |
|Servidores Front-End  |Serviço de conferência de mensagens instantâneas do Skype for Business Server  |5062  |TCP  |Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).  |
|Servidores Front-End  |Serviço do Skype for Business Server Web de Webconferência  |8057  |TCP (TLS)  |Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.  |
|Servidores Front-End  |Serviço de compatibilidade de conferência da Web do Skype for Business Server  |8058  |TCP (TLS)  |Usado para ouvir conexões do modelo de objeto compartilhado persistente (PSOM) do cliente de reunião ao vivo e versões anteriores do Skype for Business Server.  |
|Servidores Front-End  |Serviço de conferência de áudio/vídeo do Skype for Business Server  |5063  |TCP  |Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).  |
|Servidores Front-End  |Serviço de conferência de áudio/vídeo do Skype for Business Server  |57501-65535  |TCP/UDP  |Intervalo de porta de mídia usado para videoconferência.  |
|Servidores Front-End  |Serviço de compatibilidade da Web do Skype for Business Server  |80  |HTTP  |Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.  |
|Servidores Front-End  |Serviço de compatibilidade da Web do Skype for Business Server  |443  |HTTPS  |Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).  |
|Servidores Front-End  |Serviço de compatibilidade da Web do Skype for Business Server  |8080  |TCP e HTTP  |Usado pelos componentes da Web para acesso externo.  |
|Servidores Front-End  |Servidor de componentes da Web  |4443  |HTTPS  |Comunicações entre pools de front-end HTTPS (de Proxy Reverso) e HTTPS para conexão de Descoberta automática.  |
|Servidores Front-End  |Servidor de componentes da Web  |8060  |TCP (MTLS)  ||
|Servidores Front-End  |Servidor de componentes da Web  |8061  |TCP (MTLS)  ||
|Servidores Front-End  |Componente dos serviços de mobilidade  |5086  |TCP (MTLS)  |Porta SIP usada pelos processos internos dos Serviços de Mobilidade  |
|Servidores Front-End  |Componente dos serviços de mobilidade  |5087  |TCP (MTLS)  |Porta SIP usada pelos processos internos dos Serviços de Mobilidade  |
|Servidores Front-End  |Componente dos serviços de mobilidade  |443  |HTTPS  ||
|Servidores Front-End  |Serviço de atendedor de conferência do Skype for Business Server (conferência discada)  |5064  |TCP  |Usada para solicitações SIP de entrada para conferência discada.  |
|Servidores Front-End  |Serviço de atendedor de conferência do Skype for Business Server (conferência discada)  |5072  |TCP  |Usado para solicitações SIP de entrada do atendente (discagem por conferência).  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5070  |TCP  |Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5067  |TCP (TLS)  |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5068  |TCP  |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5081  |TCP  |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5082  |TCP (TLS)  |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  |
|Servidores Front-End  |Serviço de compartilhamento de aplicativos do Skype for Business Server  |5065  |TCP  |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  |
|Servidores Front-End  |Serviço de compartilhamento de aplicativos do Skype for Business Server  |49152-65535  |TCP  |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  |
|Servidores Front-End  |Serviço de anúncio de conferências do Skype for Business Server  |5073  |TCP  |Usado para solicitações SIP recebidas para o serviço de anúncio de conferência do Skype for Business Server (ou seja, para conferência discada).  |
|Servidores Front-End  |Serviço de estacionamento de chamadas do Skype for Business Server  |5075  |TCP  |Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.  |
|Servidores Front-End  |Serviço de teste de áudio do Skype for Business Server  |5076  |TCP  |Usada para solicitações SIP de entrada para o serviço Teste de Áudio.  |
|Servidores Front-End  |Não aplicável  |5066  |TCP  |Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.  |
|Servidores Front-End  |Serviço do grupo de resposta do Skype for Business Server  |5071  |TCP  |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  |
|Servidores Front-End  |Serviço do grupo de resposta do Skype for Business Server  |8404  |TCP (MTLS)  |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  |
|Servidores Front-End  |Serviço de política de largura de banda do Skype for Business Server  |5080  |TCP  |Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.  |
|Servidores Front-End  |Acesso ao servidor de compartilhamento de arquivos do Skype for Business Server  |445   |SMB/TCP  | Usado para recuperar o catálogo de endereços, o conteúdo da reunião e outros itens armazenados no servidor de compartilhamento de arquivos.  |
|Servidores Front-End  |Serviço de política de largura de banda do Skype for Business Server  |448  |TCP  |Usado para o controle de admissão de chamadas pelo serviço de política de largura de banda do Skype for Business Server.  |
|Servidores front-end nos quais o repositório de gerenciamento central reside  | Serviço do agente do mestre Replicator do Skype for Business Server |445  |TCP  |Usado para enviar por push dados de configuração do repositório de gerenciamento central para servidores que executam o Skype for Business Server.  |
|Todos os servidores  |Navegador do SQL  |1434  |UDP  |Navegador do SQL para cópia replicada local de dados do repositório de gerenciamento central na instância do SQL Server local  |
|Todos os servidores internos  |Vários  |49152-57500  |TCP/UDP  |Intervalo de porta de mídia usada para audioconferência em todos os servidores internos. Usado por todos os servidores que terminam o áudio: servidores front-end (para serviço de atendedor de conferência do Skype for Business Server, serviço de anúncio de conferência do Skype for Business Server e serviço de conferência de áudio/vídeo do Skype for Business Server) e Servidor de mediação.  |
|Servidor Office Web Apps  ||443  ||Usado pelo Skype for Business Server para se conectar ao servidor do Office Web Apps.  |
|Diretores  |Serviço de front-end do Skype for Business Server  |5060  |TCP  |Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.  |
|Diretores  |Serviço de front-end do Skype for Business Server  |444  |HTTPS  <br/> TCP  |Comunicação entre servidores entre Front-End e Diretor. Além disso, a publicação de certificado do cliente (para servidores front-end) ou a validar se o certificado do cliente já foi publicado.  |
|Diretores  |Serviço de compatibilidade da Web do Skype for Business Server  |80  |TCP  |Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.  |
|Diretores  |Serviço de compatibilidade da Web do Skype for Business Server  |443  |HTTPS  |Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).  |
|Diretores  |Serviço de front-end do Skype for Business Server  |5061  |TCP  |Usada para comunicações internas entre os servidores e para conexões do cliente.  |
|Servidores de Mediação  |Serviço de mediação do Skype for Business Server  |5070  |TCP  |Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.  |
|Servidores de Mediação  |Serviço de mediação do Skype for Business Server  |5067  |TCP (TLS)  |Usada para solicitações SIP de entrada do gateway PSTN.  |
|Servidores de mediação  |Serviço de mediação do Skype for Business Server  |5068  |TCP  |Usada para solicitações SIP de entrada do gateway PSTN.  |
|Servidores de mediação  |Serviço de mediação do Skype for Business Server  |5070  |TCP (MTLS)  |Usada para solicitações SIP dos Servidores Front-End.  |
|Servidor de front-end de bate-papo persistente  |SIP de bate-papo persistente  |5041  |TCP (MTLS)  ||
|Servidor de front-end de bate-papo persistente  |Bate-papo persistente do Windows Communication Foundation (WCF)  |881  |TCP (TLS) e TCP (MTLS)  ||
|Servidor de front-end de bate-papo persistente  |Serviço de transferência de arquivos de bate-papo persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX. Embora o Skype for Business Server não use mais a porta TCP 5060, durante a implantação do controle de chamada remota, você cria uma configuração de servidor confiável, que associa o FQDN do servidor de linha de RCC à porta TCP que o servidor front-end ou o diretor usará para se conectar ao Sistema PBX. Para obter detalhes, consulte o cmdlet **CsTrustedApplicationComputer** na documentação do Shell de gerenciamento do Skype for Business Server.
  
Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.
  
**Portas do balanceador de carga de hardware se estiver usando somente o balanceador de carga de hardware**

|Balanceador de carga|Porta|Protocolo|
|:-----|:-----|:-----|
|Balanceador de carga do Servidor Front-End  |5061  |TCP (TLS)  |
|Balanceador de carga do Servidor Front-End  |444  |HTTPS  |
|Balanceador de carga do Servidor Front-End  |135  |DCOM e RPC (controle de procedimento remoto)  |
|Balanceador de carga do Servidor Front-End  |80  |HTTP  |
|Balanceador de carga do Servidor Front-End  |8080  |Recuperação de cliente TCP e dispositivo de certificado raiz do servidor front-end-clientes e dispositivos autenticados por NTLM  |
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
|Balanceador de carga do Servidor Front-End  |8080  |Recuperação de cliente TCP e dispositivo de certificado raiz do servidor front-end-clientes e dispositivos autenticados por NTLM  |
|Balanceador de carga do Servidor Front-End  |4443  |HTTPS (do proxy reverso)  |
|Balanceador de carga do Diretor  |443  |HTTPS  |
|Balanceador de carga do Diretor  |4443  |HTTPS (do proxy reverso)  |

**Portas do cliente necessárias**

|Componente|Porta|Protocolo|Notas|
|:-----|:-----|:-----|:-----|
|Clientes  |67/68  |DHCP  |Usado pelo Skype for Business Server para localizar o FQDN do registrador (isto é, se as configurações de SRV DNS falharem e as configurações manuais não estiverem definidas).  |
|Clientes  |443  |TCP (TLS)  |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  |
|Clientes  |443  |TCP (PSOM/TLS)  |Usada para acesso de usuário externo às sessões de webconferência.  |
|Clientes  |443  |TCP (STUN/MSTURN)  |Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)  |
|Clientes  |3478  |UDP (STUN/MSTURN)  |Usada para acesso de usuário externo às sessões de A/V e mídia (UDP)  |
|Clientes  |5061  |TCP (MTLS)  |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  |
|Clientes  |6891-6901  |TCP  |Usado para transferência de arquivos entre clientes do Skype for Business e clientes anteriores.  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de porta de áudio (mínimo de 20 portas necessárias)  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de porta de vídeo (mínimo de 20 portas necessárias).  |
|Clientes  |1024-65535\*  |TCP  |Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).  |
|Clientes  |1024-65535\*  |TCP  |Compartilhamento de aplicativos.  |
|Telefone de área comum Aastra 6721ip  <br/> Telefone de mesa Aastra 6725ip  <br/> Telefone IP HP 4110 (telefone de área comum)  <br/> Telefone IP HP 4120 (telefone de mesa)  <br/> Telefone de área comum IP Polycom CX500  <br/> Telefone de mesa IP Polycom CX600  <br/> Telefone de mesa IP Polycom CX700  <br/> Telefone de conferência IP Polycom CX3000  |67/68  |DHCP  |Usado pelos dispositivos listados para localizar o certificado do Skype for Business Server, o provisionamento e o FQDN do registrador.  |
   
\*Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (parâmetros ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).
  
> [!NOTE]
> Os programas de instalação para clientes do Skype for Business criam automaticamente as exceções necessárias de firewall do sistema operacional no computador cliente. 

> [!NOTE]
> As portas que são usadas para acesso ao usuário externo são necessárias para qualquer cenário no qual o cliente deve atravessar o firewall da organização (por exemplo, quaisquer comunicações externas ou reuniões hospedadas por outras organizações). 
  
## <a name="ipsec-exceptions"></a>Exceções IPsec

Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorâmico. Essa recomendação existe porque é necessário evitar atrasos na alocação das portas de mídia por causa da negociação IPsec.
  
A tabela a seguir explica as configurações de exceções recomendadas do IPsec. 
  
**Exceções recomendadas do IPsec**

|Nome da regra|IP de origem|IP de destino|Protocolo|Porta de origem|Porta de destino|Requisito de autenticação|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Entrada interna do Servidor de Borda A/V  |Qualquer um  |Interno do Servidor de Borda A/V  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Entrada externa do Servidor de Borda A/V  |Qualquer um  |Externo do Servidor de Borda A/V  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Saída interna do Servidor de Borda A/V  |Interno do Servidor de Borda A/V  |Qualquer um  |UDP &amp; TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Saída externa do Servidor de Borda A/V  |Externo do Servidor de Borda A/V  |Qualquer um  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Entrada do Servidor de Mediação  |Qualquer um  |Mediação  <br/> Servidor(es)  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Saída do Servidor de Mediação  |Mediação  <br/> Servidor(es)  |Qualquer um  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Entrada do Atendedor de Conferência  |Qualquer um  |Servidor Front-End executando o Atendedor de Conferência  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Saída do Atendedor de Conferência  |Servidor Front-End executando o Atendedor de Conferência  |Qualquer um  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Entrada de Conferência A/V  |Qualquer um  |Servidores Front-End  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Saída de Conferência A/V  |Servidores Front-End  |Qualquer um  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Entrada do Exchange  |Qualquer um  |Unificação de Mensagens do Exchange  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Entrada dos Servidores de Compartilhamento de Aplicativo  |Qualquer um  |Servidores de Compartilhamento de Aplicativos  |TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Saída do Servidor de Compartilhamento de Aplicativos  |Servidores de Compartilhamento de Aplicativos  |Qualquer um  |TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Saída do Exchange  |Unificação de Mensagens do Exchange  |Qualquer um  |UDP e TCP  |Qualquer um   |Qualquer um  |Não autenticar  |
|Clientes  |Qualquer um   |Qualquer um  |UDP  |Intervalo especificado de portas de mídia  |Qualquer um  |Não autenticar  |
