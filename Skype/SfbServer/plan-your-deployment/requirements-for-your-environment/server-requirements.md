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
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Resumo: Prepare seu Skype para servidores de negócios Server 2015 com este tópico. Hardware, sistema operacional, bancos de dados, software, todos os requisitos do sistema e recomendações estão aqui ajudar a garantir uma instalação bem-sucedida e a implantação de farm de servidores.'
ms.openlocfilehash: 8a86c96554d7aa1be0597c5c82614cd43816540f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
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
|:-----|:-----|:-----|
|Microsoft SQL Server 2014 Enterprise (edição de 64 bits) e você deve executar com 6 de atualização cumulativa ou posterior ([download de 6 de atualização cumulativa](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.  <br/> |Microsoft SQL Server 2008 R2 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.  <br/> |
|Microsoft SQL Server 2014 Standard (edição de 64 bits) e você deve executar com 6 de atualização cumulativa ou posterior ([download de 6 de atualização cumulativa](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.  <br/> |Microsoft SQL Server 2008 R2 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente  <br/> |
   
Se você não vir a edição do SQL Server que você deseja usar listado aqui, você não pode usá-lo.
  
> [!NOTE]
> Você vai também precisa instalar o SQL Server Reporting Services para a função Monitoring Server, mas precisamos que você saiba que isso não vai ser suportados com SQL sempre em até post-RTM. 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Mirroring, SQL Clustering e SQL Always On

É possível usar o espelhamento SQL ou cluster SQL com Skype para Business Server 2015, ela é suportada. SQL espelhamento configurada por meio do Skype para construtor de topologia de servidor de negócios. Se você estiver intenção sobre como configurar o Clustering do SQL, que é feito no SQL Server.
  
Verifique se que você tem uma configuração ativa/passiva para agrupamento do SQL, já que é o que é suportado. Não compartilhe o nó passivo com qualquer outra instância do SQL.
  
Você pode ter os seguintes itens para clustering de failover:
  
Dois nós:
  
- Microsoft SQL Server 2014 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
-  Microsoft SQL Server 2012 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
- Microsoft SQL Server 2008 R2 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
Dezesseis nós:
  
- Microsoft SQL Server 2014 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
- Microsoft SQL Server 2012 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
- Microsoft SQL Server 2008 R2 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
> [!IMPORTANT]
> Para atualizar, queremos para garantir que em seus servidores Front-End você possui pelo menos, SQL Server 2012 SP1 instalado antes da atualização. [Aqui está um link](https://www.microsoft.com/en-us/download/details.aspx?id=35575) para o SP1, se você quiser baixá-lo imediatamente.
  
Se você precisar ler até obter mais informações sobre o espelhamento SQL, temos uma alta disponibilidade de servidor Back-End em Skype para tópico Business Server 2015. Configure o clustering do SQL Server para Skype para Business Server 2015 tem as etapas para obtenção de clustering ready. Também há ainda mais links em failover cluster do SQL, de [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)e [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> A novidade nessa versão é o suporte ao SQL AlwaysOn. Ele é suportado, e você pode ler mais sobre ele no tópico de [alta disponibilidade do servidor Back-End no Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>O software que deve ser instalado antes da implantação do Skype for Business Server 2015
<a name="Software"> </a>

Há algumas coisas que você vai precisar instalar ou configurar para qualquer servidor executando o Skype para Business Server 2015 e são listadas abaixo. Depois disso, há requisitos adicionais para funções de servidor específicas.
  
 **Todos os servidores:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |All Skype for Business Server servers need Windows PowerShell 3.0 installed.  <br/> • If you're doing the installation on Windows Server 2012 or Windows Server 2012 R2, you're set, because it's already there.  <br/> • Se você estiver fazendo uma atualização no Windows Server 2008 R2, você pode baixar o [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) para instalá-la. <br/> **Dica:** Depois que você tiver o PowerShell correto no daí, confirme se ele está BuildVersion 6.2.9200.0 ou posterior indo para o PowerShell solicitar e digitando `$PSVersionTable`. Você verá todas as informações de que precisa.  <br/> |
|Microsoft .NET Framework  <br/> |Os serviços WCF é um **recurso** que não tenha instalado como um recurso do Windows, em **Gerenciador de servidores**, nenhum download necessário. <br/> • Você precisará certificar-se, quando você instalar esse recurso, ou se ele já estiver instalado e você está verificando nele, a opção de **Ativação de HTTP** também é verificada e instalada, da seguinte forma: <br/> ![Captura de tela mostrando a opção de ativação de HTTP sob os recursos do .NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Não se preocupe se você receber um pop-up adicional dizendo algumas outras coisas precisam ser instalados para ativação de HTTP ser instalado. Isso é normal, então clique em OK e siga em frente. Se a janela pop-up não aparecer, isso significa que essas coisas já estão instaladas e você pode seguir em frente.  <br/> Microsoft .NET Framework geralmente é instalado quando o Windows Server 2012 R2 ou Windows Server 2016 estão instalados. Skype para Business Server funciona com as seguintes versões do Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • .NET 4.7 (para Skype para Business Server CU 5 ou versões posteriores)  <br/>  .NET framework 3.5 provavelmente será instalado por padrão em sua máquina do Windows Server 2008 R2 (definitivamente Certifique-se antes de atualizar), mas ele realmente não será em seus servidores do Windows Server 2012/Windows Server 2012 R2 (para instalações novas). Para adicioná-lo no, você precisará ter acesso à sua unidade de instalação ou mídia (o local do Windows Server foi instalado a partir ou onde os arquivos de instalação estão agora). Depois, você poderá instalá-lo como um recurso do Gerenciador do Servidor e apontar para a mídia de instalação (mais especificamente, a pasta **\sources\sxs**) quando solicitado, e então continuar a instalação. <br/> |
|Media Foundation  <br/> |For Windows Server 2016, Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.  <br/> Todos os servidores Front-End e servidores Standard Edition usados para conferências exigem o Windows Media Format Runtime executar os arquivos Windows Media Audio (. wma) que reproduzem os aplicativos estacionamento de chamada, grupo de resposta e comunicado para anúncios e música.  <br/> |
|Windows Identity Foundation  <br/> |We need Windows Identity Foundation 3.5 to support server-to-server authentication scenarios for Skype for Business Server 2015.  <br/> • Para Windows Server 2012 e Windows Server 2012 R2, não é necessário para baixar qualquer coisa. Abra o **Gerenciador do Servidor** e vá para o **Assistente de Adição de Funções e Recursos**. O **Windows Identity Foundation 3.5** está listado na seção **Recursos**. If it's checked, you're good. Caso contrário, clique em Avançar para acessar o botão **Instalar**. <br/> |
|AD DS and AD LDS ToolsFerramentas de Administração de Servidor Remoto  <br/> |Ferramentas de Administração de Funções: ferramentas do AD DS e AD LDS  <br/> |
   
 **Front End Servers and Standard Edition server also need:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|IIS (Serviços de Informações da Internet)  <br/> |IIS is needed on all Front End Servers, as well as all Standard Edition servers, with the following modules selected:  <br/> • Os recursos HTTP comuns: padrão de conteúdo de documento, erros de HTTP, estático  <br/> • Health and Diagnostics: HTTP Logging, Logging Tools, Tracing  <br/> • Performance: Static Content Compression, Dynamic Content Compression  <br/> • Security: Request Filtering, Client Certificate Mapping Authentication, Windows Authentication  <br/> • Application Development: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI Extensions, ISAPI Filters  <br/> • Management Tools: IIS Management Console, IIS Management Scripts and Tools  <br/> We should also note Anonymous Access is also needed, but you get that when you install IIS, so you don't have a place to select that on the list.  <br/> |
|Tempo de Execução do Windows Media Format  <br/> | For Windows Server 2016, Windows Server 2012, and Windows Server 2012 R2, you'll need to install the **Media Foundation** feature in **Server Manager**. Agora, na verdade, você pode iniciar sua Skype para Business Server 2015 instalação sem este aqui, mas você será solicitado a instalá-lo e, em seguida, reinicializar o servidor, antes do Skype para Business Server 2015 instalar continua. É melhor fazer isso com antecedência. <br/> |
|Silverlight  <br/> |You can install the latest version of Silverlight at [this link](https://www.microsoft.com/silverlight/).  <br/> |
   
Para ajudar você, separamos esta amostra de script do PowerShell que você pode executar para automatizar esse processo:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Directors also need:**
  
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
    
(If you're wondering, it's the same module set as the Front End Servers and Standard Edition servers, with the Dynamic Content Compression and Management Tools left out.)
  
Abaixo, também temos um código do PowerShell para isso:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Persistent Chat Servers also need:**
  
Enfileiramento de Mensagens, também é chamado MSMQ. It's a Windows Server component, and you can install it under the Features section in Server Manager. If you want to read more about this, check out [Installing and Managing Message Queuing](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Últimas observações:**
  
Please don't install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software (any third-party firewalls or anti-virus network inspection software would be included here) on any of your front end servers or standalone mediation servers. Poor media traffic performance has been seen when that software's installed.
  

