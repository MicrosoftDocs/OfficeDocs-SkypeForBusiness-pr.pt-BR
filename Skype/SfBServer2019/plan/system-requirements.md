---
title: Requisitos do sistema para o Skype for Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 'Resumo: Prepare seus servidores do Skype for Business Server 2019 e a infraestrutura de domínio com este tópico. Hardware, sistema operacional, bancos de dados, software, todos os requisitos de sistema e recomendações, juntamente com o DNS de certificado, o compartilhamento de arquivos e as informações do Active Directory, estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas do seu farm de servidores.'
ms.openlocfilehash: b173097377c100fcb03b07d7a502e1e6c096608f
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925323"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Requisitos do sistema para o Skype for Business Server 2019
 
**Resumo:** Prepare-se para instalar o Skype for Business Server 2019 com este tópico. Hardware, sistema operacional, software, bancos de dados, certificados, Diretory ativos, DNS e fileshares são abordados aqui. Todos os requisitos de sistema e recomendações estão aqui para ajudar a garantir uma instalação e uma implantação bem-sucedidas do seu farm de servidores.
  
Como você pode esperar, há alguns preparativos a fazer antes de começar a implantar o Skype for Business Server 2019. Este artigo explica como deve ser o planejamento dos seguintes itens:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Sistemas operacionais](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Bancos de dados SQL back end](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [DNS (Sistema de Nomes de Domínio)](system-requirements.md#DNS)
  
- [Certificados](system-requirements.md#Certs)
  
- [Compartilhamento de arquivos](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware para o Skype for Business Server 2019
<a name="Hardware"> </a>

Depois que a sua topologia ficar desativada (e se você não fizer isso, poderá conferir o tópico [noções básicas de topologia para o tópico do Skype for Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ), é hora de pensar nos servidores. Os servidores do Skype for Business Server 2019 exigem hardware de 64 bits. Nossas recomendações para hardware estão listadas abaixo. Estes são os requisitos, mas refletem os requisitos necessários para o melhor desempenho. Temos uma documentação de planejamento de capacidade que ajudará você a determinar se precisa de mais alguma coisa, dependendo das suas circunstâncias.
  
Hardware recomendado para servidores Standard Edition:

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior.  <br/> Os processadores Intel Itanium não são compatíveis com as funções do Skype for Business Server 2019.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DESTAS OPÇÕES:  <br/> • 8 ou mais 10000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco (dois discos usando RAID 1 e 6 usando RAID 10).  <br/> OR  <br/> • Os discos de estado sólido (SSDs) podem fornecer o mesmo espaço livre e desempenho semelhante para os drives de disco mecânico 8 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> **Não** há suporte para configurações de duas ou várias bases para servidores front-end, servidores back-end e servidores Standard Edition. <br/> Desde que não estejam expostos ao sistema operacional e estejam sendo usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento fora de banda, como o DRAC ou o ILO. Esse cenário não constitui um servidor multihomed e tem suporte.  <br/> |


Hardware recomendado para servidores front-end e servidores back-end:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior. <br/> Os processadores Intel Itanium não são compatíveis com as funções do Skype for Business Server 2019.  <br/> |
|Memória  <br/> |64 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DESTAS OPÇÕES:  <br/> • 8 ou mais 10000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco (dois discos usando RAID 1 e 6 usando RAID 10).  <br/> OR  <br/> • Os discos de estado sólido (SSDs) podem fornecer o mesmo espaço livre e desempenho semelhante para os drives de disco mecânico 8 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> **Não** há suporte para configurações de duas ou várias bases para servidores front-end, servidores back-end e servidores Standard Edition. <br/> Desde que não estejam expostos ao sistema operacional e estejam sendo usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento fora de banda, como o DRAC ou o ILO. Esse cenário não constitui um servidor multihomed e tem suporte.  <br/> |
   
Hardware recomendado para servidores de borda, servidores de mediação autônomos e directors:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior.  <br/> Os processadores Intel Itanium não são compatíveis com as funções do Skype for Business Server 2019.  <br/> |
|Memória  <br/> |32 gigabytes.  <br/> |
|Disco  <br/> |UMA DESTAS OPÇÕES:  <br/> • 4 ou mais 10000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco (os discos devem estar em uma configuração RAID 1 2x).  <br/> OR  <br/> • Os discos de estado sólido (SSDs) podem fornecer o mesmo espaço livre e desempenho semelhante para os drives de disco mecânico 4 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> **Não** há suporte para configurações de duas ou várias bases para servidores e diretores de interoperabilidade de vídeo. <br/> Servidores de borda exigem duas interfaces de rede que são adaptadores de rede dual-port, 1 Gbps ou superior (ou dois adaptador de rede pareados, com um total de quatro, sendo que cada par está combinado com um único endereço MAC e um único endereço IP).  <br/> Em servidores de mediação autônomos, a instalação de placas de interface de rede adicionais (NICs) para permitir a configuração de um endereço IP PSTN específico tem suporte.  <br/> |


> [!NOTE]
> Seja qual for a função do servidor, também recomendamos as seguintes configurações de hardware para o Skype for Business Server 2019 (isso pode variar dependendo da marca de hardware que você comprou, portanto, consulte a documentação do fabricante para obter informações específicas):
> - Configuração do BIOS-deve ser definido como plano do NUMA.
> - Habilite o hyperthreading.
> - A configuração da fila RSS deve ser definida como 8 fila.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Sistemas operacionais para o Skype for Business Server 2019
<a name="OS"> </a>

Depois de instalar o hardware, você precisará do sistema operacional de instalação (SO) que permitirá que você instale e use com êxito o Skype for Business Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Qualquer coisa diferente dos sistemas operacionais listados aqui não funcionará corretamente; Não experimente instalar o Skype for Business Server 2019. Por exemplo, a opção de núcleo do servidor não está listada e, portanto, não é suportada.

> [!NOTE]
> 
> Se você estiver instalando o centro de administração do Windows 2019 em seu computador com o Windows Server 2019, ele solicitará que você aguarde uma porta de escuta. Há um liklihood de que você pode escolher a porta 443, mas se a máquina tiver o Skype for Business Server 2019 instalado, ou se o Skype for Business Server 2019 instalado nele, você deverá escolher um número de porta diferente.
> 
>Por que esse é o caso? Se o centro de administração do Windows 2019 estiver em execução na porta 443, você não poderá se conectar ao servidor usando o painel de controle do Skype for Business, nem poderá se conectar a qualquer serviço Web interno executado no servidor (serviço Web de catálogo de endereços , Serviço de descoberta automática, serviço webticket, etc.  Na verdade, você não será capaz de se conectar a qualquer URL de serviço Web interno. Escolha uma porta diferente, caso você precise ou deseje colocar o centro de administração do Windows 2019 em um servidor com o Skype for Business Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software que deve ser instalado antes de uma implantação do Skype for Business Server 2019
<a name="Software"> </a>

Há algumas coisas que você precisará instalar ou configurar para qualquer servidor que esteja executando o Skype for Business Server 2019. Elas são listadas abaixo, seguidas pelos requisitos adicionais para funções específicas do servidor.
  
 **Todos os servidores:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos os servidores do Skype for Business precisam ter o Windows PowerShell 3,0 instalado.  <br/> • Isso deve ser instalado por padrão com o Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Os serviços do WCF são um **recurso** que é instalado como um recurso do Windows, no **Gerenciador de servidores**, inicialmente não há necessidade de downloads. <br/> • Você precisa ter certeza de que, ao instalar esse recurso, ou se ele já estiver instalado e você estiver verificando, se a opção de **ativação http** também está marcada e instalada, assim: <br/> ![Captura de tela mostrando a opção de ativação HTTP nos recursos do .NET Framework 4,5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Não se preocupe se você tiver uma janela pop up adicional dizendo que outras devem ser instaladas para que a Ativação HTTP seja instalada. Isso é normal; clique em OK e vá em frente. Se você não receber esse pop-up, poderá pressupor que essas coisas já estejam instaladas e prosseguir.  <br/> O Microsoft .NET Framework geralmente é instalado quando o Windows Server 2016 está instalado. No entanto, o Skype for Business Server requer o Microsoft .NET Framework 4,7, portanto, é provável que você precise atualizá-lo. Você pode encontrar a atualização [aqui](https://support.microsoft.com/en-us/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Para o Windows Server 2016, o tempo de execução do Windows Media Format é instalado com o Microsoft Media Foundation.  <br/> Todos os servidores de front-end e servidores de edição padrão usados para a conferência exigem o tempo de execução do Windows Media Format para executar os arquivos de áudio do Windows Media (. WMA) que os aplicativos do parque, do anúncio e do grupo de resposta da chamada são reproduzidos para anúncios e músicas.  <br/> |
|Windows Identity Foundation  <br/> |Precisamos do Windows Identity Foundation 3,5 para dar suporte a cenários de autenticação de servidor para servidor para o Skype for Business Server 2019.  <br/> • Para Windows Server 2016, não é necessário baixar nada. Abra o **Gerenciador do Servidor** e vá para o **Assistente de Adição de Funções e Recursos**. O **Windows Identity Foundation 3.5** está listado na seção **Recursos**. Se estiver selecionado, você está bom. Caso contrário, selecione-o e clique em **Avançar** para acessar o botão **instalar** . <br/> |
|AD DS and AD LDS ToolsFerramentas de Administração de Servidor Remoto  <br/> |Ferramentas de Administração de Funções: ferramentas do AD DS e AD LDS  <br/> |
   
 **Os servidores front-end e o servidor Standard Edition também precisam ter:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|IIS (Serviços de Informações da Internet)  <br/> |O IIS é necessário em todos os servidores front-end, bem como em todos os servidores de edição padrão, com os seguintes módulos selecionados:  <br/> • Recursos comuns de HTTP: documento padrão, erros de HTTP, conteúdo estático  <br/> • Integridade e diagnóstico: log HTTP, ferramentas de log, rastreamento  <br/> • Desempenho: compactação de conteúdo estático, compactação de conteúdo dinâmico  <br/> • Segurança: filtragem de solicitações, autenticação de mapeamento de certificado de cliente, autenticação do Windows  <br/> • Desenvolvimento de aplicativos: extensibilidade do .NET 3,5, extensibilidade do .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, extensões ISAPI, filtros ISAPI  <br/> • Ferramentas de gerenciamento: console de gerenciamento do IIS, scripts e ferramentas de gerenciamento do IIS  <br/> Observe que o acesso anônimo também é necessário, mas você obtém isso ao instalar o IIS, portanto, você não tem um local para selecioná-lo na lista.  <br/> |
|Tempo de Execução do Windows Media Format  <br/> | Para o Windows Server 2016, você precisará instalar o recurso **Media Foundation** no **Gerenciador de servidores**. Na verdade, você pode iniciar a instalação do Skype for Business Server 2019 sem isso, mas será solicitado a instalá-la e, em seguida, reinicializar o servidor, antes que a instalação do 2019 do Skype for Business Server continue. É melhor fazê-lo com antecedência. <br/> |
|Silverlight  <br/> |Você pode instalar a versão mais recente do Silverlight [aqui](https://www.microsoft.com/silverlight/).  <br/> |
   
Para ajudar você, separamos esta amostra de script do PowerShell que você pode executar para automatizar esse processo:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bancos de dados back-end que funcionarão com o Skype for Business Server 2019
<a name="DBs"> </a>

Ao instalar o Skype for Business Server 2019 Standard Edition, você terá o SQL Server 2016 Express (64-bit Edition).

O Skype for Business Server 2019 Enterprise Edition exigirá SQL Server completo, conforme indicado abaixo (somente edição de 64 bits; não use as edições de 32 bits):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64-bit Edition), e você deve executar com as atualizações mais recentes.  <br/> |Microsoft SQL Server 2017 (64-bit Edition), e você deve executar com as atualizações mais recentes.  <br/> |
Microsoft SQL Server 2016 (64-bit Edition), e você deve executar com as atualizações mais recentes.|
 |

Se você não vir a edição do SQL Server que deseja usar listada aqui, não poderá usá-la.
  
> [!NOTE]
> Você também precisa instalar o SQL Server Reporting Services para a função de servidor de monitoramento. 
  
### <a name="sql-clustering-and-sql-always-on"></a>Agrupamento do SQL e SQL AlwaysOn

Há suporte para o clustering do SQL com o Skype for Business Server 2019. Se você quiser configurar o agrupamento do SQL, isso é feito no SQL Server.
  
Verifique se você tem uma configuração ativa/passiva para agrupamento do SQL, com suporte. Não compartilhe o nó passivo com nenhuma outra instância do SQL.
  
Você pode ter os seguintes itens para clustering de failover:
  
Dois nós:
  
- Microsoft SQL Server 2019 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente.
- Microsoft SQL Server 2017 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente.
- Microsoft SQL Server 2016 Standard (64-bit Edition), e recomendamos executar com o Service Pack mais recente.

Dezesseis nós:
  
- Microsoft SQL Server 2019 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente.
- Microsoft SQL Server 2017 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente.
- Microsoft SQL Server 2016 Enterprise (64-bit Edition) e recomendamos executar com o Service Pack mais recente.

O SQL sempre ativado tem suporte, e você pode ler mais sobre isso no [servidor back-end de alta disponibilidade no Skype for Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Recomendações de instalação do servidor adicionais:
  
Não instale nenhum software cliente do Microsoft Internet Security and Acceleration (ISA) Server, ou qualquer outro software de provedores de serviços em camadas (LSP) do Winsock (qualquer firewall de terceiros ou software de inspeção de rede antivírus estaria incluído aqui) em qualquer um dos seus servidores front-end ou servidores de mediação autônomos. Um desempenho de tráfego de mídia fraco foi visto quando o software está instalado.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Embora muitos dos dados de configuração para servidores e serviços estejam armazenados no repositório de gerenciamento central do Skype for Business Server 2019, existem algumas coisas ainda armazenadas no Active Directory:
  
|**Objetos do Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensões de esquema  <br/> |Extensões de objetos de usuário  <br/> |
||Extensões para o Skype for Business Server 2015 e Lync Server 2013, para manter a compatibilidade com versões anteriores do suporte  <br/> |
|Dados  <br/> |URI do SIP do usuário e outras configurações de usuário  <br/> |
||Objetos de contato para aplicativos (como o aplicativo grupo de resposta e o aplicativo de assistente de conferência)  <br/> |
||Dados publicados para compatibilidade com versões anteriores  <br/> |
||Um SCP (ponto de controle de serviço) para o repositório de gerenciamento central  <br/> |
||Conta de autenticação Kerberos (um objeto de computador opcional)  <br/> |
   
### <a name="os-for-domain-controllers"></a>OS para controladores de domínio

Os seguintes sistemas operacionais do controlador de domínio podem ser usados:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
O nível funcional do domínio de qualquer domínio no qual você implanta o Skype for Business Server 2019 e o nível funcional da floresta de todas as quais você implanta o Skype for Business Server 2019 em, deve ser um dos seguintes:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
É possível ter controladores de domínio somente leitura nesses ambientes? Não se esqueça de que, desde que haja também controladores de domínio graváveis disponíveis.
  
É importante saber que o Skype for Business Server 2019 não é compatível com domínios de rótulo único. O que são esses domínios? Se você tiver um domínio raiz chamado contoso. local, isso vai funcionar bem. Se você tiver um domínio raiz chamado de local, isso não funcionará, e isso não será compatível como resultado. Um pouco mais sobre isso foi escrito neste [artigo da base de dados de conhecimento](https://support.microsoft.com/kb/300684/en-us).
  
O Skype for Business Server 2019 também não permite a renomeação de domínios. Se você realmente precisa renomear seu domínio, será necessário desinstalar o Skype for Business Server 2019, fazer a renomeação do domínio e, em seguida, reinstalar o Skype for Business Server 2019.
  
Por fim, você pode estar lidando com um domínio com um ambiente de AD DS bloqueado, e isso está bem. Temos mais informações sobre como implantar o Skype for Business Server 2019 em um ambiente de AD DS bloqueado na documentação de implantação.
  
### <a name="ad-topologies"></a>Topologias do AD

As topologias com suporte no Skype for Business Server 2019 são:
  
- Floresta única com domínio único
    
- Floresta única com uma única árvore e vários domínios
    
- Floresta única com várias árvores e namespaces não contíguos
    
- Várias florestas em uma topologia de floresta central
    
- Várias florestas em uma topologia de floresta de recursos
    
- Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
    
- Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Connect
    
Temos diagramas e descrições para ajudá-lo a determinar qual topologia você tem em seu ambiente ou o que talvez seja necessário configurar antes de instalar o Skype for Business Server 2019. Para simplificar, também estamos incluindo uma chave:
  
![O é uma chave para os ícones usados nos diagramas de topologia do Skype for Business](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Floresta única com domínio único

![Diagrama de uma única floresta do Active Directory com um único domínio](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Não fica mais fácil do que isso; é uma floresta de domínio única, uma topologia comum.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Floresta única com uma única árvore e vários domínios

![Um único diagrama de floresta, árvore única e domínios do mutiple](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Esse diagrama mostra uma floresta única, mas ela também tem um ou mais domínios filho (há três deles neste exemplo específico). Portanto, o domínio no qual os usuários são criados pode ser diferente do domínio no qual o Skype for Business Server 2019 é implantado. Por que isso é relevante? É importante lembrar que quando você implanta um pool de front-end do Skype for Business Server, todos os servidores nesse pool precisam estar em um único domínio. Você pode ter administração entre domínios por meio do suporte do Skype for Business Server aos grupos de administradores universais do Windows.
  
No diagrama acima, você pode ver que os usuários de um domínio podem acessar pools do Skype for Business Server do mesmo domínio ou de domínios diferentes, mesmo se esses usuários estiverem em um domínio filho.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Floresta única com várias árvores e namespaces não contíguos

![Um único floresta, várias árvores e diagramas de namespaces de desjunção](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Você pode ter uma topologia semelhante a este diagrama, onde você tem uma floresta, mas dentro dessa floresta há vários domínios, com namespaces de anúncios separados. Nesse caso, este diagrama é uma boa ilustração, porque inclui usuários em três domínios diferentes que acessam o Skype for Business Server 2019. Linhas sólidas indicam que elas estão acessando um pool do Skype for Business Server em seu próprio domínio, enquanto uma linha tracejada indica que elas estão indo para um pool em uma árvore diferente.
  
Como você pode ver, os usuários no mesmo domínio, a mesma árvore ou até mesmo uma árvore diferente podem acessar os pools com êxito.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Várias florestas em uma topologia de floresta central

![Várias florestas em um diagrama de topologia de floresta central](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
O Skype for Business Server 2019 oferece suporte a várias florestas configuradas em uma topologia de floresta central. Se você não tiver certeza de que é o que você tem, a floresta central na topologia usa objetos nele para representar usuários nas outras florestas e hospeda contas de usuário para qualquer usuário da floresta.
  
Como isso funciona? Um produto de sincronização de diretório (como o Forefront Identity Manager ou FIM) gerencia as contas de usuário da sua organização durante a existência. Quando uma conta é criada ou excluída de uma floresta, essa mudança é sincronizada até o contato correspondente na floresta central.
  
Claramente, se a sua infraestrutura de anúncios estiver em vigor, a migração para essa topologia pode não ser fácil, mas se você já estiver lá ou ainda estiver planejando a infraestrutura da floresta, isso pode ser uma boa opção. Você pode centralizar a implantação do Skype for Business Server 2019 em uma única floresta, enquanto os usuários podem pesquisar, comunicar e visualizar a presença de outros usuários em qualquer floresta. Todas as atualizações de contato são feitas automaticamente com o software de sincronização.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business
<a name="BKMK_multipleforestopology"> </a>

![Várias florestas em um diagrama de topologia de floresta de recursos](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Também há suporte para uma topologia de floresta de recursos; é onde uma floresta é dedicada à execução de aplicativos do servidor, como o Microsoft Exchange Server e o Skype for Business Server 2019. Essas florestas de recursos também hospedam uma representação sincronizada de objetos de usuário ativo, mas não contas de usuário habilitadas para logon. Portanto, a floresta de recursos é um ambiente de serviços compartilhados para outras florestas nas quais os objetos de usuários residem, e que têm uma relação de confiança no nível de floresta com a floresta de recursos.
  
Observe que o Exchange Server pode ser implantado na mesma floresta de recursos que o Skype for Business Server ou em uma floresta diferente.
  
Para implantar o Skype for Business Server 2019 nesse tipo de topologia, crie um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas do usuário (se o Microsoft Exchange Server já estiver no ambiente, isso pode ser feito para você). Em seguida, você precisa de uma ferramenta de sincronização de diretório (como Forefront Identity Manager ou FIM) para gerenciar contas de usuário durante o ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Esta topologia é similar à topologia descrita em [Várias florestas em uma topologia de floresta de recursos do Skype for Business](system-requirements.md#BKMK_multipleforestopology).
  
Nessa topologia, há uma ou mais florestas do usuário, e o Skype for Business Server é implantado em uma floresta de recursos dedicada. O Exchange Server pode ser implantado no mesmo local na mesma floresta de recursos ou em uma floresta diferente e configurada para híbrido com o Exchange Online, ou os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais. Não há um diagrama disponível para esta topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Várias florestas em uma topologia de floresta de recursos com Skype for Business Online e Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra duas florestas de anúncios, uma floresta de usuário e uma floresta de recursos. As duas florestas têm uma relação de confiança. Eles são sincronizados com o Office 365 usando o Azure AD Connect. Todos os usuários estão habilitados para o Skype for Business por meio do Office 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Neste cenário há várias florestas locais, com uma topologia de floresta de recursos. Há um relacionamento de total confiança entre as florestas do Active Directory. A ferramenta Azure Active Directory Connect é usada para sincronizar contas entre as florestas de usuários locais e o Office 365.
  
 A organização também tem o Office 365 e usa o [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar suas contas locais com o Office 365. Os usuários habilitados para o Skype for Business são habilitados via Office 365 e Skype for Business online. O Skype for Business Server não é implantado no local.
  
A autenticação de logon único é fornecida por um farm de serviços de Federação do Active Directory localizado na floresta do usuário.
  
Nesse cenário, é possível implantar o Exchange local, o Exchange Online, uma solução híbrida do Exchange ou não ter o Exchange implantado. O diagrama mostra somente o Exchange no Local, mas as outras soluções do Exchange são totalmente aceitas.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Várias florestas em uma topologia de floresta de recursos com o Skype for Business híbrido 
<a name="BKMK_multipleforestopology"> </a>

Nesse cenário, há uma ou mais florestas de usuários locais, e o Skype for Business é implantado em uma floresta de recursos dedicada e está configurado para o modo híbrido com o Skype for Business online. O Exchange Server pode ser implantado no mesmo local na mesma floresta de recursos ou em uma floresta diferente e pode ser configurado para híbrido com o Exchange Online. Como alternativa, os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais.
  
Para obter mais informações, consulte [configurar um ambiente de várias florestas para o Skype for Business híbrido](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Sistema de Nomes de Domínio (DNS)
<a name="DNS"> </a>

O Skype for Business Server 2019 requer o DNS, pelos seguintes motivos:
  
- O DNS permite que o Skype for Business Server 2019 descubra servidores ou pools internos, permitindo comunicações entre servidores.
    
- O DNS permite que máquinas clientes descubram o pool de front-end ou o servidor Standard Edition sendo usado para transações SIP.
    
- Ele associa URLs simples para conferências aos servidores que as hospedam.
    
- O DNS permite que usuários externos e máquinas cliente se conectem a seus servidores de borda ou ao proxy de reverso HTTP para mensagens instantâneas (IM) ou conferência.
    
- Ele permite que dispositivos de comunicação unificada (UC) não estejam registrados descubram o pool de front-end ou o servidor Standard Edition que está executando o serviço Web de atualização de dispositivos para obter atualizações e enviar logs.
    
- O uso do DNS permite que clientes móveis descubram automaticamente os recursos dos serviços Web sem que os usuários tenham que inserir URLs manualmente em suas configurações do dispositivo.
    
- Ele é usado no balanceamento de carga de DNS.
    
É importante observar que o Skype for Business Server 2019 não é compatível com os IDNs (nomes de domínio internacionalizados).
  
E é extremamente importante lembrar que qualquer nome no DNS é idêntico ao nome do computador configurado em qualquer servidor usado pelo Skype for Business Server 2019. Especificamente, não podemos ter nomes curtos no ambiente e devem ter FQDNs para o construtor de topologias.
  
Isso parece ser lógico para qualquer computador que já ingressou em um domínio, mas se você tiver um servidor de borda que não ingressou em seu domínio, ele poderá ter um nome curto, sem nenhum sufixo de domínio. Certifique-se de que não seja o caso, em DNS ou no servidor de borda, ou qualquer servidor ou pool do Skype for Business Server 2019, para isso.
  
Definitivamente, não use caracteres Unicode ou sublinhados. Os caracteres padrão (que são A-Z, a-z, 0-9 e hifens) são compatíveis com o DNS externo e as autoridades de certificação públicas (você precisará atribuir FQDNs ao SN no certificado, é importante lembrar), portanto, você pode se lembrar de muitos problemas se nomear com isso em mente desde o início.
  
Para saber mais sobre os requisitos do DNS para redes, consulte a seção [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) da sua documentação de planejamento.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Uma das coisas mais importantes a fazer antes da implantação é verificar se os seus certificados estão corretos. O Skype for Business Server 2019 precisa de uma PKI (infraestrutura de chave pública) para conexões de Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS). Basicamente, para comunicar-se com segurança de forma padronizada, o Skype for Business Server usa certificados emitidos por autoridades de certificação (CAs).
  
Estas são algumas das coisas que o Skype for Business Server 2019 usa certificados para:
  
- Conexões TLS entre clientes e servidores
    
- Conexões MTLS entre servidores
    
- Federação usando descoberta automática de DNS de parceiros
    
- Acesso de usuários remotos a IM (mensagens instantâneas)
    
- Acesso de usuário externo a sessões de A/V (áudio/vídeo), compartilhamento de aplicativos e conferência
    
- Conversando com aplicativos da Web e o Outlook Web Access (OWA)
    
Portanto, o planejamento de certificados é necessário. Agora, vamos examinar uma lista de algumas das coisas que você precisa ter em mente ao solicitar certificados:
  
- Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).
    
- Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).
    
- Todos os certificados devem ser assinados usando um algoritmo de assinatura que seja compatível com o sistema operacional. O Skype for Business Server 2019 é compatível com o conjunto de resumos SHA-1 e SHA-2 (224, 256, 384 e 512-bit) e atende ou supera os requisitos do sistema operacional.
    
- O registro automático tem suporte para servidores internos que executam o Skype for Business Server 2019.
    
- Não há suporte para a inscrição automática em servidores de borda do Skype for Business Server 2019.
    
> [!NOTE]
> O uso do algoritmo de assinatura RSASSA-PSS não é permitido e pode levar a erros no login e a problemas de encaminhamento de chamadas, entre outros.  
  
- Os comprimentos de chave de criptografia de 1024, 2048 e 4096 são suportados. Comprimentos de pelo menos 2048 são recomendados.
    
- O algoritmo de hash de assinatura ou sumário padrão é RSA. Os algoritmos ECDH_P256, ECDH_P384 e ECDH_P521 também têm suporte.
    
Há muito o que pensar, e há uma variedade de níveis de conforto com a solicitação de certificados de uma CA. Vamos dar a você mais algumas diretrizes a seguir para fazer seu planejamento o mais simples possível.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para seus servidores internos

Você precisará de certificados para a maioria dos seus servidores internos e, provavelmente, receberá uma CA interna (essa é uma CA localizada no seu domínio). Se quiser, você pode solicitar esses certificados de uma CA externa (uma localizada na Internet). Se você estiver se perguntando qual é a autoridade de certificação pública, pode dar uma olhada na lista de [parceiros do certificado de Comunicação](/SkypeForBusiness/certification/services-ssl) unificada.
  
Você também precisará de certificados quando o Skype for Business Server 2019 se comunicar com outros aplicativos e servidores, como o Microsoft Exchange Server. Isso, obviamente, precisa ser um certificado que esses outros aplicativos e servidores podem usar de forma compatível. O Skype for Business Server 2019 e outros produtos da Microsoft dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor. Se você estiver interessado nisso, temos um artigo de planejamento adicional para o OAuth e o Skype for Business Server 2019.
  
O Skype for Business Server 2019 também inclui suporte para (sem exigir) certificados assinados usando a função hash de criptografia SHA-256. Para oferecer suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma AC pública usando SHA-256.
  
Para manter as coisas simples, colocamos os requisitos de certificado para servidores de edição padrão, grupos de front-end e outras funções, nas tabelas a seguir, com o contoso.com fictício sendo usado para exemplos (você provavelmente usará outra coisa para seu ambiente). Todos esses são certificados do servidor Web padrão, com chaves privadas que não são exportáveis. Outras observações:
  
- O Uso Avançado de Chave (EKU) no servidor é automaticamente configurado quando o assistente de certificado é usado para solicitar certificados.
    
- Cada nome amigável do certificado deve ser exclusivo no repositório do computador.
    
- De acordo com os exemplos de nomes abaixo, se você configurou o sipinternal.contoso.com ou o sipexternal.contoso.com em seu DNS, ele precisará ser adicionado ao nome alternativo da entidade (SAN) do certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nome do assunto/nome comum**|**Nome alternativo de entidade**|**Exemplo**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Em servidores de edição padrão, o FQDN do servidor é o mesmo que o FQDN do pool.  <br/> O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também utiliza este certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interno (que é o mesmo que o FQDN do servidor)  <br/> AND  <br/> • Conheça URLs simples  <br/> • URL simples discada  <br/> • URL simples de administrador  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN =\*. contoso.com  <br/> |Não é possível substituir o FQDN da Web interna no construtor de topologias.  <br/> Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como SANs.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externo  <br/> AND  <br/> • URL simples discada  <br/> • Atender URLs simples por domínio SIP  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para servidores front-end em um pool de front-ends:
  
|**Certificado**|**Nome do assunto/nome comum**|**Nome alternativo de entidade**|**Exemplo**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também utiliza este certificado para Autenticação de Servidor para Servidor.  <br/> |
|Web interna  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN interno da Web (que não é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> AND  <br/> • Conheça URLs simples  <br/> • URL simples discada  <br/> • URL simples de administrador  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN =\*. contoso.com  <br/> |Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externo  <br/> AND  <br/> • URL simples discada  <br/> • URL simples de administrador  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para o diretor:
  
|**Certificado**|**Nome do assunto/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |Pool de diretores  <br/> |FQDN do diretor, FQDN do pool de directors.  <br/> Se esse pool for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de entradas para SIP. sipdomain (para cada domínio SIP que você tiver).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Se esse pool de diretor for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interno (que é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> AND  <br/> • Conheça URLs simples  <br/> • URL simples discada  <br/> • URL simples de administrador  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN =\*. contoso.com  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externo  <br/> AND  <br/> • Atender URLs simples por domínio SIP  <br/> • URL simples discada  <br/> OR  <br/> • Uma entrada curinga para as URLs simples  <br/> |O FQDN da Web externa do diretor deve ser diferente do pool de front-end ou do servidor front-end.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Como usar um certificado curinga:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN =\*. contoso.com  <br/> |
   
Certificados para servidor de mediação autônomo:
  
|**Certificado**|**Nome do assunto/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool  <br/> FQDN do servidor membro do pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificados para appliances de ramificação sobreviventes (especificamente, o appliance de ramificação sobreviventes 2015 para o Skype for Business Server 2019):
  
|**Certificado**|**Nome do assunto/nome comum**|**Nome alternativo de entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do aplicativo  <br/> |SPI. \<sipdomain\> (você precisa apenas de uma entrada por domínio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificados para acesso de usuário externo (Borda)

O Skype for Business Server 2019 oferece suporte ao uso de um **único certificado público** para interfaces externas de Edge de acesso e Web ProPlus, além do serviço de autenticação a/V, que é fornecido por meio do (s) servidor (es) de borda. A interface interna do Edge geralmente usará um certificado particular emitido pela sua CA interna, mas se preferir, você também pode usar um certificado público para isso, se for de uma CA confiável.
  
Seu proxy reverso (RP) também usará um certificado público que criptografa a comunicação entre o RP e os clientes e entre o RP e os servidores internos usando HTTP (ou, mais precisamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para mobilidade

Se você estiver implantando a mobilidade e estiver oferecendo suporte à descoberta automática para clientes móveis, será necessário incluir algumas entradas de nomes alternativos de entidades adicionais em seus certificados para dar suporte às conexões seguras dos clientes móveis.
  
Você precisará de nomes de SAN para descoberta automática nos seguintes certificados:
  
- Pool de diretores
    
- Pool de Front-Ends
    
- Proxy reverso
    
As especificações estão listadas nas tabelas abaixo.
  
É aqui que um pouco de planejamento é bom, mas às vezes você implantou o Skype for Business Server 2019 sem se pretender implantar a mobilidade, e isso será feito posteriormente quando você já tiver certificados em seu ambiente. Reemitir certificados através da AC interna costuma ser uma tarefa fácil, mas no caso de certificados públicos de uma AC pública, a reemissão pode custar caro.
  
Se for o que você está vendo e se você tiver muitos domínios SIP (o que torna a adição de SANS mais dispendiosas), você pode configurar seu proxy reverso para usar HTTP para a solicitação de serviço de descoberta automática inicial, em vez de usar HTTPS (que é o padrão configuração). O artigo [plano para mobilidade](../../SfbServer/plan-your-deployment/mobility.md) tem mais informações sobre isso.
  
Requisitos do pool de directors e do certificado de pool de front-end:
  
|**Descrição**|**Entrada do SAN**|
|:-----|:-----|
|URL interna do serviço de Descoberta Automática  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL externa do serviço de Descoberta Automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Você também pode usar o SAN =\*. \<sipdomain\>
  
Requisitos de certificado de proxy reverso (AC pública):
  
|**Descrição**|**Entrada do SAN**|
|:-----|:-----|
|URL externa do serviço de Descoberta Automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Este SAN precisa ser atribuído ao certificado que, por sua vez, é atribuído ao Ouvinte do SSL em seu proxy reverso.
  
> [!NOTE]
> Seu ouvinte de proxy reverso vai ter SANs para as URLs de seus serviços Web externos. Alguns exemplos seriam SAN = skypewebextpool01. contoso. com e dirwebexternal.contoso.com, se você tiver implantado o diretor, (que é opcional). 
  
## <a name="file-share"></a>Compartilhamento de arquivo
<a name="Fileshare"> </a>

O Skype for Business Server 2019 pode usar o mesmo compartilhamento de arquivo para todo o armazenamento de arquivos. Deve-se ter em mente:
  
- Um compartilhamento de arquivo precisa estar em um armazenamento anexado direto (DAS) ou em uma rede de área de armazenamento (SAN), e isso inclui o sistema de arquivos distribuído (DFS), bem como uma matriz redundante de RAID para repositórios de arquivos. Para ler mais sobre o DFS para Windows Server 2012, confira [esta página DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Recomendamos um cluster compartilhado para o compartilhamento de arquivo. Se você estiver usando um deles, deve clusterizar o Windows Server 2012 ou o Windows Server 2012 R2. Por que as janelas mais recentes? Versões antigas podem não ter as permissões adequadas para habilitar todos os recursos. Você pode usar o administrador de cluster para criar os compartilhamentos de arquivos, e isso [criará um artigo em](https://support.microsoft.com/en-us/help/224967) KB de cluster ajudará você com esses detalhes.
    
> [!CAUTION]
> Você deve saber que o uso de NAS como compartilhamento de arquivo não é compatível; portanto, use uma das opções listadas acima. 
  








