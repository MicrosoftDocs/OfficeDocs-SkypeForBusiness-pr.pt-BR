---
title: Gerenciar Skype for Business Server 2019 usando o pacote de Gerenciamento SCOM
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Resumo: saiba como configurar sua infraestrutura Skype for Business Server 2019 para trabalhar com System Center Operations Manager.'
ms.openlocfilehash: e0e5f7c090c51fbe3b7b022f890fd3fc8f254aa3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844884"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Gerenciar Skype for Business Server 2019 usando o pacote de Gerenciamento SCOM
 
**Resumo:** Saiba como configurar sua infraestrutura Skype for Business Server 2019 para trabalhar com System Center Operations Manager.
  
Em um mundo ideal, você nunca encontrará problemas com Skype for Business Server 2019. No entanto, Skype for Business Server podem ser afetados por fatores externos, por exemplo, falhas de rede e falhas de hardware. Ao usar Skype for Business Server 2019 Management Packs, você pode identificar e resolver possíveis problemas proativamente. Dessa forma, os pacotes de gerenciamento Skype for Business Server 2019 estendem os recursos do System Center Operations Manager.
  
Essas informações foram escritas com base na versão 9319.0 do Monitoring Pack para Skype for Business Server de comunicações 2019.
  
## <a name="configuration-overview"></a>Visão geral da configuração

 Para configurar sua infraestrutura Skype for Business Server 2019 para trabalhar com o System Center Operations Manager, você deve fazer três coisas:
  
Identificar e [configurar o Servidor de Gerenciamento Principal.](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md) Para fazer isso, você deve instalar o System Center Operations Manager 2012 SP1 ou R2. 
  
 Identificar e [configurar os computadores Skype for Business Server que serão monitorados.](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md) Para monitorar um computador Skype for Business Server usando o System Center Operations Manager, você deve instalar os arquivos de agente do System Center Operations Manager e configurar cada servidor para atuar como um proxy. 
  
 Identificar e [instalar e configurar nós do watcher.](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md) Os nós Skype for Business Server do Skype for Business Server são computadores que são executados periodicamente em transações sintéticas Windows PowerShell cmdlets que verificam se os principais componentes do Skype for Business Server, como a capacidade de fazer logon no sistema ou a capacidade de trocar mensagens instantâneas, estão funcionando conforme o esperado. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Suporte ao Servidor de Gerenciamento Raiz do Operations Manager e ao Agente

Os Pacotes de Gerenciamento podem ser usados com o System Center Operations Manager 2007 R2 (64 bits) (com suporte apenas para fins de migração) ou com o System Center Operations Manager 2012 SP1 &amp; R2 (64 bits). A tabela a seguir mostra as configurações com suporte para os Pacotes de Gerenciamento para Skype for Business Server 2019: 
  
|Configuração|Com suporte?|
|:-----|:-----|
|Sistema operacional Windows Server 2008 R2  <br/> Windows Server 2012 Sistema operacional R2   |Sim. Tanto no servidor Skype for Business Server 2019 quanto nos nós do watcher de transações sintéticas.   |
|Servidores em cluster   |Sem suporte.   |
|Monitoramento sem agente   |Sem suporte.   |
|Ambiente virtual   |Sim.   |
|Funções de servidor ingressados no domínio   |Todas as Skype for Business Server de servidor 2019 devem ser ingressados no domínio.   |
|Funções de servidor autônomos   |Skype for Business Server servidores de borda 2019 não são necessários para ingressar no domínio.   |
|Limitações de topologia   |Todas as funções de servidor em uma implantação devem ser monitoradas do mesmo Grupo de Gerenciamento do Operations Manager.   |
|Nó do watcher de transações sintéticas   |Há suporte para a disponibilidade do cenário de monitoramento com um nó do watcher de transações sintéticas (configuração adicional necessária). Nós do watcher não são necessários para serem ingressados no domínio.   |
   
A tabela a seguir mostra a capacidade e os requisitos do sistema operacional para um nó do watcher de transação sintética:
  
|Componente de hardware|Requisitos mínimos|
|:-----|:-----|
|CPU   |Um dos seguintes:  <br/> Processador de 64 bits, quad-core, 2,33 GHz ou superior  <br/> Processador 2 de 64 bits, dual-core, 2,33 GHz ou superior   |
|Memória   |8 GB   |
|Sistema operacional   |Windows Server 2008 R2 Windows Server 2012 R2   |
|Rede   |1 adaptador de rede a 1 Gbps   |
   
## <a name="prerequisites"></a>Pré-requisitos

Para executar um nó do watcher de transação sintética, você deve primeiro instalar o seguinte:
  
- System Center Agente do Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server principais arquivos de instalação (OcsCore.msi) e a UCMA (Unified Communications Managed API) (versões devem corresponder à versão Skype for Business Server WatcherNode.msi)
    
## <a name="files-in-this-monitoring-pack"></a>Arquivos neste Pacote de Monitoramento

O Monitoring Pack para Skype for Business Server 2019 inclui os seguintes arquivos:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novidades

Os recursos a seguir são novos para Skype for Business Server 2019 Management Packs.

- **Alterações na [atualização de setembro de 2019](https://www.microsoft.com/download/details.aspx?id=57511)** Alguns alertas tiveram caracteres especiais removidos. Em alguns casos, caracteres especiais interferem no recurso de notificação do canal de comando do SCOM.

- **Descoberta automática para Entrada do Cliente** Os aplicativos cliente que Skype for Business Server 2019 geralmente descobrem automaticamente o servidor para o que entrar. As transações sintéticas agora suportam a verificação de que a descoberta automática está configurada corretamente.
    
- **Intervalos de executar transações sintéticas personalizadas** Para simplificar o processo de configuração dos Nós do Watcher, as transações sintéticas podem compartilhar contas de usuário. Isso reduz a frequência na qual os testes são executados à medida que os testes são serializados para evitar conflitos. Por padrão, as transações sintéticas são executados a cada 15 minutos para garantir que todos os testes tenham tempo para ser executados. Os administradores que optarem por usar mais usuários ou menos testes por usuário também podem reduzir o intervalo de executar.
    
- Transação sintética dos Serviços de **Interop de Vídeo** Os clientes que estão migrando para o Skype for Business Server 2019 de outras soluções de fornecedor geralmente desejam continuar usando os VTCs (dispositivos de teleconferência de vídeo) desses outros fornecedores. O Servidor de Interop de Vídeo é uma nova função de servidor Skype for Business Server 2019 que permite que os clientes continuem a usar os VTCs cisco em suas salas de conferência conectando-se ao Cisco CUCM por meio de um tronco SIP de vídeo. Esse recurso também adiciona uma transação sintética para ajudar a verificar se o Servidor de Interop de Vídeo está em cima e pode manipular as conexões de entrada em um tronco SIP de vídeo.
    
- **Transação sintética de Conferência de Compartilhamento de Aplicativos** A validação de cenário de ponta a ponta para conferências de compartilhamento de aplicativos agora é suportada.
    
## <a name="monitoring-scenarios"></a>Cenários de monitoramento

O Skype for Business Server 2019 Management Pack aproveita uma variedade de recursos para ajudá-lo a detectar e diagnosticar problemas. Esses recursos fornecem visibilidade em tempo real sobre a saúde de um ambiente Skype for Business Server 2019.
  
|Cenário de monitoramento|Descrição|
|:-----|:-----|
|Transações sintéticas   | Windows PowerShell cmdlets para testar e ajudar a garantir alta disponibilidade de cenários, como entrada, presença, IM e conferência para usuários. <br/> As transações sintéticas podem ser executados de qualquer local geográfico, incluindo dentro da empresa, fora da empresa e em filiais.  <br/> Quando uma transação sintética falha, os log HTML são criados para ajudar a determinar a natureza exata da falha. Isso inclui entender qual ação falhou, a latência de cada ação, a linha de comando usada para executar o teste e o erro específico que ocorreu.   |
|Alertas de confiabilidade de chamada   |Os Registros de Detalhes de Chamada (CDRs) escritos pelos servidores Skype for Business Server 2019 refletem se os usuários podem se conectar a uma chamada ou por que uma chamada é encerrada. Os alertas de confiabilidade de chamada consultam o banco de dados CDR para produzir alertas que indicam quando um alto número de usuários tem problemas de conectividade para chamadas ponto a ponto ou funcionalidade básica de conferência.  <br/> A cobertura do cenário inclui chamadas de áudio, mensagens instantâneas ponto a ponto (IM) e outros recursos de conferência.   |
|Alertas de qualidade de mídia   |Consultas de banco de dados que pesquisam relatórios de Qualidade de Experiência (QoE) publicados pelos clientes Skype for Business Server 2019 no final de cada chamada. Essas consultas produzem alertas que identificam cenários onde os usuários provavelmente experimentarão a qualidade de mídia comprometida durante chamadas e conferências. Os dados são construídos com base em métricas-chave, como latência e perda de pacotes, que contribuem diretamente para a qualidade da experiência do usuário.   |
|Alertas de saúde do componente   |Os componentes individuais do servidor levantam alertas por meio de logs de eventos e contadores de desempenho para indicar condições de falha que podem afetar significativamente os cenários do usuário. Esses alertas indicam uma variedade de condições, como serviços que não estão em execução, altas taxas de falha, alta latência de mensagens ou problemas de conectividade.   |
|Monitoramento de saúde de dependência   |Skype for Business Server pode falhar por vários motivos externos. O Pacote de Gerenciamento monitora e coleta dados para dependências externas críticas que podem indicar problemas graves. Essas dependências incluem Serviços de Informações da Internet disponibilidade (IIS) e CPU de servidores usados para Skype for Business Server.   |
   
### <a name="alert-prioritization"></a>Priorização de Alerta

Os alertas são classificados nas seguintes categorias: 
  
 **Alertas de alta prioridade:** Esses alertas indicam condições que causam paralisações de serviço para grandes grupos de usuários e exigem ações imediatas. As paralisações detectadas por transações sintéticas e serviços offline (como Skype for Business Server conferência de áudio/vídeo) se qualificam como alertas de Alta Prioridade. Por outro lado, uma falha de componente em um único computador não é um alerta de Alta Prioridade. Skype for Business Server 2019 tem recursos de alta disponibilidade integrados para essas situações, por exemplo, vários Servidores Front-End atrás de balanceadores de carga.
  
 **Alertas de Prioridade Média:** Esses alertas indicam condições que afetam um subconjunto de usuários ou indicam problemas na qualidade da chamada, por exemplo, falhas de componentes, latência no estabelecimento de chamadas ou menor qualidade de áudio em chamadas. Os alertas nesta categoria são estado (ou seja, a natureza das alterações de alerta com base no estado da conexão de rede.) Por exemplo, se os tempos de estabelecimento de chamada indicarem latência, mas retornarem para um limite normal, esse alerta de Prioridade Média será resolvido automaticamente no System Center Operations Manager e os administradores não precisarão tomar medidas. Alertas que não podem ser resolvidos automaticamente normalmente são abordados pelos administradores no mesmo dia útil.
  
 **Outros alertas:** Esses alertas são gerados a partir de componentes que podem afetar um usuário ou subconjunto específico de usuários. Por exemplo, um alerta típico seria que o serviço de Livro de Endereços não poderia analisar a entrada dos Serviços de Domínio do Active Directory® (AD DS) para o usuário: testuser@contoso.com. Os administradores podem resolver esses alertas sempre que têm tempo disponível.
  
### <a name="synthetic-transactions"></a>Transações sintéticas

Skype for Business Server pacotes de gerenciamento 2019 oferecem cobertura maior para alertas por meio de transações sintéticas. As transações sintéticas Windows PowerShell cmdlets integrados ao pacote de gerenciamento do Operations Manager para testar cenários de usuário de ponta a ponta. Quando você designa um servidor para executar transações sintéticas, esses cmdlets são disparados periodicamente pelo pacote de gerenciamento. Falhas resultantes de uma transação sintética geram um alerta de estado. Aqui estão as transações sintéticas com suporte para Skype for Business Server 2019:
  
**Transações sintéticas com suporte para registro, presença e contatos**

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|1   |Registro (logon do usuário)   |Lync Server 2010 disponível e além   |
|2   |Serviço de Livro de Endereços (download de arquivo)   |Lync Server 2010 disponível e além   |
|3   |Consulta à web do Catálogo de endereços   |Lync Server 2010 disponível e além   |
|4   |Presença   |Lync Server 2010 disponível e além   |
|5   |Armazenamento de Contato Unificado   |Lync Server 2013 disponível e além   |
   
**Transações sintéticas com suporte para serviços ponto a ponto**

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|6    |Mensagens Instantâneas ponto a ponto   |Disponível no Lync Server 2010 e além   |
|7    |Vídeo de áudio ponto a ponto   |Disponível no Lync Server 2010 e além   |
|8    |Mensagem Instantânea Ponto a Ponto MCX (móvel)   |Disponível na versão de setembro de 2011 do Lync Server 2010 para Skype for Business 2019   |
 
> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
**Transações sintéticas com suporte para conferência e chat persistente**

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|9    |Conferências de áudio/vídeo   |Disponível no Lync Server 2010 e além   |
|10    |Conferência de Dados   |Disponível no Lync Server 2013 e além   |
|11   |Conferência de Mensagens Instantâneas   |Disponível no Lync Server 2010 e além   |
|12    | Chat persistente  |Disponível no Lync Server 2013 e além   |
|13   |Ingressar no Launcher (reuniões agendadas)   |Disponível no Lync Server 2013 e além   |
|14    |Discar em conferência   |Disponível no Skype for Business Server 2015 e além  |
|15    |Conferência de Compartilhamento de Aplicativos   |Disponível no Skype for Business Server 2015 e além  |
|16   |Conferência UCWA (união de reunião da Web)   |Disponível no Skype for Business Server 2015 e além  |
   
**Transações sintéticas com suporte para dependências de rede e parceiros**

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|17    |Conectividade de Borda AV   |Disponível no Lync Server 2013 e além   |
|18    |Conectividade de Borda AV Exchange Conectividade de Mensagem Unificada (caixa postal)   |Disponível no Lync Server 2013 e além   |
|19   |Chamada ponto a ponto PSTN   |Disponível no Lync Server 2010 e além   |
|20   |Mensagens Instantâneas XMPP (federação)   |Disponível no Lync Server 2013 e além   |
| 21    |Servidor de Interoperabilidade de Vídeo   |Disponível no Skype for Business Server 2015 e além   |
   
## <a name="how-health-rolls-up"></a>Como a saúde é acumulada

A tabela a seguir mostra os estados de saúde dos objetos do Skype for Business Server de monitoramento.
  
|Objeto Management Pack|Descrição|
|:-----|:-----|
|Skype for Business Server Implantação   |Representa a implantação do Skype for Business Server 2019 na organização.   |
|Skype for Business Server Site   |Representa locais geográficos diferentes onde os serviços são implantados.   |
|Skype for Business Server Pool   |Um Pool (dentro de um Site) que fornece serviços de comunicação, como mensagens instantâneas e conferência, aos usuários. Aplicável a pools de Front-End, pools de Borda e Pools de Diretor, mesmo que haja apenas um único computador em um determinado pool.   |
|Skype for Business Server Função   |Uma função de servidor que hospeda Skype for Business Server Service.   |
|Skype for Business Server Serviço   |Representa uma funcionalidade implantada em um computador específico (por exemplo, serviço de usuário em fp01.contoso.com).   |
|Skype for Business Server Componente   |Um componente do Serviço (por exemplo, o componente Download do Livro de Endereços faz parte do Serviço Web).   |
|Skype for Business Server Pool Watcher   |Uma instância de transações sintéticas que estão sendo executados em um pool.   |
|Skype for Business Server Registrador Watcher   |Uma instância de transações sintéticas que são executados em um pool de Registradores.   |
|Skype for Business Server User Services Pool Watcher   |Uma instância de transações sintéticas que são executados em um pool de Serviços de Usuário.   |
|Skype for Business Server Voice Pool Watcher   |Uma instância de transações sintéticas que são executados em um pool de Voz.   |
|Skype for Business Server Port Watcher   |Uma instância de Porta verifica em execução em um pool.   |
|Simples Url Watcher   |Executa a sondagem HTTPS das URLs simples configuradas em uma implantação.   |
   
![Rollup SCOM.](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Um pool Skype for Business Server pode conter vários sistemas Skype for Business Server individuais (com mais de uma função Skype for Business Server, serviço Skype for Business Server e Skype for Business Server componente). Portanto, a falha de um servidor ou componente individual é menos crítica para a saúde geral do pool de Skype for Business Server, pois outros servidores no mesmo pool podem fornecer o serviço de aplicativo ao cliente. A saúde será acumulada em um nível percentual para o pool de Skype for Business Server. 
  
O Skype for Business Server Pool Watcher executa transações sintéticas em um pool Skype for Business Server pool. A falha consecutiva de uma ou mais transações sintéticas (um processo conhecido como intervalo de sondagem consecutivo) reverterá o estado crítico de saúde para o nível do pool (o pior de qualquer transação sintética), conforme mostrado no diagrama a seguir. 
  
![Votação consecutiva de rolagem de SCOM.](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Práticas práticas: criar um pacote de gerenciamento para personalizações

Por padrão, o Operations Manager salva todas as personalizações, como substituições ao Pacote de Gerenciamento Padrão. Como prática prática, você deve criar um pacote de gerenciamento separado para cada pacote de gerenciamento selada que deseja personalizar. 
  
Ao criar um pacote de gerenciamento para armazenar configurações personalizadas para um pacote de gerenciamento selada, recomendamos nomear o novo pacote de gerenciamento adequadamente, como "Personalizações Skype for Business Server 2019".
  
A criação de um novo pacote de gerenciamento para armazenar personalizações de cada pacote de gerenciamento selada facilita a exportação das personalizações de um ambiente de teste para um ambiente de produção. Isso também facilita a exclusão de um pacote de gerenciamento, pois você deve excluir quaisquer dependências antes de poder excluir um pacote de gerenciamento. Se as personalizações de todos os pacotes de gerenciamento são salvas no Pacote de Gerenciamento Padrão e você precisa excluir um único pacote de gerenciamento, primeiro exclua o Pacote de Gerenciamento Padrão, que também exclui personalizações para outros pacotes de gerenciamento. 
  
## <a name="links"></a>Links

Os links a seguir conectam-se a informações sobre tarefas comuns associadas System Center Pacotes de Monitoramento 2012:
  
- [Ciclo de vida do Pacote de Gerenciamento](/previous-versions/system-center/system-center-2012-R2/hh212732(v=sc.12))
    
- [Como importar um pacote de gerenciamento no Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212691(v=sc.12))
    
- [Como substituir uma regra ou monitor](/previous-versions/system-center/system-center-2012-R2/hh212869(v=sc.12))
    
- [Como criar uma conta executar como no Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh321655(v=sc.12))
    
- [Gerenciando executar contas e perfis](/previous-versions/system-center/system-center-2012-R2/hh212714(v=sc.12))
    
- [Como exportar um pacote de gerenciamento do Operations Manager](/previous-versions/system-center/system-center-2012-R2/hh320149(v=sc.12))
    
- [Como remover um pacote de gerenciamento do Operations Manager](/previous-versions/system-center/system-center-2012-R2/hh230746(v=sc.12))
    
Os links a seguir conectam-se a informações sobre tarefas comuns associadas a System Center 2007 Monitoring Packs:
  
- [Administrando o ciclo de vida do Pacote de Gerenciamento](/previous-versions/system-center/operations-manager-2007-r2/cc974486(v=technet.10))
    
- [Como importar um pacote de gerenciamento no Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/cc974494(v=technet.10))
    
- [Como monitorar o uso de substituições](/previous-versions/system-center/operations-manager-2007-r2/bb309719(v=technet.10))
    
- [Como criar uma conta executar como no Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/bb309445(v=technet.10))
    
- [Como modificar um perfil de executar como existente](/previous-versions/system-center/operations-manager-2007-r2/dd891202(v=technet.10))
    
- [Como exportar personalizações do Pacote de Gerenciamento](/previous-versions/system-center/operations-manager-2007-r2/cc974487(v=technet.10))
    
- [Como remover um pacote de gerenciamento](/previous-versions/system-center/operations-manager-2007-r2/cc974489(v=technet.10))
    
Para saber mais sobre o Operations Manager e os pacotes de monitoramento, consulte o [fórum System Center de comunidade do Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Um recurso útil é o [blog System Center Operations Manager Unleashed,](https://opsmgrunleashed.wordpress.com/) que contém postagens "Por Exemplo" para pacotes de monitoramento específicos.
  
Para obter informações adicionais sobre o Operations Manager, consulte os seguintes blogs: 
  
- [Blog de Equipe do Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Ideias sobre OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
    
> [!IMPORTANT]
> Todas as informações e conteúdos em sites que não são da Microsoft são fornecidos pelo proprietário ou pelos usuários do site. A Microsoft não faz garantias, expressas, implícitas ou estatutários, quanto às informações neste site.
  
## <a name="see-also"></a>Confira também

[Skype for Business Server ferramentas de gerenciamento 2019](../management-tools-2019.md)