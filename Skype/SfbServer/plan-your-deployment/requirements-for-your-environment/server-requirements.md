---
title: Requisitos de servidor no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Resumo: Prepare seus servidores do Skype for Business Server 2015 com este tópico. Hardware, sistema operacional, bancos de dados, software, todos os requisitos de sistema e recomendações estão aqui para ajudar a garantir uma instalação e uma implantação bem-sucedidas do seu farm de servidores.'
ms.openlocfilehash: f806137b5972968332723a370092724bd9680697
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801881"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos de servidor no Skype for Business Server 2015
 
**Resumo:** prepare seus servidores do Skype for Business Server 2015 com este tópico. Hardware, sistema operacional, bancos de dados, software, todos os requisitos do sistema e recomendações estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas de seu farm de servidores.

Se você estiver procurando por requisitos ambientais, como Active Directory, DNS ou certificados, confira os [requisitos ambientais do Skype for Business Server 2015](environmental-requirements.md) doc.
  
Como você pode esperar, há alguns preparativos a fazer antes de começar a implantar o Skype for Business Server 2015. Este artigo explica como deve ser o planejamento dos seguintes itens:
  
- [Hardware para o Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operacionais para o Skype for Business Server 2015](server-requirements.md#OS)
  
- [Bancos de dados back-end compatíveis com o Skype for Business Server 2015](server-requirements.md#DBs)
  
- [O software que deve ser instalado antes da implantação do Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para o Skype for Business Server 2015
<a name="Hardware"> </a>

Agora que você já tem a sua topologia (e se não tiver, Confira as noções básicas de topologia para o tópico sobre o [Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), é hora de pensar nos servidores. Os servidores do Skype for Business Server 2015 precisarão de hardware de 64 bits. Nossas recomendações para hardware estão listadas abaixo. Estes são os requisitos, mas refletem os requisitos necessários para o melhor desempenho. Temos uma documentação de planejamento de capacidade que ajudará você a determinar se precisa de mais alguma coisa, dependendo das suas circunstâncias.
  
Hardware recomendado para servidores front-end, servidores back-end, servidores Standard Edition e servidores de chat persistente:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior.  <br/> Os processadores Intel Itanium não são compatíveis com as funções do Skype for Business Server 2015.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DESTAS OPÇÕES:  <br/> • 8 ou mais 10000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco (dois discos usando RAID 1 e 6 usando RAID 10).  <br/> OR  <br/> • Os discos de estado sólido (SSDs) podem fornecer o mesmo espaço livre e desempenho semelhante para os drives de disco mecânico 8 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> **Não** há suporte para configurações de duas ou várias bases para servidores front-end, servidores back-end, servidores de edição padrão e servidores de chat persistente. <br/> Desde que não sejam expostos ao sistema operacional e sejam usados para monitorar e gerenciar o hardware de servidor, você pode ter sistemas de gerenciamento fora de banda, como DRAC ou ILO. Esse cenário não constitui um servidor multihomed e tem suporte.<br/> |
   
Hardware recomendado para servidores de borda, servidores de mediação autônomo, servidores de interoperabilidade de vídeo e directors:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de 64 bits, quad-core, 2.26 gigahertz (GHz) ou superior.  <br/> Os processadores Intel Itanium não são compatíveis com as funções do Skype for Business Server 2015.  <br/> |
|Memória  <br/> |16 GB.  <br/> |
|Disco  <br/> |UMA DESTAS OPÇÕES:  <br/> • 4 ou mais 10000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco (os discos devem estar em uma configuração RAID 1 2x).  <br/> OR  <br/> • Os discos de estado sólido (SSDs) podem fornecer o mesmo espaço livre e desempenho semelhante para os drives de disco mecânico 4 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> **Não** há suporte para configurações de duas ou várias bases para servidores e diretores de interoperabilidade de vídeo. <br/> Servidores de borda exigem duas interfaces de rede que são adaptadores de rede dual-port, 1 Gbps ou superior (ou dois adaptador de rede pareados, com um total de quatro, sendo que cada par está combinado com um único endereço MAC e um único endereço IP).  <br/> Em servidores de mediação autônomos, há suporte para a instalação de placas de interface de rede adicionais (NICs) para permitir a configuração de um endereço IP PSTN específico.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operacionais para o Skype for Business Server 2015
<a name="OS"> </a>

Após o hardware, você precisará instalar o sistema operacional (SO). Estes são o sistema operacional que permitirá que você instale e use com êxito o Skype for Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (você precisa do Skype for Business, atualização cumulativa 9 ou posterior). <br/> |Windows Server 2016 (é necessária a atualização cumulativa 5 do Skype for Business) ou posterior. Para obter mais informações, consulte [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Sistema operacional Windows Server 2012 R2 Datacenter com todas as atualizações necessárias instaladas.  <br/> |Sistema operacional Windows Server 2012 R2 Standard com todas as atualizações necessárias instaladas.  <br/> |
|Sistema operacional Windows Server 2012 datacenter com todas as atualizações necessárias instaladas.  <br/> |Sistema operacional Windows Server 2012 padrão com todas as atualizações necessárias instaladas.  <br/> |
   
Se ele não estiver nesta lista, ele não funcionará corretamente, não tente fazê-lo para novas instalações do Skype for Business Server 2015. Observe que a atualização in-loco do sistema operacional não é compatível com o Lync Server 2013.  Você deve implantar um pool separado e migrar usuários para o novo pool com um sistema operacional diferente.
  
> [!NOTE]
> Você pode ter notado que o Windows Server 2008 R2 não está na lista. Isso é porque recomendamos que o Windows Server 2012 R2 seja usado para todos os novos servidores para SFB. Você só deve usar o Windows Server 2008 R2 quando tiver servidores existentes com o Lync Server 2013 já instalados e se estiver pretendendo fazer uma atualização local deles. O Windows Server 2008 R2 chegou ao final do ciclo de vida do suporte principal no 1/13/2015 e chegará ao final do ciclo de vida do suporte no 1/14/2020.
  
Além da última versão do service pack, as atualizações a seguir devem estar instaladas quando for pertinente para você:
  
- Para o Windows Server 2012, instale o artigo 2858668 da base de dados de conhecimento antes de fazer uma atualização. [Obtenha-o aqui](https://support.microsoft.com/kb/2858668/).
    
- Se você tem o Windows Server 2012 R2, instale o artigo 2982006 da base de dados de conhecimento antes de fazer uma atualização. [Aqui encontra-se aqui](https://support.microsoft.com/kb/2982006/).
    
- Se você está fazendo uma atualização em uma caixa do Windows Server 2008 R2 (veja a Observação acima), instale o artigo 2533623 da base de dados de conhecimento primeiro. [Ele está nesse link](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bancos de dados back-end compatíveis com o Skype for Business Server 2015
<a name="DBs"> </a>


Ao instalar o Skype for Business Server 2015 Standard Edition, o SQL Server 2014 Express (64-bit Edition) também será instalado automaticamente.
  
O Skype for Business Server 2015 Enterprise Edition é um pouco mais complicado, mas a lista suportada está abaixo (tudo é a edição de 64 bits, você notará que não usa as edições de 32 bits):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente. <br/> |Microsoft SQL Server 2017 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente. <br/> |Microsoft SQL Server 2016 Enterprise (64-bit Edition) com Service Pack 1 ou posterior, e você deve executar com a atualização cumulativa 7 ou posterior do Skype for Business ([Baixe a atualização cumulativa do Skype for Business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (64-bit Edition), e você deve executar com a atualização cumulativa 6 ou posterior ([baixar atualização cumulativa 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente.  <br/> |
|Microsoft SQL Server 2019 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente. <br/> |Microsoft SQL Server 2017 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente. <br/> |Microsoft SQL Server 2016 Standard (64-bit Edition) com Service Pack 1 ou posterior, e você deve executar com a atualização cumulativa 7 ou posterior do Skype for Business ([Baixe a atualização cumulativa do Skype for Business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (64-bit Edition), e você deve executar com a atualização cumulativa 6 ou posterior ([baixar atualização cumulativa 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente.  <br/> |
   
Se você não vir a edição do SQL Server que deseja usar listada aqui, não poderá usá-la.
  
- Você também precisará instalar o SQL Server Reporting Services para a função de servidor de monitoramento.
- Para um back-end SQL bem conectado, a conexão com o front-end do Skype for Business deve ser local e não através de um link de baixa velocidade. 
- Não há suporte para o compartilhamento de back-back do SQL entre dois ou mais pools.

### <a name="microsoft-exchange-storage"></a>Armazenamento do Microsoft Exchange
Meeting content files, such as PowerPoint presentations, are archived as attachments. Se quiser armazenar dados de arquivo do Skype for Business com dados de conformidade do Exchange, você deve usar o Exchange para a implantação do Exchange e garantir que o tamanho máximo de armazenamento seja compatível com o armazenamento dos arquivos de conteúdo da reunião. Você deve implantar o Exchange antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para arquivamento no Skype for Business Server 2015
  
O arquivamento não é uma função de servidor definida, você não precisa instalar um servidor separado para arquivar. Os agentes de coleta de dados unificados são instalados e ativados automaticamente em cada pool de front-end Enterprise Edition e cada servidor Standard Edition. Você precisa habilitar e publicar a topologia do seu arquivamento usando o Construtor de Topologias.
    
O arquivamento usa o armazenamento de arquivos do Skype for Business Server para armazenamento temporário de arquivos de conteúdo da reunião, para que você não configure um armazenamento de arquivos separado para o arquivamento.
    
O enfileiramento de mensagens da Microsoft não é necessário.
    
Além disso, você deve configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui escolher o armazenamento do Exchange ou do arquivamento usando o SQL Server.   Os requisitos da infraestrutura de arquivamento do Skype for Business Server são os mesmos para a implantação do Skype for Business Server. Para obter detalhes, consulte [requisitos para o seu ambiente do Skype for Business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Para dar suporte a usuários que não são hospedados em servidores Exchange, ou se você não quiser usar a opção de integração do Microsoft Exchange, você deve implantar o arquivamento de armazenamento usando um banco de dados do SQL Server de 64 bits. 
    
Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte a [documentação do SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
O aumento de carga para arquivamento pode ser significativo. Portanto, você deve certificar-se de que o espaço em disco é adequado para servidores front-end em que o arquivamento está habilitado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Mirroring, SQL Clustering e SQL Always On

Você pode usar o espelhamento do SQL ou o agrupamento do SQL com o Skype for Business Server 2015, compatível. O espelhamento do SQL está configurado com o construtor de topologias do Skype for Business Server. Se você pretende configurar o agrupamento do SQL, isso é feito no SQL Server.
  
Certifique-se de que você tenha uma configuração ativa/passiva para agrupamento do SQL, pois isso é suportado. Não compartilhe o nó passivo com nenhuma outra instância do SQL.
  
Você pode ter os seguintes itens para clustering de failover:
  
Dois nós:
  
- Microsoft SQL Server 2019 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente.

- Microsoft SQL Server 2017 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente.

- Microsoft SQL Server 2016 Standard (64-bit Edition) com Service Pack 1 ou posterior. Recomendamos executar com o Service Pack mais recente.

- Microsoft SQL Server 2014 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente.
    
-  Microsoft SQL Server 2012 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente.

Dezesseis nós:

- Microsoft SQL Server 2019 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente.

- Microsoft SQL Server 2017 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente.

- Microsoft SQL Server 2016 Enterprise (64-bit Edition) com Service Pack 1 ou posterior. Recomendamos executar com o Service Pack mais recente.
  
- Microsoft SQL Server 2014 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente.
    
- Microsoft SQL Server 2012 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente.

> [!IMPORTANT]
> Para a atualização, queremos que você garanta que em seus servidores front-end você tenha pelo menos o SQL Server 2012 SP1 instalado antes da atualização. [Aqui está um link para o](https://www.microsoft.com/download/details.aspx?id=35575) SP1, se você quiser baixá-lo imediatamente.
  
Se você precisar ler mais sobre o espelhamento do SQL, temos um tópico servidor back-end de alta disponibilidade no Skype for Business Server 2015. Configurar o cluster do SQL Server para o Skype for Business Server 2015 tem as etapas para a obtenção de clusters pronto. Também há mais links no cluster de failover para SQL, para o [2014](https://technet.microsoft.com/library/hh231721.aspx), o [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)e o [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> A novidade do lançamento do 2015 é o suporte do SQL sempre ativado. Ele tem suporte e você pode ler mais sobre isso no tópico [back-end Server High Availability in Skype for Business server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .

> [!NOTE]
> O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>O software que deve ser instalado antes da implantação do Skype for Business Server 2015
<a name="Software"> </a>

Há algumas coisas que você precisará instalar ou configurar para qualquer servidor que esteja executando o Skype for Business Server 2015 e estiverem listados abaixo. Depois disso, há requisitos adicionais para funções de servidor específicas.
  
> [Observação!] O Skype for Business Server 2015 não é compatível com o .NET Framework 4,8.
  
 **Todos os servidores:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos os servidores do Skype for Business precisam ter o Windows PowerShell 3,0 instalado.  <br/> • Se você estiver fazendo a instalação no Windows Server 2012 ou no Windows Server 2012 R2, estará pronto, pois ele já está lá.  <br/> • Se estiver fazendo uma atualização no Windows Server 2008 R2, você pode baixar a [estrutura de gerenciamento do windows 3,0](https://www.microsoft.com/download/details.aspx?id=34595) para obtê-la. <br/> **Dica:** Depois que você tiver o PowerShell correto nele, confirme se ele é BuildVersion 6.2.9200.0 ou posterior acessando o prompt do PowerShell e `$PSVersionTable`digitando. Isso deve exibir as informações de que você precisa.  <br/> |
|Microsoft .NET Framework  <br/> |Os serviços do WCF são um **recurso** instalado como um recurso do Windows, em **Gerenciador de servidor**, sem necessidade de downloads. <br/> • Você precisa ter certeza de que, ao instalar esse recurso, ou se ele já estiver instalado e você estiver verificando, se a opção de **ativação http** também está marcada e instalada, da seguinte maneira: <br/> ![Captura de tela mostrando a opção de ativação HTTP nos recursos do .NET Framework 4,5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Não se preocupe se você receber um pop-up adicional para dizer que outras coisas precisam ser instaladas para que a ativação http seja instalada. Isso é normal, então clique em OK e siga em frente. Se a janela pop-up não aparecer, isso significa que essas coisas já estão instaladas e você pode seguir em frente.  <br/> O Microsoft .NET Framework geralmente é instalado quando o Windows Server 2012 R2 ou o Windows Server 2016 está instalado. O Skype for Business Server funciona com as seguintes versões do Microsoft .NET Framework:  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (para o Skype for Business Server RECOR 5 ou versões posteriores)  <br/>  O .NET Framework 3,5 provavelmente será instalado por padrão em seu computador com o Windows Server 2008 R2 (definitivamente, verifique se você está seguro antes de atualizar), mas na verdade ele não estará em seus servidores Windows Server 2012/Windows Server 2012 R2 (para novas instalações). Para adicioná-lo, você precisará ter acesso à sua unidade de instalação ou mídia (o local de onde o Windows Server foi instalado ou onde os arquivos de instalação estão agora). Depois, você poderá instalá-lo como um recurso do Gerenciador do Servidor e apontar para a mídia de instalação (mais especificamente, a pasta **\sources\sxs**) quando solicitado, e então continuar a instalação. <br/> |
|Media Foundation  <br/> |Para o Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado com o Microsoft Media Foundation.  <br/> Todos os servidores de front-end e servidores de edição padrão usados para a conferência exigem o tempo de execução do Windows Media Format para executar os arquivos de áudio do Windows Media (. WMA) que os aplicativos do parque, do anúncio e do grupo de resposta da chamada são reproduzidos para anúncios e músicas.  <br/> |
|Windows Identity Foundation  <br/> |Precisamos do Windows Identity Foundation 3,5 para dar suporte a cenários de autenticação de servidor para servidor para o Skype for Business Server 2015.  <br/> • Para Windows Server 2012 e Windows Server 2012 R2, não é necessário baixar nada. Abra o **Gerenciador do Servidor** e vá para o **Assistente de Adição de Funções e Recursos**. O **Windows Identity Foundation 3.5** está listado na seção **Recursos**. Se estiver marcada, você está bom. Caso contrário, clique em Avançar para acessar o botão **Instalar**. <br/> |
|AD DS and AD LDS ToolsFerramentas de Administração de Servidor Remoto  <br/> |Ferramentas de Administração de Funções: ferramentas do AD DS e AD LDS  <br/> |
   
 **Os servidores front-end e o servidor Standard Edition também precisam ter:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|IIS (Serviços de Informações da Internet)  <br/> |O IIS é necessário em todos os servidores front-end, bem como em todos os servidores de edição padrão, com os seguintes módulos selecionados:  <br/> • Recursos comuns de HTTP: documento padrão, erros de HTTP, conteúdo estático  <br/> • Integridade e diagnóstico: log HTTP, ferramentas de log, rastreamento  <br/> • Desempenho: compactação de conteúdo estático, compactação de conteúdo dinâmico  <br/> • Segurança: filtragem de solicitações, autenticação de mapeamento de certificado de cliente, autenticação do Windows  <br/> • Desenvolvimento de aplicativos: extensibilidade do .NET 3,5, extensibilidade do .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, extensões ISAPI, filtros ISAPI  <br/> • Ferramentas de gerenciamento: console de gerenciamento do IIS, scripts e ferramentas de gerenciamento do IIS  <br/> Também devemos observar que o acesso anônimo também é necessário, mas você obtém isso ao instalar o IIS, portanto, você não tem um local para selecioná-lo na lista.  <br/> |
|Tempo de Execução do Windows Media Format  <br/> | Para o Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, você precisará instalar o recurso **Media Foundation** no **Gerenciador de servidores**. Agora, você pode iniciar a instalação do Skype for Business Server 2015 sem isso, mas será solicitado a instalá-la e, em seguida, reinicializar o servidor, antes que a instalação do 2015 do Skype for Business Server continue. É melhor fazer isso com antecedência. <br/> |
|Silverlight  <br/> |Você pode instalar a versão mais recente do Silverlight neste [link](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Você também pode precisar habilitar a navegação em diretório se estiver usando um balanceador de carga. Caso contrário, uma página em branco carregará qual o balanceador de carga pode considerar uma falha. 

Para ajudar você, separamos esta amostra de script do PowerShell que você pode executar para automatizar esse processo:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> O comando procura arquivos de origem em uma ordem específica. Se você estiver online, o comando acessa o Windows Update. No entanto, se você estiver offline, terá que verificar se os arquivos de origem estão disponíveis para o comando. Para obter mais informações sobre como usar o PowerShell para instalar funções e recursos, confira [funções de instalação ou desinstalação, serviços de função ou recursos](https://technet.microsoft.com/library/hh831809.aspx) não se esqueça de executar o Windows Update novamente depois de instalar pré-requisitos, mesmo se você usar o comando do PowerShell.

 **Os directors também precisam de:**
  
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
    
(Se você estiver se perguntando, é o mesmo conjunto de módulos de front-end que os servidores de front-end e os servidores da edição padrão, com as ferramentas de gerenciamento e compactação de conteúdo dinâmico deixadas.)
  
Abaixo, também temos um código do PowerShell para isso:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Também é preciso ter servidores de chat persistentes:**
  
Enfileiramento de Mensagens, também é chamado MSMQ. É um componente do Windows Server e você pode instalá-lo na seção recursos do Gerenciador de servidores. Se você quiser ler mais sobre isso, confira a [instalação e o gerenciamento do enfileiramento de mensagens](https://technet.microsoft.com/library/cc771474.aspx).
  
 **Últimas observações:**
  
Não instale nenhum software cliente do Microsoft Internet Security and Acceleration (ISA) Server, ou qualquer outro software de provedores de serviços em camadas (LSP) do Winsock (qualquer firewall de terceiros ou software de inspeção de rede antivírus estaria incluído aqui) em qualquer um dos seus servidores front-end ou servidores de mediação autônomos. Um desempenho de tráfego de mídia fraco foi visto quando o software está instalado.
  

