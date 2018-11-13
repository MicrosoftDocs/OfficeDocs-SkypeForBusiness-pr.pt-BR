---
title: Requisitos de sistema do Skype para Business Server 2019
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 'Resumo: Prepare seu Skype para servidores de negócios Server 2019 e infraestrutura de domínio com este tópico. Hardware, SO, bancos de dados, software, todos os os requisitos do sistema e recomendações, juntamente com o certificado DNS, compartilhamento de arquivos e informações do Active Directory, estão aqui ajudar a garantir uma instalação bem-sucedida e a implantação de farm de servidores.'
ms.openlocfilehash: c7064f4d1c8136cf714d784fd1985efd0f21c979
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296152"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Requisitos de sistema do Skype para Business Server 2019
 
**Resumo:** Preparar-se para instalar o Skype para Business Server 2019 com este tópico. Hardware, sistema operacional, software, bancos de dados, certificados, Active Directory, DNS e compartilhamentos de arquivos são abordados aqui. Todos os requisitos do sistema e recomendações estão aqui ajudar a garantir uma instalação bem-sucedida e a implantação de farm de servidores.
  
Como você pode esperar, existem alguns preparativos a serem antes de começar a implantação do Skype para Business Server 2019. Este artigo explica como deve ser o planejamento dos seguintes itens:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Sistemas operacionais](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Bancos de dados back-end SQL](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [DNS (Sistema de Nomes de Domínio)](system-requirements.md#DNS)
  
- [Certificados](system-requirements.md#Certs)
  
- [Compartilhamento de arquivos](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware para Skype para Business Server 2019
<a name="Hardware"> </a>

Depois de você ter sua topologia inferiores (e se não fizer isso, você pode visitar o tópico [Noções básicas de topologia para Skype para Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ), é hora de pensar em servidores. Skype para servidores de negócios Server 2019 exigem hardware de 64 bits. Nossas recomendações para hardware estão listadas abaixo. Eles não têm requisitos, mas eles reflitam os requisitos necessários para um desempenho ideal. Temos uma documentação de planejamento de capacidade que ajudará você a determinar se precisa de mais alguma coisa, dependendo das suas circunstâncias.
  
Hardware recomendado para servidores Standard Edition:

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de v3 Intel Xeon E5-2673, 6-core, 2,4 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para Skype para funções de negócios Server 2019.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DAS OPÇÕES:  <br/> • 8 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre (dois dos discos usando RAID 1 e 6 usando RAID 10).   <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar ao de 8 unidades de disco mecânicas de 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> Configurações de duas ou multihomed são **não** suportado para servidores Front-End, servidores Back-End e Standard Edition servidores. <br/> Desde que eles não são expostos para o sistema operacional e estão sendo usados para monitorar e gerenciar o hardware de servidor, você pode ter sistemas de gerenciamento de fora da faixa, DRAC ou ILO. Esse cenário não constitui um servidor multihomed e tem suporte.  <br/> |


Hardware recomendado para servidores Front-End e servidores Back-End:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de v3 Intel Xeon E5-2673, 6-core, 2,4 gigahertz (GHz) ou superior. <br/> Processadores Intel Itanium não são suportados para Skype para funções de negócios Server 2019.  <br/> |
|Memória  <br/> |64 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DAS OPÇÕES:  <br/> • 8 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre (dois dos discos usando RAID 1 e 6 usando RAID 10).   <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar ao de 8 unidades de disco mecânicas de 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> Configurações de duas ou multihomed são **não** suportado para servidores Front-End, servidores Back-End e Standard Edition servidores. <br/> Desde que eles não são expostos para o sistema operacional e estão sendo usados para monitorar e gerenciar o hardware de servidor, você pode ter sistemas de gerenciamento de fora da faixa, DRAC ou ILO. Esse cenário não constitui um servidor multihomed e tem suporte.  <br/> |
   
Hardware recomendado para servidores de borda, servidores de mediação autônomo e diretores:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de v3 Intel Xeon E5-2673, 6-core, 2,4 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para Skype para funções de negócios Server 2019.  <br/> |
|Memória  <br/> |32 gigabytes.  <br/> |
|Disco  <br/> |UMA DESTAS OPÇÕES:  <br/> • 4 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre (os discos devem estar em uma configuração de 2x RAID 1).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar ao de 4 unidades de disco mecânicas de 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> São configurações duas multihomed ou **não** tem suporte para servidores de interoperabilidade de vídeo e diretores. <br/> Servidores de borda exigem duas interfaces de rede que são adaptadores de rede dual-port, 1 Gbps ou superior (ou dois adaptador de rede pareados, com um total de quatro, sendo que cada par está combinado com um único endereço MAC e um único endereço IP).  <br/> Em autônoma servidores de mediação, há suporte para a instalação de placas de interface de rede adicionais (NICs) para permitir que a configuração de um endereço IP PSTN específico.  <br/> |


> [!NOTE]
> Independentemente da função de servidor, também recomendamos as seguintes configurações de hardware para Skype para Business Server 2019 (Isso pode variar dependendo da marca do hardware que você comprou, isso, consulte a documentação do fabricante para obter informações específicas):
> - Configuração de BIOS - deve ser definido como plano de NUMA.
> - Habilite o Hyperthreading.
> - A configuração de fila RSS deve ser definida como 8 fila.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Sistemas operacionais para Skype para Business Server 2019
<a name="OS"> </a>

Depois que o hardware no lugar, você precisará ao instalar sistema operacional (SO) que permitirá que você instalar e usar o Skype para Business Server 2019 com êxito.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Qualquer coisa diferente de sistemas operacionais listados aqui não funcionarão corretamente; Não tente ele instalações do Skype para Business Server 2019.

> [!NOTE]
> 
> Se você estiver instalando o Windows Admin Center 2019 em sua máquina do Windows Server 2019, avisará para escutar em uma porta. Não há um liklihood que você pode escolher a porta 443, mas se essa máquina tem Skype para negócios 2019 de servidor instaladas nele, ou terá Skype para negócios 2019 de servidor instaladas nele, em seguida, você deve escolher um número de porta diferente.
> 
>Por que isso é o caso? Se 2019 de centro de administração do Windows estiver em execução na porta 443, não será capaz de se conectar ao servidor usando o Skype para painel de controle de negócios, nem será capaz de se conectar a qualquer serviço da web internos em execução no servidor (serviço de Web catálogo de endereços Autodiscover Service, WebTicket Service, etc).  Na verdade, não será capaz de se conectar a qualquer URL interna do serviço Web. Escolha uma porta diferente, no caso você precise ou deseja colocar 2019 de centro de administração do Windows em um servidor com Skype para Business Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software que deve ser instalado antes de um Skype para implantação Business Server 2019
<a name="Software"> </a>

Há algumas coisas que você vai precisar instalar ou configurar para qualquer servidor executando o Skype para Business Server 2019. Eles são listados abaixo, seguido por requisitos adicionais para funções de servidor específicas.
  
 **Todos os servidores:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Skype todos os servidores do Business Server precisa Windows PowerShell 3.0 instalado.  <br/> • Isso deve ser instalado por padrão com o Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Os serviços WCF é um **recurso** que não tenha instalado como um recurso do Windows, em **Gerenciador de servidores**, nenhum download necessário. <br/> • Você precisará certificar-se, quando você instalar esse recurso, ou se ele já estiver instalado e você está verificando nele, a opção de **Ativação de HTTP** também é verificada e instalada, da seguinte forma: <br/> ![Captura de tela mostrando a opção de Ativação HTTP nos Recursos do .NET Framework 4.5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Não se preocupe se você tiver uma janela pop up adicional dizendo que outras devem ser instaladas para que a Ativação HTTP seja instalada. Isso é normal; Clique em Okey e prosseguir. Se você não conseguir fazer isso pop-up, você pode assumir essas coisas já estiverem instaladas e prosseguir.  <br/> Geralmente, o Microsoft .NET Framework é instalado quando 2016 do Windows Server está instalado. Skype para Business Server funciona com as seguintes versões do Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • .NET 4.7 <br/> |
|Media Foundation  <br/> |Para 2016 do Windows Server, o Windows Media Format Runtime é instalado com o Microsoft Media Foundation.  <br/> Todos os servidores Front-End e servidores Standard Edition usados para conferências exigem o Windows Media Format Runtime executar os arquivos Windows Media Audio (. wma) que reproduzem os aplicativos estacionamento de chamada, grupo de resposta e comunicado para anúncios e música.  <br/> |
|Windows Identity Foundation  <br/> |Precisamos Windows Identity Foundation 3.5 para suportar cenários de autenticação de servidor-para-servidor para Skype para Business Server 2019.  <br/> • Para 2016 do Windows Server, não é necessário para baixar qualquer coisa. Abra o **Gerenciador do Servidor** e vá para o **Assistente de Adição de Funções e Recursos**. O **Windows Identity Foundation 3.5** está listado na seção **Recursos**. Se ele estiver marcado, você está bom. Caso contrário, selecione-o e clique em **próximo** para acessar o botão **instalar** . <br/> |
|AD DS and AD LDS ToolsFerramentas de Administração de Servidor Remoto  <br/> |Ferramentas de Administração de Funções: ferramentas do AD DS e AD LDS  <br/> |
   
 **Também necessário Front End servidores e servidor Standard Edition:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|IIS (Serviços de Informações da Internet)  <br/> |O IIS é necessário em todos os servidores Front-End, bem como todos os servidores Standard Edition, com os seguintes módulos selecionados:  <br/> • Os recursos HTTP comuns: padrão de conteúdo de documento, erros de HTTP, estático  <br/> • Integridade e diagnósticos: log, ferramentas de log de rastreamento de HTTP  <br/> • Desempenho: compactação de conteúdo estático, compressão de conteúdo dinâmico  <br/> • Segurança: filtragem de solicitações, autenticação de mapeamento de certificado de cliente, a autenticação do Windows  <br/> Desenvolvimento de aplicativos •: extensibilidade do .NET 3.5, extensibilidade do .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, extensões ISAPI, filtros ISAPI  <br/> • Ferramentas de gerenciamento: Console de gerenciamento do IIS, Scripts de gerenciamento do IIS e ferramentas  <br/> Observe que o acesso anônimo também é necessária, mas você obtém que, quando você instala o IIS, portanto você não tem um lugar para selecioná-la na lista.  <br/> |
|Tempo de Execução do Windows Media Format  <br/> | Para 2016 do Windows Server, você precisará instalar o recurso de **Media Foundation** no **Gerenciador do servidor**. Na verdade, você pode iniciar sua Skype para instalação Business Server 2019 sem isso, mas será solicitado para instalá-lo e, em seguida, continua a reinicialização do servidor, antes do Skype para Business Server 2019 instalar. É melhor fazê-lo antes do tempo. <br/> |
|Silverlight  <br/> |Você pode instalar a versão mais recente do Silverlight [aqui](https://www.microsoft.com/silverlight/).  <br/> |
   
Para ajudar você, separamos esta amostra de script do PowerShell que você pode executar para automatizar esse processo:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bancos de dados de back-end que funcionarão com Skype para Business Server 2019
<a name="DBs"> </a>

Ao instalar o Skype para Business Server 2019 Standard Edition, você terá SQL Server 2016 Express (edição de 64 bits).

Skype para Business Server 2019 Enterprise Edition exigirá completa do SQL Server, conforme indicado a seguir (edição de 64 bits somente; não use edições de 32 bits):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2016/2017 Enterprise (edição de 64 bits) e você deve executar com as atualizações mais recentes e com grupos de disponibilidade do AlwaysOn.  <br/> ||
 |
   
Se você não vir a edição do SQL Server que você deseja usar listado aqui, você não pode usá-lo.
  
> [!NOTE]
> Você também precisará instalar o SQL Server Reporting Services para a função Monitoring Server. 
  
### <a name="sql-clustering-and-sql-always-on"></a>Clusters do SQL e SQL sempre ativada

Cluster de SQL com Skype para Business Server 2019 é suportado. Se você deseja configurar o Clustering do SQL, que é feito no SQL Server.
  
Verifique se que você tem uma configuração de clusters ativos/passivos de cluster do SQL, que é suportado. Não compartilhe o nó passivo com qualquer outra instância do SQL.
  
Você pode ter os seguintes itens para clustering de failover:
  
Dois nós:
  
- Microsoft SQL Server 2016/2017 Standard (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
Dezesseis nós:
  
- Microsoft SQL Server 2016/2017 Enterprise (edição de 64 bits) e é recomendável executar com o service pack mais recente.
    
Teremos um artigo, Configure o SQL Server clustering do Skype para Business Server 2019, que terá as etapas para obtenção de clustering ready.
 
SQL Always On é suportado, e você pode ler mais sobre ele em um [servidor Back-End de alta disponibilidade em Skype para Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Recomendações de instalação de servidor adicionais:
  
Não instale qualquer software de cliente do Microsoft Internet Security and Acceleration (ISA) Server, ou qualquer outro software de provedores de serviço em camadas (LSP) da Winsock (qualquer firewalls de terceiros ou o software de inspeção de rede de antivírus será incluído aqui) em qualquer um dos seus servidores front-end ou servidores de mediação autônomo. Desempenho do tráfego de mídia ruim foi observado quando esse software está instalado.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Embora grande parte dos dados de configuração para servidores e serviços é armazenado no Skype para o repositório de gerenciamento Central do Business Server 2019, há algumas coisas que ainda são armazenadas no Active Directory:
  
|**Objetos do Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensões de esquema  <br/> |Extensões de objetos de usuário  <br/> |
||Versões compatíveis de extensões para Skype para Business Server 2015 e o Lync Server 2013, para manter compatibilidade com anterior  <br/> |
|Dados  <br/> |URI do SIP do usuário e outras configurações de usuário  <br/> |
||Objetos de contato para aplicativos (como o aplicativo grupo de resposta e aplicativo Atendedor de conferência)  <br/> |
||Dados publicados para compatibilidade com versões anteriores  <br/> |
||Ponto de um controle de serviço (SCP) para o repositório de gerenciamento Central  <br/> |
||Conta de autenticação Kerberos (um objeto de computador opcional)  <br/> |
   
### <a name="os-for-domain-controllers"></a>OS para controladores de domínio

Os seguintes sistemas operacionais de controlador de domínio podem ser usados:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
O nível funcional do domínio de qualquer domínio em que você implantar o Skype para negócios 2019 de servidor em e o nível funcional de floresta de qualquer floresta que você implanta o Skype para o servidor de negócios 2019 into, devem ser um dos seguintes procedimentos:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
É possível ter controladores de domínio somente leitura nesses ambientes? Com certeza, contanto que daí também estão controladores de domínio graváveis disponíveis.
  
É importante saber que Skype para Business Server 2019 não dá suporte a domínios com rótulo único. O que são esses domínios? Se você tiver um domínio raiz rotulado Contoso, que vai ser tudo bem. Se você tiver um domínio raiz chamado apenas local, que não vai funcionar, e não é suportado como resultado. Saiba mais sobre isso lendo [este artigo da base de dados de conhecimento](https://support.microsoft.com/kb/300684/en-us).
  
Skype para Business Server 2019 também não tem suporte para renomeação de domínios. Se você tiver realmente renomear seu domínio, você vai precisa desinstalar Skype para negócios 2019 do servidor, faça a renomeação de domínio e reinstalar Skype para Business Server 2019.
  
Finalmente, talvez você esteja lidando com um domínio com um ambiente do AD DS bloqueados, e isso é muito bem. Temos obter mais informações sobre como implantar o Skype para Business Server 2019 em um ambiente bloqueado do AD DS na documentação de implantação.
  
### <a name="ad-topologies"></a>Topologias do AD

Topologias com suporte no Skype para Business Server 2019 são:
  
- Floresta única com domínio único
    
- Floresta única com uma única árvore e vários domínios
    
- Floresta única com várias árvores e namespaces não contíguos
    
- Várias florestas em uma topologia de floresta central
    
- Várias florestas em uma topologia de floresta de recursos
    
- Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
    
- Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Connect
    
Temos diagramas e descrições para ajudá-lo a determinar qual topologia que você tem no seu ambiente, ou o que você pode precisar configurar antes da instalação do Skype para Business Server 2019. Para manter simples, estamos incluindo também uma chave:
  
![Há uma chave para os ícones usados nos diagramas de topologia do Skype for Business](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Floresta única com domínio único

![Diagrama da floresta única do Active Directory com um único domínio](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Nada é mais fácil do que isso; é uma floresta de domínio único, uma topologia comum.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Floresta única com uma única árvore e vários domínios

![Um diagrama de floresta única, com árvore única e vários domínios](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Esse diagrama mostra uma floresta única, mas ela também tem um ou mais domínios filho (há três deles neste exemplo específico). Portanto o domínio em que os usuários são criados no pode ser diferente do domínio Skype para Business Server 2019 é implantado. Por que isso é relevante? É importante lembrar que, quando você implanta um Skype para pool de Front End do servidor de negócios, todos os servidores desse pool precisam estar em um único domínio. Você pode realizar a administração entre domínios via Skype para Business Server suporte dos grupos de universal de administradores do Windows.
  
No diagrama acima, você pode ver que os usuários de um domínio são capazes de acessar Skype para pools de servidor de negócios do mesmo domínio ou de domínios diferentes, mesmo se os usuários estiverem em um domínio filho.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Floresta única com várias árvores e namespaces não contíguos

![Um diagrama de floresta única com várias árvores e namespaces não contíguos](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Você pode ter uma topologia semelhante a este diagrama, onde você tem uma floresta, mas dentro dessa floresta está vários domínios, com os namespaces separados do AD. Nesse caso, este diagrama é uma BOM ilustração, porque ele inclui usuários em três domínios diferentes accessing Skype para Business Server 2019. Linhas sólidas indicam que eles estiver acessando um Skype para pool de servidores de negócios em seu próprio domínio, enquanto uma linha tracejada indica que irão para um pool em uma árvore diferente todo.
  
Como você pode ver, os usuários no mesmo domínio, na mesma árvore ou até mesmo em uma árvore diferente podem acessar pools com êxito.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Várias florestas em uma topologia de floresta central

![Várias florestas em um diagrama de topologia de floresta central](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype para Business Server 2019 dá suporte a várias florestas configuradas em uma topologia de floresta central. Se você não tiver certeza de que é o que você tem, a floresta central na topologia usa objetos para representar usuários nas outras florestas e contas de usuário de hosts para todos os usuários da floresta.
  
Como isso funciona? Um produto de sincronização de diretório (por exemplo, Forefront Identity Manager ou FIM) gerencia as contas de usuário da sua organização em toda sua existência. Quando uma conta é criada ou excluída de uma floresta, essa mudança é sincronizada até o contato correspondente na floresta central.
  
Sem dúvida, se sua infraestrutura do AD está no lugar, a movimentação para esta topologia pode não ser fácil, mas se você já existe, ou ainda planejamento sua infra-estrutura de floresta, isso pode ser uma boa opção. Você pode centralizar seu Skype para implantação de negócios 2019 de servidor em uma única floresta, enquanto os usuários podem pesquisar, se comunicar e visualizar a presença de outros usuários em qualquer floresta. Todas as atualizações de contato são feitas automaticamente com o software de sincronização.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business
<a name="BKMK_multipleforestopology"> </a>

![Várias florestas em uma topologia de floresta de recursos](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Também há suporte para uma topologia de floresta de recursos; é onde uma floresta é dedicada à execução de aplicativos de servidor, como o Microsoft Exchange Server e do Skype para Business Server 2019. Essas florestas de recursos também hospedam uma representação sincronizada de objetos de usuário ativo, mas não contas de usuário habilitadas para logon. Portanto, a floresta de recursos é um ambiente de serviços compartilhados para outras florestas nas quais os objetos de usuários residem, e que têm uma relação de confiança no nível de floresta com a floresta de recursos.
  
Observe que o Exchange Server pode ser implantado na floresta de recursos como Skype para Business Server ou em uma floresta diferente.
  
Para implantar o Skype para o servidor de negócios 2019 nesse tipo de topologia, você criará um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas de usuário (se Microsoft Exchange Server já estiver no ambiente, isso pode ser feito para você). Em seguida, você precisa de uma ferramenta de sincronização de diretórios (como o Forefront Identity Manager ou FIM) para gerenciar contas de usuário por meio do seu ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topologia é similar à topologia descrita em [Várias florestas em uma topologia de floresta de recursos do Skype for Business](system-requirements.md#BKMK_multipleforestopology).
  
Nessa topologia, há uma ou mais florestas de usuário e Skype para Business Server é implantado em uma floresta de recurso dedicado. Exchange Server podem ser implantados no local na mesma floresta do recurso ou uma floresta diferente e configurado para o híbrido com o Exchange Online ou serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais. Não há um diagrama disponível para esta topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra duas florestas AD, uma floresta de usuários e uma floresta de recursos. As duas florestas têm uma relação de confiança. Elas são sincronizadas com o Office 365 usando o Azure AD Connect. Todos os usuários são habilitados para Skype for Business via Office 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Neste cenário há várias florestas locais, com uma topologia de floresta de recursos. Há um relacionamento de total confiança entre as florestas do Active Directory. A ferramenta Azure Active Directory Connect é usada para sincronizar contas entre as florestas de usuários locais e o Office 365.
  
 A organização também tem o Office 365 e usa o [Azure Active Directory Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect) para sincronizar suas contas locais com o Office 365. Os usuários habilitados para o Skype para negócios estão habilitados por meio do Office 365 e Skype para Business Online. Skype para Business Server não é implantados no local.
  
Autenticação de logon única é fornecida por um farm de serviços de Federação do Active Directory localizado na floresta de usuário.
  
Neste cenário, ele é suportado para implantar o Exchange local, o Exchange Online, uma solução híbrida do Exchange, ou não tiver implantado em todos os de câmbio. O diagrama mostra somente o Exchange no Local, mas as outras soluções do Exchange são totalmente aceitas.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Várias florestas em uma topologia de floresta de recursos com o Skype for Business híbrido 
<a name="BKMK_multipleforestopology"> </a>

Neste cenário, há um ou mais locais florestas de usuários e Skype para negócios é implantado em uma floresta de recurso dedicado e está configurado para modo híbrido com Skype para negócios Online. Exchange Server podem ser implantados no local na mesma floresta do recurso ou uma floresta diferente e pode ser configurado para o híbrido com o Exchange Online. Como alternativa, os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais.
  
Para obter mais informações, consulte [Configure um ambiente de várias floresta para o híbrido Skype para negócios](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de Nomes de Domínio (DNS)
<a name="DNS"> </a>

Skype para Business Server 2019 requer o DNS, pelos seguintes motivos:
  
- DNS permite Skype para negócios 2019 de servidor descobrir servidores ou pools, internos permitindo para comunicações de servidor-para-servidor.
    
- DNS permite que clientes máquinas descubram o pool de Front-End ou servidor Standard Edition que está sendo usado para transações SIP.
    
- Ele associa URLs simples para conferências aos servidores que as hospedam.
    
- DNS permite que usuários externos e computadores cliente se conectem aos servidores de borda, ou o proxy reverso HTTP para mensagens instantâneas (IM) ou conferência.
    
- Ele permite que as comunicações unificadas (UC) dispositivos que não são registrados no descubram o pool de Front-End ou o servidor Standard Edition que está executando o serviço web de atualização de dispositivo para obter atualizações e enviem logs.
    
- O uso do DNS permite que clientes móveis descubram automaticamente os recursos dos serviços Web sem que os usuários tenham que inserir URLs manualmente em suas configurações do dispositivo.
    
- Ele tem usado no balanceamento de carga DNS.
    
É importante observar que Skype para Business Server 2019 não dá suporte a nomes de domínio internacionalizados (IDNs).
  
E é extremamente importante lembrar que qualquer nome no DNS ser idêntica ao nome do computador configurado em qualquer servidor que está sendo usado pelo Skype para Business Server 2019. Especificamente, estamos não podem ter qualquer short-nomes no ambiente e devem ter os FQDNs do construtor de topologias.
  
Isso parece seria lógica para qualquer computador que já está associado a um domínio, mas se você tiver um servidor de borda que não está vinculada ao seu domínio, ele pode ter um valor padrão de um nome curto, com nenhum sufixo de domínio. Certifique-se de que não é o caso, no DNS ou no servidor de borda ou qualquer Skype para Business Server 2019 servidor ou pool, na verdade.
  
Definitivamente não use caracteres Unicode nem sublinhados. Os caracteres padrão (que fazem A-Z, a-z, 0-9 e hifens) suportados pelo DNS externo e as autoridades de certificação pública (você precisará atribuir FQDNs ao SN no certificado, é importante lembrar), portanto, você vai reserva sozinho muitos problemas se você nomear com isso em mente desde o início.
  
Para saber mais sobre os requisitos do DNS para redes, consulte a seção [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) da sua documentação de planejamento.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Uma das coisas mais importantes a fazer antes da implantação é verificar se os seus certificados estão corretos. Skype para Business Server 2019 precisa de uma infraestrutura de chave pública (PKI) para transport layer security (TLS) e conexões do mutual transport layer security (MTLS). Basicamente, para se comunicar com segurança de uma maneira padronizada, Skype para Business Server usa certificados emitidos por autoridades de certificação (CAs).
  
Estas são algumas coisas que Skype para Business Server 2019 usa certificados para:
  
- Conexões TLS entre clientes e servidores
    
- Conexões MTLS entre servidores
    
- Usando a descoberta automática de DNS de parceiros de Federação
    
- Acesso de usuários remotos a IM (mensagens instantâneas)
    
- Acesso de usuário externo a sessões de A/V (áudio/vídeo), compartilhamento de aplicativos e conferência
    
- Comunicando com aplicativos da web e o Outlook Web Access (OWA)
    
Para que o planejamento de certificado é obrigatória. Agora, vejamos uma lista de algumas coisas que você precisa ter em mente ao solicitar certificados:
  
- Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).
    
- Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).
    
- Todos os certificados devem ser assinados usando um algoritmo de assinatura que seja compatível com o sistema operacional. Skype para Business Server 2019 suporta SHA-1 e SHA-2 suite de digest dimensiona (224, 256, 384 e 512 bits) e atende ou excede os requisitos de sistema operacional.
    
- Registro automático é suportado para servidores internos executando Skype para Business Server 2019.
    
- Registro automático não é suportado para Skype Business Server 2019 para servidores de borda.
    
> [!NOTE]
> O uso do algoritmo de assinatura RSASSA-PSS não é permitido e pode levar a erros no login e a problemas de encaminhamento de chamadas, entre outros.  
  
- Os comprimentos de chave de criptografia de 1024, 2048 e 4096 são suportados. Comprimentos de pelo menos 2048 são recomendados.
    
- O algoritmo de hash de assinatura ou sumário padrão é RSA. Os algoritmos ECDH_P256, ECDH_P384 e ECDH_P521 também têm suporte.
    
Isso é muito serem levados em consideração e há uma variedade de níveis de confortável com solicitar certificados de uma autoridade de certificação. Daremos algumas diretrizes mais abaixo para tornar o seu planejamento mais simples possíveis.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para seus servidores internos

Você precisará de certificados para a maioria dos seus servidores internos e provavelmente, você obterá-los a partir de uma autoridade de certificação interna (ou seja, uma autoridade de certificação localizada em seu domínio). Se desejar, você poderá solicitar esses certificados de uma autoridade de certificação externa (um localizados na Internet). Se você está se perguntando o que autoridade de certificação pública você deve ir, você pode visitar a lista de [parceiros de certificado de comunicação unificada](https://support.microsoft.com/kb/929395/en-us) .
  
Você também precisará certificados quando Skype para Business Server 2019 se comunica com outros aplicativos e servidores, como o Microsoft Exchange Server. Isso, obviamente, deverá ser um certificado que esses aplicativos e servidores podem usar uma forma com suporte. Skype para Business Server 2019 e outros produtos da Microsoft suporte ao protocolo de autorização aberta (OAuth) para autorização e autenticação de servidor-para-servidor. Se estiver interessado neste, temos um artigo de planejamento adicional para OAuth e Skype para Business Server 2019.
  
Skype para Business Server 2019 também inclui o suporte para (sem exigir) certificados assinados usando a função de hash criptográfico SHA-256. Para oferecer suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma AC pública usando SHA-256.
  
Para manter as coisas simples, nós agrupamos os requisitos de certificado para servidores Standard Edition, pools Front-End e outras funções, em tabelas a seguir, com a empresa fictícia contoso.com sendo usados para exemplos (você provavelmente usará algo diferente de seu ambiente). Todos esses são certificados do servidor Web padrão, com chaves privadas que não são exportáveis. Outras observações:
  
- O Uso Avançado de Chave (EKU) no servidor é automaticamente configurado quando o assistente de certificado é usado para solicitar certificados.
    
- Cada nome amigável do certificado deve ser exclusivo no repositório do computador.
    
- Conforme os exemplos de nomes abaixo, se você tiver configurado sipinternal.contoso.com ou sipexternal.contoso.com em seu DNS, eles precisam ser adicionado ao nome de alternativo de entidade (SAN) do certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nome da entidade nome/comum**|**Nome alternativo de entidade**|**Exemplo**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nos servidores Standard Edition, o FQDN do servidor é igual ao FQDN do pool.  <br/> O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também utiliza este certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • Internos da web FQDN (que é o mesmo que o FQDN do servidor)  <br/> AND  <br/> • Atender a URLs simples  <br/> • Dial-in de URL simples  <br/> • URL simples de Admin  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN =\*. contoso.com  <br/> |Você não pode substituir o FQDN no construtor de topologia de web interna.  <br/> Se você tiver vários atender a URLs simples, você deve incluir todos eles como SANs.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN de web externa  <br/> AND  <br/> • Dial-in de URL simples  <br/> • Atender a URLs simples por domínio SIP  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Se você tiver vários atender a URLs simples, você deve incluir todos eles como nomes de entidade alternativos.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para servidores Front-End em um pool de Front-End:
  
|**Certificado**|**Nome da entidade nome/comum**|**Nome alternativo de entidade**|**Exemplo**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também utiliza este certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • Internos da web FQDN (que não é o mesmo que o FQDN do servidor)  <br/> • O FQDN do servidor  <br/> • Skype para o FQDN do pool de negócios  <br/> AND  <br/> • Atender a URLs simples  <br/> • Dial-in de URL simples  <br/> • URL simples de Admin  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN =\*. contoso.com  <br/> |Se você tiver vários atender a URLs simples, você deve incluir todos eles como nomes de entidade alternativos.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN de web externa  <br/> AND  <br/> • Dial-in de URL simples  <br/> • URL simples de Admin  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. contoso.com  <br/> |Se você tiver vários atender a URLs simples, você deve incluir todos eles como nomes de entidade alternativos.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para o Diretor:
  
|**Certificado**|**Nome da entidade nome/comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |Pool de diretores  <br/> |FQDN do diretor, FQDN do pool de diretores.  <br/> Se esse pool for o servidor de logon automático para clientes e a combinação estrita DNS é exigida na política de grupo, você também precisará de entradas para sipdomain (para cada domínio SIP que você tiver).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Se esse pool de diretor for o servidor de logon automático para clientes e estrita de DNS for exigida na política de grupo, também serão precisos; SAN = SIP.Fabrikam.com  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • Internos da web FQDN (que é o mesmo que o FQDN do servidor)  <br/> • O FQDN do servidor  <br/> • Skype para o FQDN do pool de negócios  <br/> AND  <br/> • Atender a URLs simples  <br/> • Dial-in de URL simples  <br/> • URL simples de Admin  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN =\*. contoso.com  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN de web externa  <br/> AND  <br/> • Atender a URLs simples por domínio SIP  <br/> • Dial-in de URL simples  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |A FQDN de web externa de diretores deve ser diferente do pool de Front-End ou servidor Front-End.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN =\*. contoso.com  <br/> |
   
Certificados para o servidor de mediação autônomo:
  
|**Certificado**|**Nome da entidade nome/comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool  <br/> FQDN do servidor membro do pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para aparelho de filial persistente (especificamente, aparelho de filial persistente 2015 para Skype para Business Server 2019):
  
|**Certificado**|**Nome da entidade nome/comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do aplicativo  <br/> |SIP. \<sipdomain\> (necessário apenas uma entrada por domínio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificados para acesso de usuário externo (Borda)

Skype para Business Server 2019 suporta o uso de um **único certificado público** para o acesso e web conferência interfaces externas de borda, além de A / o serviço de autenticação de V, que é fornecido por meio de todos os servidores de borda. Sua interface interna da borda normalmente usará um certificado privado emitido pela autoridade de certificação interna, mas se você preferir, você pode usar um certificado público para que isso também se ela for proveniente de uma autoridade de certificação confiável.
  
Seu proxy reverso (RP) também usará um certificado público que criptografa a comunicação entre o RP e os clientes e entre o RP e os servidores internos usando HTTP (ou, mais precisamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para mobilidade

Se você estiver implantando mobilidade e você está apoiando descoberta automática para clientes móveis, você vai precisar incluir algumas entradas de nome alternativo da entidade adicionais em seus certificados para oferecer suporte as conexões seguras entre os clientes móveis.
  
Você precisará nomes de SAN para descoberta automática nos certificados a seguir:
  
- Pool de diretores
    
- Pool de Front-Ends
    
- Proxy reverso
    
As especificações estão listadas nas tabelas a seguir.
  
Isso é onde um pouco de planejamento prévio é bom, mas às vezes você implantou Skype para Business Server 2019 sem pretende implantar a mobilidade e que surge posterior ao já tiver certificados no seu ambiente. Reemitir certificados através da AC interna costuma ser uma tarefa fácil, mas no caso de certificados públicos de uma AC pública, a reemissão pode custar caro.
  
Se esse for o que você estiver examinando e se você tiver muitos dos domínios SIP (o que tornaria adicionando SANS mais caro), você pode configurar o proxy reverso para utilizar HTTP para a solicitação inicial de Autodiscover Service, em vez de usar o HTTPS (que é o padrão configuração). O artigo de [planejamento para mobilidade](../../SfbServer/plan-your-deployment/mobility.md) tem mais informações sobre isso.
  
Requisitos de certificado do pool de diretor e o pool de Front-End:
  
|**Descrição**|**Entrada do SAN**|
|:-----|:-----|
|URL interna do serviço de Descoberta Automática  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL externa do serviço de Descoberta Automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Como alternativa, é possível usar SAN =\*. \<sipdomain\>
  
Requisitos de certificado de proxy reverso (AC pública):
  
|**Descrição**|**Entrada do SAN**|
|:-----|:-----|
|URL externa do serviço de Descoberta Automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN precisa ser atribuído ao certificado que, por sua vez, é atribuído ao Ouvinte do SSL em seu proxy reverso.
  
> [!NOTE]
> Seu ouvinte de proxy reverso vai ter SANs para suas URLs de serviços Web externos. Alguns exemplos seria SAN=skypewebextpool01.contoso.com e dirwebexternal.contoso.com, se você implantou o diretor, (que é opcional). 
  
## <a name="file-share"></a>Compartilhamento de arquivo
<a name="Fileshare"> </a>

Skype para Business Server 2019 pode usar o compartilhamento de arquivo a mesma para todo o armazenamento de arquivo. Deve-se ter em mente:
  
- Um compartilhamento de arquivo precisa estar em um armazenamento anexado direto (DAS) ou em uma rede de área de armazenamento (SAN), e isso inclui o sistema de arquivos distribuído (DFS), bem como uma matriz redundante de RAID para repositórios de arquivos. Para ler mais sobre DFS para o Windows Server 2012, consulte [esta página do DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Recomendamos um cluster compartilhado para o compartilhamento de arquivo. Se você estiver usando uma, você deve cluster Windows Server 2012 ou Windows Server 2012 R2. Por que o Windows mais recente? Versões antigas podem não ter as permissões adequadas para habilitar todos os recursos. Você pode usar o Administrador de Cluster para criar os compartilhamentos de arquivo e este artigo da base de dados de conhecimento, [Criando um Cluster](https://support.microsoft.com/en-us/help/224967) ajudará você a lidar com esses detalhes.
    
> [!CAUTION]
> Você deve saber que o uso de NAS como compartilhamento de arquivo não é compatível; portanto, use uma das opções listadas acima. 
  








