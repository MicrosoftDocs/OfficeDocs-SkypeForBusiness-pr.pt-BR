---
title: Requisitos de porta e protocolo para servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumo: revise as considerações de uso da porta antes de implementar o Skype for Business Server.'
ms.openlocfilehash: 09b0d187195faa0aa4b5278456991d9223427f9d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220381"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de porta e protocolo para servidores
 
**Resumo:** Revise as considerações de uso da porta antes de implementar o Skype for Business Server.
  
O Skype for Business Server requer que as portas específicas nos firewalls externos e internos estejam abertas. Além disso, se a segurança do protocolo Internet (IPsec) for implantada em sua organização, o IPsec deverá ser desabilitado no intervalo de portas usadas para a entrega de áudio, vídeo e vídeo panorâmico. 
  
Embora isso possa parecer um pouco intimidante primeiro, o trabalho pesado para planejar isso pode ser feito usando a [ferramenta de planejamento do Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Depois de realizar as perguntas do assistente sobre quais recursos você planeja usar, para cada site que você definir, poderá exibir o relatório de firewall dentro do relatório de administração de borda e usar as informações listadas para criar regras do yourfirewall. Você também pode fazer ajustes em muitos dos nomes e endereços IP usados, para obter detalhes, consulte [revisar o relatório de firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Tenha em mente que você pode exportar o relatório de administração de borda para uma planilha do Excel, e o relatório de firewall será uma das planilhas no arquivo. 
  
Você também pode encontrar as informações nessas tabelas no formulário do diagrama, examinando o pôster de cargas de trabalho de protocolo vinculado dos [diagramas técnicos do artigo do Skype for Business Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Se você estiver implementando o Skype for Business online (Microsoft 365 ou o Office 365), consulte as [URLs e os intervalos de endereços IP do microsoft 365 e do office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Os ambientes híbridos precisarão fazer referência a este tópico e também [planejar a conectividade híbrida](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Você pode ter firewalls de hardware ou software, não exigimos modelos ou versões específicos. O que importa é que as portas são listadas para que o firewall não prejudique o funcionamento do Skype for Business Server.
  
## <a name="port-and-protocol-details"></a>Detalhes de Porta e Protocolo

Esta seção resume as portas e os protocolos usados por servidores, balanceadores de carga e clientes em uma implantação do Skype for Business Server.
  
> [!NOTE]
> Quando o Skype for Business Server é iniciado, ele abre as portas necessárias no firewall do Windows. O Firewall do Windows já deve estar sendo executado na maioria dos aplicativos normais, mas se ele não estiver sendo usado, o Skype for Business Server funcionará sem ele. 
  
Para obter detalhes sobre a configuração de firewall para componentes de borda, consulte [cenários de servidor de borda no Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno. 
  
**Portas do servidor necessárias (por Função de servidor)**

|Função de servidor|Nome do serviço|Porta|Protocolo|Observações|
|:-----|:-----|:-----|:-----|:-----|
|Todos os servidores  |Navegador do SQL  |1434  |VIA  |SQL browser para a cópia replicada local do banco de dados do repositório de gerenciamento central.  |
|Servidores Front-End  |Serviço front-end do Skype for Business Server  |5060  |TCP  |Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.  |
|Servidores Front-End  |Serviço front-end do Skype for Business Server  |5061  | TCP (TLS) |Usada pelos servidores Standard Edition e pools Front-End para todas as comunicações SIP internas entre servidores (MTLS), para comunicações SIP entre o Servidor e o Cliente (TLS) e para comunicações SIP entre os Servidores Front-End e os Servidores de Mediação (MTLS). Também usado para comunicação com um servidor de monitoramento.  |
| Servidores Front-End |Serviço front-end do Skype for Business Server  |444  | HTTPS <br/> TCP  |Usada para comunicação HTTPS entre o foco (o componente do Skype for Business Server que gerencia o estado da conferência) e os servidores individuais.  <br/> Essa porta também é usada para comunicação TCP entre aparelhos de filial persistente e servidores front-end.  |
|Servidores Front-End  |Serviço front-end do Skype for Business Server  |135  |DCOM e RPC (controle de procedimento remoto)  |Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.  |
|Servidores Front-End  |Serviço de conferência de mensagens instantâneas do Skype for Business Server  |5062  |TCP  |Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).  |
|Servidores Front-End  |Serviço de Webconferência do Skype for Business Server  |8057  |TCP (TLS)  |Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.  |
|Servidores Front-End  |Serviço de compatibilidade de Webconferência do Skype for Business Server  |8058  |TCP (TLS)  |Usado para ouvir conexões do modelo de objeto compartilhado persistente (PSOM) do cliente do Live Meeting e versões anteriores do Skype for Business Server.  |
|Servidores Front-End  |Serviço de conferência de áudio/vídeo do Skype for Business Server  |5063  |TCP  |Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).  |
|Servidores Front-End  |Serviço de conferência de áudio/vídeo do Skype for Business Server  |57501-65535  |TCP/UDP  |Intervalo de porta de mídia usado para videoconferência.  |
|Servidores Front-End  |Serviço de compatibilidade da Web do Skype for Business Server  |80  |HTTP  |Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.  |
|Servidores Front-End  |Serviço de compatibilidade da Web do Skype for Business Server  |443  |HTTPS  |Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).  |
|Servidores Front-End  |Serviço de compatibilidade da Web do Skype for Business Server  |8080  |TCP e HTTP  |Usado por componentes da Web para acesso externo.  |
|Servidores Front-End  |Componente do servidor Web  |4443  |HTTPS  |HTTPS (de proxy reverso) e comunicação de front-ends entre pools de HTTPS para entrada de descoberta automática.  |
|Servidores Front-End  |Componente do servidor Web  |8060  |TCP (MTLS)  ||
|Servidores Front-End  |Componente do servidor Web  |8061  |TCP (MTLS)  ||
|Servidores Front-End  |Componente de serviços de mobilidade  |5086  |TCP (MTLS)  |Porta SIP usada pelos processos internos de serviços de mobilidade  |
|Servidores Front-End  |Componente de serviços de mobilidade  |5087  |TCP (MTLS)  |Porta SIP usada pelos processos internos de serviços de mobilidade  |
|Servidores Front-End  |Componente de serviços de mobilidade  |443  |HTTPS  ||
|Servidores Front-End  |Serviço de atendedor de conferência do Skype for Business Server (conferência discada)  |5064  |TCP  |Usada para solicitações SIP de entrada para conferência discada.  |
|Servidores Front-End  |Serviço de atendedor de conferência do Skype for Business Server (conferência discada)  |5072  |TCP  |Usado para solicitações SIP de entrada para o atendedor (conferência discada).  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5070  |TCP  |Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5067  |TCP (TLS)  |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5068  |TCP  |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5081  |TCP  |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Serviço de mediação do Skype for Business Server  |5082  |TCP (TLS)  |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  |
|Servidores Front-End  |Serviço de compartilhamento de aplicativos do Skype for Business Server  |5065  |TCP  |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  |
|Servidores Front-End  |Serviço de compartilhamento de aplicativos do Skype for Business Server  |49152-65535  |TCP  |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  |
|Servidores Front-End  |Serviço de anúncio de conferência do Skype for Business Server  |5073  |TCP  |Usado para solicitações SIP de entrada para o serviço de anúncio de conferência do Skype for Business Server (ou seja, para conferência discada).  |
|Servidores Front-End  |Serviço de estacionamento de chamadas do Skype for Business Server  |5075  |TCP  |Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.  |
|Servidores Front-End  |Serviço de teste de áudio do Skype for Business Server  |5076  |TCP  |Usada para solicitações SIP de entrada para o serviço Teste de Áudio.  |
|Servidores Front-End  |NA (Not applicable)  |5066  |TCP  |Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.  |
|Servidores Front-End  |Serviço de grupo de resposta do Skype for Business Server  |5071  |TCP  |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  |
|Servidores Front-End  |Serviço de grupo de resposta do Skype for Business Server  |8404  |TCP (MTLS)  |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  |
|Servidores Front-End  |Serviço de política de largura de banda do Skype for Business Server  |5080  |TCP  |Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.  |
|Servidores Front-End  |Acesso ao servidor de compartilhamento de arquivos do Skype for Business Server  |445   |SMB/TCP  | Usado para recuperar o catálogo de endereços, o conteúdo da reunião e outros itens armazenados no servidor de compartilhamento de arquivos.  |
|Servidores Front-End  |Serviço de política de largura de banda do Skype for Business Server  |448  |TCP  |Usado para controle de admissão de chamadas pelo serviço de política de largura de banda do Skype for Business Server.  |
|Servidores front-end onde reside o repositório de gerenciamento central  | Serviço do agente do Master Replicator do Skype for Business Server |445  |TCP  |Usado para enviar dados de configuração do repositório de gerenciamento central para servidores que executam o Skype for Business Server.  |
|Todos os servidores  |Navegador do SQL  |1434  |VIA  |Navegador do SQL para cópia replicada local de dados do repositório de gerenciamento central na instância local do SQL Server  |
|Todos os servidores internos  |Vários  |49152-57500  |TCP/UDP  |Intervalo de porta de mídia usado para audioconferência em todos os servidores internos. Usado por todos os servidores que encerram áudio: servidores front-end (para o serviço de atendedor de conferência do Skype for Business Server, serviço de anúncio de conferência do Skype for Business Server e serviço de conferência de áudio/vídeo do Skype for Business Server) e servidor de mediação.  |
|Servidores do Office Web Apps  ||443  ||Usado pelo Skype for Business Server para se conectar ao servidor do Office Web Apps.  |
|Director  |Serviço front-end do Skype for Business Server  |5060  |TCP  |Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.  |
|Director  |Serviço front-end do Skype for Business Server  |444  |HTTPS  <br/> TCP  |A comunicação entre servidores Front-End e Diretor. Além disso, a publicação de certificado de cliente (para servidores front-end) ou a validação se o certificado de cliente já tiver sido publicado.  |
|Director  |Serviço de compatibilidade da Web do Skype for Business Server  |80  |TCP  |Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.  |
|Director  |Serviço de compatibilidade da Web do Skype for Business Server  |443  |HTTPS  |Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).  |
|Director  |Serviço front-end do Skype for Business Server  |5061  |TCP  |Usada para comunicações internas entre os servidores e para conexões do cliente.  |
|Servidores de mediação  |Serviço de mediação do Skype for Business Server  |5070  |TCP  |Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.  |
|Servidores de mediação  |Serviço de mediação do Skype for Business Server  |5067  |TCP (TLS)  |Usada para solicitações SIP de entrada do gateway PSTN.  |
|Servidores de mediação  |Serviço de mediação do Skype for Business Server  |5068  |TCP  |Usada para solicitações SIP de entrada do gateway PSTN.  |
|Servidores de mediação  |Serviço de mediação do Skype for Business Server  |5070  |TCP (MTLS)  |Usada para solicitações SIP dos Servidores Front-End.  |
|Servidor front-end de chats persistentes  |SIP de chat persistente  |5041  |TCP (MTLS)  ||
|Servidor front-end de chats persistentes  |Chat persistente Windows Communication Foundation (WCF)  |881  |TCP (TLS) e TCP (MTLS)  ||
|Servidor front-end de chats persistentes  |Serviço de transferência de arquivos de chat persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX. Embora o Skype for Business Server não use mais a porta TCP 5060, durante a implantação de controle de chamada remota, você cria uma configuração de servidor confiável, que associa o FQDN do servidor de linha RCC à porta TCP que o servidor front-end ou diretor usará para se conectar ao sistema PBX. Para obter detalhes, consulte o cmdlet **CsTrustedApplicationComputer** na documentação do Shell de gerenciamento do Skype for Business Server.
  
Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.
  
**Portas do balanceador de carga de hardware se estiver usando somente o balanceador de carga de hardware**

|Balanceador de carga|Porta|Protocolo|
|:-----|:-----|:-----|
|Balanceador de carga do Servidor Front-End  |5061  |TCP (TLS)  |
|Balanceador de carga do Servidor Front-End  |444  |HTTPS  |
|Balanceador de carga do Servidor Front-End  |135  |DCOM e RPC (controle de procedimento remoto)  |
|Balanceador de carga do Servidor Front-End  |80  |HTTP  |
|Balanceador de carga do Servidor Front-End  |8080  |TCP-cliente e dispositivo recuperação de certificado raiz do servidor front-end-clientes e dispositivos autenticados por NTLM  |
|Balanceador de carga do Servidor Front-End  |443  |HTTPS  |
|Balanceador de carga do Servidor Front-End  |4443  |HTTPS (do proxy reverso)  |
|Balanceador de carga do Servidor Front-End  |5072  |TCP  |
|Balanceador de carga do Servidor Front-End  |5073  |TCP  |
|Balanceador de carga do Servidor Front-End  |5075  |TCP  |
|Balanceador de carga do Servidor Front-End  |5076  |TCP  |
|Balanceador de carga do Servidor Front-End  |5071  |TCP  |
|Balanceador de carga do Servidor Front-End  |5080  |TCP  |
|Balanceador de carga do Servidor Front-End  |448  |TCP  |
|Balanceador de carga do servidor de mediação  |5070  |TCP  |
|Balanceador de carga do servidor front-end (se o pool também executar o servidor de mediação)  |5070  |TCP  |
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
|Balanceador de carga do Servidor Front-End  |8080  |TCP-cliente e dispositivo recuperação de certificado raiz do servidor front-end-clientes e dispositivos autenticados por NTLM  |
|Balanceador de carga do Servidor Front-End  |4443  |HTTPS (do proxy reverso)  |
|Balanceador de carga do Diretor  |443  |HTTPS  |
|Balanceador de carga do Diretor  |4443  |HTTPS (do proxy reverso)  |

**Portas do cliente necessárias**

|Componente|Porta|Protocolo|Observações|
|:-----|:-----|:-----|:-----|
|Clientes  |67/68  |ESCOPO  |Usado pelo Skype for Business Server para encontrar o FQDN do registrador (ou seja, se o DNS SRV falhar e as configurações manuais não forem definidas).  |
|Clientes  |443  |TCP (TLS)  |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  |
|Clientes  |443  |TCP (PSOM/TLS)  |Usada para acesso de usuário externo às sessões de webconferência.  |
|Clientes  |443  |TCP (STUN/MSTURN)  |Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)  |
|Clientes  |3478  |UDP (STUN/MSTURN)  |Usado para acesso de usuário externo a sessões de A/V e mídia (UDP)  |
|Clientes  |5061  |TCP (MTLS)  |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  |
|Clientes  |6891-6901  |TCP  |Usado para transferência de arquivos entre clientes do Skype for Business e clientes anteriores.  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de porta de áudio (mínimo de 20 portas necessárias)  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de porta de vídeo (mínimo de 20 portas necessárias)  |
|Clientes  |1024-65535\*  |TCP  |Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).  |
|Clientes  |1024-65535\*  |TCP  |Compartilhamento de aplicativos  |
|Telefone de área comum Aastra 6721ip  <br/> Telefone de mesa Aastra 6725ip  <br/> Telefone IP HP 4110 (telefone de área comum)  <br/> Telefone IP HP 4120 (telefone de mesa)  <br/> Telefone de área comum IP Polycom CX500  <br/> Telefone de mesa IP Polycom CX600  <br/> Telefone de mesa IP Polycom CX700  <br/> Telefone de conferência IP Polycom CX3000  |67/68  |ESCOPO  |Usada pelos dispositivos listados para encontrar o certificado do Skype for Business Server, o FQDN de provisionamento e o FQDN do registrador.  |
   
\*Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange parâmetros).
  
> [!NOTE]
> Os programas de instalação para clientes do Skype for Business criam automaticamente as exceções de firewall do sistema operacional necessárias no computador cliente. 

> [!NOTE]
> As portas usadas para acesso de usuário externo são necessárias para qualquer cenário no qual o cliente deve atravessar o firewall da organização (por exemplo, qualquer comunicação externa ou reunião hospedada por outras organizações). 
  
## <a name="ipsec-exceptions"></a>Exceções IPsec

Para redes corporativas nas quais o protocolo IPsec (Internet Protocol Security) (consulte IETF RFC 4301-4309) foi implantado, o IPsec deve estar desabilitado no intervalo de portas usadas para a entrega de áudio, vídeo e vídeo panorâmico. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.
  
A tabela a seguir explica as configurações de exceções recomendadas do IPsec. 
  
**Exceções recomendadas do IPsec**

|Nome da regra|IP de origem|IP de destino|Protocolo|Porta de origem|Porta de destino|Requisito de autenticação|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Entrada interna do Servidor de Borda A/V  |Qualquer tamanho  |Interno do Servidor de Borda A/V  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Entrada externa do Servidor de Borda A/V  |Qualquer tamanho  |Externo do Servidor de Borda A/V  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Saída interna do Servidor de Borda A/V  |Interno do Servidor de Borda A/V  |Qualquer tamanho  |&amp;TCP UDP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Saída externa do Servidor de Borda A/V  |Externo do Servidor de Borda A/V  |Qualquer tamanho  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Entrada do Servidor de Mediação  |Qualquer tamanho  |Mediação  <br/> Servidor (es)  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Saída do Servidor de Mediação  |Mediação  <br/> Servidor (es)  |Qualquer tamanho  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Entrada do Atendedor de Conferência  |Qualquer tamanho  |Servidor Front End executando o Atendedor de Conferência  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Saída do Atendedor de Conferência  |Servidor Front End executando o Atendedor de Conferência  |Qualquer tamanho  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Entrada de Conferência A/V  |Qualquer tamanho  |Servidores Front-End  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Saída de Conferência A/V  |Servidores Front-End  |Qualquer tamanho  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Entrada do Exchange  |Qualquer tamanho  |Unificação de Mensagens do Exchange  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Entrada dos Servidores de Compartilhamento de Aplicativo  |Qualquer tamanho  |Servidores de Compartilhamento de Aplicativos  |TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Saída do Servidor de Compartilhamento de Aplicativos.  |Servidores de Compartilhamento de Aplicativos  |Qualquer tamanho  |TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Saída do Exchange  |Unificação de Mensagens do Exchange  |Qualquer tamanho  |UDP e TCP  |Qualquer tamanho  |Qualquer tamanho  |Não autenticar  |
|Clientes  |Qualquer tamanho  |Qualquer tamanho  |VIA  |Intervalo especificado de portas de mídia  |Qualquer tamanho  |Não autenticar  |
