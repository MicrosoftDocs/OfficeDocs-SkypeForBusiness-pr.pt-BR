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
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumo: Revise as considerações de uso da porta antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: 1e66437b5422e8de571f5db3ca0892377a10b9d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de porta e protocolo para servidores
 
**Resumo:** Revise as considerações de uso da porta antes de implementar Skype para Business Server 2015.
  
Skype para Business Server requer que portas específicas nos firewalls internos e externos estejam abertos. Adicionalmente, se o protocolo IPsec (Internet Protocol security) tiver sido implantado em sua organização, ele deverá estar desabilitado no intervalo de portas usadas para a distribuição de áudio, vídeo e vídeo panorama. 
  
Isso pode parecer desanimador bit em um primeiro momento, o trabalho pesado para o planejamento, isso pode ser feito usando o [Skype para ferramenta de planejamento do Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Depois que você tiver ido pelas perguntas do assistente sobre quais recursos você planeja usar, para cada site que você define você pode exibir o relatório de Firewall dentro do relatório de administração de borda e use as informações na lista para criar regras de yourfirewall. Você também pode fazer ajustes muitos dos nomes e endereços IP usados para obter detalhes consulte [Review o relatório de Firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Lembre-Lembre-se pode exportar o relatório de administração de borda para uma planilha do Excel e o relatório de Firewall será uma das planilhas no arquivo. 
  
Você também pode encontrar as informações nestas tabelas no formulário de diagrama examinando o cartaz de cargas de trabalho de protocolo vinculado do artigo [Technical diagrams for Skype para Business Server 2015](../../technical-diagrams.md) .
  
## <a name="port-and-protocol-details"></a>Detalhes de protocolo e porta

Esta seção resume as portas e protocolos usados pelos servidores, balanceadores de carga e clientes em um Skype para implantação de servidor de negócios.
  
> [!NOTE]
> Quando Skype para Business Server é iniciado, ele abre as portas necessárias no Firewall do Windows. Já deve estar executando o Firewall do Windows em aplicativos mais normais, mas se ele não está sendo usado Skype para Business Server funcionará sem ele. 
  
Para obter detalhes sobre a configuração de firewall para componentes de borda, consulte [cenários de servidor de borda no Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno. 
  
**Portas do servidor necessárias (por função de servidor)**

|**Função de servidor**|**Nome do serviço**|**Porta**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|Todos os servidores  <br/> |Navegador do SQL  <br/> |1434  <br/> |UDP  <br/> |Navegador SQL para a cópia replicada local do banco de dados do Repositório de Gerenciamento Central.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de front-end Server de negócios  <br/> |5060  <br/> |TCP  <br/> |Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de front-end Server de negócios  <br/> |5061  <br/> | TCP (TLS) <br/> |Usada pelos servidores Standard Edition e pools de front-ends em todas as comunicações SIP internas entre servidores (MTLS), em comunicações SIP entre o servidor e o cliente (TLS) e em comunicações SIP entre os servidores front-end e os servidores de mediação (MTLS). Também é usada em comunicações com o Monitoring Server.  <br/> |
| Servidores Front-End <br/> |Skype para serviço de front-end Server de negócios  <br/> |444  <br/> | HTTPS <br/> TCP  <br/> |Usado para comunicação HTTPS entre o foco (o Skype para componente Business Server que gerencia o estado da conferência) e os servidores individuais.  <br/> Essa porta também é usada para comunicação TCP entre servidores Front-End e de aparelhos de filial persistente.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de front-end Server de negócios  <br/> |135  <br/> |DCOM e RPC (controle de procedimento remoto)  <br/> |Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de conferência de mensagens Instantâneas do servidor de negócios  <br/> |5062  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de Webconferência de servidor de negócios  <br/> |8057  <br/> |TCP (TLS)  <br/> |Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de compatibilidade de webconferência Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Usado para escutar conexões do modelo de objeto Persistent Shared (PSOM) do cliente do Live Meeting e de versões anteriores do Skype para Business Server.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de conferência de áudio/vídeo do Business Server  <br/> |5063  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de conferência de áudio/vídeo do Business Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para videoconferência.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de compatibilidade da Web Server Business  <br/> |80  <br/> |HTTP  <br/> |Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de compatibilidade da Web Server Business  <br/> |443  <br/> |HTTPS  <br/> |Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de compatibilidade da Web Server Business  <br/> |8080  <br/> |TCP e HTTP  <br/> |Usado pelos componentes da Web para acesso externo.  <br/> |
|Servidores Front-End  <br/> |Servidor de componentes da Web  <br/> |4443  <br/> |HTTPS  <br/> |Comunicações entre pools de front-end HTTPS (de Proxy Reverso) e HTTPS para conexão de Descoberta automática.  <br/> |
|Servidores Front-End  <br/> |Servidor de componentes da Web  <br/> |8060  <br/> |TCP (MTLS)  <br/> ||
|Servidores Front-End  <br/> |Servidor de componentes da Web  <br/> |8061  <br/> |TCP (MTLS)  <br/> ||
|Servidores Front-End  <br/> |Componente dos serviços de mobilidade  <br/> |5086  <br/> |TCP (MTLS)  <br/> |Porta SIP usada pelos processos internos dos Serviços de Mobilidade  <br/> |
|Servidores Front-End  <br/> |Componente dos serviços de mobilidade  <br/> |5087  <br/> |TCP (MTLS)  <br/> |Porta SIP usada pelos processos internos dos Serviços de Mobilidade  <br/> |
|Servidores Front-End  <br/> |Componente dos serviços de mobilidade  <br/> |443  <br/> |HTTPS  <br/> ||
|Servidores Front-End  <br/> |Skype para o serviço Atendedor de conferência Business Server (conferência discada)  <br/> |5064  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para conferência discada.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço Atendedor de conferência Business Server (conferência discada)  <br/> |5072  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para Atendedor (discada).  <br/> |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5070  <br/> |TCP  <br/> |Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.  <br/> |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5067  <br/> |TCP (TLS)  <br/> |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  <br/> |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5068  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.  <br/> |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5081  <br/> |TCP  <br/> |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  <br/> |
|Servidores Front-End que também executam um Servidor de Mediação Colocado  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5082  <br/> |TCP (TLS)  <br/> |Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de compartilhamento de aplicativos de servidor de negócios  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Skype para o serviço de compartilhamento de aplicativos de servidor de negócios  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de anúncio de conferência do servidor de negócios  <br/> |5073  <br/> |TCP  <br/> |Usado para solicitações SIP de entrada para o Skype para serviço de anúncio de conferência do servidor de negócios (ou seja, para conferência discada).  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de estacionamento de chamada do servidor de negócios  <br/> |5075  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de teste de áudio do servidor de negócios  <br/> |5076  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para o serviço Teste de Áudio.  <br/> |
|Servidores Front-End  <br/> |Não aplicável  <br/> |5066  <br/> |TCP  <br/> |Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de grupo de resposta do servidor de negócios  <br/> |5071  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de grupo de resposta do servidor de negócios  <br/> |8404  <br/> |TCP (MTLS)  <br/> |Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de política de largura de banda do Business Server  <br/> |5080  <br/> |TCP  <br/> |Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.  <br/> |
|Servidores Front-End  <br/> |Skype para serviço de política de largura de banda do Business Server  <br/> |448  <br/> |TCP  <br/> |Usada para controle de admissão de chamada pelo Skype para serviço de política de largura de banda Business Server.  <br/> |
|Front servidores End em que reside o repositório de gerenciamento Central  <br/> | Skype para o serviço agente replicador mestre do servidor de negócios <br/> |445  <br/> |TCP  <br/> |Usado para enviar dados de configuração do repositório de gerenciamento Central para os servidores que executam o Skype para Business Server.  <br/> |
|Todos os servidores  <br/> |Navegador do SQL  <br/> |1434  <br/> |UDP  <br/> |Navegador do SQL para cópia local replicada do gerenciamento Central armazenam dados na instância local do SQL Server  <br/> |
|Todos os servidores internos  <br/> |Vários  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usada para audioconferência em todos os servidores internos. Usado por todos os servidores que encerram áudio: servidores Front-End (para Skype para o serviço Atendedor de conferência do servidor de negócios, Skype para serviço de anúncio de conferência do servidor de negócios e Skype para o serviço de conferência de áudio/vídeo do Business Server), e Servidor de mediação.  <br/> |
|Servidor Office Web Apps  <br/> ||443  <br/> ||Usada pelo Skype para Business Server 2015 para se conectar ao servidor do Office Web Apps.  <br/> |
|Diretores  <br/> |Skype para serviço de front-end Server de negócios  <br/> |5060  <br/> |TCP  <br/> |Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.  <br/> |
|Diretores  <br/> |Skype para serviço de front-end Server de negócios  <br/> |444  <br/> |HTTPS  <br/> TCP  <br/> |Comunicação entre servidores entre Front-End e Diretor. Além disso, o certificado de cliente publicar (para servidores Front-End) ou validar se o certificado de cliente já tiver sido publicado.  <br/> |
|Diretores  <br/> |Skype para serviço de compatibilidade da Web Server Business  <br/> |80  <br/> |TCP  <br/> |Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.  <br/> |
|Diretores  <br/> |Skype para serviço de compatibilidade da Web Server Business  <br/> |443  <br/> |HTTPS  <br/> |Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).  <br/> |
|Diretores  <br/> |Skype para serviço de front-end Server de negócios  <br/> |5061  <br/> |TCP  <br/> |Usada para comunicações internas entre os servidores e para conexões do cliente.  <br/> |
|Servidores de mediação  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5070  <br/> |TCP  <br/> |Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.  <br/> |
|Servidores de mediação  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5067  <br/> |TCP (TLS)  <br/> |Usada para solicitações SIP de entrada do gateway PSTN.  <br/> |
|Servidores de mediação  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5068  <br/> |TCP  <br/> |Usada para solicitações SIP de entrada do gateway PSTN.  <br/> |
|Servidores de mediação  <br/> |Skype para serviço de mediação do servidor de negócios  <br/> |5070  <br/> |TCP (MTLS)  <br/> |Usada para solicitações SIP dos Servidores Front-End.  <br/> |
|Servidor de front-end de bate-papo persistente  <br/> |SIP de bate-papo persistente  <br/> |5041  <br/> |TCP (MTLS)  <br/> ||
|Servidor de front-end de bate-papo persistente  <br/> |Bate-papo persistente do Windows Communication Foundation (WCF)  <br/> |881  <br/> |TCP (TLS) e TCP (MTLS)  <br/> ||
|Servidor de front-end de bate-papo persistente  <br/> |Serviço de transferência de arquivos de bate-papo persistente  <br/> |443  <br/> |TCP (TLS)  <br/> ||
   
> [!NOTE]
> Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX. Embora Skype para Business Server não são mais usa a porta TCP 5060, durante a implantação do controle de chamada remota você criar uma configuração de servidores confiáveis, que associa o FQDN do servidor de linha RCC a porta TCP que o servidor Front-End ou diretor usará para se conectar ao Sistema PBX. Para obter detalhes, consulte o cmdlet **CsTrustedApplicationComputer** no Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.
  
Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.
  
**Balanceamento de carga de portas de Balanceador de carga de hardware se estiver usando apenas o Hardware**

|**Balanceador de carga**|**Porta**|**Protocolo**|
|:-----|:-----|:-----|
|Balanceador de carga do Servidor Front-End  <br/> |5061  <br/> |TCP (TLS)  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |444  <br/> |HTTPS  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |135  <br/> |DCOM e RPC (controle de procedimento remoto)  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |80  <br/> |HTTP  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |8080  <br/> |Clientes TCP - recuperação de clientes e dispositivos do certificado raiz do servidor Front-End - e dispositivos autenticados por NTLM  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |443  <br/> |HTTPS  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |4443  <br/> |HTTPS (do proxy reverso)  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |5072  <br/> |TCP  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |5073  <br/> |TCP  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |5075  <br/> |TCP  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |5076  <br/> |TCP  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |5071  <br/> |TCP  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |5080  <br/> |TCP  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |448  <br/> |TCP  <br/> |
|Balanceador de carga do Servidor de mediação  <br/> |5070  <br/> |TCP  <br/> |
|Balanceador de carga do Servidor Front-End (se o pool também executa o Servidor de mediação)  <br/> |5070  <br/> |TCP  <br/> |
|Balanceador de carga do Diretor  <br/> |443  <br/> |HTTPS  <br/> |
|Balanceador de carga do Diretor  <br/> |444  <br/> |HTTPS  <br/> |
|Balanceador de carga do Diretor  <br/> |5061  <br/> |TCP  <br/> |
|Balanceador de carga do Diretor  <br/> |4443  <br/> |HTTPS (do proxy reverso)  <br/> |
   
Seus pools do Front-End e do Diretor que usam o balanceamento de carga DNS também precisam ter um balanceador de carga de hardware implantado. A tabela a seguir mostra as portas que precisam ser abertas nesses balanceadores de carga de hardware.
  
**Portas do balanceador de carga de hardware se estiver usando o balanceamento de carga DNS**

|**Balanceador de carga**|**Porta**|**Protocolo**|
|:-----|:-----|:-----|
|Balanceador de carga do Servidor Front-End  <br/> |80  <br/> |HTTP  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |443  <br/> |HTTPS  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |8080  <br/> |Clientes TCP - recuperação de clientes e dispositivos do certificado raiz do servidor Front-End - e dispositivos autenticados por NTLM  <br/> |
|Balanceador de carga do Servidor Front-End  <br/> |4443  <br/> |HTTPS (do proxy reverso)  <br/> |
|Balanceador de carga do Diretor  <br/> |443  <br/> |HTTPS  <br/> |
|Balanceador de carga do Diretor  <br/> |4443  <br/> |HTTPS (do proxy reverso)  <br/> |
   
**Portas necessárias do cliente**

|**Componente**|**Porta**|**Protocolo**|**Observações**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |67/68  <br/> |DHCP  <br/> |Usado pelo Skype para Business Server para encontrar o FQDN do registrador (ou seja, se o DNS SRV falhar e as configurações manuais não forem definidas).  <br/> |
|Clientes  <br/> |443  <br/> |TCP (TLS)  <br/> |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  <br/> |
|Clientes  <br/> |443  <br/> |TCP (PSOM/TLS)  <br/> |Usada para acesso de usuário externo às sessões de webconferência.  <br/> |
|Clientes  <br/> |443  <br/> |TCP (STUN/MSTURN)  <br/> |Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)  <br/> |
|Clientes  <br/> |3478  <br/> |UDP (STUN/MSTURN)  <br/> |Usada para acesso de usuário externo às sessões de A/V e mídia (UDP)  <br/> |
|Clientes  <br/> |5061  <br/> |TCP (MTLS)  <br/> |Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.  <br/> |
|Clientes  <br/> |6891-6901  <br/> |TCP  <br/> |Usado para transferência de arquivos entre Skype para clientes corporativos e antigos clientes.  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de porta de áudio (mínimo de 20 portas necessárias)  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de porta de vídeo (mínimo de 20 portas necessárias).  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP  <br/> |Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP  <br/> |Compartilhamento de aplicativos.  <br/> |
|Telefone de área comum Aastra 6721ip  <br/> Telefone de mesa Aastra 6725ip  <br/> Telefone IP HP 4110 (telefone de área comum)  <br/> Telefone IP HP 4120 (telefone de mesa)  <br/> Telefone de área comum IP Polycom CX500  <br/> Telefone de mesa IP Polycom CX600  <br/> Telefone de mesa IP Polycom CX700  <br/> Telefone de conferência IP Polycom CX3000  <br/> |67/68  <br/> |DHCP  <br/> |Usada pelos dispositivos listados para encontrar o Skype para o certificado do servidor de negócios, fornecendo FQDN e FQDN do registrador.  <br/> |
   
\*Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (parâmetros ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).
  
> [!NOTE]
> Os programas de instalação de Skype para clientes corporativos criam automaticamente as exceções de firewall necessárias para o sistema operacional no computador cliente. 
  
> [!NOTE]
> As portas que são usadas para acesso de usuários externos são necessárias para qualquer cenário no qual o cliente deve atravessar do firewall da organização (por exemplo, qualquer comunicações externas ou reuniões hospedadas por outras empresas). 
  
## <a name="ipsec-exceptions"></a>Exceções IPsec

Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorâmico. Essa recomendação existe porque é necessário evitar atrasos na alocação das portas de mídia por causa da negociação IPsec.
  
A tabela a seguir explica as configurações de exceções recomendadas do IPsec. 
  
**Exceções recomendadas do IPsec**

|**Nome da regra**|**IP de origem**|**Destino IP**|**Protocolo**|**Porta de origem**|**Porta de destino**|**Requisito de autenticação**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Entrada interna do Servidor de Borda A/V  <br/> |Qualquer um  <br/> |Interno do Servidor de Borda A/V  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Entrada externa do Servidor de Borda A/V  <br/> |Qualquer um  <br/> |Externo do Servidor de Borda A/V  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Saída interna do Servidor de Borda A/V  <br/> |Interno do Servidor de Borda A/V  <br/> |Qualquer um  <br/> |UDP &amp; TCP  <br/> |Qualquer  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Saída externa do Servidor de Borda A/V  <br/> |Externo do Servidor de Borda A/V  <br/> |Qualquer um  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Entrada do Servidor de Mediação  <br/> |Qualquer um  <br/> |Mediação  <br/> Servidor(es)  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Saída do Servidor de Mediação  <br/> |Mediação  <br/> Servidor(es)  <br/> |Qualquer um  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Entrada do Atendedor de Conferência  <br/> |Qualquer um  <br/> |Servidor Front-End executando o Atendedor de Conferência  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Saída do Atendedor de Conferência  <br/> |Servidor Front-End executando o Atendedor de Conferência  <br/> |Qualquer um  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Entrada de Conferência A/V  <br/> |Qualquer um  <br/> |Servidores Front-End  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Saída de Conferência A/V  <br/> |Servidores Front-End  <br/> |Qualquer um  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Entrada do Exchange  <br/> |Qualquer um  <br/> |Unificação de Mensagens do Exchange  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Entrada dos Servidores de Compartilhamento de Aplicativo  <br/> |Qualquer um  <br/> |Servidores de Compartilhamento de Aplicativos  <br/> |TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Saída do Servidor de Compartilhamento de Aplicativos  <br/> |Servidores de Compartilhamento de Aplicativos  <br/> |Qualquer um  <br/> |TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Saída do Exchange  <br/> |Unificação de Mensagens do Exchange  <br/> |Qualquer um  <br/> |UDP e TCP  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
|Clientes  <br/> |Qualquer um  <br/> |Qualquer um  <br/> |UDP  <br/> |Intervalo especificado de portas de mídia  <br/> |Qualquer um  <br/> |Não autenticar  <br/> |
   

