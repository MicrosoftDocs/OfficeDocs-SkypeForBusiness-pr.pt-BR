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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Resumo: saiba como configurar sua infraestrutura do Skype for Business Server 2015 para trabalhar com o System Center Operations Manager.'
ms.openlocfilehash: 5622b09b3d55b4d0d3a3fe026f66b28e3c4be75e
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "36824544"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Manage Skype for Business Server 2015 using SCOM Management pack
 
**Resumo:** Saiba como configurar sua infraestrutura do Skype for Business Server 2015 para trabalhar com o System Center Operations Manager.
  
Em um mundo ideal, você nunca encontraria problemas com o Skype for Business Server 2015. No entanto, o Skype for Business Server pode ser afetado por fatores externos — por exemplo, falhas de rede e falhas de hardware. Usando pacotes de gerenciamento do Skype for Business Server 2015, você pode identificar e solucionar possíveis problemas proativamente. Dessa forma, os pacotes de gerenciamento do Skype for Business Server 2015 estendem os recursos do System Center Operations Manager.
  
Essas informações foram escritas com base na versão 9319,0 do software de comunicação do pacote de monitoramento do Skype for Business Server 2015.
  
## <a name="configuration-overview"></a>Visão Geral da Configuração

 Para configurar sua infraestrutura do Skype for Business Server 2015 para trabalhar com o System Center Operations Manager, você deve fazer três coisas:
  
Identificar e [Configurar o servidor de gerenciamento primário](configure-the-primary.md). Para fazer isso, você deve instalar o System Center Operations Manager 2012 SP1 ou R2. 
  
 Identificar e [configurar os computadores do Skype for Business Server que serão monitorados](configure-computers-to-monitor.md). Para monitorar um computador com o Skype for Business Server usando o System Center Operations Manager, você deve instalar os arquivos de agente do System Center Operations Manager e configurar cada servidor para atuar como um proxy. 
  
 Identificar e [instalar e configurar nós do Inspetor](watcher-nodes.md). Os nós de Inspetor são computadores que executam periodicamente transações sintéticas do Skype for Business Server — cmdlets do Windows PowerShell que verificam os principais componentes do Skype for Business Server, como a capacidade de conectar-se ao sistema ou a capacidade de trocar mensagens de chat as mensagens estão funcionando conforme esperado. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Suporte do agente e servidor de gerenciamento raiz do System Center Operations Manager

Os pacotes de gerenciamento podem ser usados com o System Center Operations Manager 2007 R2 (64 bits) (com suporte somente para fins de migração) ou o System &amp; Center Operations Manager 2012 SP1 R2 (64-bit) ou o System Center Operations Manager 2016 (64-bit). A tabela a seguir mostra as configurações com suporte para os pacotes de gerenciamento do Skype for Business Server 2015: 
  
|Configuração|Com suporte?|
|:-----|:-----|
|Sistema operacional Windows Server 2008 R2  <br/> Sistema operacional Windows Server 2012 R2  <br/> |Sim. Ambos no servidor do Skype for Business Server 2015 e nós do Inspetor de transação sintética.  <br/> |
|Servidores em Cluster  <br/> |Sem suporte.  <br/> |
|Monitoramento sem agente  <br/> |Sem suporte.  <br/> |
|Ambiente Virtual  <br/> |Sim.  <br/> |
|Funções do servidor associadas a um domínio  <br/> |Todas as funções internas do servidor do Skype for Business Server 2015 devem ser unidas ao domínio.  <br/> |
|Funções autônomas do servidor  <br/> |Os servidores de borda do Skype for Business Server 2015 não precisam ser associados ao domínio.  <br/> |
|Limitações da Topologia  <br/> |Todas as funções do servidor em uma implantação devem ser monitoradas a partir do mesmo Grupo de Gerenciamento do Gerente de Operações.  <br/> |
|Nó do Inspetor das Transações Sintéticas  <br/> |A disponibilidade do cenário de monitoramento é suportada com um nó do inspetor de transações sintéticas (configuração adicional obrigatória).  Os nós do inspetor não precisam estar associados a um domínio.  <br/> |
   
A tabela a seguir mostra a capacidade e os requisitos de sistema operacional para um nó do inspetor da transação sintética:
  
|Componente de hardware|Requisitos mínimos|
|:-----|:-----|
|CPU  <br/> |Um dos seguintes:  <br/> Processador de 64 bits, quad-core, 2.33 GHz ou superior  <br/> Processador de 2 vias e 64 bits, dual-core, 2.33 GHz ou superior  <br/> |
|Memória  <br/> |8 GB  <br/> |
|Sistema operacional  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Rede  <br/> |1 adaptador de rede com 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Pré-requisitos

Para executar um nó do inspetor da transação sintética, primeiro você precisa instalar o seguinte:
  
- Agente do Operations Manager do System Center 
    
-  Microsoft.NET Framework 4.5
    
- Os arquivos de instalação do Skype for Business Server (OcsCore. msi) e a API gerenciada de comunicação unificada (UCMA) (as versões devem corresponder à versão WatcherNode. msi do Skype for Business Server)
    
## <a name="files-in-this-monitoring-pack"></a>Arquivos neste Pacote de Monitoramento

O pacote de monitoramento para o Skype for Business Server 2015 inclui os seguintes arquivos:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- Watchernode.msi
    
## <a name="whats-new"></a>Novidades

Os recursos a seguir são novos nos pacotes de gerenciamento do Skype for Business Server 2015.

- **Alterações na [atualização de setembro de 2019](https://www.microsoft.com/en-in/download/details.aspx?id=47364) ** Alguns alertas têm caracteres especiais removidos. Em alguns casos, os caracteres especiais interferem com o recurso de notificação de canal de comando do SCOM.

- **Descoberta automática para entrada do cliente** Os aplicativos cliente que entram no Skype for Business Server 2015 geralmente detectam automaticamente o servidor para entrar. As transações sintéticas agora oferecem suporte para verificar se a descoberta automática está configurada corretamente.
    
- **Intervalos de execução de transação sintética personalizada** Para simplificar o processo de configuração dos nós de Inspetor, as transações sintéticas podem compartilhar contas de usuário. Isso diminui a frequência com que os testes são executados uma vez que os testes são serializados para evitar conflitos. Por padrão, as transações sintéticas são executadas a cada 15 minutos para garantir que todos os testes sejam executados em tempo hábil. Os administradores que optam por utilizar mais usuários ou menos testes por usuário agora também podem reduzir o intervalo de execução.
    
- **Transação sintética dos serviços de interoperabilidade de vídeo** Os clientes que estão migrando para o Skype for Business Server 2015 de outras soluções do fornecedor muitas vezes desejam continuar usando os dispositivos de teleconferência de vídeo (VTCs) desses outros fornecedores. O servidor de interoperabilidade de vídeo é uma nova função de servidor do Skype for Business Server 2015 que permite que os clientes continuem a usar o Cisco VTCs nas salas de conferência conectando-se ao Cisco CUCM por meio de um tronco de vídeo SIP. Este recurso também adiciona uma transação sintética para ajudar a verificar se o Servidor de Interoperabilidade de Vídeo está ativo e pode lidar com conexões de entrada através de um tronco SIP de vídeo.
    
- **Transação Sintética de Conferência para Compartilhamento de Aplicativos** Agora, a validação do cenário completo para Conferências de Compartilhamento de Aplicativos é compatível.
    
## <a name="monitoring-scenarios"></a>Monitoramento de Cenários

O pacote de gerenciamento do Skype for Business Server 2015 aproveita vários recursos para ajudá-lo a detectar e diagnosticar problemas. Esses recursos fornecem visibilidade em tempo real da integridade de um ambiente do Skype for Business Server 2015.
  
|Monitoramento de Cenário|Descrição|
|:-----|:-----|
|Transações sintéticas  <br/> | Cmdlets do Windows PowerShell para testar e ajudar a garantir a alta disponibilidade de cenários como entrar, presença, mensagens instantâneas e conferências para usuários. <br/> As transações sintéticas podem ser executadas de qualquer localização geográfica incluindo locais dento da empresa, fora da empresa e filiais.  <br/> Quando uma transação sintética falhar, os logs HTML são criados para ajudar a determinar a natureza exata da falha. Isso inclui entender qual ação falhou, a latência de cada ação, a linha de comando usada para executar o teste e o erro específico que ocorreu.  <br/> |
|Alertas de confiabilidade de chamada  <br/> |Os registros de detalhes da chamada (CDRs) escritos pelos servidores do Skype for Business Server 2015 refletem se os usuários podem se conectar a uma chamada ou por que uma chamada é encerrada. Os alertas de confiabilidade de chamada consultam o banco de dados do CDR para produzir alertas que indicam quando um grande número de usuários experimentam problemas de conectividade para chamadas ponto a ponto ou funcionalidade básica de conferência.  <br/> A cobertura do cenário inclui chamadas de áudio, mensagens instantâneas (IM) de ponto a ponto e outros recursos de conferência.  <br/> |
|Alertas de qualidade de mídia  <br/> |Consultas de banco de dados que procuram relatórios de qualidade da experiência (QoE) publicadas pelos clientes do Skype for Business Server 2015 no final de cada chamada. Essas consultas produzem alertas que identificam cenários nos quais os usuários provavelmente terão uma qualidade de mídia comprometida durante chamadas e conferências. Os dados estão embutidos nas principais métricas como latência e perda de pacote, que contribuem diretamente para a qualidade da experiência do usuário.  <br/> |
|Alertas da Integridade do componente  <br/> |Os componentes individuais do servidor geram alertas via logs de eventos e contadores de desempenho para indicar condições de falha que possam afetar significativamente os cenários do usuário. Esses alertas indicam uma variedade de condições como serviços que não estão funcionando, alta taxa de falhas, alta latência de mensagens ou problemas de conectividade.  <br/> |
|Monitoramento de Integridade da Dependência  <br/> |O Skype for Business Server pode falhar por vários motivos externos. O Pacote de Gerenciamento monitora e os coleta dados para dependência externas críticas que podem indicar problemas graves. Essas dependências incluem a disponibilidade dos serviços de informações da Internet (IIS) e a CPU de servidores usados para o Skype for Business Server.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Priorização de Alertas

Os alertas são classificados de acordo com as seguintes categorias: 
  
 **Alertas de alta prioridade:** Esses alertas indicam condições que causam interrupções de serviço para grupos grandes de usuários e exigem ação imediata. Paralisações detectadas por transações sintéticas e serviços offline (como videoconferência/videoconferência do Skype for Business Server) qualificam-se como alertas de alta prioridade. Por outro lado, uma falha de componente em uma única máquina não é um alerta de alta prioridade. O Skype for Business Server 2015 tem recursos de alta disponibilidade internos para essas situações — por exemplo, vários servidores front-end com balanceamento de carga.
  
 **Alertas de prioridade média:** Esses alertas indicam condições que afetam um subconjunto de usuários ou indicam problemas na qualidade da chamada, por exemplo, falhas de componentes, latência no estabelecimento de chamadas ou baixa qualidade de áudio em chamadas. Os alertas nessa categoria são stateful (ou seja, a natureza do alerta muda com base no estado da conexão de rede). Por exemplo, se o tempo de estabelecimento da chamada indicar latência, mas retornar a um limite normal, esse alerta de prioridade média seria resolvido automaticamente no System Center Operations Manager e os administradores não precisariam fazer nada. Os alertas que não podem ser resolvidos automaticamente são geralmente solucionados pelos administradores no mesmo dia útil.
  
 **Outros alertas:** Esses alertas são gerados a partir de componentes que podem afetar um usuário específico ou um subconjunto de usuários. Por exemplo, um alerta típico seria que o serviço de Catálogo de Endereços não consiga analisar a entrada dos Serviços de Domínio do Active Directory® (AD DS) para o usuário: testuser@contoso.com. Os administradores podem corrigir esses alertas sempre que tiverem tempo disponível.
  
### <a name="synthetic-transactions"></a>Transações Sintéticas

Os pacotes de gerenciamento do Skype for Business Server 2015 fornecem maior cobertura para alertas por meio de transações sintéticas. As transações sintéticas são cmdlets do Windows PowerShell integrados ao pacote de gerenciamento do Operations Manager para testar cenários de usuário de ponta a ponta. Quando você designa um servidor para executar transações sintéticas, esses cmdlets são acionados periodicamente pelo pacote de gerenciamento. As falhas resultantes de uma transação sintética geram um alerta de estado. Aqui há suporte para transações sintéticas do Skype for Business Server 2015:
  


|Transações Sintéticas Suportadas para Registro, Presença e Contatos|||
|:-----|:-----|:-----|
|1  <br/> |Registro (login do usuário)  <br/> |Disponível Lync Server 2010 e posterior  <br/> |
|2  <br/> |Serviço de Catálogo de Endereços (download de arquivo)  <br/> |Disponível Lync Server 2010 e posterior  <br/> |
|3  <br/> |Consulta à Web do Catálogo de Endereços  <br/> |Disponível Lync Server 2010 e posterior  <br/> |
|4  <br/> |Presença  <br/> |Disponível Lync Server 2010 e posterior  <br/> |
|5  <br/> |Repositório Unificado de Contatos  <br/> |Disponível Lync Server 2013 e posterior  <br/> |
||||   

|Transações Sintéticas Suportadas para Serviços Ponto-a-Ponto|||
|:-----|:-----|:-----|
|6  <br/> |Sistema de Mensagens Instantâneas Ponto-a-Ponto  <br/> |Disponível no Lync Server 2010 e mais recentes  <br/> |
|7  <br/> |Áudio Vídeo Ponto-a-Ponto  <br/> |Disponível no Lync Server 2010 e mais recentes  <br/> |
|8  <br/> |Sistema de Mensagens Instantâneas Ponto-a-Ponto do MCX (móvel)  <br/> |Disponível no lançamento de setembro de 2011 do Lync Server 2010 para o Skype for Business 2015  <br/> |
 
> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.


|Transações Sintéticas Suportadas para Conferência e Chat Persistente|||
|:-----|:-----|:-----|
|9  <br/> |Conferências de áudio/vídeo  <br/> |Disponível no Lync Server 2010 e mais recentes  <br/> |
|254  <br/> |Conferência de dados  <br/> |Disponível no Lync Server 2013 e mais recentes  <br/> |
|11:00  <br/> |Conferência de Mensagens Instantâneas  <br/> |Disponível no Lync Server 2010 e mais recentes  <br/> |
|12  <br/> | Chat Persistente <br/> |Disponível no Lync Server 2013 e mais recentes  <br/> |
|0,13  <br/> |Iniciador de Ingresso (reuniões agendadas)  <br/> |Disponível no Lync Server 2013 e mais recentes  <br/> |
|14  <br/> |Conferência discada  <br/> |Novo no Skype for Business Server 2015  <br/> |
|15  <br/> |Conferência para Compartilhamento de Aplicativos  <br/> |Novo no Skype for Business Server 2015  <br/> |
|16  <br/> |Conferência de UCWA (participação de reunião na web)  <br/> |Novo no Skype for Business Server 2015  <br/> |
||||

|Transações Sintéticas Suportadas para Dependências de Rede e Parceiro|||
|:-----|:-----|:-----|
|16  <br/> |Conectividade de Borda AV  <br/> |Disponível no Lync Server 2013 e mais recentes  <br/> |
|dezoito  <br/> |Conectividade de Borda AV e Conectividade de Mensagem Unificada do Exchange (caixa postal)  <br/> |Disponível no Lync Server 2013 e mais recentes  <br/> |
|pol  <br/> |Chamada Ponto-a-Ponto PSTN  <br/> |Disponível no Lync Server 2010 e mais recentes  <br/> |
|cedido  <br/> |Sistema de Mensagens Instantâneas XMPP (federação)  <br/> |Disponível no Lync Server 2013 e no Skype for Business 2015  <br/> |
|21  <br/> |Servidor de Interoperabilidade de Vídeo  <br/> |Novo no Skype for Business Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Estado de Integridade

A tabela a seguir mostra os Estados de integridade dos objetos do pacote de monitoramento do Skype for Business Server.
  
|Objeto do Pacote de Gerenciamento|Descrição|
|:-----|:-----|
|Implantação do Skype for Business Server  <br/> |Representa a implantação do Skype for Business Server 2015 na organização.  <br/> |
|Site do Skype for Business Server  <br/> |Representa as diferentes áreas geográficas onde os serviços são implantados.  <br/> |
|Pool do servidor do Skype for Business  <br/> |Um pool (dentro de um site) que proporciona serviços de comunicação, como mensagens instantâneas e conferências, aos usuários. Pode ser aplicado a pools de Front-Ends, pools de Borda e pools de Diretor, mesmo se houver apenas uma única máquina em um determinado pool.  <br/> |
|Função do servidor do Skype for Business  <br/> |Uma função de servidor que hospeda o serviço do Skype for Business Server.  <br/> |
|Serviço do Skype for Business Server  <br/> |Representa uma funcionalidade implantada em uma máquina específica (por exemplo, serviço de usuário no fp01.contoso.com).  <br/> |
|Componente do Skype for Business Server  <br/> |Um componente do Serviço (por exemplo, o componente do download do Catálogo de Endereços é uma parte do Serviço da Web).  <br/> |
|Inspetor do pool do servidor do Skype for Business  <br/> |Uma instância do transações sintéticas que são executadas em um pool.  <br/> |
|Inspetor de registrador do Skype for Business Server  <br/> |Uma instância de transações sintéticas que são executadas em um pool do Registrador Avançado.  <br/> |
|Inspetor do pool de serviços de usuário do Skype for Business Server  <br/> |Uma instância de transações sintéticas que são executadas em um pool de Serviços de Usuário.  <br/> |
|Inspetor do pool de voz do Skype for Business Server  <br/> |Uma instância de transações sintéticas que são executadas em um pool de voz.  <br/> |
|Inspetor de porta do Skype for Business Server  <br/> |Uma instância da Porta verifica a execução em um pool.  <br/> |
|Inspetor de URL Simples  <br/> |Realiza a sondagem HTTPS dos URLs simples configurados em uma implantação.  <br/> |
   
![Pacote cumulativo do SCOM](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Um pool do servidor do Skype for Business pode conter vários sistemas individuais do Skype for Business Server (com mais de uma função do servidor do Skype for Business, serviço do Skype for Business Server e componente do Skype for Business Server). Portanto, a falha de um servidor ou componente individual é menos crítica para a integridade geral do pool do servidor do Skype for Business, porque outros servidores no mesmo pool podem fornecer o serviço de aplicativo para o cliente. A integridade será acumulada em um nível de porcentagem do pool do Skype for Business Server. 
  
O Inspetor do pool do servidor do Skype for Business executa transações sintéticas em um pool do Skype for Business Server. A falha consecutiva de uma ou mais transações sintéticas (um processo conhecido como intervalo consecutivo de sondagem) atingirá o estado crítico de integridade a nível do pool (o pior de qualquer transação sintética), conforme mostrado no diagrama a seguir. 
  
![Sondagem consecutiva cumulativa do SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Prática recomendada: Criar um Pacote de Gerenciamento para personalizações

Por padrão, o Operations Manager salva todas as personalizações, como substituições no Pacote de Gerenciamento Padrão. Como prática recomendada, você deve criar uma pacote de gerenciamento separado para cada pacote de gerenciamento selado que você deseja personalizar. 
  
Ao criar um pacote de gerenciamento para armazenar configurações personalizadas para um pacote de gerenciamento selado, nós recomendamos nomear o novo pacote de gerenciamento apropriadamente, como "Personalizações para Skype for Business Server 2015". 
  
A criação de um novo pacote de gerenciamento para armazenar personalizações de cada pacote de gerenciamento selado facilita a exportação das personalizações de um ambiente de teste para um ambiente de produção. Isso também facilita a exclusão de um pacote de gerenciamento, pois você deve excluir quaisquer dependências antes de excluir um pacote de gerenciamento. Se as personalizações para todos os pacotes de gerenciamento forem salvas no Pacote de Gerenciamento Padrão e você precisar excluir um único pacote de gerenciamento, você deve primeiro excluir o Pacote de Gerenciamento Padrão, que também excluirá as personalizações para outros pacotes de gerenciamento. 
  
## <a name="links"></a>Links

Os links abaixo conectam você com as informações sobre tarefas comuns que estão associados aos Pacotes de Monitoramento do System Center 2012:
  
- [Ciclo de vida do pacote de gerenciamento](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Como importar um pacote de gerenciamento no Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Como substituir uma regra ou um monitor](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Como criar uma conta Executar como no Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Gerenciando contas Executar como e perfis](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Como exportar um pacote de gerenciamento do Operations Manager](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Como remover um pacote de gerenciamento do Operations Manager](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
Os links abaixo conectam você com as informações sobre tarefas comuns que estão associados aos Pacotes de Monitoramento do System Center 2007:
  
- [Administração do ciclo de vida do pacote de gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Como importar um pacote de gerenciamento no Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Como monitorar usando substituições](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Como criar uma conta Executar como no Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Como modificar um perfil executar como existente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Como exportar personalizações do pacote de gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Como remover um pacote de gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Para perguntas sobre o Operations Manager e os pacotes de monitoramento, consulte o [Fórum da Comunidade System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Um recurso útil é o blog [liberar o System Center Operations Manager](https://opsmgrunleashed.wordpress.com/) , que contém as postagens "por exemplo" para pacotes de monitoramento específicos.
  
Para obter informações adicionais sobre o Operations Manager, consulte os seguintes blogs: 
  
- [Blog da equipe do Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog do OpsMgr de Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Pensamentos sobre o OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de Raphael Burri](https://rburri.wordpress.com/)
    
- [Espaço de gerenciamento do BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Gerenciador de operações + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Todas as informações e conteúdos em sites que não sejam da Microsoft são fornecidos pelo proprietário ou por usuários do website. A Microsoft não oferece garantias expressas, implícitas ou estatutárias relativas às informações contidas nesse website. 
  
## <a name="see-also"></a>Confira também

[Ferramentas de gerenciamento do Skype for Business Server 2015](../../management-tools/management-tools.md)
