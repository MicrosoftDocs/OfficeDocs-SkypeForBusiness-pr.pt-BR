---
title: Requisitos do sistema para o Skype for Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: 'Resumo: Prepare seus servidores do Skype for Business Server 2019 e a infraestrutura de domínio com este tópico. Hardware, so, bancos de dados, software, todos os requisitos e recomendações do sistema, juntamente com as informações de DNS, compartilhamento de arquivos e Active Directory, estão aqui para ajudar a garantir uma instalação e implantação bem-sucedidas do farm de servidores.'
ms.openlocfilehash: 7e0e8e3480c849fadd32921a5859766133ec1166
ms.sourcegitcommit: 379bfaf6b0584c1ac93341af605f93ab932a442b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240531"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Requisitos do sistema para o Skype for Business Server 2019
 
**Resumo:** Prepare-se para instalar o Skype for Business Server 2019 com este tópico. Hardware, so, software, bancos de dados, certificados, Active Diretory, DNS e fileshares são abordados aqui. Todos os requisitos e recomendações do sistema estão aqui para ajudar a garantir uma instalação bem-sucedida e uma implantação do farm de servidores.
  
Como você pode esperar, é possível fazer algumas preparações antes de começar a implantar o Skype for Business Server 2019. Este artigo orientará você no planejamento do seguinte:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Sistemas operacionais](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Bancos de dados SQL de back-end](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Domain Name System (DNS)](system-requirements.md#DNS)
  
- [Certificados](system-requirements.md#Certs)
  
- [Compartilhamento de arquivos](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware para o Skype for Business Server 2019
<a name="Hardware"> </a>

Depois que sua topologia estiver desativada (e se você não fizer isso, confira o tópico [Basics Topology for Skype for Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ), é hora de pensar nos servidores. Os servidores do Skype for Business Server 2019 exigem hardware de 64 bits. Nossas recomendações de hardware estão abaixo. Eles não são requisitos, mas refletem os requisitos necessários para o desempenho ideal. Temos documentação de planejamento de capacidade que ajudará você a determinar se precisa de mais do que isso, dependendo de suas circunstâncias.
  
Hardware recomendado para servidores Standard Edition:

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para funções do Skype for Business Server 2019.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |EM  <br/> • 8 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre em disco (dois dos discos usando RAID 1 e 6 usando RAID 10).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar a drives de disco mecânico 8 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas precisam ser agrupados com um único endereço MAC e um único endereço IP).  <br/> As configurações de duas ou várias bases **não** têm suporte para servidores front-end, servidores de back-end e servidores Standard Edition. <br/> Contanto que eles não estejam expostos ao sistema operacional e estejam sendo usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento fora de banda, como DRAC ou ILO. Este cenário não constitui um servidor de hospedagem múltipla e é suportado.  <br/> |


Hardware recomendado para servidores front-end e back-end:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior. <br/> Processadores Intel Itanium não são suportados para funções do Skype for Business Server 2019.  <br/> |
|Memória  <br/> |64 gigabytes (GB).  <br/> |
|Disco  <br/> |EM  <br/> • 8 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre em disco (dois dos discos usando RAID 1 e 6 usando RAID 10).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar a drives de disco mecânico 8 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas precisam ser agrupados com um único endereço MAC e um único endereço IP).  <br/> As configurações de duas ou várias bases **não** têm suporte para servidores front-end, servidores de back-end e servidores Standard Edition. <br/> Contanto que eles não estejam expostos ao sistema operacional e estejam sendo usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento fora de banda, como DRAC ou ILO. Este cenário não constitui um servidor de hospedagem múltipla e é suportado.  <br/> |
   
Hardware recomendado para servidores de borda, servidores de mediação autônomos e diretores:
  
|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para funções do Skype for Business Server 2019.  <br/> |
|Memória  <br/> |32 gigabytes.  <br/> |
|Disco  <br/> |EM  <br/> • 4 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre em disco (os discos devem estar em uma configuração RAID 1 2x).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho similar a drives de disco mecânico 4 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas precisam ser agrupados com um único endereço MAC e um único endereço IP).  <br/> Configurações de duas ou várias bases **não** são suportadas para servidores e diretores de interoperabilidade de vídeo. <br/> Os servidores de borda exigirão duas interfaces de rede que sejam adaptadores de rede de duas portas, 1 Gbps ou superior (ou dois adaptadores de rede emparelhados, para um total de quatro, cada par que está sendo agrupado com um único endereço MAC e um único endereço IP, para um total de dois pares).  <br/> Em servidores de mediação autônomos, a instalação de NICs (placas de interface de rede) adicionais para permitir a configuração de um endereço IP PSTN específico é suportada.  <br/> |


> [!NOTE]
> Independentemente da função de servidor, também recomendamos as seguintes configurações de hardware para o Skype for Business Server 2019 (isso pode variar dependendo da marca de hardware que você comprou, portanto, consulte a documentação do fabricante para obter informações específicas):
> - BIOS config-deve ser definido como simples de NUMA.
> - Habilitar hyperthreading.
> - A configuração da fila de RSS deve ser definida como 8 fila.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Sistemas operacionais para o Skype for Business Server 2019
<a name="OS"> </a>

Após o hardware, você precisará do sistema operacional de instalação (SO) que permitirá instalar e usar com êxito o Skype for Business Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Qualquer coisa diferente dos sistemas operacionais listados aqui não funcionará corretamente; Não tente fazê-lo para instalar o Skype for Business Server 2019. Por exemplo, a opção Server Core não está listada e, portanto, não é suportada.

> [!NOTE]
> A atualização in-loco do sistema operacional não é suportada pelo Lync Server 2013. Você deve implantar um pool separado e migrar os usuários para o novo pool com um sistema operacional diferente. Todos os servidores em um pool devem ter a mesma versão do sistema operacional.

> [!NOTE]
> 
> Se você estiver instalando o centro de administração do Windows 2019 no computador com o Windows Server 2019, ele solicitará uma porta para escuta. Há um liklihood você pode escolher a porta 443, mas se essa máquina tiver o Skype for Business Server 2019 instalado ou se o Skype for Business Server 2019 estiver instalado nele, você deverá escolher um número de porta diferente.
> 
>Por que esse é o caso? Se o centro de administração do Windows 2019 estiver em execução na porta 443, você não poderá se conectar ao servidor usando o painel de controle do Skype for Business, nem poderá se conectar a qualquer serviço Web interno em execução no servidor (serviço Web do catálogo de endereços, serviço de descoberta automática, serviço webticket, etc.).  Na verdade, você não poderá se conectar a qualquer URL do serviço Web interno. Escolha uma porta diferente, no caso de você precisar ou deseja colocar o centro de administração do Windows 2019 em um servidor com o Skype for Business Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software que deve ser instalado antes da implantação do Skype for Business Server 2019
<a name="Software"> </a>

Há algumas coisas que você precisará instalar ou configurar para qualquer servidor que executa o Skype for Business Server 2019. Eles estão listados abaixo, seguidos de requisitos adicionais para funções de servidor específicas.

> [!IMPORTANT]
> O Skype for Business 2019 suporta o .NET Framework 4,8. 
  
 **Todos os servidores:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Todos os servidores Skype for Business Server precisam ter o Windows PowerShell 3,0 instalado.  <br/> • Isso deve ser instalado por padrão com o Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |O serviços WCF é um **recurso** que é instalado como um recurso do Windows, no **Gerenciador de servidores**, inicialmente não há downloads necessários. <br/> • Você precisa certificar-se de que, quando instalar esse recurso, ou se ele já estiver instalado e você estiver verificando-o, se a opção de **ativação http** também está marcada e instalada, da seguinte forma: <br/> ![Captura de tela mostrando a opção de ativação HTTP nos recursos do .NET Framework 4,5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Não se preocupe se você receber um pop-up adicional, dizendo que outras coisas precisam ser instaladas para que a ativação HTTP seja instalada. Isso é normal; clique em OK e vá em frente. Se você não receber esse pop-up, poderá assumir que essas coisas já estão instaladas e prosseguir.  <br/> O Microsoft .NET Framework geralmente é instalado quando o Windows Server 2016 é instalado. O Skype for Business Server requer o Microsoft .NET Framework 4,7 ou 4,8 no entanto, portanto, provavelmente você precisará atualizá-lo. Você pode encontrar a atualização [aqui](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Para o Windows Server 2016, o tempo de execução do Windows Media Format é instalado com o Microsoft Media Foundation.  <br/> Todos os servidores front-end e servidores Standard Edition usados para conferência exigem o tempo de execução do Windows Media Format para executar os arquivos de áudio do Windows Media (. WMA) que os aplicativos de estacionamento de chamada, anúncio e grupo de resposta tocam para anúncios e música.  <br/> |
|Windows Identity Foundation  <br/> |Precisamos do Windows Identity Foundation 3,5 para dar suporte a cenários de autenticação de servidor para servidor para o Skype for Business Server 2019.  <br/> • Para o Windows Server 2016, não é necessário baixar nada. Abra o **Gerenciador do servidor**e vá para o assistente de adição de **funções e recursos**. O **Windows Identity Foundation 3,5** está listado na seção **recursos** . Se estiver selecionada, você está bom. Caso contrário, selecione-a e clique em **Avançar** para acessar o botão **instalar** . <br/> |
|Ferramentas de administração de servidor remoto  <br/> |Ferramentas de administração de funções: AD DS e ferramentas AD LDS  <br/> |
   
 **Servidores front-end e servidor Standard Edition também precisam de:**
  
|**Software/função**|**Detalhes**|
|:-----|:-----|
|Serviços de Informações da Internet (IIS)  <br/> |O IIS é necessário em todos os servidores front-end, bem como em todos os servidores Standard Edition, com os seguintes módulos selecionados:  <br/> • Recursos HTTP comuns: documento padrão, erros HTTP, conteúdo estático  <br/> • Integridade e diagnóstico: log HTTP, ferramentas de log, rastreamento  <br/> • Desempenho: compactação de conteúdo estático, compactação de conteúdo dinâmico  <br/> • Segurança: filtragem de solicitações, autenticação de mapeamento de certificado de cliente, autenticação do Windows  <br/> • Desenvolvimento de aplicativos: extensibilidade .NET 3,5, .NET Extensibility 4,5, ASP.NET 3,5, ASP.NET 4,5, extensões ISAPI, filtros ISAPI  <br/> • Ferramentas de gerenciamento: console de gerenciamento do IIS, scripts e ferramentas de gerenciamento do IIS  <br/> Observe que o acesso anônimo também é necessário, mas você obtém isso ao instalar o IIS, portanto, você não tem um local para selecioná-lo na lista.  <br/> |
|Tempo de Execução do Windows Media Format  <br/> | Para o Windows Server 2016, você precisará instalar o recurso **Media Foundation** no **Gerenciador do servidor**. Na verdade, você pode iniciar a instalação do Skype for Business Server 2019 sem isso, mas você será solicitado a instalá-lo e, em seguida, reinicializar o servidor, antes da continuação da instalação do Skype for Business Server 2019. É melhor fazê-lo antes do tempo. <br/> |
|Silverlight  <br/> |Você pode instalar a versão mais recente do Silverlight [aqui](https://www.microsoft.com/silverlight/).  <br/> |
   
Para ajudá-lo, aqui está um exemplo de script do PowerShell que você pode executar para automatizar isso:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Bancos de dados back-end que funcionarão com o Skype for Business Server 2019
<a name="DBs"> </a>

Ao instalar o Skype for Business Server 2019 Standard Edition, você terá o SQL Server 2016 Express (64-bit Edition).

O Skype for Business Server 2019 Enterprise Edition exigirá o SQL Server completo, conforme indicado abaixo (apenas edição de 64 bits; não use as edições de 32 bits):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64-bit Edition) e você deve executar com as atualizações mais recentes.  <br/> |Microsoft SQL Server 2017 (64-bit Edition) e você deve executar com as atualizações mais recentes.  <br/> |
Microsoft SQL Server 2016 (64-bit Edition) e você deve executar com as atualizações mais recentes.|
 |

Se você não vir a edição do SQL Server que deseja usar listada aqui, não poderá usá-la.
  
> [!NOTE]
> Você também precisa instalar o SQL Server Reporting Services para a função de servidor de monitoramento. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL clustering e SQL Always on

O cluster do SQL com o Skype for Business Server 2019 é suportado. Se você deseja configurar o cluster SQL, isso é feito no SQL Server.
  
Verifique se você tem uma configuração ativa/passiva para o cluster do SQL, com suporte. Não compartilhe o nó passivo com nenhuma outra instância do SQL.
  
Você pode ter os seguintes itens para clustering de failover:
  
Dois nós:
  
- Microsoft SQL Server 2019 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente.
- Microsoft SQL Server 2017 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente.
- Microsoft SQL Server 2016 Standard (edição de 64 bits) e recomendamos a execução com o Service Pack mais recente.

Dezesseis nós:
  
- Microsoft SQL Server 2019 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente.
- Microsoft SQL Server 2017 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente.
- Microsoft SQL Server 2016 Enterprise (64-bit Edition) e recomendamos a execução com o Service Pack mais recente.

O SQL Always on é suportado e você pode ler mais sobre ele no [back-end Server High Availability in Skype for Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Recomendações de instalação de servidor adicional:
  
Não instale nenhum software cliente do Microsoft Internet Security and Acceleration (ISA) Server ou qualquer outro software do LSP (provedor de serviços em camadas) do Winsock (qualquer software de inspeção de rede antivírus ou firewall de terceiros será incluído aqui) em qualquer um dos servidores front-end ou servidores de mediação autônomos. Um desempenho de tráfego de mídia ruim é visto quando esse software é instalado.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Embora muitos dos dados de configuração de servidores e serviços estejam armazenados no repositório de gerenciamento central do Skype for Business Server 2019, há algumas coisas ainda armazenadas no Active Directory:
  
|**Objetos do Active Directory**|**Tipos de objeto**|
|:-----|:-----|
|Extensões de esquema  <br/> |Extensões do objeto do usuário  <br/> |
||Extensões para o Skype for Business Server 2015 e Lync Server 2013, para manter a compatibilidade com versões anteriores com suporte  <br/> |
|Dados  <br/> |URI do SIP do usuário e outras configurações do usuário  <br/> |
||Objetos de contato para aplicativos (como o aplicativo de grupo de resposta e o aplicativo de atendedor de conferência)  <br/> |
||Dados publicados para compatibilidade com versões anteriores  <br/> |
||Um ponto de controle de serviço (SCP) para o repositório de gerenciamento central  <br/> |
||Conta de autenticação Kerberos (um objeto de computador opcional)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operacional para controladores de domínio

Os seguintes sistemas operacionais de controlador de domínio podem ser usados:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
O nível funcional do domínio de qualquer domínio para o qual você implanta o Skype for Business Server 2019 e o nível funcional de floresta de qualquer floresta que implanta o Skype for Business Server 2019 no, deve ser um dos seguintes:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Você pode ter controladores de domínio somente leitura nesses ambientes? Certamente, contanto que haja controladores de domínio graváveis disponíveis.
  
É importante saber que o Skype for Business Server 2019 não oferece suporte a domínios com rótulo único. O que são? Se você tiver um domínio raiz chamado contoso. local, isso vai ser bom. Se você tiver um domínio raiz apenas chamado local, isso não funcionará e, como resultado, não será suportado. Um pouco mais sobre isso foi escrito neste [artigo da base de conhecimento](https://support.microsoft.com/kb/300684/).
  
O Skype for Business Server 2019 também não dá suporte à renomeação de domínios. Se você realmente precisa renomear seu domínio, será necessário desinstalar o Skype for Business Server 2019, fazer o domínio renomear e, em seguida, reinstalar o Skype for Business Server 2019.
  
Por fim, você pode estar lidando com um domínio com um ambiente do AD DS bloqueado, e isso é muito certo. Temos mais informações sobre como implantar o Skype for Business Server 2019 em um ambiente do AD DS bloqueado na documentação de implantação.
  
### <a name="ad-topologies"></a>Topologias do AD

As topologias com suporte no Skype for Business Server 2019 são:
  
- Floresta única com domínio único
    
- Floresta única com uma única árvore e vários domínios
    
- Floresta única com várias árvores e namespaces não contíguos
    
- Várias florestas em uma topologia de floresta central
    
- Várias florestas em uma topologia de floresta de recursos
    
- Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
    
- Várias florestas em uma topologia de floresta de recursos com o Skype for Business Online e o Azure Active Directory Connect
    
Temos diagramas e descrições para ajudá-lo a determinar qual topologia você tem no seu ambiente ou o que você pode precisar configurar antes de instalar o Skype for Business Server 2019. Para simplificar, também estamos incluindo uma chave:
  
![O é uma chave para os ícones usados para diagramas de topologia do Skype for Business](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Floresta única com domínio único

![Diagrama da floresta única do Active Directory com um único domínio](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Não fica mais fácil do que isso; é uma floresta de domínio único, uma topologia comum.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Floresta única com uma única árvore e vários domínios

![Um único diagrama de floresta, de árvore única e de domínios do vários](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Este diagrama mostra uma única floresta, novamente, mas também tem um ou mais domínios filho (há três neste exemplo específico). Portanto, o domínio no qual os usuários são criados pode ser diferente do domínio do Skype for Business Server 2019 que é implantado. Por que se preocupar com isso? É importante lembrar que quando você implanta um pool de front-ends do Skype for Business Server, todos os servidores desse pool precisam estar em um único domínio. Você pode ter a administração entre domínios através do suporte do Skype for Business Server de grupos de administradores universais do Windows.
  
No diagrama acima, você pode ver que os usuários de um domínio podem acessar pools do Skype for Business Server do mesmo domínio ou de domínios diferentes, mesmo se esses usuários estiverem em um domínio filho.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Floresta única com várias árvores e namespaces não contíguos

![Um diagrama de floresta única, várias árvores e namespaces não contíguos](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Você pode ter uma topologia semelhante a este diagrama, onde você tem uma floresta, mas dentro dessa floresta estão vários domínios, com namespaces do AD separados. Nesse caso, esse diagrama é uma boa ilustração, pois inclui usuários em três domínios diferentes que acessam o Skype for Business Server 2019. As linhas sólidas indicam que eles estão acessando um pool do Skype for Business Server em seu próprio domínio, enquanto uma linha tracejada indica que eles estão acessando um pool em uma árvore diferente completamente.
  
Como você pode ver, os usuários no mesmo domínio, a mesma árvore ou até mesmo uma árvore diferente podem acessar pools com êxito.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Várias florestas em uma topologia de floresta central

![Várias florestas em um diagrama de topologia de floresta central](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
O Skype for Business Server 2019 oferece suporte a várias florestas configuradas em uma topologia de floresta central. Se você não tiver certeza de que tem o que você tem, a floresta central na topologia usa objetos nela para representar usuários nas outras florestas e hospeda contas de usuário para qualquer usuário na floresta.
  
Como isso funciona? Um produto de sincronização de diretório (como o Forefront Identity Manager ou FIM) gerencia as contas de usuário da sua organização por toda a sua existência. Quando uma conta é criada ou excluída de uma floresta, essa alteração é sincronizada para o contato correspondente na floresta central.
  
Obviamente, se sua infraestrutura do AD estiver em vigor, mover para essa topologia pode não ser fácil, mas se você já estiver lá ou ainda estiver planejando a infraestrutura da floresta, essa pode ser uma boa opção. Você pode centralizar a implantação do Skype for Business Server 2019 em uma única floresta, enquanto os usuários podem pesquisar, se comunicar e visualizar a presença de outros usuários em qualquer floresta. Todas as atualizações de contato de usuário são manipuladas automaticamente com o software de sincronização.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business
<a name="BKMK_multipleforestopology"> </a>

![Várias florestas em um diagrama de topologia de floresta de recursos](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Uma topologia de floresta de recursos também é suportada; é onde uma floresta é dedicada à execução de seus aplicativos de servidor, como o Microsoft Exchange Server e o Skype for Business Server 2019. Essas florestas de recursos também hospedam uma representação sincronizada de objetos de usuário ativos, mas nenhuma conta de usuário habilitada para logon. Portanto, a floresta de recursos é um ambiente de serviços compartilhados para outras florestas em que os objetos de usuário residem e têm uma relação de confiança de nível de floresta com a floresta de recursos.
  
Observe que o Exchange Server pode ser implantado na mesma floresta de recursos que o Skype for Business Server ou em uma floresta diferente.
  
Para implantar o Skype for Business Server 2019 nesse tipo de topologia, você deve criar um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas de usuário (se o Microsoft Exchange Server já estiver no ambiente, isso pode ser feito para você). Em seguida, você precisará de uma ferramenta de sincronização de diretório (como Forefront Identity Manager ou FIM) para gerenciar contas de usuário por meio do seu ciclo de vida.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Skype for Business com o Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Essa topologia é semelhante à topologia descrita em [várias florestas em uma topologia de floresta de recursos do Skype for Business](system-requirements.md#BKMK_multipleforestopology).
  
Nesta topologia, há uma ou mais florestas de usuários, e o Skype for Business Server é implantado em uma floresta de recursos dedicada. O Exchange Server pode ser implantado no local na mesma floresta de recursos ou em uma floresta diferente e configurado para híbrido com o Exchange Online, ou os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais. Não há um diagrama disponível para essa topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Várias florestas em uma topologia de floresta de recursos com o Skype for Business Online e o Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra duas florestas do AD, uma floresta de usuário e uma floresta de recursos. As duas florestas têm uma relação de confiança. Eles são sincronizados com o Office 365 usando o Azure AD Connect. Todos os usuários estão habilitados para o Skype for Business por meio do Office 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Com esse cenário, há várias florestas no local, com uma topologia de floresta de recursos. Há uma relação de confiança total entre as florestas do Active Directory. A ferramenta Azure Active Directory Connect é usada para sincronizar contas entre as florestas de usuário local e o Office 365.
  
 A organização também tem o Office 365 e usa o [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar suas contas locais com o Office 365. Os usuários habilitados para o Skype for Business são habilitados via Office 365 e Skype for Business online. O Skype for Business Server não é implantado no local.
  
A autenticação de logon único é fornecida por um farm de serviços de Federação do Active Directory localizado na floresta do usuário.
  
Neste cenário, há suporte para implantar o Exchange local, o Exchange Online, uma solução híbrida do Exchange ou não ter o Exchange implantado. (O diagrama mostra somente o Exchange no local, mas as outras soluções do Exchange também são totalmente compatíveis).
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Várias florestas em uma topologia de floresta de recursos com Skype for Business híbrido
<a name="BKMK_multipleforestopology"> </a>

Neste cenário, há uma ou mais florestas de usuários locais, e o Skype for Business é implantado em uma floresta de recursos dedicada e é configurado para o modo híbrido com o Skype for Business online. O Exchange Server pode ser implantado no local na mesma floresta de recursos ou em uma floresta diferente e pode ser configurado para híbrido com o Exchange Online. Como alternativa, os serviços de email podem ser fornecidos exclusivamente pelo Exchange Online para as contas locais.
  
Para obter mais informações, consulte [configurar um ambiente de várias florestas para o Skype for Business híbrido](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

O Skype for Business Server 2019 requer o DNS, pelos seguintes motivos:
  
- O DNS permite que o Skype for Business Server 2019 descubra servidores ou pools internos, permitindo a comunicação entre servidores.
    
- O DNS permite que máquinas clientes descubram o pool de front-ends ou o servidor Standard Edition que está sendo usado para transações SIP.
    
- Ele associa URLs simples a conferências com os servidores que hospedam essas conferências.
    
- O DNS permite que usuários externos e máquinas clientes se conectem aos servidores de borda ou ao proxy reverso HTTP, para mensagens instantâneas (IM) ou conferência.
    
- Ele permite que os dispositivos UC (comunicações unificadas) que não estão conectados descubram o pool de front-ends ou o servidor Standard Edition executando o serviço Web de atualização de dispositivo para obter atualizações e enviar logs.
    
- O uso de DNS permite que clientes móveis descubram automaticamente os recursos dos serviços Web sem exigir que os usuários insiram URLs manualmente nas configurações do dispositivo.
    
- Ele é usado no balanceamento de carga DNS.
    
É importante observar que o Skype for Business Server 2019 não dá suporte a IDNs (nomes de domínio internacionalizados).
  
E é extremamente importante lembrar que qualquer nome no DNS é idêntico ao nome do computador configurado em qualquer servidor que estiver sendo usado pelo Skype for Business Server 2019. Especificamente, não podemos ter nenhum nome curto no ambiente e deve ter FQDNs para o construtor de topologias.
  
Isso parece ser lógico para qualquer computador que já tenha ingressado em um domínio, mas se você tiver um servidor de borda que não ingressou no seu domínio, ele poderá ter um nome curto, sem nenhum sufixo de domínio. Certifique-se de que não é o caso, no DNS ou no servidor de borda, ou qualquer servidor ou pool do Skype for Business Server 2019, para esse assunto.
  
Definitivamente não use caracteres Unicode ou sublinhados. Os caracteres padrão (que são A-Z, a-z, 0-9 e hifens) têm suporte de autoridades de certificação públicas e de DNS externos (você precisará atribuir FQDNs ao SN no certificado, é importante lembrar-se), portanto, você pode se reportar muito, se você se deparar com isso em mente no início.
  
Para ler mais sobre os requisitos de DNS para redes, confira a seção [rede](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) da nossa documentação de planejamento.
  
## <a name="certificates"></a>Certificados
<a name="Certs"> </a>

Uma das coisas mais importantes que você pode fazer antes da implantação é garantir que você tenha seus certificados na ordem. O Skype for Business Server 2019 precisa de uma infraestrutura de chave pública (PKI) para conexões TLS e de protocolo de segurança de camada de transporte (MTLS). Basicamente, para se comunicar com segurança de forma padronizada, o Skype for Business Server usa certificados emitidos por autoridades de certificação (CAs).
  
Estas são algumas das coisas que o Skype for Business Server 2019 usa certificados para:
  
- Conexões TLS entre clientes e servidores
    
- Conexões MTLS entre servidores
    
- Federação usando a descoberta automática de parceiros no DNS
    
- Acesso de usuários remotos a IM (mensagens instantâneas)
    
- Acesso de usuário externo a sessões de áudio/vídeo (AV), compartilhamento de aplicativos e conferência
    
- Conversando com aplicativos da Web e o Outlook Web Access (OWA)
    
Portanto, o planejamento de certificados é necessário. Agora, vamos dar uma olhada em uma lista de algumas das coisas que você precisa ter em mente ao solicitar certificados:
  
- Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).
    
- Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).
    
- Todos os certificados devem ser assinados usando um algoritmo de assinatura suportado pelo sistema operacional. O Skype for Business Server 2019 oferece suporte ao pacote de resumos SHA-1 e SHA-2 de tamanhos de resumo (224, 256, 384 e 512 bits) e atende ou supera os requisitos do sistema operacional.
    
- O registro automático é suportado para servidores internos que executam o Skype for Business Server 2019.
    
- O registro automático não é suportado para servidores de borda do Skype for Business Server 2019.
    
> [!NOTE]
> O uso do algoritmo de assinatura RSASSA-PSS não é suportado e pode levar a erros em problemas de encaminhamento de chamadas e login, entre outros problemas. 
  
- Há suporte para os comprimentos de chave de criptografia de 1024, 2048 e 4096. São recomendados os comprimentos de chave de 2048 e superior.
    
- A compilação padrão ou a assinatura de hash, algoritmo é RSA. Os algoritmos de ECDH_P256, ECDH_P384 e ECDH_P521 também são suportados.
    
Há muito o que pensar, e há vários níveis de conforto com a solicitação de certificados de uma AC. Forneceremos mais orientações abaixo para tornar o planejamento o mais simples possível.
  
### <a name="certificates-for-your-internal-servers"></a>Certificados para seus servidores internos

Você precisará de certificados para a maioria dos seus servidores internos e, provavelmente, você os receberá de uma AC interna (que é uma autoridade de certificação localizada em seu domínio). Se quiser, você pode solicitar esses certificados de uma AC externa (uma localizada na Internet). Se você estiver se perguntando qual AC pública deve ir, confira a lista de [parceiros de certificados de comunicações unificadas](/SkypeForBusiness/certification/services-ssl) .
  
Você também precisará de certificados quando o Skype for Business Server 2019 se comunicar com outros aplicativos e servidores, como o Microsoft Exchange Server. Isso, obviamente, precisa ser um certificado que esses outros aplicativos e servidores podem usar de uma maneira suportada. O Skype for Business Server 2019 e outros produtos da Microsoft dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor. Se você estiver interessado nisso, temos um artigo de planejamento adicional para o OAuth e o Skype for Business Server 2019.
  
O Skype for Business Server 2019 também inclui suporte para (sem exigir) certificados assinados usando a função de hash de criptografia SHA-256. Para dar suporte ao acesso externo usando SHA-256, o certificado externo precisa ser emitido por uma autoridade de certificação pública usando SHA-256.
  
Para simplificar as coisas, colocamos os requisitos de certificado para servidores Standard Edition, pools de front-ends e outras funções nas seguintes tabelas, com a contoso.com fictícia que está sendo usada para exemplos (provavelmente você usará algo para o seu ambiente). Estes são todos os certificados de servidor Web padrão, com chaves privadas que não são exportáveis. Algumas coisas adicionais a serem observadas:
  
- O uso avançado de chave (EKU) do servidor é automaticamente configurado quando você usa o assistente de certificado para solicitar certificados.
    
- Cada nome amigável do certificado deve ser exclusivo no repositório do computador.
    
- De acordo com os exemplos de nomes abaixo, se você configurou o sipinternal.contoso.com ou o sipexternal.contoso.com no seu DNS, eles precisam ser adicionados ao nome alternativo da entidade (SAN) do certificado.
    
Certificados para servidores Standard Edition:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com  <br/> Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nos servidores Standard Edition, o FQDN do servidor é o mesmo que o FQDN do pool.  <br/> O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também pode usar esse certificado para autenticação de servidor para servidor.  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que é o mesmo que o FQDN do servidor)  <br/> E  <br/> • Atender a URLs simples  <br/> • URL simples discada  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN =\*. contoso.com  <br/> |Não é possível substituir o FQDN interno da Web no construtor de topologias.  <br/> Se você tiver vários URLs simples de reunião, você deve incluir todos eles como SANs.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externa  <br/> E  <br/> • URL simples discada  <br/> • Atender a URLs simples por domínio SIP  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com  <br/> Como usar um certificado coringa:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para servidores front-end em um pool de front-ends:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool e FQDN do servidor  <br/> Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.  <br/> Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).  <br/> |SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com  <br/> Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.  <br/> Você também pode usar esse certificado para autenticação de servidor para servidor.  <br/> |
|Web interna  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que não é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> E  <br/> • Atender a URLs simples  <br/> • URL simples discada  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN =\*. contoso.com  <br/> |Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
|Web externa  <br/> |FQDN do pool  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externa  <br/> E  <br/> • URL simples discada  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.  <br/> As entradas curinga são suportadas pelas entradas de URL simples.  <br/> |
   
Certificados para o diretor:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |Director pool  <br/> |FQDN do diretor, FQDN do pool de diretores.  <br/> Se esse pool for o servidor de logon automático para clientes e a correspondência de DNS estrita for necessária na política de grupo, você também precisará de entradas para o SIP. sipdomain (para cada domínio SIP que você tiver).  <br/> |pool.contoso.com; SAN = dir01. contoso. com  <br/> Se esse pool de Diretor for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Web interna  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web interna (que é o mesmo que o FQDN do servidor)  <br/> • FQDN do servidor  <br/> • FQDN do pool do Skype for Business  <br/> E  <br/> • Atender a URLs simples  <br/> • URL simples discada  <br/> • URL simples de administração  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN =\*. contoso.com  <br/> |
|Web externa  <br/> |FQDN do servidor  <br/> |Cada um dos seguintes:  <br/> • FQDN da Web externa  <br/> E  <br/> • Atender a URLs simples por domínio SIP  <br/> • URL simples discada  <br/> OU  <br/> • Uma entrada curinga para URLs simples  <br/> |O FQDN da Web externa do diretor deve ser diferente do pool de front-ends ou servidor front-end.  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = encontro. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com  <br/> Como usar um certificado curinga:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN =\*. contoso.com  <br/> |
   
Certificados para servidor de mediação autônomo:
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do pool  <br/> |FQDN do pool  <br/> FQDN do servidor membro do pool  <br/> |SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. net  <br/> |
   
Certificados para aparelho de filial persistente (especificamente, dispositivo de filial persistente 2015 para o Skype for Business Server 2019):
  
|**Certificado**|**Nome da entidade/nome comum**|**Nome alternativo da entidade**|**Exemplo**|
|:-----|:-----|:-----|:-----|
|Padrão  <br/> |FQDN do aplicativo  <br/> |SIP. \<sipdomain\> (você precisa apenas de uma entrada por domínio SIP)  <br/> |SN = sba01. contoso. net; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificados para acesso de usuário externo (borda)

O Skype for Business Server 2019 suporta o uso de um **único certificado público** para interfaces externas de borda de acesso e webconferência, além do serviço de autenticação a/V, que é fornecido através dos servidores de borda. A interface interna de borda normalmente usará um certificado privado emitido pela autoridade de certificação interna, mas se preferir, você também poderá usar um certificado público para isso, caso seja proveniente de uma autoridade de certificação confiável.
  
Seu proxy reverso (RP) também usará um certificado público e criptografará a comunicação do seu RP para os clientes e o RP para servidores internos usando HTTP (ou mais precisamente, TLS sobre HTTP).
  
### <a name="certificates-for-mobility"></a>Certificados para mobilidade

Se você estiver implantando a mobilidade e estiver oferecendo suporte à descoberta automática para clientes móveis, será necessário incluir algumas entradas de nome alternativo de entidade adicional nos seus certificados para dar suporte a conexões seguras dos clientes móveis.
  
Você precisará de nomes SAN para descoberta automática nos seguintes certificados:
  
- Director pool
    
- Pool de Front-Ends
    
- Proxy reverso
    
As especificações estão listadas nas tabelas a seguir.
  
É aí que um pouco de planejamento é bom, mas, às vezes, você implantou o Skype for Business Server 2019 sem a intenção de implantar a mobilidade, e isso é feito mais tarde, quando você já tem certificados no ambiente. A reemissão deles por meio de uma autoridade de certificação interna normalmente é muito fácil, mas com certificados públicos de uma AC pública, que pode ser um pouco mais caro.
  
Se for o que você está procurando e se você tiver muitos domínios SIP (o que tornaria a adição de SANS mais caras), poderá configurar seu proxy reverso para usar HTTP para a solicitação de serviço de descoberta automática inicial, em vez de usar HTTPS (que é a configuração padrão). O artigo [Plan for Mobility](../../SfbServer/plan-your-deployment/mobility.md) tem mais informações sobre isso.
  
Requisitos de certificado de pool de front-end e pool de diretores:
  
|**Descrição**|**Entrada de SAN**|
|:-----|:-----|
|URL interna do serviço de descoberta automática  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL externa do serviço de descoberta automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Como alternativa, você pode usar SAN\*=. \<sipdomain\>
  
Requisitos de certificado de proxy reverso (AC pública):
  
|**Descrição**|**Entrada de SAN**|
|:-----|:-----|
|URL externa do serviço de descoberta automática  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
Essa SAN precisa ser atribuída ao certificado atribuído ao ouvinte SSL em seu proxy reverso.
  
> [!NOTE]
> Seu ouvinte de proxy reverso terá SANs para seus URLs de serviços Web externos. Alguns exemplos seriam SAN = skypewebextpool01. contoso. com e dirwebexternal.contoso.com, se você tiver implantado o diretor (opcional). 
  
## <a name="file-share"></a>Compartilhamento de arquivo
<a name="Fileshare"> </a>

O Skype for Business Server 2019 pode usar o mesmo compartilhamento de arquivo para todo o armazenamento de arquivos. Você precisa ter em mente o seguinte:
  
- Um compartilhamento de arquivos precisa estar em um (armazenamento de conexão direta) ou em uma rede de área de armazenamento (SAN), e isso inclui o sistema de arquivos distribuído (DFS), bem como uma matriz redundante de discos independentes (RAID) para repositórios de arquivos. Para ler mais sobre o DFS no Windows Server 2012, confira [esta página DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- Recomendamos um cluster compartilhado para o compartilhamento de arquivos. Se você já estiver usando um, deverá ter o cluster do Windows Server 2012 ou versões posteriores

> [!Note]
> **Por que a versão mais recente do Windows?** Versões mais antigas podem não ter as permissões corretas para habilitar todos os recursos. Você pode usar o administrador de cluster para criar os compartilhamentos de arquivos. Consulte este artigo de suporte [como criar compartilhamentos de arquivos em um cluster](https://support.microsoft.com/help/224967) para obter mais detalhes.
    
> [!CAUTION]
> Você deve saber que usar o NAS (armazenamento conectado à rede) como um compartilhamento de arquivos não é suportado, portanto, use uma das opções listadas acima. Essa limitação de suporte é causada pelo design de variáveis de dispositivos NAS que precisam fornecer capacidade de adaptação ao sistema de arquivos para o computador baseado no Windows Server que acessa o sistema de arquivos compartilhado dos dispositivos.
  








