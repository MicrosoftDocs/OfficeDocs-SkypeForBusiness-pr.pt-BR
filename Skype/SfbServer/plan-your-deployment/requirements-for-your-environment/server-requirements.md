---
title: Requisitos de servidor para Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Resumo: prepare seus Skype for Business Server 2015 com este tópico. Hardware, so, bancos de dados, software, todos os requisitos e recomendações do sistema estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas do farm de servidores.'
ms.openlocfilehash: f12dcd955f044e626deda5e8e21fec00e53b876c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860948"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos de servidor para Skype for Business Server 2015
 
**Resumo:** Prepare seus Skype for Business Server 2015 com este tópico. Hardware, so, bancos de dados, software, todos os requisitos e recomendações do sistema estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas do farm de servidores.

Se você estiver procurando requisitos ambientais, como Active Directory, DNS ou certificados, confira os requisitos ambientais do documento Skype for Business Server [2015.](environmental-requirements.md)
  
Como você pode esperar, há algumas preparações a fazer antes de começar a implantar Skype for Business Server 2015. Este artigo o acompanhará por meio do planejamento para o seguinte:
  
- [Hardware para Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operacionais para Skype for Business Server 2015](server-requirements.md#OS)
  
- [Bancos de dados back-end que funcionarão com Skype for Business Server 2015](server-requirements.md#DBs)
  
- [Software que deve ser instalado antes de uma implantação Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para Skype for Business Server 2015
<a name="Hardware"> </a>

Agora que você baixou a topologia (e, se não tiver, poderá conferir o tópico [Topologia Básicas do Skype for Business Server 2015),](../../plan-your-deployment/topology-basics/topology-basics.md) é hora de pensar nos servidores. Skype for Business Server servidores 2015 exigirão hardware de 64 bits. Nossas recomendações para hardware estão abaixo. Não são requisitos, mas refletem os requisitos necessários para o desempenho ideal. Temos documentação de planejamento de capacidade que o ajudará a determinar se você precisa de mais do que isso, dependendo das circunstâncias.
  
Hardware recomendado para servidores front-end, servidores back-end, servidores Edição Standard e servidores de Chat Persistente:
  
|Componente de hardware|Recomendado|
|:-----|:-----|
|CPU   |Processador duplo de 64 bits, hex-core, 2,26 gigahertz (GHz) ou superior.  <br/> Os processadores Intel Itanium não têm suporte para funções Skype for Business Server 2015.   |
|Memória   |32 gigabytes (GB).   |
|Disco   |OU:  <br/> • 8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco (dois dos discos que usam RAID 1 e 6 usando RAID 10).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho semelhante a 8 unidades de disco mecânicas de 10.000 RPM.   |
|Rede   |1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam ser em equipe com um único endereço MAC e um único endereço IP).  <br/> Configurações duplas ou multi-homed não são suportadas para servidores front-end, servidores back-end, servidores Edição Standard e servidores de chat persistente.  <br/> Desde que eles não sejam expostos ao sistema operacional e sejam usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento de banda fora, como DRAC ou ILO. Esse cenário não constitui um servidor multi-homed e é suportado.   |
   
Hardware recomendado para Servidores de Borda, Servidores de Mediação autônomos, Servidores de Interop de Vídeo e Diretores:
  
|Componente de hardware|Recomendado|
|:-----|:-----|
|CPU   |Processador duplo de 64 bits, quad-core, 2,26 gigahertz (GHz) ou superior.  <br/> Os processadores Intel Itanium não têm suporte para funções Skype for Business Server 2015.   |
|Memória   |16 gigabytes.   |
|Disco   |OU:  <br/> • 4 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco (os discos devem estar em uma configuração raid 1 2x).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho semelhante a 4 unidades de disco mecânicas de 10.000 RPM.   |
|Rede   |1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam ser em equipe com um único endereço MAC e um único endereço IP).  <br/> Configurações dual ou multi-homed não **são** suportadas para Servidores e Diretores de Interop de Vídeo. <br/> Os servidores de borda exigirão duas interfaces de rede que são adaptadores de rede de porta dupla, 1 Gbps ou superior (ou dois adaptadores de rede emparelhados, para um total de quatro, cada par sendo emparelhado com um único endereço MAC e um único endereço IP, para um total de dois pares).  <br/> Em Servidores de Mediação autônomos, há suporte para a instalação de nics (cartões de interface de rede) adicionais para permitir a configuração de um endereço IP PSTN específico.   |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operacionais para Skype for Business Server 2015
<a name="OS"> </a>

Depois de ter o hardware instalado, você precisará instalar os sistemas operacionais (SO). Esses são os so que permitirão que você instale e use com êxito Skype for Business Server 2015.
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Windows Server 2019 (Você precisa Skype for Business Atualização Cumulativa 9 ou posterior).  |Windows Server 2016 (Você precisa Skype for Business Atualização Cumulativa 5 ou posterior. Para obter mais informações, verifique [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))   |
|Windows Server 2012 Sistema operacional do Datacenter R2 com todas as atualizações necessárias instaladas.   |Windows Server 2012 R2 Sistema operacional padrão com todas as atualizações necessárias instaladas.   |
|Windows Server 2012 Datacenter Sistema operacional com todas as atualizações necessárias instaladas.   |Windows Server 2012 Standard Sistema operacional com todas as atualizações necessárias instaladas.   |
   
Se não estiver nessa lista, ele não funcionará corretamente, não tente novas instalações do Skype for Business Server 2015.

> [!NOTE]
> A atualização in-local do sistema operacional não é suportada com o Lync Server 2013. Você deve implantar um pool separado e migrar usuários para o novo pool com um sistema operacional diferente. Todos os servidores em um pool devem ter a mesma versão do sistema operacional.
  
> [!NOTE]
> Você deve ter notado Windows server 2008 R2 não está nesta lista. Isso porque recomendamos que Windows Server 2012 R2 para todos os novos servidores a serem usados para SFB. Você só deve usar o Windows Server 2008 R2 quando tiver servidores existentes com o Lync Server 2013 já instalado e pretende fazer uma atualização in-locar deles. Windows O Servidor 2008 R2 atingiu o final do ciclo de vida de suporte principal em 13/1/2015 e chegará ao final de seu ciclo de vida de suporte em 14/1/2020.
  
Além do service pack mais recente, você vai querer garantir que as seguintes atualizações sejam instaladas quando relevantes para você:
  
- Para Windows Server 2012, o artigo KB 2858668 deve ser instalado antes de uma atualização. [Obter aqui](https://support.microsoft.com/kb/2858668/).
    
- Se você tiver Windows Server 2012 R2, instale o artigo KB 2982006 antes de atualizar. [Ele é encontrado aqui](https://support.microsoft.com/kb/2982006/).
    
- Se você estiver atualizando em uma caixa do Windows Server 2008 R2 (consulte a Observação acima), então você vai querer instalar o artigo KB 2533623 primeiro. [Está neste link](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bancos de dados back-end que funcionarão com Skype for Business Server 2015
<a name="DBs"> </a>


Ao instalar o Skype for Business Server 2015 Edição Standard, você também terá o SQL Server 2014 Express (edição de 64 bits) instalado automaticamente.
  
Skype for Business Server 2015 Edição Enterprise é um pouco mais complicado, mas a lista suportada está abaixo (tudo é edição de 64 bits, você notará, por favor, não use edições de 32 bits):
  
|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (edição de 64 bits) e recomendamos a execução com o service pack mais recente.  |Microsoft SQL Server 2017 Enterprise (edição de 64 bits) e recomendamos a execução com o service pack mais recente.  |Microsoft SQL Server 2016 Enterprise (edição de 64 bits) com Service Pack 1 ou posterior, e você deve executar com Skype for Business Atualização Cumulativa 7 ou posterior ( baixar Skype for Business[Atualização Cumulativa](https://support.microsoft.com/help/3061064)).   |Microsoft SQL Server 2014 Enterprise (edição de 64 bits) e você deve executar com a Atualização Cumulativa 6 ou posterior ([baixe a Atualização Cumulativa 6](https://support.microsoft.com/kb/3031047/)).   |Microsoft SQL Server 2012 Enterprise (edição de 64 bits) e recomendamos a execução com o service pack mais recente.   |
|Microsoft SQL Server 2019 Standard (edição de 64 bits) e recomendamos a execução com o service pack mais recente.  |Microsoft SQL Server 2017 Standard (edição de 64 bits) e recomendamos a execução com o service pack mais recente.  |Microsoft SQL Server 2016 Standard (edição de 64 bits) com Service Pack 1 ou posterior, e você deve executar com Skype for Business Atualização Cumulativa 7 ou posterior ( baixar Skype for Business[Atualização Cumulativa](https://support.microsoft.com/help/3061064)).   |Microsoft SQL Server 2014 Standard (edição de 64 bits) e você deve executar com a Atualização Cumulativa 6 ou posterior ([baixe a Atualização Cumulativa 6](https://support.microsoft.com/kb/3031047/)).   |Microsoft SQL Server 2012 Standard (edição de 64 bits) e recomendamos a execução com o service pack mais recente.   |
   
Se você não vir a SQL Server edição que deseja usar listada aqui, não poderá usá-la.
  
- Você também precisará instalar o SQL Server Reporting Services para a função de Servidor de Monitoramento.
- Para um back-end SQL bem conectado, a conexão com o front-end Skype for Business deve ser local e não através de um link de baixa velocidade. 
- Não há suporte SQL compartilhamento de back ends entre dois ou mais pools.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange armazenamento
Conteúdo de reuniões, como apresentações em PowerPoint, são arquivados como anexos. Se você deseja armazenar Skype for Business dados de arquivo morto com dados de conformidade Exchange, você deve usar o Exchange para sua implantação Exchange e garantir que o tamanho máximo de armazenamento suporta o armazenamento dos arquivos de conteúdo da reunião. Você deve implantar Exchange antes da implantação e habilitação do arquivamento usando a opção de Exchange de integração da Microsoft. 
    
Se você optar por usar o armazenamento Exchange, não precisará implantar bancos de dados SQL Server separados para arquivamento, a menos que você tenha Skype for Business usuários que não estão em casa em seus servidores Exchange. Se você implantar o arquivamento usando Exchange opção de integração do Microsoft Exchange, os dados de arquivo morto Skype for Business serão armazenados com dados de conformidade Exchange somente para os usuários que estão armazenados em seus servidores Exchange. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para arquivamento no Skype for Business Server 2015
  
O arquivamento não é uma função de servidor definida, você não precisa instalar um servidor separado para arquivamento. Os Agentes de Coleta de Dados Unificados são instalados e ativados automaticamente em cada pool Edição Enterprise front-end e em todos os Edição Standard Server. Você precisará habilitar e publicar sua topologia de arquivamento usando o Construtor de Topologias.
    
O arquivamento usa o Skype for Business Server de arquivos para armazenamento temporário de arquivos de conteúdo de reunião, para que você não configurar um armazenamento de arquivos separado para arquivamento.
    
A en fila de mensagens da Microsoft não é necessária.
    
Você precisará configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui escolher o armazenamento de Exchange ou arquivamento usando SQL Server.   Skype for Business Server Os requisitos de infraestrutura de arquivamento são os mesmos da implantação de Skype for Business Server. Para obter detalhes, consulte [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Para dar suporte a usuários que não estão em casa em servidores Exchange, ou se você não quiser usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados de 64 bits SQL Server. 
    
Você deve configurar as plataformas SQL Server antes da implantação e habilitação do arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação. Para obter detalhes SQL Server, consulte a [documentação SQL Server .](/sql/sql-server/)
    
O aumento de carga para arquivamento pode ser significativo. Portanto, você deve garantir que o espaço em disco seja adequado para Servidores Front-End nos quais o arquivamento está habilitado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Espelhamento, SQL clustering e SQL Always On

Você pode usar SQL espelhamento ou SQL clustering com Skype for Business Server 2015, ele tem suporte. SQL O espelhamento é criado por meio do Construtor Skype for Business Server Topologia. Se você tiver a intenção de configurar SQL clustering, isso é feito em SQL Server.
  
Certifique-se de ter uma configuração ativa/passiva para SQL clustering, pois é isso que é suportado. Não compartilhe o nó passivo com nenhuma outra instância SQL.
  
Você pode ter o seguinte para cluster de failover:
  
Dois nós:
  
- Microsoft SQL Server 2019 Standard (edição de 64 bits) e recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2017 Standard (edição de 64 bits) e recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2016 Standard (edição de 64 bits) com Service Pack 1 ou posterior. Recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2014 Standard (edição de 64 bits) e recomendamos a execução com o service pack mais recente.
    
-  Microsoft SQL Server 2012 Standard (edição de 64 bits) e recomendamos a execução com o service pack mais recente.

Dezesseis nós:

- Microsoft SQL Server 2019 Enterprise (edição de 64 bits) e recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2017 Enterprise (edição de 64 bits) e recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2016 Enterprise (edição de 64 bits) com Service Pack 1 ou posterior. Recomendamos a execução com o service pack mais recente.
  
- Microsoft SQL Server 2014 Enterprise (edição de 64 bits) e recomendamos a execução com o service pack mais recente.
    
- Microsoft SQL Server 2012 Enterprise (edição de 64 bits) e recomendamos a execução com o service pack mais recente.

> [!IMPORTANT]
> Para atualizar, queremos garantir que, em seus Servidores Front-End, você tenha pelo menos SQL Server 2012 SP1 instalado antes da atualização. [Aqui está um link para](https://www.microsoft.com/download/details.aspx?id=35575) SP1 se você quiser baixá-lo imediatamente.
  
Se você precisar ler mais sobre o SQL Espelhamento, temos uma alta disponibilidade do Servidor back-end no tópico Skype for Business Server 2015. Configurar SQL Server clustering para Skype for Business Server 2015 tem as etapas para preparar o clustering. Também há outros links sobre cluster de failover para SQL, para [2014](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation), [2012](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))e [2008](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)).
  
> [!NOTE]
> A novidade na versão 2015 é o suporte SQL Always On. Ele é suportado e você pode ler mais sobre ele no tópico De alta disponibilidade do [Servidor back-end no Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

> [!NOTE]
> SQL O espelhamento está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn (FCI) e SQL de clustering de failover são preferenciais com o Skype for Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que deve ser instalado antes de uma implantação Skype for Business Server 2015
<a name="Software"> </a>

Há algumas coisas que você precisará instalar ou configurar para qualquer servidor que esteja executando Skype for Business Server 2015, e elas estão listadas abaixo. Depois disso, há requisitos adicionais para funções de servidor específicas.

  
 **Todos os servidores:**
  
|Software/Função|Detalhes|
|:-----|:-----|
|Windows PowerShell 3.0   |Todos Skype for Business Server servidores precisam Windows PowerShell 3.0 instalados.  <br/> • Se você estiver fazendo a instalação no Windows Server 2012 ou Windows Server 2012 R2, você está definido, porque ele já está lá.  <br/> • Se você estiver fazendo uma atualização no Windows Server 2008 R2, baixe o [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) para obter. <br/> **Dica:** Depois de ter o PowerShell correto, confirme se é BuildVersion 6.2.9200.0 ou posterior, indo para o prompt do PowerShell e digitando `$PSVersionTable` . Isso deve trazer a informação de que você precisa.   |
|Microsoft .NET Framework   |Os serviços WCF são **um recurso** instalado como um recurso Windows, em **Gerenciador** de Servidores, sem downloads necessários. <br/> • Você precisa certificar-se de que, ao instalar esse recurso ou se ele já estiver instalado e estiver verificando, a opção Ativação **HTTP** também está marcada e instalada, da seguinte forma: <br/> ![Captura de tela mostrando a opção De ativação HTTP na .NET Framework recursos 4.5.](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Não se preocupe se você receber um pop-up adicional dizendo que algumas outras coisas precisam ser instaladas para a ativação HTTP ser instalada. Isso é normal, clique em OK e vá em frente. Se você não receber esse pop-up, suponha que essas coisas já estão instaladas e vá em frente.  <br/> O Microsoft .NET Framework geralmente é instalado quando Windows Server 2012 R2 ou Windows Server 2016 estão instalados. Skype for Business Server funciona com as seguintes versões do Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (para versões Skype for Business Server CU 5 ou posteriores)  <br/> • .NET 4.7.2 (para versões Skype for Business Server CU 6 ou posteriores)  <br/>  • .NET 4.8 (para versões Skype for Business Server CU 9 ou posteriores) <br/>  .NET Framework 3.5 provavelmente será instalado por padrão em seu computador do Windows Server 2008 R2 (verifique com certeza antes de atualizar), mas ele não estará nos servidores Windows Server 2012/Windows Server 2012 R2 (para novas instalações). Para adicioná-lo, você precisará acessar sua unidade de instalação ou mídia (o local de onde o Windows Server foi instalado ou onde os arquivos de instalação estão agora). Em seguida, vá em frente e instale-o como um recurso do Gerenciador de Servidores e aponte para a mídia de instalação (especificamente a **pasta \sources\sxs)** quando solicitado e continue a instalá-la.  |
|Media Foundation   |Para Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2 o Windows Tempo de Execução de Formato de Mídia é instalado com o Microsoft Media Foundation.  <br/> Todos os servidores front-end e servidores Edição Standard Windows usados para conferência exigem um tempo de execução de formato de mídia Windows para executar os arquivos de áudio de mídia (.wma) que os aplicativos estacionamento de chamada, comunicado e grupo de resposta reproduzem para anúncios e música.   |
|Windows Identity Foundation  <br/> |Precisamos Windows Identity Foundation 3.5 para dar suporte a cenários de autenticação de servidor para servidor para Skype for Business Server 2015.  <br/> • Para Windows Server 2012 e Windows Server 2012 R2, não é necessário baixar nada. Abra **o Gerenciador de** Servidores e vá para o Assistente adicionar funções e **recursos.** **Windows Identity Foundation 3.5** está listado na **seção Recursos.** Se for verificado, você é bom. Caso contrário, selecione-o e clique em Próximo para alcançar o **botão Instalar.**  |
|Ferramentas de Administração de Servidor Remoto   |Ferramentas de Administração de Função: ferramentas do AD DS e do AD LDS   |
   
 **Servidores front-end e Edição Standard servidor também precisam:**
  
|Software/Função|Detalhes|
|:-----|:-----|
|IIS (Serviços de Informações da Internet)   |O IIS é necessário em todos os Servidores Front-End, bem como em todos os servidores Edição Standard, com os seguintes módulos selecionados:  <br/> • Recursos HTTP comuns: Documento Padrão, Erros HTTP, Conteúdo Estático  <br/> • Health and Diagnostics: HTTP Logging, Logging Tools, Tracing  <br/> • Desempenho: Compactação de Conteúdo Estático, Compactação dinâmica de conteúdo  <br/> • Segurança: Filtragem de Solicitação, Autenticação de Mapeamento de Certificados do Cliente, Windows Autenticação  <br/> • Desenvolvimento de aplicativos: Extensibilidade .NET 3.5, Extensibilidade .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, Extensões ISAPI, Filtros ISAPI  <br/> • Ferramentas de Gerenciamento: Console de Gerenciamento do IIS, Scripts e Ferramentas de Gerenciamento do IIS  <br/> Também devemos observar que o Acesso Anônimo também é necessário, mas você pode obter isso ao instalar o IIS, para que não tenha um local para selecionar isso na lista.   |
|Tempo de Execução do Windows Media Format   | Para Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, você precisará instalar o recurso **Media Foundation** no **Gerenciador do Servidor.** Agora, você realmente pode iniciar sua instalação do Skype for Business Server 2015 sem essa, mas será solicitado a instalá-lo e reiniciar o servidor, antes que a instalação do Skype for Business Server 2015 continue. É melhor fazer isso com antecedência.  |
|Silverlight   |Você pode instalar a versão mais recente do Silverlight [neste link](https://www.microsoft.com/silverlight/).   |
   
> [!NOTE] 
> Você também pode precisar habilitar a Navegação de Diretório se estiver usando um balanceador de carga. Caso contrário, uma página em branco carregará a qual o balanceador de carga pode considerar uma falha. 

Para ajudá-lo, aqui está um exemplo de script do PowerShell que você pode executar para automatizar isso:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> O comando procura arquivos de origem em uma ordem específica. Se você estiver online, o comando acessará Windows Update. No entanto, se você estiver offline, precisará garantir que os arquivos de origem estão disponíveis para o comando. Para obter mais informações sobre como usar o PowerShell para instalar funções e recursos, consulte Install or [Uninstall Roles, Role Services, or Features](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.

 **Os diretores também precisam:**
  
IIS, com os seguintes módulos selecionados:
  
- Recursos HTTP Comuns
    
  - Documento padrão
    
  - Erros HTTP
    
  - Conteúdo Estático
    
- Manutenção e diagnóstico
    
  - Log HTTP
    
  - Ferramentas de log
    
  - Rastreamento
    
- Desempenho
    
  - Compactação de conteúdo estático
    
- Segurança
    
  - Filtragem de Solicitações
    
  - Autenticação de mapeamento de certificado de cliente
    
  - Autenticação do Windows
    
- Desenvolvimento de aplicativo
    
  - Extensibilidade do .NET 3.5
    
  - Extensibilidade do .NET 4.5
    
  - ASP.NET 3,5
    
  - ASP.NET 4,5
    
  - Extensão ISAPI
    
  - Filtros ISAPI
    
(Se você estiver se perguntando, é o mesmo conjunto de módulos que os Servidores front-end e servidores Edição Standard, com as Ferramentas dinâmicas de Compactação e Gerenciamento de Conteúdo.)
  
E também temos alguns códigos do PowerShell abaixo para isso:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Os Servidores de Chat Persistente também precisam:**
  
En fila de mensagens, que também é chamada de MSMQ. É um componente Windows Server e você pode instalá-lo na seção Recursos no Gerenciador do Servidor. Se quiser ler mais sobre isso, confira Instalando e [gerenciando a en fila de mensagens.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11))
  
 **Últimos comentários:**
  
Não instale nenhum software cliente de IsA (Segurança e Aceleração da Internet) da Microsoft ou qualquer outro software LSP (Provedores de Serviços em Camadas) winsock (qualquer firewall de terceiros ou software de inspeção de rede antivírus seria incluído aqui) em qualquer um dos servidores front-end ou servidores de mediação autônomos. O desempenho ruim do tráfego de mídia foi visto quando esse software está instalado.
