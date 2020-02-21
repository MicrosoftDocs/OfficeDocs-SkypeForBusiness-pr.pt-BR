---
title: Requisitos de servidor para o Skype for Business Server 2015
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
description: 'Resumo: Prepare seus servidores do Skype for Business Server 2015 com este tópico. Hardware, so, bancos de dados, software, todos os requisitos e recomendações do sistema estão aqui para ajudar a garantir uma instalação bem-sucedida e uma implantação do farm de servidores.'
ms.openlocfilehash: f1898fc9de5999276b963a78c181e3b098876b69
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160388"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos de servidor para o Skype for Business Server 2015
 
**Resumo:** Prepare seus servidores do Skype for Business Server 2015 com este tópico. Hardware, so, bancos de dados, software, todos os requisitos e recomendações do sistema estão aqui para ajudar a garantir uma instalação bem-sucedida e uma implantação do farm de servidores.

Se você estiver procurando requisitos de ambiente, como Active Directory, DNS ou certificados, confira os [requisitos de ambiente do Skype for Business Server 2015](environmental-requirements.md) doc.
  
Como você pode esperar, é possível fazer algumas preparações antes de começar a implantar o Skype for Business Server 2015. Este artigo orientará você no planejamento do seguinte:
  
- [Hardware para o Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operacionais para o Skype for Business Server 2015](server-requirements.md#OS)
  
- [Bancos de dados back-end que funcionarão com o Skype for Business Server 2015](server-requirements.md#DBs)
  
- [Software que deve ser instalado antes da implantação do Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para o Skype for Business Server 2015
<a name="Hardware"> </a>

Agora que você está com sua topologia inoperante (e, se não tiver, confira o tópico [Basics Topology for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), é hora de pensar nos servidores. Os servidores do Skype for Business Server 2015 precisarão de hardware de 64 bits. Nossas recomendações de hardware estão abaixo. Eles não são requisitos, mas refletem os requisitos necessários para o desempenho ideal. Temos documentação de planejamento de capacidade que ajudará você a determinar se precisa de mais do que isso, dependendo de suas circunstâncias.
  
Hardware recomendado para servidores front-end, servidores de back-end, servidores Standard Edition e servidores de chat persistente:
  
|**Componente de hardware**|**Recomenda**|
|:-----|:-----|
|CPU  <br/> |processador dual de 64 bits, Hex-Core, 2,26 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para funções do Skype for Business Server 2015.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |EM  <br/> • 8 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre em disco (dois dos discos usando RAID 1 e 6 usando RAID 10).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar a drives de disco mecânico 8 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas precisam ser agrupados com um único endereço MAC e um único endereço IP).  <br/> As configurações de duas ou várias bases **não** têm suporte para servidores front-end, servidores de back-end, servidores Standard Edition e servidores de chat persistente. <br/> Contanto que eles não estejam expostos ao sistema operacional e estejam sendo usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento fora de banda, como DRAC ou ILO. Este cenário não constitui um servidor de hospedagem múltipla e é suportado.  <br/> |
   
Hardware recomendado para servidores de borda, servidores de mediação autônomo, servidores de interoperabilidade de vídeo e diretores:
  
|**Componente de hardware**|**Recomenda**|
|:-----|:-----|
|CPU  <br/> |processador dual de 64 bits, Quad-Core, 2,26 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para funções do Skype for Business Server 2015.  <br/> |
|Memória  <br/> |16 gigabytes.  <br/> |
|Disco  <br/> |EM  <br/> • 4 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre em disco (os discos devem estar em uma configuração RAID 1 2x).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar a drives de disco mecânico 4 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas precisam ser agrupados com um único endereço MAC e um único endereço IP).  <br/> Configurações de duas ou várias bases **não** são suportadas para servidores e diretores de interoperabilidade de vídeo. <br/> Os servidores de borda exigirão duas interfaces de rede que sejam adaptadores de rede de duas portas, 1 Gbps ou superior (ou dois adaptadores de rede emparelhados, para um total de quatro, cada par que está sendo agrupado com um único endereço MAC e um único endereço IP, para um total de dois pares).  <br/> Em servidores de mediação autônomos, a instalação de NICs (placas de interface de rede) adicionais para permitir a configuração de um endereço IP PSTN específico é suportada.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operacionais para o Skype for Business Server 2015
<a name="OS"> </a>

Após o hardware, você precisará instalar o sistema operacional (OS). Estes são os sistemas operacionais que lhe permitirão instalar e usar com êxito o Skype for Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (você precisa do Skype for Business atualização cumulativa 9 ou posterior). <br/> |Windows Server 2016 (você precisa do Skype for Business atualização cumulativa 5 ou posterior. Para obter mais informações, consulte [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 R2 Datacenter OS com todas as atualizações necessárias instaladas.  <br/> |Sistema operacional Windows Server 2012 R2 Standard com todas as atualizações necessárias instaladas.  <br/> |
|Windows Server 2012 datacenter OS com todas as atualizações necessárias instaladas.  <br/> |Sistema operacional Windows Server 2012 Standard com todas as atualizações necessárias instaladas.  <br/> |
   
Se ele não estiver na lista, não funcionará corretamente, não tente fazer novas instalações do Skype for Business Server 2015. Observe que a atualização in-loco do sistema operacional não é suportada pelo Lync Server 2013.  Você deve implantar um pool separado e migrar os usuários para o novo pool com um sistema operacional diferente.
  
> [!NOTE]
> Você pode ter notado que o Windows Server 2008 R2 não está na lista. Isso porque recomendamos o Windows Server 2012 R2 para todos os novos servidores a serem usados para o SFB. Você só deve usar o Windows Server 2008 R2 quando tiver servidores existentes com o Lync Server 2013 já instalado, e você pretende fazer uma atualização in-loco deles. O Windows Server 2008 R2 chegou ao fim do ciclo de vida do suporte principal em 1/13/2015 e chegará ao fim do seu ciclo de vida de suporte no 1/14/2020.
  
Além do Service Pack mais recente, você deve garantir que as seguintes atualizações estejam instaladas, onde relevante:
  
- Para o Windows Server 2012, o artigo 2858668 KB deve ser instalado antes de uma atualização. [Veja aqui](https://support.microsoft.com/kb/2858668/).
    
- Se você tiver o Windows Server 2012 R2, instale o artigo 2982006 do KB antes da atualização. [Ele é encontrado aqui](https://support.microsoft.com/kb/2982006/).
    
- Se você estiver atualizando em uma caixa do Windows Server 2008 R2 (consulte a observação acima), será necessário instalar o artigo de KB 2533623 primeiro. [Ele está neste link](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bancos de dados back-end que funcionarão com o Skype for Business Server 2015
<a name="DBs"> </a>


Ao instalar o Skype for Business Server 2015 Standard Edition, você terá o SQL Server 2014 Express (64-bit Edition) também instalado automaticamente.
  
O Skype for Business Server 2015 Enterprise Edition é um pouco mais complicado, mas a lista com suporte está abaixo (tudo é a edição de 64 bits, mas não use as edições de 32 bits):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente. <br/> |Microsoft SQL Server 2017 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente. <br/> |Microsoft SQL Server 2016 Enterprise (64-bit Edition) com Service Pack 1 ou posterior, e você deve executar a atualização cumulativa 7 ou posterior do Skype for Business ([Baixe a atualização cumulativa do Skype for Business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (64-bit Edition) e você deve executar a atualização cumulativa 6 ou posterior ([Baixe a atualização cumulativa 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente.  <br/> |
|Microsoft SQL Server 2019 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente. <br/> |Microsoft SQL Server 2017 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente. <br/> |Microsoft SQL Server 2016 Standard (64-bit Edition) com Service Pack 1 ou posterior, e você deve executar a atualização cumulativa 7 ou posterior do Skype for Business ([Baixe a atualização cumulativa do Skype for Business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (edição de 64 bits) e você deve executar a atualização cumulativa 6 ou posterior ([Baixe a atualização cumulativa 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente.  <br/> |
   
Se você não vir a edição do SQL Server que deseja usar listada aqui, não poderá usá-la.
  
- Você também precisará instalar o SQL Server Reporting Services para a função de servidor de monitoramento.
- Para um back-end SQL bem conectado, a conexão com o front-end do Skype for Business deve ser local e não através de um link de baixa velocidade. 
- Não há suporte para o compartilhamento de back-end do SQL entre dois ou mais pools.

### <a name="microsoft-exchange-storage"></a>Armazenamento do Microsoft Exchange
Conteúdo de reuniões, como apresentações em PowerPoint, são arquivados como anexos. Se quiser armazenar dados de arquivo morto do Skype for Business com dados de conformidade do Exchange, você deve usar o Exchange para sua implantação do Exchange e garantir que o tamanho máximo de armazenamento seja compatível com o armazenamento dos arquivos de conteúdo da reunião. Você deve implantar o Exchange antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para arquivamento no Skype for Business Server 2015
  
O arquivamento não é uma função de servidor definida, não é necessário instalar um servidor separado para arquivamento. Os agentes de coleta de dados unificados são instalados e ativados automaticamente em cada pool de front-ends Enterprise Edition e todos os servidores Standard Edition. Você precisará habilitar e publicar sua topologia de arquivamento usando o construtor de topologias.
    
O arquivamento usa o armazenamento de arquivos do Skype for Business Server para armazenamento temporário de arquivos de conteúdo de reunião, portanto, você não configura um repositório de arquivos separado para arquivamento.
    
O enfileiramento de mensagens da Microsoft não é necessário.
    
Você precisará configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui escolher o armazenamento de arquivamento ou do Exchange usando o SQL Server.   Os requisitos de infraestrutura de arquivamento do Skype for Business Server são os mesmos para a implantação do Skype for Business Server. Para obter detalhes, consulte [Requirements for your Skype for Business Environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Para dar suporte a usuários que não estão hospedados em servidores Exchange, ou se você não deseja usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados de 64 bits do SQL Server. 
    
Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte a [documentação do SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
O aumento de carga para arquivamento pode ser significativo. Portanto, você deve verificar se o espaço em disco é adequado para servidores front-end nos quais o arquivamento está habilitado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Espelhamento de SQL, cluster SQL e SQL Always on

Você pode usar o espelhamento do SQL ou o cluster SQL com o Skype for Business Server 2015, há suporte para ele. O espelhamento do SQL é configurado através do construtor de topologias do Skype for Business Server. Se você pretende configurar o cluster do SQL, isso é feito no SQL Server.
  
Certifique-se de que você tem uma configuração ativa/passiva para o cluster do SQL, já que isso é suportado. Não compartilhe o nó passivo com nenhuma outra instância do SQL.
  
Você pode ter os seguintes itens para clustering de failover:
  
Dois nós:
  
- Microsoft SQL Server 2019 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente.

- Microsoft SQL Server 2017 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente.

- Microsoft SQL Server 2016 Standard (64-bit Edition) com Service Pack 1 ou posterior. Recomendamos a execução com o Service Pack mais recente.

- Microsoft SQL Server 2014 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente.
    
-  Microsoft SQL Server 2012 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente.

Dezesseis nós:

- Microsoft SQL Server 2019 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente.

- Microsoft SQL Server 2017 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente.

- Microsoft SQL Server 2016 Enterprise (64-bit Edition) com Service Pack 1 ou posterior. Recomendamos a execução com o Service Pack mais recente.
  
- Microsoft SQL Server 2014 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente.
    
- Microsoft SQL Server 2012 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente.

> [!IMPORTANT]
> Para atualizar, queremos garantir que em seus servidores front-end você tenha pelo menos o SQL Server 2012 SP1 instalado antes da atualização. [Aqui está um link para o](https://www.microsoft.com/download/details.aspx?id=35575) SP1, se quiser baixá-lo imediatamente.
  
Se você precisar ler mais sobre o espelhamento de SQL, temos um tópico de back-end de alta disponibilidade do servidor do Skype for Business Server 2015. Configurar o cluster do SQL Server para o Skype for Business Server 2015 tem as etapas para se preparar o clustering. Há também outros links sobre clustering de failover para SQL, para [2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)e [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> A novidade no lançamento de 2015 é o suporte do SQL Always on. É suportado e você pode ler mais sobre ele no tópico back- [end Server High Availability in Skype for Business server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .

> [!NOTE]
> O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de clustering de failover do SQL são preferidos com o Skype for Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que deve ser instalado antes da implantação do Skype for Business Server 2015
<a name="Software"> </a>

Há algumas coisas que você precisará instalar ou configurar para qualquer servidor que executa o Skype for Business Server 2015 e que estão listadas abaixo. Após isso, os requisitos adicionais para funções de servidor específicas.
  
> [Observação!] O Skype for Business Server 2015 não é compatível com o .NET Framework 4,8.
  
 **Todos os servidores:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos os servidores Skype for Business Server precisam ter o Windows PowerShell 3,0 instalado.  <br/> • Se estiver fazendo a instalação no Windows Server 2012 ou no Windows Server 2012 R2, você está pronto, pois ele já está lá.  <br/> • Se estiver fazendo uma atualização no Windows Server 2008 R2, você pode baixar a [estrutura de gerenciamento do windows 3,0](https://www.microsoft.com/download/details.aspx?id=34595) para obtê-la. <br/> **Dica:** Depois de ter o PowerShell correto nele, confirme se ele é BuildVersion 6.2.9200.0 ou mais tarde, acessando o prompt do PowerShell `$PSVersionTable`e digitando. Isso deve exibir as informações necessárias.  <br/> |
|Microsoft .NET Framework  <br/> |O serviços WCF é um **recurso** instalado como um recurso do Windows, no **Gerenciador de servidores**, sem downloads necessários. <br/> • Você precisa certificar-se de que, quando instalar esse recurso, ou se ele já estiver instalado e você estiver verificando-o, se a opção de **ativação http** também está marcada e instalada, da seguinte maneira: <br/> ![Captura de tela mostrando a opção de ativação HTTP nos recursos do .NET Framework 4,5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Não se preocupe se você receber um pop-up adicional, dizendo que outras coisas precisam ser instaladas para que a ativação http seja instalada. Isso é normal, clique em OK e vá em frente. Se você não receber esse pop-up, vamos supor que esses itens já estejam instalados e vá em frente.  <br/> Normalmente, o Microsoft .NET Framework é instalado quando o Windows Server 2012 R2 ou o Windows Server 2016 estão instalados. O Skype for Business Server funciona com as seguintes versões do Microsoft .NET Framework:  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (para o Skype for Business Server CU 5 ou versões posteriores)  <br/> • .NET 4.7.2 (para o Skype for Business Server CU 6 ou versões posteriores)  <br/>  O .NET Framework 3,5 provavelmente será instalado por padrão em sua máquina Windows Server 2008 R2 (definitivamente, verifique se você está antes de atualizar), mas na verdade não estará em seus servidores Windows Server 2012/Windows Server 2012 R2 (para novas instalações). Para adicioná-lo ao, você precisará de acesso à sua unidade de instalação ou mídia (o local de onde o Windows Server foi instalado ou onde os arquivos de instalação estão agora). Em seguida, vá em frente e instale-o como um recurso do Gerenciador do servidor e aponte para a mídia de instalação (especificamente a pasta **\sources\sxs** ), quando solicitado, e continue a instalá-lo. <br/> |
|Media Foundation  <br/> |Para o Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado com o Microsoft Media Foundation.  <br/> Todos os servidores front-end e servidores Standard Edition usados para conferência exigem o tempo de execução do Windows Media Format para executar os arquivos de áudio do Windows Media (. WMA) que os aplicativos de estacionamento de chamada, anúncio e grupo de resposta tocam para anúncios e música.  <br/> |
|Windows Identity Foundation  <br/> |Precisamos do Windows Identity Foundation 3,5 para dar suporte a cenários de autenticação de servidor para servidor para o Skype for Business Server 2015.  <br/> • Para o Windows Server 2012 e o Windows Server 2012 R2, não é necessário baixar nada. Abra o **Gerenciador do servidor**e vá para o assistente de adição de **funções e recursos**. O **Windows Identity Foundation 3,5** está listado na seção **recursos** . Se estiver marcada, você está em boas condições. Caso contrário, selecione-a e clique em avançar para acessar o botão **instalar** . <br/> |
|Ferramentas de administração de servidor remoto  <br/> |Ferramentas de administração de funções: AD DS e ferramentas AD LDS  <br/> |
   
 **Servidores front-end e servidor Standard Edition também precisam de:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Serviços de Informações da Internet (IIS)  <br/> |O IIS é necessário em todos os servidores front-end, bem como em todos os servidores Standard Edition, com os seguintes módulos selecionados:  <br/> • Recursos HTTP comuns: documento padrão, erros HTTP, conteúdo estático  <br/> • Integridade e diagnóstico: log HTTP, ferramentas de log, rastreamento  <br/> • Desempenho: compactação de conteúdo estático, compactação de conteúdo dinâmico  <br/> • Segurança: filtragem de solicitações, autenticação de mapeamento de certificado de cliente, autenticação do Windows  <br/> • Desenvolvimento de aplicativos: extensibilidade .NET 3,5, .NET Extensibility 4,5, ASP.NET 3,5, ASP.NET 4,5, extensões ISAPI, filtros ISAPI  <br/> • Ferramentas de gerenciamento: console de gerenciamento do IIS, scripts e ferramentas de gerenciamento do IIS  <br/> Também deveremos observar que o acesso anônimo também é necessário, mas você obtém isso ao instalar o IIS, portanto, você não tem um local para selecioná-lo na lista.  <br/> |
|Tempo de Execução do Windows Media Format  <br/> | Para o Windows Server 2016, o Windows Server 2012 e o Windows Server 2012 R2, você precisará instalar o recurso **Media Foundation** no **Gerenciador do servidor**. Agora, você pode iniciar a instalação do Skype for Business Server 2015 sem esse, mas você será solicitado a instalá-lo e, em seguida, reinicializar o servidor, antes da continuação da instalação do Skype for Business Server 2015. Melhor fazer isso antecipadamente. <br/> |
|Silverlight  <br/> |Você pode instalar a versão mais recente do Silverlight neste [link](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Você também pode precisar habilitar a pesquisa no diretório se estiver usando um balanceador de carga. Caso contrário, uma página em branco carregará o balanceador de carga pode considerar uma falha. 

Para ajudá-lo, aqui está um exemplo de script do PowerShell que você pode executar para automatizar isso:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> O comando procura arquivos de origem em uma ordem específica. Se você estiver online, o comando acessa o Windows Update. No entanto, se você estiver offline, precisará certificar-se de que os arquivos de origem estão disponíveis para o comando. Para obter mais informações sobre como usar o PowerShell para instalar funções e recursos, confira [instalar ou desinstalar funções, serviços de função ou recursos](https://technet.microsoft.com/library/hh831809.aspx) não se esqueça de executar o Windows Update novamente depois de instalar os pré-requisitos, mesmo que você use o comando do PowerShell.

 **Os diretores também precisam de:**
  
IIS, com os seguintes módulos selecionados:
  
- Recursos HTTP Comuns
    
  - Documento padrão
    
  - Erros HTTP
    
  - Conteúdo Estático
    
- Manutenção e diagnóstico
    
  - Log HTTP
    
  - Ferramentas de log
    
  - Rastreia
    
- Desempenho
    
  - Compactação de conteúdo estático
    
- Segurança
    
  - Filtragem de Solicitações
    
  - Autenticação de mapeamento de certificado de cliente
    
  - Autenticação do Windows
    
- Desenvolvimento de aplicativo
    
  - Extensibilidade do .NET 3,5
    
  - Extensibilidade do .NET 4.5
    
  - ASP.NET 3,5
    
  - ASP.NET 4,5
    
  - Extensão ISAPI
    
  - Filtros ISAPI
    
(Se você estiver se perguntando, é o mesmo conjunto de módulos que os servidores front-end e Standard Edition, com a compactação de conteúdo dinâmico e as ferramentas de gerenciamento saíram.)
  
E temos também um código do PowerShell abaixo:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Os servidores de chat persistente também precisam de:**
  
O enfileiramento de mensagens, também chamado de MSMQ. É um componente do Windows Server e você pode instalá-lo na seção recursos no Gerenciador do servidor. Se você quiser ler mais sobre isso, confira [Instalando e gerenciando o enfileiramento de mensagens](https://technet.microsoft.com/library/cc771474.aspx).
  
 **Últimas opiniões:**
  
Não instale nenhum software cliente do Microsoft Internet Security and Acceleration (ISA) Server ou qualquer outro software do LSP (provedor de serviços em camadas) do Winsock (qualquer software de inspeção de rede antivírus ou firewall de terceiros será incluído aqui) em qualquer um dos servidores front-end ou servidores de mediação autônomos. Um desempenho de tráfego de mídia ruim é visto quando o software é instalado.
  

