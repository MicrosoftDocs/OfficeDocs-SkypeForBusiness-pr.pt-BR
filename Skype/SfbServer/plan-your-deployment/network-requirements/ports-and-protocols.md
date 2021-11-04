---
title: Requisitos de porta e protocolo para servidores
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumo: revise as considerações de uso da porta antes de implementar Skype for Business Server.'
ms.openlocfilehash: a1523ccb821006737a53094151d4a6694c502fc4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777931"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de porta e protocolo para servidores
 
**Resumo:** Revise as considerações de uso da porta antes de implementar Skype for Business Server.
  
Skype for Business Server exige que portas específicas nos firewalls externos e internos sejam abertas. Além disso, se a IPsec (Segurança do Protocolo de Internet) for implantada em sua organização, o IPsec deverá ser desabilitado no intervalo de portas usadas para a entrega de áudio, vídeo e vídeo panorâmica. 
  
Embora isso possa parecer um pouco assustador, o trabalho pesado para planejar isso pode ser feito usando a Ferramenta de Planejamento Skype for Business Server 2015. Depois de passar pelas perguntas do assistente sobre quais recursos você planeja usar, para cada site definido, você pode exibir o Relatório de Firewall no Relatório de Administração de Borda e usar as informações listadas lá para criar suas regras de firewall. Você também pode fazer ajustes em muitos dos nomes e endereços IP usados, para obter detalhes em [Review the Firewall Report](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Lembre-se de que você pode exportar o Relatório de Administração de Borda para uma planilha de Excel, e o Relatório de Firewall será uma das planilhas no arquivo. 
  
Você encontra as informações nessas tabelas em forma de diagrama, revendo o cartaz Cargas de Trabalho de Protocolo vinculadas fora dos diagramas técnicos do artigo Skype for Business Server [2015.](../../technical-diagrams.md)

> [!NOTE]
> - Se você estiver implementando o Skype for Business Online (Microsoft 365 ou Office 365) consulte Microsoft 365 [e Office 365 URLs](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)e intervalos de endereços IP. Os ambientes híbridos precisarão fazer referência a este tópico e também [planejar a conectividade híbrida.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2floc.json&toc=%2fSkypeForBusiness%2ftoc.json)
> - Você pode ter firewall de hardware ou software. Não exigimos modelos ou versões específicas. O que importa é quais portas são adicionadas a uma lista de Skype for Business Server.
  
## <a name="port-and-protocol-details"></a>Detalhes de Porta e Protocolo

Esta seção resume as portas e protocolos usados por servidores, balanceadores de carga e clientes em uma implantação Skype for Business Server.
  
> [!NOTE]
> Quando Skype for Business Server, ele abre as portas necessárias no firewall Windows. Windows O firewall já deve estar sendo executado na maioria dos aplicativos normais, mas se ele não estiver sendo usado Skype for Business Server funcionará sem ele. 
  
Para obter detalhes sobre a configuração de firewall para componentes de borda, consulte Cenários do Servidor de Borda [Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno. 
  
**Portas do servidor necessárias (por Função de servidor)**

|Função de servidor|Nome do serviço|Porta|Protocolo|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Todos os servidores  |Navegador do SQL  |1434  |UDP  |SQL Navegador para a cópia replicada local do banco de dados do Armazenamento de Gerenciamento Central.  |
|Front-End Servidores  |Skype for Business Server Front-End serviço  |5060  |TCP  |Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.  |
|Servidores Front-End  |Skype for Business Server Front-End serviço  |5061  | TCP (TLS) |Usada pelos servidores Standard Edition e pools Front-End para todas as comunicações SIP internas entre servidores (MTLS), para comunicações SIP entre o Servidor e o Cliente (TLS) e para comunicações SIP entre os Servidores Front-End e os Servidores de Mediação (MTLS). Também usado para comunicações com um Monitoring Server.  |
| Servidores Front-End |Skype for Business Server Front-End serviço  |444  | HTTPS <br/> TCP  |Usado para comunicação HTTPS entre o Focus (o componente Skype for Business Server que gerencia o estado da conferência) e os servidores individuais.  <br/> Essa porta também é usada para comunicação TCP entre Aparelhos de Filial E Servidores Front-End.  |
|Servidores Front-End  |Skype for Business Server Front-End serviço  |135  |DCOM e RPC (controle de procedimento remoto)  |Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.  |
|Servidores Front-End  |Skype for Business Server Serviço de Conferência de IM  |5062  |TCP  |Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).  |
|Servidores Front-End  |Skype for Business Server Serviço de WebConferência  |8057  |TCP (TLS)  |Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.  |
|Servidores Front-End  |Skype for Business Server Serviço de Compatibilidade de WebConferência  |8058  |TCP (TLS)  |Usado para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente Live Meeting e versões anteriores Skype for Business Server.  |
|Servidores Front-End  |Skype for Business Server Serviço de Audioconferência de Vídeo  |5063  |TCP  |Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).  |
|Servidores Front-End  |Skype for Business Server Serviço de Audioconferência de Vídeo  |57501-65535  |TCP/UDP  |Intervalo de porta de mídia usado para videoconferência.  |
|Servidores Front-End  |Skype for Business Server Serviço de Compatibilidade da Web  |80  |HTTP  |Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.  |
|Servidores Front-End  |Skype for Business Server Serviço de Compatibilidade da Web  |443  |HTTPS  |Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).  |
|Servidores Front-End  |Skype for Business Server Serviço de Compatibilidade da Web  |8080  |TCP e HTTP  |Usado por componentes da Web para acesso externo.  |
|Servidores Front-End  |Componente do servidor Web  |4443  |HTTPS  |HTTPS (do Proxy Reverso) e comunicações entre pools de front-end HTTPS para entrada de Descoberta Automática.  |
|Servidores Front-End  |Componente do servidor Web  |8060  |TCP (MTLS)  ||
|Servidores Front-End  |Componente do servidor Web  |8061  |TCP (MTLS)  ||
|Servidores Front-End  |Componente do Mobility Services  |5086  |TCP (MTLS)  |Porta SIP usada pelos processos internos do Mobility Services  |
|Servidores Front-End  |Componente do Mobility Services  |5087  |TCP (MTLS)  |Porta SIP usada pelos processos internos do Mobility Services  |
|Servidores Front-End  |Componente do Mobility Services  |443  |HTTPS  ||
|Servidores Front-End  |Skype for Business Server Atendedor de Conferência serviço (conferência discda)  |5064  |TCP  |Usada para solicitações SIP de entrada para conferência discada.  |
|Servidores Front-End  |Skype for Business Server Atendedor de Conferência serviço (conferência discda)  |5072  |TCP  |Usado para solicitações SIP de entrada para o Attendant (discagem em conferência).  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype for Business Server Serviço de mediação  |5070  |TCP  |Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype for Business Server Serviço de mediação  |5067  |TCP (TLS)  |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype for Business Server Serviço de mediação  |5068  |TCP  |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype for Business Server Serviço de mediação  |5081  |TCP  |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  |Skype for Business Server Serviço de mediação  |5082  |TCP (TLS)  |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  |
|Servidores Front-End  |Skype for Business Server Serviço de Compartilhamento de Aplicativos  |5065  |TCP  |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  |
|Servidores Front-End  |Skype for Business Server Serviço de Compartilhamento de Aplicativos  |49152-65535  |TCP  |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  |
|Servidores Front-End  |Skype for Business Server Comunicado de Conferência serviço  |5073  |TCP  |Usado para solicitações SIP de entrada Skype for Business Server Comunicado de Conferência serviço de Skype for Business Server Comunicado de Conferência (ou seja, para conferência discagem).  |
|Servidores Front-End  |Skype for Business Server Serviço estacionamento de chamada  |5075  |TCP  |Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.  |
|Servidores Front-End  |Skype for Business Server Serviço de Teste de Áudio  |5076  |TCP  |Usada para solicitações SIP de entrada para o serviço Teste de Áudio.  |
|Servidores Front-End  |NA (Not applicable)  |5066  |TCP  |Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.  |
|Servidores Front-End  |Skype for Business Server Serviço do Grupo de Resposta  |5071  |TCP  |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  |
|Servidores Front-End  |Skype for Business Server Serviço do Grupo de Resposta  |8404  |TCP (MTLS)  |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  |
|Servidores Front-End  |Skype for Business Server Serviço de Política de Largura de Banda  |5080  |TCP  |Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.  |
|Servidores Front-End  |Skype for Business Server Acesso ao servidor de Compartilhamento de Arquivos  |445   |SMB/TCP  | Usado para recuperar o livro de endereços, o conteúdo da reunião e outros itens armazenados no servidor de Compartilhamento de Arquivos.  |
|Servidores Front-End  |Skype for Business Server Serviço de Política de Largura de Banda  |448  |TCP  |Usado para controle de admissão de chamada pelo serviço Skype for Business Server Política de Largura de Banda.  |
|Servidores Front-End onde o armazenamento de Gerenciamento Central reside  | Skype for Business Server Serviço do Agente Replicador Mestre |445  |TCP  |Usado para empurrar dados de configuração do armazenamento de Gerenciamento Central para servidores que executam Skype for Business Server.  |
|Todos os servidores  |Navegador do SQL  |1434  |UDP  |SQL Navegador para cópia replicada local dos dados do armazenamento de gerenciamento central em instância SQL Server local  |
|Todos os servidores internos  |Vários  |49152-57500  |TCP/UDP  |Intervalo de porta de mídia usado para audioconferência em todos os servidores internos. Usado por todos os servidores que encerram o áudio: Servidores front-end (para serviço Skype for Business Server Atendedor de Conferência, Skype for Business Server Comunicado de Conferência serviço e Skype for Business Server Serviço de Conferência de Áudio/Vídeo) e Servidor de Mediação.  |
|Office Servidores Web Apps  ||443  ||Usado por Skype for Business Server para se conectar ao Office Web Apps.  |
|Diretores  |Skype for Business Server Front-End serviço  |5060  |TCP  |Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.  |
|Diretores  |Skype for Business Server Front-End serviço  |444  |HTTPS  <br/> TCP  |A comunicação entre servidores Front-End e Diretor. Além disso, o certificado do cliente publica (em Servidores front-end) ou valida se o certificado do cliente já foi publicado.  |
|Diretores  |Skype for Business Server Serviço de Compatibilidade da Web  |80  |TCP  |Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.  |
|Diretores  |Skype for Business Server Serviço de Compatibilidade da Web  |443  |HTTPS  |Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).  |
|Diretores  |Skype for Business Server Front-End serviço  |5061  |TCP  |Usada para comunicações internas entre os servidores e para conexões do cliente.  |
|Servidores de mediação  |Skype for Business Server Serviço de mediação  |5070  |TCP  |Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.  |
|Servidores de mediação  |Skype for Business Server Serviço de mediação  |5067  |TCP (TLS)  |Usada para solicitações SIP de entrada do gateway PSTN.  |
|Servidores de mediação  |Skype for Business Server Serviço de mediação  |5068  |TCP  |Usada para solicitações SIP de entrada do gateway PSTN.  |
|Servidores de mediação  |Skype for Business Server Serviço de mediação  |5070  |TCP (MTLS)  |Usada para solicitações SIP dos Servidores Front-End.  |
|Servidor front-end de chats persistentes  |SIP de Chat Persistente  |5041  |TCP (MTLS)  ||
|Servidor front-end de chats persistentes  |WCF (Persistent Chat Windows Communication Foundation)  |881  |TCP (TLS) e TCP (MTLS)  ||
|Servidor front-end de chats persistentes  |Serviço de Transferência de Arquivo de Chat Persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX. Embora Skype for Business Server não use mais a porta TCP 5060, durante a implantação do controle de chamada remota, você cria uma configuração de servidor confiável, que associa o FQDN do Servidor de Linha RCC à porta TCP que o Servidor ou Diretor front-end usará para se conectar ao sistema PBX. Para obter detalhes, consulte o cmdlet **CsTrustedApplicationComputer** na documentação Skype for Business Server Shell de Gerenciamento.
  
Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.
  
**Portas do balanceador de carga de hardware se estiver usando somente o balanceador de carga de hardware**

|Balanceador de carga|Porta|Protocolo|
|:-----|:-----|:-----|
|Balanceador de carga do Servidor Front-End  |5061  |TCP (TLS)  |
|Balanceador de carga do Servidor Front-End  |444  |HTTPS  |
|Balanceador de carga do Servidor Front-End  |135  |DCOM e RPC (controle de procedimento remoto)  |
|Balanceador de carga do Servidor Front-End  |80  |HTTP  |
|Balanceador de carga do Servidor Front-End  |8080  |TCP - Recuperação de cliente e dispositivo do certificado raiz do Servidor Front-End - clientes e dispositivos autenticados pelo NTLM  |
|Balanceador de carga do Servidor Front-End  |443  |HTTPS  |
|Balanceador de carga do Servidor Front-End  |4443  |HTTPS (do proxy reverso)  |
|Balanceador de carga do Servidor Front-End  |5072  |TCP  |
|Balanceador de carga do Servidor Front-End  |5073  |TCP  |
|Balanceador de carga do Servidor Front-End  |5075  |TCP  |
|Balanceador de carga do Servidor Front-End  |5076  |TCP  |
|Balanceador de carga do Servidor Front-End  |5071  |TCP  |
|Balanceador de carga do Servidor Front-End  |5080  |TCP  |
|Balanceador de carga do Servidor Front-End  |448  |TCP  |
|Balanceador de carga do Servidor de Mediação  |5070  |TCP  |
|Balanceador de carga do Servidor front-end (se o pool também executa o Servidor de Mediação)  |5070  |TCP  |
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
|Balanceador de carga do Servidor Front-End  |8080  |TCP - Recuperação de cliente e dispositivo do certificado raiz do Servidor Front-End - clientes e dispositivos autenticados pelo NTLM  |
|Balanceador de carga do Servidor Front-End  |4443  |HTTPS (do proxy reverso)  |
|Balanceador de carga do Diretor  |443  |HTTPS  |
|Balanceador de carga do Diretor  |4443  |HTTPS (do proxy reverso)  |

**Portas do cliente necessárias**

|Componente|Porta|Protocolo|Notas|
|:-----|:-----|:-----|:-----|
|Clientes  |67/68  |DHCP  |Usado por Skype for Business Server para encontrar o FQDN do Registrador (isto é, se o SRV DNS falhar e as configurações manuais não estão configuradas).  |
|Clientes  |443  |TCP (TLS)  |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  |
|Clientes  |443  |TCP (PSOM/TLS)  |Usada para acesso de usuário externo às sessões de webconferência.  |
|Clientes  |443  |TCP (STUN/MSTURN)  |Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)  |
|Clientes  |3478  |UDP (STUN/MSTURN)  |Usado para acesso de usuário externo a sessões E/V e mídia (UDP)  |
|Clientes  |5061  |TCP (MTLS)  |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  |
|Clientes  |6891-6901  |TCP  |Usado para transferência de arquivos entre Skype for Business clientes e clientes anteriores.  |
|Clientes  |1024-65535 \*  |TCP/UDP  |Intervalo de porta de áudio (mínimo de 20 portas necessárias)  |
|Clientes  |1024-65535 \*  |TCP/UDP  |Intervalo de porta de vídeo (mínimo de 20 portas necessárias)  |
|Clientes  |1024-65535 \*  |TCP  |Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).  |
|Clientes  |1024-65535 \*  |TCP  |Compartilhamento de aplicativos  |
|Telefone de área comum Aastra 6721ip  <br/> Telefone de mesa Aastra 6725ip  <br/> Telefone IP HP 4110 (telefone de área comum)  <br/> Telefone IP HP 4120 (telefone de mesa)  <br/> Telefone de área comum IP Polycom CX500  <br/> Telefone de mesa IP Polycom CX600  <br/> Telefone de mesa IP Polycom CX700  <br/> Telefone de conferência IP Polycom CX3000  |67/68  |DHCP  |Usado pelos dispositivos listados para encontrar o certificado Skype for Business Server, o FQDN de provisionamento e o FQDN do Registrador.  |
   
\* Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (parâmetros ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).
  
> [!NOTE]
> Os programas de instalação para Skype for Business clientes criam automaticamente as exceções de firewall do sistema operacional necessárias no computador cliente. 

> [!NOTE]
> As portas usadas para acesso de usuário externo são necessárias para qualquer cenário no qual o cliente deve percorrer o firewall da organização (por exemplo, qualquer comunicação externa ou reuniões hospedadas por outras organizações). 
  
## <a name="ipsec-exceptions"></a>Exceções do IPsec

Para redes corporativas em que a segurança do Protocolo de Internet (IPsec) (consulte IETF RFC 4301-4309) foi implantada, o IPsec deve ser desabilitado no intervalo de portas usadas para a entrega de áudio, vídeo e vídeo panorâmico. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.
  
A tabela a seguir explica as configurações de exceções recomendadas do IPsec. 
  
**Exceções recomendadas do IPsec**

|Nome da regra|IP de origem|IP de destino|Protocolo|Porta de origem|Porta de destino|Requisito de autenticação|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Entrada interna do Servidor de Borda A/V  |Qualquer  |Interno do Servidor de Borda A/V  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Entrada externa do Servidor de Borda A/V  |Qualquer  |Externo do Servidor de Borda A/V  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Saída interna do Servidor de Borda A/V  |Interno do Servidor de Borda A/V  |Qualquer  |UDP &amp; TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Saída externa do Servidor de Borda A/V  |Externo do Servidor de Borda A/V  |Qualquer  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Entrada do Servidor de Mediação  |Qualquer  |Mediação  <br/> Server(s)  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Saída do Servidor de Mediação  |Mediação  <br/> Server(s)  |Qualquer  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Entrada do Atendedor de Conferência  |Qualquer  |Servidor Front End executando o Atendedor de Conferência  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Saída do Atendedor de Conferência  |Servidor Front End executando o Atendedor de Conferência  |Qualquer  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Entrada de Conferência A/V  |Qualquer  |Servidores Front-End  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Saída de Conferência A/V  |Servidores Front-End  |Qualquer  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Entrada do Exchange  |Qualquer  |Unificação de Mensagens do Exchange  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Entrada dos Servidores de Compartilhamento de Aplicativo  |Qualquer  |Servidores de Compartilhamento de Aplicativos  |TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Saída do Servidor de Compartilhamento de Aplicativos.  |Servidores de Compartilhamento de Aplicativos  |Qualquer  |TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Saída do Exchange  |Unificação de Mensagens do Exchange  |Qualquer  |UDP e TCP  |Qualquer  |Qualquer  |Não autenticar  |
|Clientes  |Qualquer  |Qualquer  |UDP  |Intervalo especificado de portas de mídia  |Qualquer  |Não autenticar  |