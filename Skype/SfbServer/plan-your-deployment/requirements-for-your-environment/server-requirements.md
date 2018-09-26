---
title: Requisitos de servidor no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
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
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Resumo: prepare seus servidores do Skype for Business Server 2015 com este tópico. Hardware, sistema operacional, bancos de dados, software, todos os requisitos do sistema e recomendações estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas de seu farm de servidores.'
ms.openlocfilehash: 4e6bbe71a75097e9b1a3a34752d9d1cd46d59307
ms.sourcegitcommit: fbef2bfa4e5eb27799aa25f0e890cfb18013cf72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2018
ms.locfileid: "25040738"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos de servidor no Skype for Business Server 2015
 
**Resumo:** prepare seus servidores do Skype for Business Server 2015 com este tópico. Hardware, sistema operacional, bancos de dados, software, todos os requisitos do sistema e recomendações estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas de seu farm de servidores.
  
Como você pode esperar, existem alguns preparativos a serem antes de começar a implantação do Skype para Business Server 2015. Este artigo explica como deve ser o planejamento dos seguintes itens:
  
- [Hardware para o Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operacionais para Skype para Business Server 2015](server-requirements.md#OS)
  
- [Bancos de dados back-end compatíveis com o Skype for Business Server 2015](server-requirements.md#DBs)
  
- [O software que deve ser instalado antes da implantação do Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para o Skype for Business Server 2015
<a name="Hardware"> </a>

Agora que você tem sua topologia para baixo (e, se não fizer isso, você pode visitar o tópico [Noções básicas de topologia para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), é hora de pensar em servidores. Skype para servidores de negócios Server 2015 exigirá hardware de 64 bits. Nossas recomendações para hardware estão listadas abaixo. Eles não têm requisitos, mas eles reflitam os requisitos necessários para um desempenho ideal. Temos uma documentação de planejamento de capacidade que ajudará você a determinar se precisa de mais alguma coisa, dependendo das suas circunstâncias.
  
Hardware recomendado para servidores Front-End, servidores Back-End, servidores Standard Edition e servidores de Chat persistente:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para Skype para funções de negócios Server 2015.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DAS OPÇÕES:  <br/> • 8 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre (dois dos discos usando RAID 1 e 6 usando RAID 10).   <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar ao de 8 unidades de disco mecânicas de 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> Configurações duas ou multihomed são **não** suportado para servidores Front-End, servidores Back-End, Standard Edition servidores e os servidores de Chat persistente. <br/> Desde que não sejam expostos ao sistema operacional e sejam usados para monitorar e gerenciar o hardware de servidor, você pode ter sistemas de gerenciamento fora de banda, como DRAC ou ILO. Esse cenário não constitui um servidor multihomed e tem suporte.<br/> |
   
Hardware recomendado para servidores de borda, servidores de mediação autônomo, servidores de interoperabilidade de vídeo e diretores:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de 64 bits, quad-core, 2.26 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para Skype para funções de negócios Server 2015.  <br/> |
|Memória  <br/> |16 GB.  <br/> |
|Disco  <br/> |UMA DESTAS OPÇÕES:  <br/> • 4 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre (os discos devem estar em uma configuração de 2x RAID 1).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar ao de 4 unidades de disco mecânicas de 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> São configurações duas multihomed ou **não** tem suporte para servidores de interoperabilidade de vídeo e diretores. <br/> Servidores de borda exigem duas interfaces de rede que são adaptadores de rede dual-port, 1 Gbps ou superior (ou dois adaptador de rede pareados, com um total de quatro, sendo que cada par está combinado com um único endereço MAC e um único endereço IP).  <br/> Em autônoma, a instalação de placas de interface de rede adicionais (NICs) para permitir que a configuração de um endereço IP PSTN específico de servidores de mediação é suportado.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operacionais para Skype para Business Server 2015
<a name="OS"> </a>

Depois que você tiver o hardware no lugar, você precisará instalar os sistemas operacionais (SO). Estes são o sistema operacional que permitirá que você instalar e usar com êxito o Skype para Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|Windows Server 2012 R2 Datacenter SO com todas as atualizações necessárias instaladas.  <br/> |Windows Server 2012 R2 Standard SO com todas as atualizações necessárias instaladas.  <br/> |
|Windows Server 2012 Datacenter SO com todas as atualizações necessárias instaladas.  <br/> |Windows Server 2012 Standard SO com todas as atualizações necessárias instaladas.  <br/> |
   
Se não for dessa lista, ele não funcionará corretamente, não tente novas instalações do Skype para Business Server 2015.
  
> [!NOTE]
> Você pode ter notado que o Windows Server 2008 R2 não está nessa lista. Isso porque recomendamos o Windows Server 2012 R2 para todos os novos servidores a serem usados para o Skype for Business. Você só poderia usar o Windows Server 2008 R2 quando já tiver servidores instalados com o Lync Server 2013 e quiser fazer uma atualização in-loco desses servidores. O Windows Server 2008 R2 chegou ao final do ciclo de vida do suporte comercial no dia 13 de janeiro de 2015. 
  
Além da última versão do service pack, as atualizações a seguir devem estar instaladas quando for pertinente para você:
  
- Para o Windows Server 2012, instale o artigo 2858668 da base de dados de conhecimento antes de fazer uma atualização. [Obtê-lo aqui](https://support.microsoft.com/en-us/kb/2858668/).
    
- Se você tem o Windows Server 2012 R2, instale o artigo 2982006 da base de dados de conhecimento antes de fazer uma atualização. [Ele é encontrado aqui](https://support.microsoft.com/en-us/kb/2982006/).
    
- Se você está fazendo uma atualização em uma caixa do Windows Server 2008 R2 (veja a Observação acima), instale o artigo 2533623 da base de dados de conhecimento primeiro. [É neste link](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bancos de dados back-end compatíveis com o Skype for Business Server 2015
<a name="DBs"> </a>

Ao instalar o Skype para Business Server 2015 Standard Edition, você terá de 2014 do SQL Server Express (edição de 64 bits) é instalada automaticamente também.
  
Skype para Business Server 2015 Enterprise Edition é um pouco mais complicado, mas a lista com suporte é abaixo (tudo é edição de 64 bits, você perceberá, por favor, não use as edições de 32 bits):
  
||||
|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2016 Enterprise (edição de 64 bits) com Service Pack 1 ou posterior e você deve executar com Skype para negócios atualização cumulativa 7 ou posterior ([Baixar Skype para atualização cumulativa de negócios](https://support.microsoft.com/en-us/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (edição de 64 bits) e você deve executar com 6 de atualização cumulativa ou posterior ([download de 6 de atualização cumulativa](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.  <br/> |Microsoft SQL Server 2008 R2 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.  <br/> |
|Microsoft SQL Server 2016 Standard (edição de 64 bits) com Service Pack 1 ou posterior e você deve executar com Skype para negócios atualização cumulativa 7 ou posterior ([Baixar Skype para atualização cumulativa de negócios](https://support.microsoft.com/en-us/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (edição de 64 bits) e você deve executar com 6 de atualização cumulativa ou posterior ([download de 6 de atualização cumulativa](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.  <br/> |Microsoft SQL Server 2008 R2 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente  <br/> |
   
Se você não vir a edição do SQL Server que você deseja usar listado aqui, você não pode usá-lo.
  
> [!NOTE]
> Você vai também precisa instalar o SQL Server Reporting Services para a função Monitoring Server, mas precisamos que você saiba que isso não vai ser suportados com SQL sempre em até post-RTM. 

### <a name="microsoft-exchange-storage"></a>Armazenamento do Microsoft Exchange
Arquivos de conteúdo das reuniões, tais como apresentações em PowerPoint, são arquivados como anexo. Se você deseja armazenar Skype para dados de arquivo morto de negócios com os dados de conformidade do Exchange, você deve usar o Exchange para sua implantação do Exchange e certifique-se de que o tamanho máximo de armazenamento suporta o armazenamento dos arquivos de conteúdo de reunião. Você deve implantar o Exchange antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para arquivamento no Skype for Business Server 2015
  
O arquivamento não é uma função de servidor definidas, você não precisará instalar um servidor separado para arquivamento. Agentes de coleta de dados Unificação instalados e ativados automaticamente em cada pool de Front End do Enterprise Edition e cada servidor Standard Edition. Você precisa habilitar e publicar a topologia do seu arquivamento usando o Construtor de Topologias.
    
Arquivamento usa o Skype para armazenamento de arquivos do servidor de negócios para armazenamento temporário de reunião arquivos de conteúdo, de modo que você não configurar um repositório de arquivos para arquivamento.
    
Microsoft Message Queuing não é necessária.
    
Além disso, você deve configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui escolher um dos Exchange ou usando o SQL Server de armazenamento de arquivamento.   Skype para requisitos de infraestrutura de arquivamento de servidor de negócios são iguais às propriedades de implantação do Skype para Business Server. Para obter detalhes, consulte [Requirements for sua Skype para ambiente de negócios](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Para suportar usuários que não esteja hospedados nos servidores do Exchange, ou se você não quiser usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados do SQL Server de 64 bits. 
    
Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte a [documentação do SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
O aumento de carga para arquivamento pode ser significativo. Portanto, você deve assegurar que o espaço em disco é adequado para servidores Front-End no qual o arquivamento estiver habilitado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Mirroring, SQL Clustering e SQL Always On

É possível usar o espelhamento SQL ou cluster SQL com Skype para Business Server 2015, ela é suportada. SQL espelhamento configurada por meio do Skype para construtor de topologia de servidor de negócios. Se você estiver intenção sobre como configurar o Clustering do SQL, que é feito no SQL Server.
  
Verifique se que você tem uma configuração ativa/passiva para agrupamento do SQL, já que é o que é suportado. Não compartilhe o nó passivo com qualquer outra instância do SQL.
  
Você pode ter os seguintes itens para clustering de failover:
  
Dois nós:
  
- Microsoft SQL Server 2016 Standard (edição de 64 bits) com Service Pack 1 ou posterior. É recomendável executar com o service pack mais recente.

- Microsoft SQL Server 2014 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
-  Microsoft SQL Server 2012 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
- Microsoft SQL Server 2008 R2 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
Dezesseis nós:

- Microsoft SQL Server 2016 Enterprise (edição de 64 bits) com Service Pack 1 ou posterior. É recomendável executar com o service pack mais recente.
  
- Microsoft SQL Server 2014 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
- Microsoft SQL Server 2012 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
- Microsoft SQL Server 2008 R2 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
> [!IMPORTANT]
> Para atualizar, queremos para garantir que em seus servidores Front-End você possui pelo menos, SQL Server 2012 SP1 instalado antes da atualização. [Aqui está um link](https://www.microsoft.com/en-us/download/details.aspx?id=35575) para o SP1, se você quiser baixá-lo imediatamente.
  
Se você precisar ler até obter mais informações sobre o espelhamento SQL, temos uma alta disponibilidade de servidor Back-End em Skype para tópico Business Server 2015. Configure o clustering do SQL Server para Skype para Business Server 2015 tem as etapas para obtenção de clustering ready. Também há ainda mais links em failover cluster do SQL, de [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)e [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Novo na versão 2015 é suporte SQL Always On. Ele é suportado, e você pode ler mais sobre ele no tópico de [alta disponibilidade do servidor Back-End no Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .

> [!NOTE]
> Espelhamento do SQL está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. Os métodos de cluster de failover de grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn (FCI) e SQL terão preferência com Skype para Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>O software que deve ser instalado antes da implantação do Skype for Business Server 2015
<a name="Software"> </a>

Há algumas coisas que você vai precisar instalar ou configurar para qualquer servidor executando o Skype para Business Server 2015 e são listadas abaixo. Depois disso, há requisitos adicionais para funções de servidor específicas.
  
 **Todos os servidores:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Skype todos os servidores do Business Server precisa Windows PowerShell 3.0 instalado.  <br/> • Se você estiver fazendo a instalação no Windows Server 2012 ou Windows Server 2012 R2, você estiver definido, pois ele já está.  <br/> • Se você estiver fazendo uma atualização no Windows Server 2008 R2, você pode baixar o [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) para instalá-la. <br/> **Dica:** Depois que você tiver o PowerShell correto no daí, confirme se ele está BuildVersion 6.2.9200.0 ou posterior indo para o PowerShell solicitar e digitando `$PSVersionTable`. Você verá todas as informações de que precisa.  <br/> |
|Microsoft .NET Framework  <br/> |Os serviços WCF é um **recurso** que não tenha instalado como um recurso do Windows, em **Gerenciador de servidores**, nenhum download necessário. <br/> • Você precisará certificar-se, quando você instalar esse recurso, ou se ele já estiver instalado e você está verificando nele, a opção de **Ativação de HTTP** também é verificada e instalada, da seguinte forma: <br/> ![Captura de tela mostrando a opção de ativação de HTTP sob os recursos do .NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Não se preocupe se você receber um pop-up adicional dizendo algumas outras coisas precisam ser instalados para ativação de HTTP ser instalado. Isso é normal, então clique em OK e siga em frente. Se a janela pop-up não aparecer, isso significa que essas coisas já estão instaladas e você pode seguir em frente.  <br/> Microsoft .NET Framework geralmente é instalado quando o Windows Server 2012 R2 ou Windows Server 2016 estão instalados. Skype para Business Server funciona com as seguintes versões do Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 e superiores (para Skype para Business Server CU 5 ou versões posteriores)  <br/>  .NET framework 3.5 provavelmente será instalado por padrão em sua máquina do Windows Server 2008 R2 (definitivamente Certifique-se antes de atualizar), mas ele realmente não será em seus servidores do Windows Server 2012/Windows Server 2012 R2 (para instalações novas). Para adicioná-lo no, você precisará ter acesso à sua unidade de instalação ou mídia (o local do Windows Server foi instalado a partir ou onde os arquivos de instalação estão agora). Depois, você poderá instalá-lo como um recurso do Gerenciador do Servidor e apontar para a mídia de instalação (mais especificamente, a pasta **\sources\sxs**) quando solicitado, e então continuar a instalação. <br/> |
|Media Foundation  <br/> |Para Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2 o Windows Media Format Runtime é instalado com o Microsoft Media Foundation.  <br/> Todos os servidores Front-End e servidores Standard Edition usados para conferências exigem o Windows Media Format Runtime executar os arquivos Windows Media Audio (. wma) que reproduzem os aplicativos estacionamento de chamada, grupo de resposta e comunicado para anúncios e música.  <br/> |
|Windows Identity Foundation  <br/> |Precisamos Windows Identity Foundation 3.5 para suportar cenários de autenticação de servidor-para-servidor para Skype para Business Server 2015.  <br/> • Para Windows Server 2012 e Windows Server 2012 R2, não é necessário para baixar qualquer coisa. Abra o **Gerenciador do Servidor** e vá para o **Assistente de Adição de Funções e Recursos**. O **Windows Identity Foundation 3.5** está listado na seção **Recursos**. Se ela estiver marcada, você está bom. Caso contrário, clique em Avançar para acessar o botão **Instalar**. <br/> |
|AD DS and AD LDS ToolsFerramentas de Administração de Servidor Remoto  <br/> |Ferramentas de Administração de Funções: ferramentas do AD DS e AD LDS  <br/> |
   
 **Também necessário Front End servidores e servidor Standard Edition:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|IIS (Serviços de Informações da Internet)  <br/> |O IIS é necessário em todos os servidores Front-End, bem como todos os servidores Standard Edition, com os seguintes módulos selecionados:  <br/> • Os recursos HTTP comuns: padrão de conteúdo de documento, erros de HTTP, estático  <br/> • Integridade e diagnósticos: log, ferramentas de log de rastreamento de HTTP  <br/> • Desempenho: compactação de conteúdo estático, compressão de conteúdo dinâmico  <br/> • Segurança: filtragem de solicitações, autenticação de mapeamento de certificado de cliente, a autenticação do Windows  <br/> Desenvolvimento de aplicativos •: extensibilidade do .NET 3.5, extensibilidade do .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, extensões ISAPI, filtros ISAPI  <br/> • Ferramentas de gerenciamento: Console de gerenciamento do IIS, Scripts de gerenciamento do IIS e ferramentas  <br/> Devemos observar acesso anônimo também é necessária, mas você obterá que, quando você instala o IIS, portanto você não tem um lugar para selecioná-la na lista.  <br/> |
|Tempo de Execução do Windows Media Format  <br/> | Para Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, você precisará instalar o recurso de **Media Foundation** no **Gerenciador do servidor**. Agora, na verdade, você pode iniciar sua Skype para Business Server 2015 instalação sem este aqui, mas você será solicitado a instalá-lo e, em seguida, reinicializar o servidor, antes do Skype para Business Server 2015 instalar continua. É melhor fazer isso com antecedência. <br/> |
|Silverlight  <br/> |Você pode instalar a versão mais recente do Silverlight [neste](https://www.microsoft.com/silverlight/)link.  <br/> |
   
> [!NOTE] 
> Você também pode precisar habilitar a pesquisa no diretório se você estiver usando um balanceador de carga. Caso contrário, será carregada uma página em branco que o balanceador de carga pode considerar uma falha. 

Para ajudar você, separamos esta amostra de script do PowerShell que você pode executar para automatizar esse processo:

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> O comando procura por arquivos de origem em uma ordem específica. Se você estiver online, o comando acessa o Windows Update. No entanto, se você estiver offline, terá que verificar se os arquivos de origem estão disponíveis para o comando. Para obter mais informações sobre como usar o PowerShell para instalar as funções e recursos, consulte [instalar ou desinstalar funções, serviços de função ou recursos](https://technet.microsoft.com/en-us/library/hh831809.aspx) não se esqueça de executar o Windows Update novamente depois de instalar os pré-requisitos, mesmo se você usar o comando PowerShell.

 **Os diretores também precisam:**
  
IIS, com os seguintes módulos selecionados:
  
- Recursos HTTP Comuns
    
  - Documento padrão
    
  - Erros HTTP
    
  - Conteúdo estático
    
- Integridade e Diagnósticos
    
  - Log HTTP
    
  - Ferramentas de log
    
  - Rastreamento
    
- Desempenho
    
  - Compressão de conteúdo estático
    
- Segurança
    
  - Requisição de filtro
    
  - Autenticação de mapeamento de certificado de cliente
    
  - Autenticação do Windows
    
- Desenvolvimento do aplicativo
    
  - Extensibilidade .NET 3.5
    
  - Extensibilidade .NET 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - Extensão ISAPI
    
  - Filtros ISAPI
    
(Se você está se perguntando, é o mesmo módulo definir como os servidores Front-End e servidores Standard Edition, com a compactação de conteúdo dinâmico e ferramentas de gerenciamento deixado de fora).
  
Abaixo, também temos um código do PowerShell para isso:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Servidores de Chat persistente também precisa:**
  
Enfileiramento de Mensagens, também é chamado MSMQ. Esse é um componente do Windows Server e você pode instalá-lo sob a seção de recursos no Gerenciador de servidores. Se você quiser ler mais sobre isso, confira [Instalando e gerenciando o serviço de enfileiramento](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Últimas observações:**
  
Não instale qualquer software de cliente do Microsoft Internet Security and Acceleration (ISA) Server, ou qualquer outro software de provedores de serviço em camadas (LSP) da Winsock (qualquer firewalls de terceiros ou o software de inspeção de rede de antivírus será incluído aqui) em qualquer um dos seus servidores front-end ou servidores de mediação autônomo. Desempenho do tráfego de mídia ruim foi observado quando esse software do instalado.
  

