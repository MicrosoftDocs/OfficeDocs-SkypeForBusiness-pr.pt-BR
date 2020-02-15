---
title: Gerenciar o Skype for Business Server 2015 usando o pacote de gerenciamento do SCOM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Resumo: saiba como configurar sua infraestrutura do Skype for Business Server 2015 para trabalhar com o System Center Operations Manager.'
ms.openlocfilehash: 06297ba7e0ab70e7046fc2f3db189275cc90f9d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005936"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Gerenciar o Skype for Business Server 2015 usando o pacote de gerenciamento do SCOM
 
**Resumo:** Saiba como configurar sua infraestrutura do Skype for Business Server 2015 para trabalhar com o System Center Operations Manager.
  
Em um mundo ideal, você nunca encontraria problemas com o Skype for Business Server 2015. No entanto, o Skype for Business Server pode ser afetado por fatores externos, por exemplo, falhas de rede e falhas de hardware. Usando os pacotes de gerenciamento do Skype for Business Server 2015, você pode identificar e resolver possíveis problemas proativamente. Dessa forma, os pacotes de gerenciamento do Skype for Business Server 2015 ampliam os recursos do System Center Operations Manager.
  
Essas informações foram escritas com base na versão 9319,0 do software de comunicações do pacote de monitoramento para o Skype for Business Server 2015.
  
## <a name="configuration-overview"></a>Visão geral da configuração

 Para configurar sua infraestrutura do Skype for Business Server 2015 para trabalhar com o System Center Operations Manager, você deve fazer três coisas:
  
Identificar e [Configurar o servidor de gerenciamento principal](configure-the-primary.md). Para fazer isso, você deve instalar o System Center Operations Manager 2012 SP1 ou R2. 
  
 Identifique e [Configure os computadores do Skype for Business Server que serão monitorados](configure-computers-to-monitor.md). Para monitorar um computador do Skype for Business Server usando o System Center Operations Manager, você deve instalar os arquivos de agente do System Center Operations Manager e configurar cada servidor para atuar como um proxy. 
  
 Identificar e [instalar e configurar nós do Inspetor](watcher-nodes.md). Os nós do Inspetor são computadores que executam periodicamente as transações sintéticas do Skype for Business Server — cmdlets do Windows PowerShell que verificam os principais componentes do Skype for Business Server, como a capacidade de fazer logon no sistema ou a capacidade de troca instantânea as mensagens estão funcionando conforme o esperado. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Suporte de agente e servidor de gerenciamento raiz do System Center Operations Manager

Os pacotes de gerenciamento podem ser usados com o System Center Operations Manager 2007 R2 (64 bits) (com suporte apenas para fins de migração) ou o System &amp; Center Operations Manager 2012 SP1 r2 (64 bits) ou o System Center Operations Manager 2016 (64 bits). A tabela a seguir mostra as configurações suportadas para os pacotes de gerenciamento do Skype for Business Server 2015: 
  
|Configuração|Com suporte?|
|:-----|:-----|
|Sistema operacional Windows Server 2008 R2  <br/> Sistema operacional Windows Server 2012 R2  <br/> |Sim. Tanto no servidor do Skype for Business Server 2015 quanto nos nós do Inspetor de transações sintéticas.  <br/> |
|Servidores em cluster  <br/> |Sem suporte.  <br/> |
|Monitoramento sem agentes  <br/> |Sem suporte.  <br/> |
|Ambiente virtual  <br/> |Sim.  <br/> |
|Funções de servidor associadas ao domínio  <br/> |Todas as funções de servidor do Skype for Business Server 2015 internas devem ter ingresso no domínio.  <br/> |
|Funções de servidor autônomas  <br/> |Os servidores de borda do Skype for Business Server 2015 não precisam ser associados ao domínio.  <br/> |
|Limitações de topologia  <br/> |Todas as funções de servidor em uma implantação devem ser monitoradas no mesmo grupo de gerenciamento do Operations Manager.  <br/> |
|Nó do Inspetor de transações sintéticas  <br/> |A disponibilidade do cenário de monitoramento com um nó de Inspetor de transações sintéticas é suportada (configuração adicional necessária). Os nós do inspetor não precisam ser associados ao domínio.  <br/> |
   
A tabela a seguir mostra os requisitos de capacidade e sistema operacional para um nó do Inspetor de transação sintética:
  
|Componente de hardware|Requisitos mínimos|
|:-----|:-----|
|CPU  <br/> |Um dos seguintes:  <br/> processador de 64 bits, Quad-Core, 2,33 GHz ou superior  <br/> processador de 2 vias com 64 bits, Dual-Core, 2,33 GHz ou superior  <br/> |
|Memória  <br/> |8 GB  <br/> |
|Sistema operacional  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Rede  <br/> |1 adaptador de rede a 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Pré-requisitos

Para executar um nó do Inspetor de transações sintéticas, primeiro você deve instalar o seguinte:
  
- Agente do System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Arquivos de instalação principais do Skype for Business Server (OcsCore. msi) e a API gerenciada de comunicações unificadas (UCMA) (as versões devem corresponder à versão WatcherNode. msi do Skype for Business Server)
    
## <a name="files-in-this-monitoring-pack"></a>Arquivos neste pacote de monitoramento

O pacote de monitoramento do Skype for Business Server 2015 inclui os seguintes arquivos:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode. msi
    
## <a name="whats-new"></a>Novidades

Os seguintes recursos são novos nos pacotes de gerenciamento do Skype for Business Server 2015.

- **Alterações na [atualização 2019 de setembro](https://www.microsoft.com/en-in/download/details.aspx?id=47364) de** Tróia Alguns alertas têm caracteres especiais removidos. Em alguns casos, os caracteres especiais interferem com o recurso de notificação do canal de comando do SCOM.

- **Descoberta automática para entrada do cliente** Os aplicativos clientes que entram no Skype for Business Server 2015 freqüentemente detectam automaticamente o servidor para entrar no. As transações sintéticas agora dão suporte à verificação de que a descoberta automática está configurada corretamente.
    
- **Intervalos de execução de transações sintéticas personalizados** Para simplificar o processo de configuração dos nós do Inspetor, as transações sintéticas podem compartilhar contas de usuário. Isso torna mais lenta a frequência na qual os testes são executados à medida que os testes são serializados para evitar conflitos. Por padrão, as transações sintéticas são executadas a cada 15 minutos para garantir que todos os testes tenham tempo de execução. Os administradores que optam por usar mais usuários ou menos testes por usuário também podem reduzir o intervalo de execução.
    
- **Transação sintética de serviços de interoperabilidade de vídeo** Os clientes que estão migrando para o Skype for Business Server 2015 de outras soluções de fornecedor muitas vezes desejam continuar usando os dispositivos de teleconferência de vídeo (VTCs) desses outros fornecedores. O servidor de interoperabilidade de vídeo é uma nova função de servidor do Skype for Business Server 2015 que permite que os clientes continuem a usar o Cisco VTCs em suas salas de conferência conectando-se ao Cisco CUCM por meio de um tronco SIP de vídeo. Esse recurso também adiciona uma transação sintética para ajudar a verificar se o servidor de interoperabilidade de vídeo está ativo e pode lidar com conexões de entrada através de um tronco SIP de vídeo.
    
- **Transação sintética de conferência de compartilhamento de aplicativo** A validação de cenário de ponta a ponta para conferências de compartilhamento de aplicativos agora é suportada.
    
## <a name="monitoring-scenarios"></a>Cenários de monitoramento

O pacote de gerenciamento do Skype for Business Server 2015 utiliza uma variedade de recursos para ajudá-lo a detectar e diagnosticar problemas. Esses recursos fornecem visibilidade em tempo real da integridade de um ambiente do Skype for Business Server 2015.
  
|Cenário de monitoramento|Descrição|
|:-----|:-----|
|Transações sintéticas  <br/> | Cmdlets do Windows PowerShell para testar e ajudar a garantir a alta disponibilidade de cenários como entrar, presença, IM e conferência para usuários. <br/> As transações sintéticas podem ser executadas de qualquer localização geográfica, incluindo dentro da empresa, fora da empresa e em filiais.  <br/> Quando uma transação sintética falha, os logs HTML são criados para ajudar a determinar a natureza exata da falha. Isso inclui entender qual ação falhou, a latência de cada ação, a linha de comando usada para executar o teste e o erro específico que ocorreu.  <br/> |
|Alertas de confiabilidade de chamada  <br/> |Os registros de detalhes da chamada (CDRs) gravados pelos servidores do Skype for Business Server 2015 refletem se os usuários podem se conectar a uma chamada ou por que uma chamada foi encerrada. Alertas de confiabilidade de chamada consultam o banco de dados CDR para produzir alertas que indicam quando um grande número de usuários enfrenta problemas de conectividade para chamadas ponto a ponto ou funcionalidade de conferência básica.  <br/> A cobertura do cenário inclui chamadas de áudio, mensagens instantâneas de ponto a ponto (IM) e outros recursos de conferência.  <br/> |
|Alertas de qualidade de mídia  <br/> |Consultas de banco de dados que procuram relatórios de QoE (qualidade da experiência) publicados pelos clientes do Skype for Business Server 2015 no final de cada chamada. Essas consultas produzem alertas que apontam cenários em que os usuários têm mais probabilidade de experimentar a qualidade da mídia comprometida durante chamadas e conferências. Os dados são criados em métricas chave, como latência e perda de pacotes, que contribuem diretamente para a qualidade da experiência do usuário.  <br/> |
|Alertas de integridade do componente  <br/> |Componentes de servidor individuais geram alertas por meio de logs de eventos e contadores de desempenho para indicar condições de falha que podem afetar significativamente os cenários do usuário. Esses alertas indicam uma variedade de condições, como serviços não executados, altas taxas de falha, alta latência de mensagens ou problemas de conectividade.  <br/> |
|Monitoramento da integridade da dependência  <br/> |O Skype for Business Server pode falhar por vários motivos externos. O pacote de gerenciamento monitora e coleta dados de dependências externas críticas que podem indicar problemas graves. Essas dependências incluem a disponibilidade dos serviços de informações da Internet (IIS) e a CPU de servidores usados para o Skype for Business Server.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Priorização de alerta

Os alertas são classificados nas seguintes categorias: 
  
 **Alertas de alta prioridade:** Esses alertas indicam condições que causam interrupções de serviço para grandes grupos de usuários e exigem ação imediata. As interrupções detectadas por transações sintéticas e serviços offline (como conferência de áudio/vídeo do Skype for Business Server) qualificam como alertas de alta prioridade. Por outro lado, uma falha de componente em um único computador não é um alerta de alta prioridade. O Skype for Business Server 2015 tem recursos de alta disponibilidade internos para essas situações — por exemplo, vários servidores de front-end atrás de balanceadores de carga.
  
 **Alertas de prioridade média:** Esses alertas indicam condições que afetam um subconjunto de usuários ou indicam problemas na qualidade da chamada, por exemplo, falhas de componente, latência no estabelecimento de chamadas ou qualidade de áudio inferior em chamadas. Os alertas nessa categoria são stateful (ou seja, a natureza do alerta é alterada com base no estado da conexão de rede). Por exemplo, se os tempos de estabelecimento de chamadas indicarem latência, mas retornarem para um limite normal, esse alerta de prioridade média será resolvido automaticamente no System Center Operations Manager e os administradores não precisarão executar a ação. Alertas que não podem ser resolvidos automaticamente normalmente são tratados pelos administradores no mesmo dia útil.
  
 **Outros alertas:** Esses alertas são gerados de componentes que podem afetar um usuário específico ou um subconjunto de usuários. Por exemplo, um alerta típico seria que o serviço de catálogo de endereços não pôde analisar a entrada de serviços de domínio do Active Directory® (AD DS) para o usuário: testuser@contoso.com. Os administradores podem resolver esses alertas sempre que têm tempo disponível.
  
### <a name="synthetic-transactions"></a>Transações sintéticas

Os pacotes de gerenciamento do Skype for Business Server 2015 oferecem maior cobertura para alertas por meio de transações sintéticas. As transações sintéticas são cmdlets do Windows PowerShell integrados ao pacote de gerenciamento do Operations Manager para testar cenários de usuário de ponta a ponta. Quando você designar um servidor para executar transações sintéticas, esses cmdlets serão acionados periodicamente pelo pacote de gerenciamento. As falhas resultantes de uma transação sintética geram um alerta de estado. Veja a seguir as transações sintéticas suportadas para o Skype for Business Server 2015:
  


|Transações sintéticas com suporte para registro, presença e contatos|||
|:-----|:-----|:-----|
|1   <br/> |Registro (logon do usuário)  <br/> |Disponível Lync Server 2010 e posterior  <br/> |
|2   <br/> |Serviço de catálogo de endereços (download de arquivo)  <br/> |Disponível Lync Server 2010 e posterior  <br/> |
|3   <br/> |Consulta à web do Catálogo de endereços  <br/> |Disponível Lync Server 2010 e posterior  <br/> |
|4   <br/> |Presença  <br/> |Disponível Lync Server 2010 e posterior  <br/> |
|5   <br/> |Armazenamento de Contato Unificado  <br/> |Disponível Lync Server 2013 e posterior  <br/> |
||||   

|Transações sintéticas suportadas para serviços ponto a ponto|||
|:-----|:-----|:-----|
|6   <br/> |Mensagens instantâneas ponto a ponto  <br/> |Disponível no Lync Server 2010 e posterior  <br/> |
|7   <br/> |Vídeo de áudio ponto a ponto  <br/> |Disponível no Lync Server 2010 e posterior  <br/> |
|8   <br/> |Mensagem instantânea ponto a ponto do MCX (celular)  <br/> |Disponível na versão de setembro de 2011 do Lync Server 2010 para o Skype for Business 2015  <br/> |
 
> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.


|Transações sintéticas suportadas para conferência e chat persistente|||
|:-----|:-----|:-----|
|9   <br/> |Conferência de vídeo de áudio  <br/> |Disponível no Lync Server 2010 e posterior  <br/> |
|10   <br/> |Conferência de dados  <br/> |Disponível no Lync Server 2013 e posterior  <br/> |
|11  <br/> |Conferência de mensagens instantâneas  <br/> |Disponível no Lync Server 2010 e posterior  <br/> |
|12   <br/> | Chat persistente <br/> |Disponível no Lync Server 2013 e posterior  <br/> |
|Treze  <br/> |Iniciador de ingresso (reuniões agendadas)  <br/> |Disponível no Lync Server 2013 e posterior  <br/> |
|14   <br/> |Conferência discada  <br/> |Novo no Skype for Business Server 2015  <br/> |
|15   <br/> |Conferência de compartilhamento de aplicativo  <br/> |Novo no Skype for Business Server 2015  <br/> |
|16   <br/> |Conferência UCWA (Associação de reunião da Web)  <br/> |Novo no Skype for Business Server 2015  <br/> |
||||

|Transações sintéticas suportadas para dependências de rede e parceiro|||
|:-----|:-----|:-----|
|17   <br/> |Conectividade de borda AV  <br/> |Disponível no Lync Server 2013 e posterior  <br/> |
|18   <br/> |Conectividade de borda de AV com conectividade de mensagens unificadas do Exchange (caixa postal)  <br/> |Disponível no Lync Server 2013 e posterior  <br/> |
|19  <br/> |Chamada ponto a ponto PSTN  <br/> |Disponível no Lync Server 2010 e posterior  <br/> |
|508  <br/> |XMPP de mensagens instantâneas (Federação)  <br/> |Disponível no Lync Server 2013 e no Skype for Business 2015  <br/> |
|21  <br/> |Servidor de interoperabilidade de vídeo  <br/> |Novo no Skype for Business Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Como a integridade é acumulada

A tabela a seguir mostra os Estados de integridade dos objetos do pacote de monitoramento do Skype for Business Server.
  
|Objeto do pacote de gerenciamento|Descrição|
|:-----|:-----|
|Implantação do Skype for Business Server  <br/> |Representa a implantação do Skype for Business Server 2015 na organização.  <br/> |
|Site do Skype for Business Server  <br/> |Representa diferentes locais geográficos onde os serviços são implantados.  <br/> |
|Pool do Skype for Business Server  <br/> |Um pool (dentro de um site) que fornece serviços de comunicação, como mensagens instantâneas e conferência, aos usuários. Aplicável a pools de front-ends, pools de borda e pools de diretores, mesmo se houver apenas um único computador em um determinado pool.  <br/> |
|Função de servidor do Skype for Business  <br/> |Uma função de servidor que hospeda o serviço do Skype for Business Server.  <br/> |
|Serviço do Skype for Business Server  <br/> |Representa uma funcionalidade implantada em uma máquina específica (por exemplo, serviço de usuário no fp01.contoso.com).  <br/> |
|Componente do Skype for Business Server  <br/> |Um componente do serviço (por exemplo, o componente de download do catálogo de endereços é parte do serviço Web).  <br/> |
|Inspetor de pool do Skype for Business Server  <br/> |Uma instância de transações sintéticas que estão sendo executadas em um pool.  <br/> |
|Inspetor de registrador do Skype for Business Server  <br/> |Uma instância de transações sintéticas que são executadas em um pool de registrador.  <br/> |
|Inspetor do pool de serviços de usuário do Skype for Business Server  <br/> |Uma instância de transações sintéticas que são executadas em um pool de serviços de usuário.  <br/> |
|Inspetor do pool de voz do Skype for Business Server  <br/> |Uma instância de transações sintéticas que são executadas em um pool de voz.  <br/> |
|Inspetor de porta do Skype for Business Server  <br/> |Uma instância da porta verifica a execução em um pool.  <br/> |
|Inspetor de URL simples  <br/> |Executa sondagens de HTTPS das URLs simples configuradas em uma implantação.  <br/> |
   
![Pacote cumulativo de atualizações do SCOM](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Um pool do Skype for Business Server pode conter vários sistemas individuais do Skype for Business Server (com mais de uma função do Skype for Business Server, o serviço do Skype for Business Server e o componente do Skype for Business Server). Portanto, a falha de um servidor ou componente individual é menos crítica à integridade geral do pool do Skype for Business Server, pois outros servidores no mesmo pool podem fornecer o serviço de aplicativo ao cliente. A integridade será acumulada em um nível de porcentagem para o pool do Skype for Business Server. 
  
O Inspetor do pool do Skype for Business Server realiza transações sintéticas em um pool do Skype for Business Server. A falha consecutiva de uma ou mais transações sintéticas (um processo conhecido como intervalo de sondagem consecutiva) acumulará o estado de integridade crítico no nível do pool (pior de qualquer transação sintética), conforme mostrado no diagrama a seguir. 
  
![Sondagem consecutiva de rollup do SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Práticas recomendadas: criar um pacote de gerenciamento para personalizações

Por padrão, o Operations Manager salva todas as personalizações, como substituições no pacote de gerenciamento padrão. Como prática recomendada, você deve criar um pacote de gerenciamento separado para cada pacote de gerenciamento lacrado que você deseja personalizar. 
  
Ao criar um pacote de gerenciamento para armazenar configurações personalizadas para um pacote de gerenciamento lacrado, recomendamos nomear o novo pacote de gerenciamento apropriadamente, como "personalizações do Skype for Business Server 2015". 
  
Criar um novo pacote de gerenciamento para armazenar personalizações de cada pacote de gerenciamento lacrado facilita a exportação das personalizações de um ambiente de teste para um ambiente de produção. Isso também facilita a exclusão de um pacote de gerenciamento, pois você deve excluir as dependências antes de excluir um pacote de gerenciamento. Se as personalizações de todos os pacotes de gerenciamento forem salvas no pacote de gerenciamento padrão e você precisar excluir um único pacote de gerenciamento, primeiro exclua o pacote de gerenciamento padrão, que também exclui personalizações para outros pacotes de gerenciamento. 
  
## <a name="links"></a>Links

Os links a seguir conectam você às informações sobre tarefas comuns que estão associadas aos pacotes de monitoramento do System Center 2012:
  
- [Ciclo de vida do pacote de gerenciamento](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Como importar um pacote de gerenciamento no Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Como substituir uma regra ou monitor](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Como criar uma conta Executar como no Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Gerenciando contas Executar como e perfis](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Como exportar um pacote de gerenciamento do Operations Manager](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Como remover um pacote de gerenciamento do Operations Manager](https://technet.microsoft.com/library/hh230746.aspx)
    
Os links a seguir conectam você às informações sobre tarefas comuns que estão associadas aos pacotes de monitoramento do System Center 2007:
  
- [Administrando o ciclo de vida do pacote de gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Como importar um pacote de gerenciamento no Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Como monitorar usando substituições](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Como criar uma conta Executar como no Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Como modificar um perfil executar como existente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Como exportar personalizações do pacote de gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Como remover um pacote de gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Para perguntas sobre o Operations Manager e pacotes de monitoramento, consulte o [Fórum da Comunidade do System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Um recurso útil é o blog [relançou o System Center Operations Manager](https://opsmgrunleashed.wordpress.com/) , que contém as postagens "por exemplo" para pacotes de monitoramento específicos.
  
Para obter informações adicionais sobre o Operations Manager, consulte os seguintes Blogs: 
  
- [Blog da equipe do Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog do OpsMgr de Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Opiniões sobre o OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de blog Rafael Rafael](https://rburri.wordpress.com/)
    
- [Espaço de gerenciamento do gerenciamento](https://blogs.technet.com/brianwren/default.aspx)
    
- [Gerente de operações + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Todas as informações e o conteúdo em sites que não são da Microsoft são fornecidos pelo proprietário ou pelos usuários do site. A Microsoft não oferece garantias, expressas, implícitas ou estatutárias, quanto às informações neste site. 
  
## <a name="see-also"></a>Confira também

[Ferramentas de gerenciamento do Skype for Business Server 2015](../../management-tools/management-tools.md)
