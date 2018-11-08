---
title: Gerenciar Skype para negócios 2019 de servidor usando o pacote de gerenciamento do SCOM
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/26/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Saiba como configurar seu Skype para Business Server 2019 infra-estrutura para funcionar com o System Center Operations Manager.'
ms.openlocfilehash: 89aeb18f896510dd251519b8a4fb618012d7e222
ms.sourcegitcommit: 139b3d3b7fcc1dd7fba7fd14ff34e4ffdfcc7eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2018
ms.locfileid: "26216079"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Gerenciar Skype para negócios 2019 de servidor usando o pacote de gerenciamento do SCOM
 
**Resumo:** Saiba como configurar seu Skype para Business Server 2019 infra-estrutura para funcionar com o System Center Operations Manager.
  
Em um mundo ideal, você nunca seria encontrar problemas com Skype para Business Server 2019. No entanto, Skype para Business Server pode ser afetado por fatores externos — por exemplo, falhas e falhas de hardware de rede. Usando Skype para pacotes de gerenciamento de 2019 Business Server, você pode identificar e abordar problemas potenciais de proativamente. Dessa forma, o Skype para pacotes de gerenciamento do Business Server 2019 estender os recursos do System Center Operations Manager.
  
Essas informações foi escritas com base na versão 9319.0 do pacote de monitoramento para Skype Business Server 2019 software de comunicações.
  
## <a name="configuration-overview"></a>Visão Geral da Configuração

 Para configurar sua Skype para Business Server 2019 infra-estrutura para funcionar com o System Center Operations Manager, você deve fazer três coisas:
  
Identificar e [Configure the Primary Management Server](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md). Para fazer isso, você deve instalar o System Center Operations Manager 2012 SP1 ou R2. 
  
 Identificar e [Configure o Skype para computadores Business Server que serão monitorados](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md). Para monitorar um Skype para o computador servidor de negócios usando o System Center Operations Manager, você deve instalar os arquivos de agente do System Center Operations Manager e configurar cada servidor para agir como um proxy. 
  
 Identificar e [instalar e configurar nós do Inspetor](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md). Nós do Inspetor são computadores que executam periodicamente Skype para transações sintéticas do Business Server — os cmdlets do Windows PowerShell que verifique se essa chave Skype para componentes de servidor de negócios, a capacidade de fazer logon no sistema ou a capacidade de trocar instantânea mensagens, estão funcionando conforme o esperado. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Suporte de agente e o servidor de gerenciamento do System Center Operations Manager raiz

Os pacotes de gerenciamento podem ser usados com o System Center Operations Manager 2007 R2 (64-bit) (suportado apenas a fins de migração) ou o System Center Operations Manager 2012 SP1 &amp; R2 (64 bits). A tabela a seguir mostra as configurações suportadas para os pacotes de gerenciamento para Skype para Business Server 2019: 
  
|**Configuração**|**Suporte?**|
|:-----|:-----|
|Sistema operacional Windows Server 2008 R2  <br/> Sistema operacional Windows Server 2012 R2  <br/> |Sim. Ambos em Skype para servidor de Business Server 2019 e nós do Inspetor de transação sintética.  <br/> |
|Servidores em Cluster  <br/> |Sem suporte.  <br/> |
|Monitoramento sem agente  <br/> |Sem suporte.  <br/> |
|Ambiente Virtual  <br/> |Sim.  <br/> |
|Funções do servidor associadas a um domínio  <br/> |Todos os Skype interno para funções de servidor de Business Server 2019 deve ser associado ao domínio.  <br/> |
|Funções autônomas do servidor  <br/> |Skype para os servidores de borda de 2019 Business Server não são necessários a ser associado ao domínio.  <br/> |
|Limitações da Topologia  <br/> |Todas as funções do servidor em uma implantação devem ser monitoradas a partir do mesmo Grupo de Gerenciamento do Gerente de Operações.  <br/> |
|Nó do Inspetor das Transações Sintéticas  <br/> |A disponibilidade do cenário de monitoramento é suportada com um nó do inspetor de transações sintéticas (configuração adicional obrigatória).  Os nós do inspetor não precisam estar associados a um domínio.  <br/> |
   
A tabela a seguir mostra a capacidade e os requisitos de sistema operacional para um nó do inspetor da transação sintética:
  
|**Componente de hardware**|**Requisitos mínimos**|
|:-----|:-----|
|CPU  <br/> |Um dos seguintes:  <br/> Processador de 64 bits, quad-core, 2.33 GHz ou superior  <br/> Processador de 2 vias e 64 bits, dual-core, 2.33 GHz ou superior  <br/> |
|Memória  <br/> |8 GB  <br/> |
|Sistema operacional  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Rede  <br/> |1 adaptador de rede com 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Pré-requisitos

Para executar um nó do inspetor da transação sintética, primeiro você precisa instalar o seguinte:
  
- Agente do System Center Operations Manager 
    
-  Microsoft.NET Framework 4.5
    
- Skype para arquivos de instalação do servidor de negócios principais (ocscore. msi) e o Unified Communications Managed API (UCMA) (versões devem corresponder o Skype para Business Server Watchernode versão)
    
## <a name="files-in-this-monitoring-pack"></a>Arquivos neste Pacote de Monitoramento

O pacote de monitoramento para Skype para Business Server 2019 inclui os seguintes arquivos:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- Watchernode.msi
    
## <a name="whats-new"></a>Novidades

Os seguintes recursos são novos no Skype para pacotes de gerenciamento do Business Server 2019.
  
- **Descoberta automática para logon do cliente** Aplicativos cliente que entrar no Skype para Business Server 2019 frequentemente automaticamente descubram o servidor para entrar no. As transações sintéticas agora oferecem suporte para verificar se a descoberta automática está configurada corretamente.
    
- **Execute a intervalos a transação sintética personalizado** Para simplificar o processo de nós do Inspetor de configuração, as transações sintéticas podem compartilhar contas de usuário. Isso diminui a frequência com que os testes são executados uma vez que os testes são serializados para evitar conflitos. Por padrão, as transações sintéticas são executadas a cada 15 minutos para garantir que todos os testes sejam executados em tempo hábil. Os administradores que optam por utilizar mais usuários ou menos testes por usuário agora também podem reduzir o intervalo de execução.
    
- **Serviços de interoperabilidade de vídeo de transação sintética** Clientes que estão migrando para o Skype para Business Server 2019 de outras soluções de fornecedor geralmente desejam continuar usando os dispositivos de videoconferência (VTCs) desses outros fornecedores. Servidor de interoperabilidade de vídeo é um novo Skype para Business Server 2019 função de servidor que permite aos clientes continuar a usar o Cisco VTCs em suas salas de conferência conectando-se à Cisco CUCM por meio de um tronco SIP de vídeo. Este recurso também adiciona uma transação sintética para ajudar a verificar se o Servidor de Interoperabilidade de Vídeo está ativo e pode lidar com conexões de entrada através de um tronco SIP de vídeo.
    
- **Transação Sintética de Conferência para Compartilhamento de Aplicativos** Agora, a validação do cenário completo para Conferências de Compartilhamento de Aplicativos é compatível.
    
## <a name="monitoring-scenarios"></a>Monitoramento de Cenários

O Skype para o pacote de gerenciamento do Business Server 2019 aproveita uma variedade de recursos para ajudá-lo a detectar e diagnosticar problemas. Esses recursos oferecem a integridade de um Skype para ambiente de negócios Server 2019 visibilidade em tempo real.
  
|**Monitoramento de Cenário**|**Descrição**|
|:-----|:-----|
|Transações sintéticas  <br/> | Cmdlets do Windows PowerShell para testar e ajudar a garantir a alta disponibilidade dos cenários, como sign in, presença, mensagens Instantâneas e conferência para usuários. <br/> As transações sintéticas podem ser executadas de qualquer localização geográfica incluindo locais dento da empresa, fora da empresa e filiais.  <br/> Quando uma transação sintética falhar, os logs HTML são criados para ajudar a determinar a natureza exata da falha. Isso inclui entender qual ação falhou, a latência de cada ação, a linha de comando usada para executar o teste e o erro específico que ocorreu.  <br/> |
|Alertas de confiabilidade de chamada  <br/> |Registros de detalhes de chamadas (CDRs) escritos por Skype para os servidores do Business Server 2019 refletir se os usuários são capazes de se conectar a uma chamada ou por que uma chamada é encerrada. Os alertas de confiabilidade de chamada consultam o banco de dados do CDR para produzir alertas que indicam quando um grande número de usuários experimentam problemas de conectividade para chamadas ponto a ponto ou funcionalidade básica de conferência.  <br/> A cobertura do cenário inclui chamadas de áudio, mensagens instantâneas (IM) de ponto a ponto e outros recursos de conferência.  <br/> |
|Alertas de qualidade de mídia  <br/> |Consultas de banco de dados que olhar sobre os relatórios de qualidade da experiência (QoE) publicados pelo Skype para clientes corporativos Server 2019 no final de cada chamada. Essas consultas produzem alertas que identificam cenários nos quais os usuários provavelmente terão uma qualidade de mídia comprometida durante chamadas e conferências. Os dados estão embutidos nas principais métricas como latência e perda de pacote, que contribuem diretamente para a qualidade da experiência do usuário.  <br/> |
|Alertas da Integridade do componente  <br/> |Os componentes individuais do servidor geram alertas via logs de eventos e contadores de desempenho para indicar condições de falha que possam afetar significativamente os cenários do usuário. Esses alertas indicam uma variedade de condições como serviços que não estão funcionando, alta taxa de falhas, alta latência de mensagens ou problemas de conectividade.  <br/> |
|Monitoramento de Integridade da Dependência  <br/> |Skype para Business Server pode falhar por vários motivos externos. O Pacote de Gerenciamento monitora e os coleta dados para dependência externas críticas que podem indicar problemas graves. Essas dependências incluem disponibilidade de serviços de informações da Internet (IIS) e CPU dos servidores usado para Skype para o servidor de negócios.  <br/> |
   
### <a name="alert-prioritization"></a>Priorização de Alertas

Os alertas são classificados de acordo com as seguintes categorias: 
  
 **Alertas de alta prioridade:** Esses alertas indicam condições que causam interrupções de serviço para grandes grupos de usuários e exigem ação imediata. Interrupções detectadas pelos serviços offline (por exemplo, o Skype para conferência de áudio/vídeo do Business Server) e de transações sintéticas qualificam como alertas de alta prioridade. Por outro lado, uma falha de componente em uma única máquina não é um alerta de alta prioridade. Skype para Business Server 2019 tem recursos internos de alta disponibilidade para essas situações — por exemplo, vários servidores Front-End atrás balanceadores de carga.
  
 **Alertas de prioridade média:** Esses alertas indicam condições que afetam um subconjunto de usuários ou indicam problemas de qualidade de chamada — por exemplo, falhas de componente, latência em estabelecimento de chamadas ou mais baixa qualidade de áudio em chamadas. Alertas nesta categoria são com informações de estado (ou seja, a natureza das alterações alertas baseado no estado de conexão de rede.) Por exemplo, se tempos de estabelecimento de chamada indicam latência, mas volte a um limite normal, este alerta médio prioridade seria autoresolvido no System Center Operations Manager e os administradores não precisam tomar ação. Os alertas que não podem ser resolvidos automaticamente são geralmente solucionados pelos administradores no mesmo dia útil.
  
 **Outros alertas:** Esses alertas são gerados a partir de componentes que podem afetar um usuário específico ou um subconjunto de usuários. Por exemplo, um alerta típico seria que o serviço de Catálogo de Endereços não consiga analisar a entrada dos Serviços de Domínio do Active Directory® (AD DS) para o usuário: testuser@contoso.com. Os administradores podem corrigir esses alertas sempre que tiverem tempo disponível.
  
### <a name="synthetic-transactions"></a>Transações Sintéticas

Skype para pacotes de gerenciamento do Business Server 2019 oferecem maior cobertura para alertas por meio de transações sintéticas. Transações sintéticas são integrados ao pacote de gerenciamento do Operations Manager para testar os cenários de usuário de ponta a ponta cmdlets do Windows PowerShell. Quando você designa um servidor para executar transações sintéticas, esses cmdlets são acionados periodicamente pelo pacote de gerenciamento. Falhas resultantes de uma transação sintética geram um alerta com informações de estado. Aqui estão as transações sintéticas com suporte para Skype para Business Server 2019:
  
**Transações Sintéticas Suportadas para Registro, Presença e Contatos**

||||
|:-----|:-----|:-----|
|1  <br/> |Registro (login do usuário)  <br/> |O Lync Server 2010 disponível e superiores  <br/> |
|2  <br/> |Serviço de Catálogo de Endereços (download de arquivo)  <br/> |O Lync Server 2010 disponível e superiores  <br/> |
|3  <br/> |Consulta à Web do Catálogo de Endereços  <br/> |O Lync Server 2010 disponível e superiores  <br/> |
|4  <br/> |Presença  <br/> |O Lync Server 2010 disponível e superiores  <br/> |
|5  <br/> |Repositório Unificado de Contatos  <br/> |Lync Server 2013 disponíveis e superiores  <br/> |
   
**Transações Sintéticas Suportadas para Serviços Ponto-a-Ponto**

||||
|:-----|:-----|:-----|
|6  <br/> |Sistema de Mensagens Instantâneas Ponto-a-Ponto  <br/> |Disponíveis no Lync Server 2010 e posteriores  <br/> |
|7  <br/> |Áudio Vídeo Ponto-a-Ponto  <br/> |Disponíveis no Lync Server 2010 e posteriores  <br/> |
|8  <br/> |Sistema de Mensagens Instantâneas Ponto-a-Ponto do MCX (móvel)  <br/> |Disponíveis na versão de setembro de 2011 do Lync Server 2010 para Skype para negócios 2019  <br/> |
 
> [!NOTE]
> Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.
  
**Transações Sintéticas Suportadas para Conferência e Chat Persistente**

||||
|:-----|:-----|:-----|
|9  <br/> |Conferências de áudio/vídeo  <br/> |Disponíveis no Lync Server 2010 e posteriores  <br/> |
| 10  <br/> |Conferência de dados  <br/> |Disponíveis no Lync Server 2013 e posteriores  <br/> |
|11  <br/> |Conferência de Mensagens Instantâneas  <br/> |Disponíveis no Lync Server 2010 e posteriores  <br/> |
|12  <br/> | Chat Persistente <br/> |Disponíveis no Lync Server 2013 e posteriores  <br/> |
|13  <br/> |Iniciador de Ingresso (reuniões agendadas)  <br/> |Disponíveis no Lync Server 2013 e posteriores  <br/> |
|14  <br/> |Conferência discada  <br/> |Disponível no Skype para Business Server 2015 e além <br/> |
|15  <br/> |Conferência para Compartilhamento de Aplicativos  <br/> |Disponível no Skype para Business Server 2015 e além <br/> |
|16  <br/> |Conferência de UCWA (participação de reunião na web)  <br/> |Disponível no Skype para Business Server 2015 e além <br/> |
   
**Transações Sintéticas Suportadas para Dependências de Rede e Parceiro**

||||
|:-----|:-----|:-----|
|17  <br/> |Conectividade de Borda AV  <br/> |Disponíveis no Lync Server 2013 e posteriores  <br/> |
|18  <br/> |Conectividade de Borda AV e Conectividade de Mensagem Unificada do Exchange (caixa postal)  <br/> |Disponíveis no Lync Server 2013 e posteriores  <br/> |
|19  <br/> |Chamada Ponto-a-Ponto PSTN  <br/> |Disponíveis no Lync Server 2010 e posteriores  <br/> |
|20  <br/> |Sistema de Mensagens Instantâneas XMPP (federação)  <br/> |Disponíveis no Lync Server 2013 e posteriores  <br/> |
|21  <br/> |Servidor de Interoperabilidade de Vídeo  <br/> |Disponível no Skype para Business Server 2015 e além  <br/> |
   
## <a name="how-health-rolls-up"></a>Estado de Integridade

A tabela a seguir mostra os estados de integridade de objetos do Skype para Business Server monitoring pack.
  
|**Objeto do Pacote de Gerenciamento**|**Descrição**|
|:-----|:-----|
|Skype para implantação de servidor de negócios  <br/> |Representa a implantação do Skype para Business Server 2019 na organização.  <br/> |
|Skype para Business Server Site  <br/> |Representa as diferentes áreas geográficas onde os serviços são implantados.  <br/> |
|Skype para o Pool de servidores corporativos  <br/> |Um pool (dentro de um site) que proporciona serviços de comunicação, como mensagens instantâneas e conferências, aos usuários. Pode ser aplicado a pools de Front-Ends, pools de Borda e pools de Diretor, mesmo se houver apenas uma única máquina em um determinado pool.  <br/> |
|Skype para a função de servidor de negócios  <br/> |Uma função de servidor que hospeda o Skype para o serviço do servidor de negócios.  <br/> |
|Skype para o serviço do servidor de negócios  <br/> |Representa uma funcionalidade implantada em uma máquina específica (por exemplo, serviço de usuário no fp01.contoso.com).  <br/> |
|Skype para o componente do servidor de negócios  <br/> |Um componente do Serviço (por exemplo, o componente do download do Catálogo de Endereços é uma parte do Serviço da Web).  <br/> |
|Skype para negócios Inspetor de Pool de servidor  <br/> |Uma instância do transações sintéticas que são executadas em um pool.  <br/> |
|Skype para negócios servidor registrador Inspetor  <br/> |Uma instância de transações sintéticas que são executadas em um pool do Registrador Avançado.  <br/> |
|Skype para Business Server usuário serviços Pool Inspetor  <br/> |Uma instância de transações sintéticas que são executadas em um pool de Serviços de Usuário.  <br/> |
|Skype para Business Server voz Pool Inspetor  <br/> |Uma instância de transações sintéticas que são executadas em um pool de voz.  <br/> |
|Skype para Inspetor de porta do servidor de negócios  <br/> |Uma instância da Porta verifica a execução em um pool.  <br/> |
|Inspetor de URL Simples  <br/> |Realiza a sondagem HTTPS dos URLs simples configurados em uma implantação.  <br/> |
   
![SCOM Rollup](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Um Skype para pool de servidores de negócios pode conter vários Skype individual para sistemas de Business Server (com mais de um Skype para Business Server role, Skype para o serviço servidor de negócios e Skype para o componente do servidor de negócios). Portanto, a falha de um servidor individual ou componente é menos importante para a integridade geral do Skype para o pool de servidores corporativos, porque a outros servidores no mesmo pool podem fornecer o serviço de aplicativo para o cliente. A integridade serão acumular em um nível de porcentagem do Skype para pool de servidores de negócios. 
  
O Skype para Inspetor de Pool do servidor de negócios executa as transações sintéticas contra um Skype para pool de servidores de negócios. A falha consecutiva de uma ou mais transações sintéticas (um processo conhecido como intervalo consecutivo de sondagem) atingirá o estado crítico de integridade a nível do pool (o pior de qualquer transação sintética), conforme mostrado no diagrama a seguir. 
  
![Sondagem consecutiva de SCOM Rollup](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Prática recomendada: Criar um Pacote de Gerenciamento para personalizações

Por padrão, o Operations Manager salva todas as personalizações, como substituições no Pacote de Gerenciamento Padrão. Como prática recomendada, você deve criar uma pacote de gerenciamento separado para cada pacote de gerenciamento selado que você deseja personalizar. 
  
Quando você cria um pacote de gerenciamento para armazenar as configurações personalizadas para um pacote de gerenciamento fechada, recomendamos que o novo pacote de gerenciamento de nomeação apropriadamente, como "Skype para personalizações de servidor 2019 Business".
  
A criação de um novo pacote de gerenciamento para armazenar personalizações de cada pacote de gerenciamento selado facilita a exportação das personalizações de um ambiente de teste para um ambiente de produção. Isso também facilita a exclusão de um pacote de gerenciamento, pois você deve excluir quaisquer dependências antes de excluir um pacote de gerenciamento. Se as personalizações para todos os pacotes de gerenciamento forem salvas no Pacote de Gerenciamento Padrão e você precisar excluir um único pacote de gerenciamento, você deve primeiro excluir o Pacote de Gerenciamento Padrão, que também excluirá as personalizações para outros pacotes de gerenciamento. 
  
## <a name="links"></a>Links

Os links abaixo conectam você com as informações sobre tarefas comuns que estão associados aos Pacotes de Monitoramento do System Center 2012:
  
- [Clico de Vida do Pacote de Gerenciamento](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Como Importar um Pacote de Gerenciamento no Operations Manager 2012 ](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Como sobrepor uma Regra ou Monitor ](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Como Criar uma Conta Executar Como no Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Gerenciando Contas Executar como e Perfis](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Como Exportar um Pacote de Gerenciamento do Operations Manager](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Como Remover um Pacote de Gerenciamento do Operations Manager](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
Os links abaixo conectam você com as informações sobre tarefas comuns que estão associados aos Pacotes de Monitoramento do System Center 2007:
  
- [Administrando o Ciclo de Vida do Pacote de Gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Como Importar um Pacote de Gerenciamento no Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Como Monitorar Usando Substituições](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Como Criar uma Conta Executar como no Operations Manager 2007 ](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Como Modificar um Perfil Executar como Existente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Como Exportar Personalizações do Pacote de Gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Como Remover um Pacote de Gerenciamento](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Para perguntas sobre o Operations Manager e pacotes de monitoramento, consulte o [fórum da comunidade do System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Um recurso útil é o blog do [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) , que contém "Por exemplo" postagens para pacotes de monitoramento específicos.
  
Para obter informações adicionais sobre o Operations Manager, consulte os seguintes blogs: 
  
- [Blog da Equipe do Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog do OpsMgr de Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Ideias sobre OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de Raphael Burri](https://rburri.wordpress.com/)
    
- [Gerenciamento de Espaço de BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Todas as informações e conteúdos em sites que não sejam da Microsoft são fornecidos pelo proprietário ou por usuários do website. A Microsoft não oferece garantias expressas, implícitas ou estatutárias relativas às informações contidas nesse website. 
  
## <a name="see-also"></a>Consulte também

[Skype para ferramentas de gerenciamento de servidor 2019 de negócios](../management-tools-2019.md)
