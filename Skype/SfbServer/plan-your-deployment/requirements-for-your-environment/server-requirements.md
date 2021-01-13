---
title: Requisitos de servidor para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: prepare seus servidores do Skype for Business Server 2015 com este tópico. Hardware, SO, bancos de dados, software, todos os requisitos e recomendações do sistema estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas do farm de servidores.'
ms.openlocfilehash: b1e7e37e46d0f3f547ed843ce2510d8445a34267
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832071"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisitos de servidor para o Skype for Business Server 2015
 
**Resumo:** Prepare seus servidores do Skype for Business Server 2015 com este tópico. Hardware, SO, bancos de dados, software, todos os requisitos e recomendações do sistema estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas do farm de servidores.

Se você estiver procurando requisitos ambientais, como Active Directory, DNS ou certificados, você pode verificar os requisitos de ambiente para o documento do [Skype for Business Server 2015.](environmental-requirements.md)
  
Como você poderia esperar, há algumas preparações a fazer antes de começar a implantar o Skype for Business Server 2015. Este artigo o acompanhará durante o planejamento do seguinte:
  
- [Hardware para o Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemas operacionais para o Skype for Business Server 2015](server-requirements.md#OS)
  
- [Bancos de dados back-end que funcionarão com o Skype for Business Server 2015](server-requirements.md#DBs)
  
- [Software que deve ser instalado antes de uma implantação do Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware para o Skype for Business Server 2015
<a name="Hardware"> </a>

Agora que sua topologia está inocada (e se não tiver, você pode conferir o tópico Noções básicas de topologia do [Skype for Business Server 2015),](../../plan-your-deployment/topology-basics/topology-basics.md) é hora de pensar nos servidores. Os servidores do Skype for Business Server 2015 exigirão hardware de 64 bits. Nossas recomendações para hardware estão abaixo. Esses não são requisitos, mas refletem os requisitos necessários para o desempenho ideal. Temos uma documentação de planejamento de capacidade que o ajudará a determinar se você precisa de mais do que isso, dependendo de suas circunstâncias.
  
Hardware recomendado para servidores front-end, servidores back-end, servidores Standard Edition e servidores de chat persistente:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de 64 bits, hex-core, 2,26 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para funções do Skype for Business Server 2015.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DAS:  <br/> • 8 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre (dois dos discos usando RAID 1 e 6 usando RAID 10).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho semelhante a 8 unidades de disco mecânico de 10.000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede de porta dupla, 1 Gbps ou superior (dois adaptadores de rede podem ser usados, mas eles precisam ser em equipe com um único endereço MAC e um único endereço IP).  <br/> As configurações dual ou  multi-homed não são suportadas para Servidores Front-End, Servidores Back-End, servidores Standard Edition e Servidores de Chat Persistente. <br/> Desde que eles não sejam expostos ao sistema operacional e sejam usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento fora de banda, como DRAC ou ILO. Este cenário não constitui um servidor multi-homed e é suportado.  <br/> |
   
Hardware recomendado para Servidores de Borda, Servidores de Mediação Autônomos, Servidores de Interop de Vídeo e Diretores:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de 64 bits, quad-core, 2.26 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para funções do Skype for Business Server 2015.  <br/> |
|Memória  <br/> |16 gigabytes.  <br/> |
|Disco  <br/> |UMA DAS:  <br/> • 4 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre em disco (os discos devem estar em uma configuração raid 1 de 2x).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho semelhante a 4 unidades de disco mecânico de 10.000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede de porta dupla, 1 Gbps ou superior (dois adaptadores de rede podem ser usados, mas eles precisam ser em equipe com um único endereço MAC e um único endereço IP).  <br/> As configurações dual ou multi-homed não **são** suportadas para Servidores de Interop de Vídeo e Diretores. <br/> Os servidores de borda exigirão duas interfaces de rede que são adaptadores de rede de porta dupla, 1 Gbps ou superior (ou dois adaptadores de rede emparelhados, para um total de quatro, cada par sendo emparelhado com um único endereço MAC e um único endereço IP, com um total de dois pares).  <br/> Em Servidores de Mediação autônomos, há suporte para a instalação de NICs (placas de interface de rede) adicionais para permitir a configuração de um endereço IP PSTN específico.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemas operacionais para o Skype for Business Server 2015
<a name="OS"> </a>

Depois de ter o hardware instalado, você precisará instalar os sistemas operacionais .. Este é o sistema operacional que permitirá que você instale e use com êxito o Skype for Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (você precisa da Atualização Cumulativa 9 ou posterior do Skype for Business). <br/> |Windows Server 2016 (você precisa da Atualização Cumulativa 5 ou posterior do Skype for Business. Para obter mais informações, [consulte KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Sistema operacional Windows Server 2012 R2 Datacenter com todas as atualizações necessárias instaladas.  <br/> |Sistema operacional Windows Server 2012 R2 Standard com todas as atualizações necessárias instaladas.  <br/> |
|Sistema operacional Windows Server 2012 Datacenter com todas as atualizações necessárias instaladas.  <br/> |Sistema operacional Windows Server 2012 Standard com todas as atualizações necessárias instaladas.  <br/> |
   
Se não estiver nessa lista, ela não funcionará corretamente. Não tente novas instalações do Skype for Business Server 2015.

> [!NOTE]
> A atualização local do sistema operacional não é suportada com o Lync Server 2013. Você deve implantar um pool separado e migrar usuários para o novo pool com um sistema operacional diferente. Todos os servidores em um pool devem ter a mesma versão do sistema operacional.
  
> [!NOTE]
> Você deve ter notado que o Windows Server 2008 R2 não está nessa lista. Isso porque recomendamos o Windows Server 2012 R2 para todos os novos servidores a serem usados para o SFB. Você só deve usar o Windows Server 2008 R2 quando já tiver servidores existentes com o Lync Server 2013 instalado, e pretende fazer uma atualização in-locada deles. O Windows Server 2008 R2 atingiu o final do ciclo de vida do suporte base em 13/01/2015 e chegará ao fim do ciclo de vida de suporte em 14/01/2020.
  
Além do service pack mais recente, você vai querer garantir que as seguintes atualizações sejam instaladas onde for relevante para você:
  
- Para o Windows Server 2012, o artigo 2858668 da KB deve ser instalado antes de uma atualização. [Get it here](https://support.microsoft.com/kb/2858668/).
    
- Se você tiver o Windows Server 2012 R2, instale o artigo 2982006 da KB antes de atualizar. [Ele foi encontrado aqui.](https://support.microsoft.com/kb/2982006/)
    
- Se você estiver atualizando em uma caixa do Windows Server 2008 R2 (consulte a Observação acima), instale primeiro o artigo 2533623 da base de dados de base. [Está neste link.](https://support.microsoft.com/kb/2533623/)
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Bancos de dados back-end que funcionarão com o Skype for Business Server 2015
<a name="DBs"> </a>


Ao instalar o Skype for Business Server 2015 Standard Edition, você também terá o SQL Server 2014 Express (edição de 64 bits) instalado automaticamente.
  
O Skype for Business Server 2015 Enterprise Edition é um pouco mais complicado, mas a lista com suporte está abaixo (tudo é edição de 64 bits, você observará, não use edições de 32 bits):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (edição de 64 bits), recomendamos a execução com o service pack mais recente. <br/> |Microsoft SQL Server 2017 Enterprise (edição de 64 bits), recomendamos a execução com o service pack mais recente. <br/> |Microsoft SQL Server 2016 Enterprise (edição de 64 bits) com Service Pack 1 ou posterior, e você deve executar com a Atualização Cumulativa 7 ou posterior do Skype for Business (baixe a Atualização[Cumulativa](https://support.microsoft.com/help/3061064)do Skype for Business).  <br/> |Microsoft SQL Server 2014 Enterprise (edição de 64 bits) e você deve executar com a Atualização Cumulativa 6 ou posterior ( baixar a Atualização[Cumulativa 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (edição de 64 bits), e recomendamos a execução com o service pack mais recente.  <br/> |
|Microsoft SQL Server 2019 Standard (edição de 64 bits), e recomendamos a execução com o service pack mais recente. <br/> |Microsoft SQL Server 2017 Standard (edição de 64 bits), e recomendamos a execução com o service pack mais recente. <br/> |Microsoft SQL Server 2016 Standard (edição de 64 bits) com Service Pack 1 ou posterior, e você deve executar com a Atualização Cumulativa 7 ou posterior do Skype for Business (baixe a Atualização[Cumulativa](https://support.microsoft.com/help/3061064)do Skype for Business).  <br/> |Microsoft SQL Server 2014 Standard (edição de 64 bits) e você deve executar com a Atualização Cumulativa 6 ou posterior (baixar a Atualização[Cumulativa 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edição de 64 bits), e recomendamos a execução com o service pack mais recente.  <br/> |
   
Se você não vir a edição do SQL Server que deseja usar listada aqui, não poderá usá-la.
  
- Você também precisará instalar o SQL Server Reporting Services para a função de Monitoring Server.
- Para um back-end SQL bem conectado, a conexão com o front-end do Skype for Business deve ser local e não em um link de baixa velocidade. 
- Não há suporte para o compartilhamento de back-ends sql entre dois ou mais pools.

### <a name="microsoft-exchange-storage"></a>Armazenamento do Microsoft Exchange
Conteúdo de reuniões, como apresentações em PowerPoint, são arquivados como anexos. Se você quiser armazenar dados de arquivo morto do Skype for Business com dados de conformidade do Exchange, deverá usar o Exchange para sua implantação do Exchange e garantir que o tamanho máximo de armazenamento suporte o armazenamento dos arquivos de conteúdo de reunião. Você deve implantar o Exchange antes de implantar e ativar o arquivamento usando a opção de integração do Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisitos de hardware e software para arquivamento no Skype for Business Server 2015
  
O arquivamento não é uma função de servidor definida, não é necessário instalar um servidor separado para arquivamento. Os Agentes de Coleta de Dados Unificados são instalados e ativados automaticamente em cada pool de Front-End Enterprise Edition e em cada Servidor Standard Edition. Você precisará habilitar e publicar sua topologia de arquivamento usando o Construtor de Topologias.
    
O arquivamento usa o armazenamento de arquivos do Skype for Business Server para armazenamento temporário de arquivos de conteúdo de reunião, portanto, você não configura um armazenamento de arquivos separado para arquivamento.
    
O En fila de mensagens da Microsoft não é necessário.
    
Você precisará configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui escolher o exchange ou o armazenamento de arquivamento usando o SQL Server.   Os requisitos de infraestrutura de arquivamento do Skype for Business Server são os mesmos da implantação do Skype for Business Server. Para obter detalhes, consulte [Requisitos para seu ambiente do Skype for Business.](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 
  
> [!NOTE]
> Para dar suporte a usuários que não estão em servidores Exchange ou se você não quiser usar a opção de integração do Microsoft Exchange, implante o armazenamento de arquivamento usando um banco de dados do SQL Server de 64 bits. 
    
Você deve configurar as plataformas do SQL Server antes de implantar e habilenciar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Também é possível criar o banco de dados posteriormente, incluído como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte a [documentação do SQL Server.](https://go.microsoft.com/fwlink/p/?linkID=129045)
    
O aumento da carga para arquivamento pode ser significativo. Portanto, você deve garantir que o espaço em disco seja adequado para servidores front-end nos quais o arquivamento está habilitado.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Sql Mirroring, SQL Clustering e SQL Always On

Você é capaz de usar o espelhamento SQL ou clustering SQL com o Skype for Business Server 2015, ele é suportado. SQL Mirroring's set up through the Skype for Business Server Topology Builder. Se você pretende configurar o CLUSTERING SQL, isso é feito no SQL Server.
  
Certifique-se de que você tenha uma configuração ativa/passiva para CLUSTERING SQL, pois é isso que tem suporte. Não compartilhe o nó passivo com nenhuma outra instância SQL.
  
Você pode ter o seguinte para clustering de failover:
  
Dois nós:
  
- Microsoft SQL Server 2019 Standard (edição de 64 bits), e recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2017 Standard (edição de 64 bits), e recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2016 Standard (edição de 64 bits) com Service Pack 1 ou posterior. Recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2014 Standard (edição de 64 bits), recomendamos a execução com o service pack mais recente.
    
-  Microsoft SQL Server 2012 Standard (edição de 64 bits), e recomendamos a execução com o service pack mais recente.

Dezesseis nós:

- Microsoft SQL Server 2019 Enterprise (edição de 64 bits), recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2017 Enterprise (edição de 64 bits), recomendamos a execução com o service pack mais recente.

- Microsoft SQL Server 2016 Enterprise (edição de 64 bits) com Service Pack 1 ou posterior. Recomendamos a execução com o service pack mais recente.
  
- Microsoft SQL Server 2014 Enterprise (edição de 64 bits), e recomendamos a execução com o service pack mais recente.
    
- Microsoft SQL Server 2012 Enterprise (edição de 64 bits), e recomendamos a execução com o service pack mais recente.

> [!IMPORTANT]
> Para atualizar, queremos que você garanta que em seus Servidores #A0 você tenha pelo menos o SQL Server 2012 SP1 instalado antes da atualização. [Aqui está um link para](https://www.microsoft.com/download/details.aspx?id=35575) o SP1 se você quiser baixá-lo imediatamente.
  
Se você precisar ler mais sobre Espelhamento SQL, temos um tópico de alta disponibilidade do Servidor #A0 no Skype for Business Server 2015. Configurar o cluster do SQL Server para o Skype for Business Server 2015 tem as etapas para preparar o clustering. Também há outros links sobre clustering de failover para SQL, [para 2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)e [2008.](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)
  
> [!NOTE]
> Uma novidade na versão 2015 é o suporte ao SQL Always On. Há suporte, e você pode ler mais sobre isso no tópico De alta disponibilidade do Servidor back-end no [Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

> [!NOTE]
> O espelhamento sql está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e métodos de cluster de failover SQL são preferenciais com o Skype for Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software que deve ser instalado antes de uma implantação do Skype for Business Server 2015
<a name="Software"> </a>

Há algumas coisas que você precisará instalar ou configurar para qualquer servidor que executa o Skype for Business Server 2015, e elas estão listadas abaixo. Depois disso, há requisitos adicionais para funções de servidor específicas.

  
 **Todos os servidores:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos os servidores do Skype for Business Server precisam do Windows PowerShell 3.0 instalado.  <br/> • Se você estiver fazendo a instalação no Windows Server 2012 ou no Windows Server 2012 R2, você está definido, pois ele já está lá.  <br/> • Se você estiver fazendo uma atualização no Windows Server 2008 R2, poderá baixar o [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) para baixá-lo. <br/> **Dica:** Depois de ter o PowerShell correto, confirme se é BuildVersion 6.2.9200.0 ou posterior, indo para o prompt do PowerShell e `$PSVersionTable` digitando. Isso deve trazer as informações de que você precisa.  <br/> |
|Microsoft .NET Framework  <br/> |Os serviços WCF são **um** Recurso instalado como um recurso do Windows, em **Gerenciador do Servidor,** sem a necessidade de downloads. <br/> • Você precisa verificar, quando instalar esse recurso, ou se ele já estiver instalado e estiver verificando se a opção de Ativação **HTTP** também está marcada e instalada, da seguinte forma: <br/> ![Captura de tela mostrando a opção de ativação HTTP nos Recursos do .NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) Não se preocupe se você receber um pop-up adicional dizendo que algumas outras coisas precisam ser instaladas para a ativação HTTP ser instalada. Isso é normal, clique em OK e vá em frente. Se você não receber esse pop-up, suponha que essas coisas já estão instaladas e vá em frente.  <br/> O Microsoft .NET Framework geralmente é instalado quando o Windows Server 2012 R2 ou o Windows Server 2016 são instalados. O Skype for Business Server funciona com as seguintes versões do Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (para o Skype for Business Server CU 5 ou versões posteriores)  <br/> • .NET 4.7.2 (para o Skype for Business Server CU 6 ou versões posteriores)  <br/>  • .NET 4.8 (para o Skype for Business Server CU 9 ou versões posteriores) <br/>  O .NET Framework 3.5 provavelmente será instalado por padrão em seu computador Windows Server 2008 R2 (verifique com certeza antes de atualizar), mas ele não estará nos servidores Windows Server 2012/Windows Server 2012 R2 (para novas instalações). Para adicioná-lo, você precisará de acesso à sua unidade de instalação ou mídia (o local onde o Windows Server foi instalado ou onde os arquivos de instalação estão agora). Em seguida, instale-o como um recurso do Gerenciador do Servidor e aponte para a mídia de instalação (especificamente a pasta **\sources\sxs)** quando solicitado e continue a instalá-la. <br/> |
|Media Foundation  <br/> |Para Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, o Windows Media Format Runtime é instalado com o Microsoft Media Foundation.  <br/> Todos os servidores Front End e Standard Edition usados para conferência exigem que o Windows Media Format Runtime execute os arquivos do Windows Media Audio (.wma) que os aplicativos Estacionamento de Chamada, Comunicado e Grupo de Resposta reproduzem para comunicados e música.  <br/> |
|Windows Identity Foundation  <br/> |Precisamos do Windows Identity Foundation 3.5 para dar suporte a cenários de autenticação servidor para servidor do Skype for Business Server 2015.  <br/> • Para o Windows Server 2012 e o Windows Server 2012 R2, não é necessário baixar nada. Abra **o Gerenciador do** Servidor e vá para o Assistente para Adicionar Funções e **Recursos.** **O Windows Identity Foundation 3.5** está listado na **seção Recursos.** Se ela estiver marcada, você está bem. Caso contrário, selecione-o e clique em Próximo para alcançar o **botão** Instalar. <br/> |
|Ferramentas de Administração de Servidor Remoto  <br/> |Ferramentas de Administração de Função: ferramentas do AD DS e do AD LDS  <br/> |
   
 **Os Servidores Front End e o servidor Standard Edition também precisam:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Serviços de Informações da Internet (IIS)  <br/> |O IIS é necessário em todos os Servidores Front-End, bem como em todos os servidores Standard Edition, com os seguintes módulos selecionados:  <br/> • Recursos HTTP comuns: Documento Padrão, Erros HTTP, Conteúdo Estático  <br/> • Health and Diagnostics: HTTP Logging, Logging Tools, Tracing  <br/> • Desempenho: Compactação de conteúdo estático, compactação de conteúdo dinâmico  <br/> • Segurança: Filtragem de Solicitação, Autenticação de Mapeamento de Certificado de Cliente, Autenticação do Windows  <br/> • Desenvolvimento de aplicativos: Extensibilidade .NET 3.5, Extensibilidade .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, Extensões ISAPI, Filtros ISAPI  <br/> • Ferramentas de Gerenciamento: Console de Gerenciamento do IIS, Scripts e Ferramentas de Gerenciamento do IIS  <br/> Também devemos observar que o Acesso Anônimo também é necessário, mas você o tem ao instalar o IIS, para que você não tenha um local para selecioná-lo na lista.  <br/> |
|Tempo de Execução do Windows Media Format  <br/> | Para Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, você precisará instalar o recurso **Media Foundation** no Gerenciador do **Servidor.** Agora, você pode realmente iniciar a instalação do Skype for Business Server 2015 sem esta, mas será solicitado a instalá-la e reiniciar o servidor, antes que a instalação do Skype for Business Server 2015 continue. É melhor fazer isso com antecedência. <br/> |
|Silverlight  <br/> |Você pode instalar a versão mais recente do Silverlight [neste link.](https://www.microsoft.com/silverlight/)  <br/> |
   
> [!NOTE] 
> Talvez também seja necessário habilitar a Navegação no Diretório se você estiver usando um balanceador de carga. Caso contrário, uma página em branco carregará a qual o balanceador de carga poderá considerar uma falha. 

Para ajudá-lo, veja um exemplo de script do PowerShell que você pode executar para automatizar o processo:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> O comando procura por arquivos de origem em uma ordem específica. Se você estiver online, o comando acessará o Windows Update. No entanto, se você estiver offline, precisará se certificar de que os arquivos de origem estão disponíveis para o comando. Para obter mais informações sobre como usar o PowerShell para instalar funções e recursos, consulte Instalar ou Desinstalar [Funções,](https://technet.microsoft.com/library/hh831809.aspx) Serviços de Função ou Recursos. Não se esqueça de executar o Windows Update novamente depois de instalar os pré-requisitos, mesmo se você usar o comando do PowerShell.

 **Os Diretores também precisam:**
  
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
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - Extensão ISAPI
    
  - Filtros ISAPI
    
(Se você estiver se perguntando, é o mesmo módulo definido como os Servidores front-end e servidores Standard Edition, com as Ferramentas de Gerenciamento e Compactação de Conteúdo Dinâmico deixadas de fora.)
  
E temos alguns códigos do PowerShell abaixo para isso também:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Os Servidores de Chat Persistente também precisam:**
  
En fila de mensagens, que também é chamado de MSMQ. É um componente do Windows Server e você pode instalá-lo na seção Recursos no Gerenciador do Servidor. Se você quiser ler mais sobre isso, confira [Instalando e gerenciando](https://technet.microsoft.com/library/cc771474.aspx)o en fila de mensagens.
  
 **Últimas ideias:**
  
Não instale nenhum software cliente do Microsoft Internet Security and Acceleration (ISA) Server ou qualquer outro software LSP (Provedor de Serviços em Camadas) winsock (qualquer firewall de terceiros ou software de inspeção de rede antivírus seria incluído aqui) em qualquer um dos servidores front-end ou servidores de mediação autônomos. O desempenho ruim do tráfego de mídia foi visto quando esse software é instalado.
  

