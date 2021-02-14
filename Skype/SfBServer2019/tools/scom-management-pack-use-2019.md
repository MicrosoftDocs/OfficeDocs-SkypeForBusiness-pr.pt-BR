---
title: Gerenciar o Skype for Business Server 2019 usando o pacote de gerenciamento do SCOM
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: saiba como configurar sua infraestrutura do Skype for Business Server 2019 para funcionar com o System Center Operations Manager.'
ms.openlocfilehash: 21493a0d49281405b4d9d25d732f9c80c6c9dff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812771"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Gerenciar o Skype for Business Server 2019 usando o pacote de gerenciamento do SCOM
 
**Resumo:** Saiba como configurar sua infraestrutura do Skype for Business Server 2019 para funcionar com o System Center Operations Manager.
  
Em um mundo ideal, você nunca encontrará problemas com o Skype for Business Server 2019. No entanto, o Skype for Business Server pode ser afetado por fatores externos, por exemplo, falhas de rede e hardware. Usando os Pacotes de Gerenciamento do Skype for Business Server 2019, você pode identificar e resolver possíveis problemas de forma proativa. Dessa forma, os Pacotes de Gerenciamento do Skype for Business Server 2019 ampliam os recursos do System Center Operations Manager.
  
Essas informações foram escritas com base na versão 9319.0 do software de comunicação Do Skype for Business Server 2019.
  
## <a name="configuration-overview"></a>Visão geral da configuração

 Para configurar sua infraestrutura do Skype for Business Server 2019 para funcionar com o System Center Operations Manager, você deve fazer três coisas:
  
Identificar e [configurar o Servidor de Gerenciamento Primário.](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md) Para fazer isso, você deve instalar o System Center Operations Manager 2012 SP1 ou R2. 
  
 Identifique e [configure os computadores do Skype for Business Server que serão monitorados.](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md) Para monitorar um computador do Skype for Business Server usando o System Center Operations Manager, você deve instalar os arquivos de agente do System Center Operations Manager e configurar cada servidor para agir como um proxy. 
  
 Identificar e [instalar e configurar nós do watcher.](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md) Os nós do watcher são computadores que periodicamente executar transações sintéticas do Skype for Business Server — cmdlets do Windows PowerShell que verificam se os principais componentes do Skype for Business Server, como a capacidade de fazer logon no sistema ou a capacidade de trocar mensagens instantâneas, estão funcionando conforme o esperado. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager Root Management Server and Agent Support

Os Pacotes de Gerenciamento podem ser usados com o System Center Operations Manager 2007 R2 (64 bits) (com suporte apenas para fins de migração) ou com o System Center Operations Manager 2012 SP1 &amp; R2 (64 bits). A tabela a seguir mostra as configurações com suporte para os Pacotes de Gerenciamento do Skype for Business Server 2019: 
  
|**Configuração**|**Com suporte?**|
|:-----|:-----|
|Sistema operacional Windows Server 2008 R2  <br/> Sistema operacional Windows Server 2012 R2  <br/> |Sim. Tanto no servidor do Skype for Business Server 2019 quanto nos nós do watcher de transação sintética.  <br/> |
|Servidores clusterados  <br/> |Sem suporte.  <br/> |
|Monitoramento sem agentes  <br/> |Sem suporte.  <br/> |
|Ambiente virtual  <br/> |Sim.  <br/> |
|Funções de servidor ingressados no domínio  <br/> |Todas as funções de servidor internas do Skype for Business Server 2019 devem ser ingressados no domínio.  <br/> |
|Funções de servidor autônomos  <br/> |Os Servidores de Borda do Skype for Business Server 2019 não precisam ser ingressados no domínio.  <br/> |
|Limitações da topologia  <br/> |Todas as funções de servidor em uma implantação devem ser monitoradas do mesmo Grupo de Gerenciamento do Operations Manager.  <br/> |
|Nó do watcher de transações sintéticas  <br/> |A disponibilidade do cenário de monitoramento com um nó do watcher de transações sintéticas é suportada (configuração adicional necessária). Nós do watcher não precisam ser ingressados no domínio.  <br/> |
   
A tabela a seguir mostra os requisitos de capacidade e sistema operacional para um nó do watcher de transação sintética:
  
|**Componente de hardware**|**Requisitos mínimos**|
|:-----|:-----|
|CPU  <br/> |Um dos seguintes:  <br/> Processador de 64 bits, quad-core, 2,33 GHz ou superior  <br/> Processador de 2 vias de 64 bits, dual-core, 2,33 GHz ou superior  <br/> |
|Memória  <br/> |8 GB  <br/> |
|Sistema operacional  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Rede  <br/> |1 adaptador de rede a 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Pré-requisitos

Para executar um nó do watcher de transação sintética, primeiro você deve instalar o seguinte:
  
- Agente do System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Os arquivos de instalação principais do Skype for Business Server (OcsCore.msi) e o Unified Communications Managed API (UCMA) (versões devem corresponder à versão do Skype for Business Server WatcherNode.msi versão)
    
## <a name="files-in-this-monitoring-pack"></a>Arquivos neste Pacote de Monitoramento

O Pacote de Monitoramento do Skype for Business Server 2019 inclui os seguintes arquivos:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novidades

Os seguintes recursos são novos nos Pacotes de Gerenciamento do Skype for Business Server 2019.

- **Alterações na [atualização de setembro de 2019](https://www.microsoft.com/download/details.aspx?id=57511)** Alguns alertas tiveram caracteres especiais removidos. Em alguns casos, caracteres especiais interferem no recurso de notificação de canal de comando SCOM.

- **Descoberta automática para entrada do cliente** Os aplicativos clientes que se ins loco no Skype for Business Server 2019 geralmente descobrem automaticamente o servidor para entrar. As transações sintéticas agora suportam a verificação de que a descoberta automática está configurada corretamente.
    
- **Intervalos de executar transações sintéticas personalizadas** Para simplificar o processo de configuração dos Nós do Watcher, as transações sintéticas podem compartilhar contas de usuário. Isso diminui a frequência na qual os testes são executados à medida que os testes são serializados para evitar conflitos. Por padrão, as transações sintéticas são executados a cada 15 minutos para garantir que todos os testes tenham tempo para ser executado. Os administradores que optam por usar mais usuários ou menos testes por usuário agora também podem reduzir o intervalo de executar.
    
- **Transação sintética dos Serviços de Interop de Vídeo** Os clientes que estão migrando para o Skype for Business Server 2019 de outras soluções de fornecedor geralmente desejam continuar usando os dispositivos de teleconferência de vídeo (VTCs) desses outros fornecedores. Servidor de Interop de Vídeo é uma nova função de servidor do Skype for Business Server 2019 que permite que os clientes continuem a usar os VTCs da Cisco em suas salas de conferência conectando-se ao Cisco CUCM por meio de um tronco SIP de vídeo. Esse recurso também adiciona uma transação sintética para ajudar a verificar se o Servidor de Interop de Vídeo está em operação e pode lidar com conexões de entrada por um tronco SIP de vídeo.
    
- **Transação sintética de Conferência de Compartilhamento de Aplicativos** A validação de cenário de ponta a ponta para Conferências de Compartilhamento de Aplicativos agora é suportada.
    
## <a name="monitoring-scenarios"></a>Cenários de monitoramento

O Pacote de Gerenciamento do Skype for Business Server 2019 aproveita diversos recursos para ajudá-lo a detectar e diagnosticar problemas. Esses recursos fornecem visibilidade em tempo real da saúde de um ambiente do Skype for Business Server 2019.
  
|**Cenário de monitoramento**|**Descrição**|
|:-----|:-----|
|Transações sintéticas  <br/> | Cmdlets do Windows PowerShell para testar e ajudar a garantir a alta disponibilidade de cenários como entrada, presença, IM e conferência para os usuários. <br/> As transações sintéticas podem ser executados de qualquer localização geográfica, incluindo dentro da empresa, fora da empresa e em filiais.  <br/> Quando uma transação sintética falha, os log HTML são criados para ajudar a determinar a natureza exata da falha. Isso inclui compreender qual ação falhou, a latência de cada ação, a linha de comando usada para executar o teste e o erro específico que ocorreu.  <br/> |
|Alertas de confiabilidade de chamada  <br/> |Os Registros de Detalhes das Chamadas (CDRs) gravados pelos Servidores do Skype for Business Server 2019 refletem se os usuários podem se conectar a uma chamada ou por que uma chamada foi encerrada. Os alertas de confiabilidade de chamada consultam o banco de dados CDR para produzir alertas que indicam quando um alto número de usuários experimentam problemas de conectividade para chamadas ponto a ponto ou funcionalidade básica de conferência.  <br/> A cobertura do cenário inclui chamadas de áudio, mensagens instantâneas (IM) ponto a ponto e outros recursos de conferência.  <br/> |
|Alertas de qualidade de mídia  <br/> |Consultas de banco de dados que consultam os relatórios de QoE (Qualidade da Experiência) publicados pelos clientes do Skype for Business Server 2019 no final de cada chamada. Essas consultas produzem alertas que identificam cenários em que os usuários provavelmente experimentarão uma qualidade de mídia comprometida durante chamadas e conferências. Os dados são construídos com base nas principais métricas, como latência e perda de pacotes, que contribuem diretamente para a qualidade da experiência do usuário.  <br/> |
|Alertas de saúde do componente  <br/> |Componentes individuais do servidor aumentem alertas por meio de logs de eventos e contadores de desempenho para indicar condições de falha que podem afetar significativamente os cenários do usuário. Esses alertas indicam uma variedade de condições, como serviços que não estão em execução, altas taxas de falha, alta latência de mensagens ou problemas de conectividade.  <br/> |
|Monitoramento de saúde de dependência  <br/> |O Skype for Business Server pode falhar por vários motivos externos. O Pacote de Gerenciamento monitora e coleta dados para dependências externas críticas que podem indicar problemas graves. Essas dependências incluem a disponibilidade dos Serviços de Informações da Internet (IIS) e a CPU dos servidores usados para o Skype for Business Server.  <br/> |
   
### <a name="alert-prioritization"></a>Priorização de Alertas

Os alertas são classificados nas seguintes categorias: 
  
 **Alertas de Alta Prioridade:** Esses alertas indicam condições que causam paralisações de serviço para grupos grandes de usuários e exigem uma ação imediata. As paralisações detectadas por transações sintéticas e serviços offline (como a Conferência de Áudio/Vídeo do Skype for Business Server) se qualificam como alertas de Alta Prioridade. Por outro lado, uma falha de componente em uma única máquina não é um alerta de Alta Prioridade. O Skype for Business Server 2019 tem recursos de alta disponibilidade integrados para essas situações— por exemplo, vários Servidores front-end por trás de balanceadores de carga.
  
 **Alertas de Prioridade Média:** Esses alertas indicam condições que afetam um subconjunto de usuários ou indicam problemas de qualidade da chamada— por exemplo, falhas de componente, latência no estabelecimento de chamadas ou qualidade de áudio inferior em chamadas. Os alertas nesta categoria são com estado (ou seja, a natureza do alerta muda com base no estado da conexão de rede).) Por exemplo, se os tempos de estabelecimento de chamada indicarem latência, mas retornarem a um limite normal, esse alerta de Prioridade Média será resolvido automaticamente no System Center Operations Manager e os administradores não precisarão tomar medidas. Os alertas que não podem ser resolvidos automaticamente são geralmente tratados pelos administradores no mesmo dia útil.
  
 **Outros alertas:** Esses alertas são gerados a partir de componentes que podem afetar um usuário específico ou um subconjunto de usuários. Por exemplo, um alerta típico seria que o serviço do Address Book não poderia analisar a entrada do Active Directory® Domain Services (AD DS) para o usuário: testuser@contoso.com. Os administradores podem resolver esses alertas sempre que eles têm tempo disponível.
  
### <a name="synthetic-transactions"></a>Transações sintéticas

Os Pacotes de Gerenciamento do Skype for Business Server 2019 oferecem maior cobertura para alertas por meio de transações sintéticas. Transações sintéticas são cmdlets do Windows PowerShell integrados ao pacote de gerenciamento do Operations Manager para testar cenários de usuário de ponta a ponta. Quando você designa um servidor para executar transações sintéticas, esses cmdlets são disparados periodicamente pelo pacote de gerenciamento. Falhas resultantes de uma transação sintética geram um alerta com estado. Aqui estão as transações sintéticas com suporte para o Skype for Business Server 2019:
  
**Transações sintéticas suportadas para registro, presença e contatos**

||||
|:-----|:-----|:-----|
|1   <br/> |Registro (logon do usuário)  <br/> |Lync Server 2010 disponível e além  <br/> |
|2   <br/> |Serviço de Agenda (download de arquivo)  <br/> |Lync Server 2010 disponível e além  <br/> |
|3   <br/> |Consulta à web do Catálogo de endereços  <br/> |Lync Server 2010 disponível e além  <br/> |
|4   <br/> |Presença  <br/> |Lync Server 2010 disponível e além  <br/> |
|5   <br/> |Armazenamento de Contato Unificado  <br/> |Lync Server 2013 disponível e além  <br/> |
   
**Transações sintéticas suportadas para serviços ponto a ponto**

||||
|:-----|:-----|:-----|
|6   <br/> |Sistema de Mensagens Instantâneas Ponto a Ponto  <br/> |Disponível no Lync Server 2010 e além  <br/> |
|7   <br/> |Vídeo de áudio ponto a ponto  <br/> |Disponível no Lync Server 2010 e além  <br/> |
|8   <br/> |McX Peer-to-Peer Instant Message (mobile)  <br/> |Disponível na versão de setembro de 2011 do Lync Server 2010 para o Skype for Business 2019  <br/> |
 
> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.
  
**Transações Sintéticas Suportadas para Conferência e Chat Persistente**

||||
|:-----|:-----|:-----|
|9   <br/> |Conferências de áudio/vídeo  <br/> |Disponível no Lync Server 2010 e além  <br/> |
|10   <br/> |Conferência de Dados  <br/> |Disponível no Lync Server 2013 e além  <br/> |
|11   <br/> |Conferência de Mensagens Instantâneas  <br/> |Disponível no Lync Server 2010 e além  <br/> |
|12   <br/> | Chat persistente <br/> |Disponível no Lync Server 2013 e além  <br/> |
|13   <br/> |Join Launcher (scheduled meetings)  <br/> |Disponível no Lync Server 2013 e além  <br/> |
|14   <br/> |Conferência discda  <br/> |Disponível no Skype for Business Server 2015 e além <br/> |
|15   <br/> |Conferência de compartilhamento de aplicativos  <br/> |Disponível no Skype for Business Server 2015 e além <br/> |
|16   <br/> |Conferência UCWA (ingressar em reunião na Web)  <br/> |Disponível no Skype for Business Server 2015 e além <br/> |
   
**Transações sintéticas suportadas para dependências de rede e parceiros**

||||
|:-----|:-----|:-----|
|17   <br/> |Conectividade de Borda AV  <br/> |Disponível no Lync Server 2013 e além  <br/> |
|18   <br/> |Conectividade de Borda AV Exchange Unified Message Connectivity (caixa postal)  <br/> |Disponível no Lync Server 2013 e além  <br/> |
|19  <br/> |Chamada Ponto a Ponto PSTN  <br/> |Disponível no Lync Server 2010 e além  <br/> |
|20  <br/> |Mensagem Instantânea XMPP (federação)  <br/> |Disponível no Lync Server 2013 e além  <br/> |
| 21   <br/> |Servidor de Interoperabilidade de Vídeo  <br/> |Disponível no Skype for Business Server 2015 e além  <br/> |
   
## <a name="how-health-rolls-up"></a>Como a saúde é acumulada

A tabela a seguir mostra os estados de saúde dos objetos do pacote de monitoramento do Skype for Business Server.
  
|**Objeto Management Pack**|**Descrição**|
|:-----|:-----|
|Implantação do Skype for Business Server  <br/> |Representa a implantação do Skype for Business Server 2019 na organização.  <br/> |
|Skype for Business Server Site  <br/> |Representa diferentes localizações geográficas onde os serviços são implantados.  <br/> |
|Skype for Business Server Pool  <br/> |Um Pool (dentro de um Site) que fornece serviços de comunicação, como mensagens instantâneas e conferências, aos usuários. Aplicável a pools de Front-End, pools de Borda e pools de Diretor, mesmo que haja apenas uma única máquina em um determinado pool.  <br/> |
|Função de servidor do Skype for Business  <br/> |Uma função de servidor que hospeda o Serviço do Skype for Business Server.  <br/> |
|Serviço Skype for Business Server  <br/> |Representa uma funcionalidade implantada em um computador específico (por exemplo, serviço de usuário fp01.contoso.com).  <br/> |
|Componente do Skype for Business Server  <br/> |Um componente do Serviço (por exemplo, o componente de Download do Address Book faz parte do Serviço Web).  <br/> |
|Skype for Business Server Pool Watcher  <br/> |Uma instância de transações sintéticas que estão sendo executados em um pool.  <br/> |
|Registrador do Skype for Business Server Watcher  <br/> |Uma instância de transações sintéticas que são executados em um pool do Registrador.  <br/> |
|Skype for Business Server User Services Pool Watcher  <br/> |Uma instância de transações sintéticas que são executados em um pool de Serviços do Usuário.  <br/> |
|Skype for Business Server Voice Pool Watcher  <br/> |Uma instância de transações sintéticas que são executados em um pool de voz.  <br/> |
|Skype for Business Server Port Watcher  <br/> |Uma instância de Porta verifica a execução em um pool.  <br/> |
|Simple URL Watcher  <br/> |Executa investigação HTTPS das URLs simples configuradas em uma implantação.  <br/> |
   
![Acúmulo de SCOM](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Um pool do Skype for Business Server pode conter vários sistemas individuais do Skype for Business Server (com mais de uma função do Skype for Business Server, serviço do Skype for Business Server e componente do Skype for Business Server). Portanto, a falha de um servidor ou componente individual é menos crítica para a saúde geral do pool do Skype for Business Server, pois outros servidores no mesmo pool podem fornecer o serviço de aplicativo ao cliente. A saúde será acumulada em um nível percentual para o pool do Skype for Business Server. 
  
O Skype for Business Server Pool Watcher realiza transações sintéticas em um pool do Skype for Business Server. A falha consecutiva de uma ou mais transações sintéticas (um processo conhecido como intervalo de sondagem consecutivo) acumula o estado crítico de saúde no nível do pool (o pior de qualquer transação sintética), conforme mostrado no diagrama a seguir. 
  
![Sondagem consecutiva do acúmulo de SCOM](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Práticas práticas: Criar um Pacote de Gerenciamento para Personalizações

Por padrão, o Operations Manager salva todas as personalizações, como substituições no Pacote de Gerenciamento Padrão. Como prática melhor, você deve criar um pacote de gerenciamento separado para cada pacote de gerenciamento selada que deseja personalizar. 
  
Ao criar um pacote de gerenciamento para armazenar configurações personalizadas para um pacote de gerenciamento selada, recomendamos nomear o novo pacote de gerenciamento adequadamente, como "Personalizações do Skype for Business Server 2019".
  
Criar um novo pacote de gerenciamento para armazenar personalizações de cada pacote de gerenciamento selada facilita a exportação das personalizações de um ambiente de teste para um ambiente de produção. Isso também facilita a exclusão de um pacote de gerenciamento, pois você deve excluir quaisquer dependências antes de excluir um pacote de gerenciamento. Se as personalizações de todos os pacotes de gerenciamento são salvas no Pacote de Gerenciamento Padrão e você precisa excluir um único pacote de gerenciamento, primeiro exclua o Pacote de Gerenciamento Padrão, que também exclui personalizações para outros pacotes de gerenciamento. 
  
## <a name="links"></a>Links

Os links a seguir conectam você a informações sobre tarefas comuns associadas aos Pacotes de Monitoramento do System Center 2012:
  
- [Ciclo de vida do Pacote de Gerenciamento](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Como importar um pacote de gerenciamento no Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Como substituir uma regra ou monitor](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Como criar uma conta Executar como no Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Gerenciando contas e perfis executar como](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Como exportar um pacote de gerenciamento do Operations Manager](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Como remover um pacote de gerenciamento do Operations Manager](https://technet.microsoft.com/library/hh230746.aspx)
    
Os links a seguir conectam você a informações sobre tarefas comuns associadas aos Pacotes de Monitoramento do System Center 2007:
  
- [Administrando o ciclo de vida do Pacote de Gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Como importar um pacote de gerenciamento no Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Como monitorar o uso de substituições](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Como criar uma conta Executar como no Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Como modificar um perfil executar como existente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Como exportar personalizações do Pacote de Gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Como remover um pacote de gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Para perguntas sobre o Operations Manager e pacotes de monitoramento, consulte o fórum da comunidade do [System Center Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Um recurso útil é o blog [do System Center Operations Manager Unleashed,](https://opsmgrunleashed.wordpress.com/) que contém postagens "Por Exemplo" para pacotes de monitoramento específicos.
  
Para obter informações adicionais sobre o Operations Manager, consulte os seguintes blogs: 
  
- [Blog da equipe do Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog OpsMgr de Dynamics Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Ideias sobre OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog do Burri](https://rburri.wordpress.com/)
    
- [Espaço de Gerenciamento de BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Todas as informações e conteúdos em sites que não são da Microsoft são fornecidos pelo proprietário ou pelos usuários do site. A Microsoft não faz garantias expressas, implícitas ou estatutrias, quanto às informações neste site. 
  
## <a name="see-also"></a>Confira também

[Ferramentas de Gerenciamento do Skype for Business Server 2019](../management-tools-2019.md)
