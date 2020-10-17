---
title: Ferramentas do kit de recursos de chat persistente do Lync Server 2013
description: Ferramentas do kit de recursos de chat persistente do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542347"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Ferramentas do kit de recursos de chat persistente do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

As ferramentas do kit de recursos de chat persistente do Lync Server 2013 ajudam a tornar tarefas rotineiras mais fáceis para os administradores de ti que implantam e gerenciam o servidor de chat persistente do Lync Server 2013. Além das instruções de instalação, este tópico descreve a finalidade de cada ferramenta e exemplos de uso.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Instalação das ferramentas do kit de recursos

Para instalar o Lync Server 2013, ferramentas do kit de recursos, **PersistentChatReskit.msi**de download. Execute **PersistentChatReskit.msi** para fazer uma instalação simples. O. msi instala todas as ferramentas no seguinte caminho: \\ **arquivos de programa \\ Microsoft Lync Server 2013 \\ persistent chat Server Resource Kit**. As ferramentas que são executáveis independentes estão nessa pasta. As ferramentas que também têm arquivos estão em suas próprias subpastas.

<div>


> [!IMPORTANT]  
> Após a instalação do Lync Server 2013, ferramentas do Resource Kit, você deve instalar <STRONG>PsExec.exe</STRONG> e copiar <STRONG>PsExec.exe</STRONG> para o seguinte caminho: \\ <STRONG>arquivos de programa \ Microsoft Lync Server 2013 \ persistent chat Server Resource Kit\ChatStressTool</STRONG>. Se você não copiar <STRONG>PsExec.exe</STRONG>, a ferramenta de estresse de chat persistente lançará uma exceção de erro e não será executada corretamente. Certifique-se de atender a esse requisito de pré-requisito antes de executar a ferramenta. Para obter detalhes sobre como instalar o <STRONG>PsExec.exe</STRONG>, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> .



</div>

</div>

<div>

## <a name="supported-environments"></a>Ambientes com suporte

Para obter o desempenho ideal, o Lync Server 2013, ferramentas do Resource Kit devem ser instalados no mesmo ambiente e com as mesmas especificações necessárias para o Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Visão geral das ferramentas do kit de recursos

Aqui estão as ferramentas fornecidas no kit de recursos de chat persistente do Lync Server 2013 persistent. A seção a seguir fornece uma descrição de cada ferramenta, incluindo os requisitos e o uso de exemplos.

  - AffCheck

  - ChatMonitoringSummary

  - Ferramenta ChatStress

  - ChatUpgradeVerifier

  - ChatUsageReport

  - ScheduleADSyncforPrincipal

</div>

<div>

## <a name="affcheck"></a>AffCheck

<div>

## <a name="description"></a>Descrição

A ferramenta AffCheck confirma que o usuário do banco de dados de back-end de chat persistente e os registros de afiliação de grupo correspondem aos dos serviços de domínio do Active Directory.

</div>

<div>

## <a name="requirements"></a>Requisitos

A ferramenta é instalada com o instalador do PersistentChatResKit em um computador ingressado no domínio.

A conta de usuário sob a qual a ferramenta é executada deve ter acesso de leitura ao banco de dados de back-end do chat persistente e aos serviços de domínio do Active Directory.

</div>

<div>

## <a name="usage"></a>Uso

Configure o arquivo de AffCheck.exe.config de acordo com as instruções no arquivo de configuração e execute a ferramenta AffCheck sem parâmetros de linha de comando. Veja a seguir o conteúdo do AffCheck.exe.config padrão.

**AffCheck.exe.config:**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>ChatMonitoringSummary

<div>

## <a name="description"></a>Descrição

A ferramenta PersistentChatMonitoringSummary move as informações de monitoramento de chat persistente do banco de dados de monitoramento para um arquivo de log CSV especificado.

O arquivo CSV conterá uma divisão de sessões de chat persistentes pelo número total de sessões, sessões bem-sucedidas, falhas inesperadas, falhas esperadas e uma divisão das falhas inesperadas por ID de diagnóstico, número de falhas e descrição de falha.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do kit de recursos de chat persistente em uma máquina associada a um domínio que tenha acesso ao banco de dados de monitoramento.

A conta de usuário sob a qual a ferramenta é executada deve ter acesso de leitura ao banco de dados de monitoramento.

O arquivo, PersistentChatMonitoringSummary.exe.config, deve conter uma \<connectionStrings\> seção que define a cadeia de caracteres de conexão com o banco de dados de monitoramento. Ele também deve conter uma chave para o PersistentChatEndpointUri para o qual os dados de monitoramento serão coletados e um caminho de arquivo para um local para o arquivo CSV que será gerado. Consulte o arquivo de configuração instalado para obter exemplos. O arquivo deve estar localizado no mesmo diretório que a ferramenta.

</div>

<div>

## <a name="usage"></a>Uso

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Estes parâmetros definem a seleção de dados:

**StartDateTime:** Especifica opcionalmente a data de início do período de seleção. Padrão: 1/1/1753 12:00:00 AM

**EndDateTime:** Especifica opcionalmente a última data do período de seleção. Padrão: agora

</div>

<div>

## <a name="example"></a>Exemplo

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>Ferramenta de estresse de chat persistente

<div>

## <a name="description"></a>Descrição

A ferramenta de estresse de chat persistente oferece uma maneira fácil de simular o uso de chat persistente para testar o desempenho do mundo real, incluindo diferentes modelos de usuário para se adequar melhor aos cenários de uso esperados.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do kit de recursos de chat persistente em uma máquina associada a um domínio que tenha acesso ao banco de dados de back-end de chat persistente.

Além desse computador *controlador* , você precisará de várias máquinas de *carregador* . Para todos os usuários de 10K em seu modelo de usuário, você precisará de pelo menos 4 GB de RAM livre em uma máquina de carregador. Por exemplo, uma execução com usuários do 80K exigirá cerca de 32 GB de RAM distribuídos em todas as máquinas de carregador. Recomendamos que você tenha pelo menos três máquinas de carregador, independentemente da carga esperada.

As máquinas de carregador devem ter a estrutura do .NET 4,5, bem como o Visual C++ 2012 Redistributable instalado.

</div>

<div>

## <a name="configuration"></a>Configuração

Copie os arquivos do ChatStressTool em uma pasta compartilhada acessível de todas as máquinas de carregador.

Criar usuários e canais para uso na execução de estresse:

  - Crie quantos usuários forem suas chamadas de modelo de usuário, habilite-os para o Lync e defina sua política de chat persistente como habilitado.

  - Crie uma categoria para seus canais de estresse e, em seguida, crie quantas salas forem necessárias nessa categoria. A categoria deve ter todos os usuários de estresse em sua lista **permitida** (por meio da adição da ou), e as salas de estresse devem ter uma configuração de privacidade **aberta**.

  - Recomendamos a criação de salas de estresse adicionais. Você pode criar salas de 50.000 com o seguinte comando de interface de linha de comando do Windows PowerShell:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Edite os arquivos de configuração de acordo com sua topologia:

Em **LoaderProcess.exe.config**, altere "Controller.contoso.com" para o nome de domínio totalmente qualificado (FQDN) do computador do controlador.

No **StressLauncher.exe.config:**

1.  Altere o valor de configuração "LoaderBinary" para o caminho da pasta compartilhada.

2.  Altere "AdminUser"/"AdminPassword" para credenciais que têm acesso de administrador a máquinas de carregador.

3.  Altere "ChannelCategory" para o nome da categoria em que os canais de estresse foram criados.

4.  Altere "UserNamePattern" e "UserPasswordPattern" para um modelo que corresponda às suas credenciais de usuário de estresse. {0} é substituído pelo número de índice do usuário.

5.  Altere "Domain" para o domínio SIP de sua topologia de teste.

6.  Altere "ConnectionString" para uma sequência de conexão para seu banco de dados de back-end de chat persistente.

7.  Altere "UserIndexStart" para o índice do primeiro usuário de estresse.

8.  Altere "LyncFQDN" para o FQDN do seu pool de front-ends.

9.  Modifique a lista "máquinas" para incluir nomes de máquina para todas as máquinas de carregador.

10. Altere o baseAddress do ponto de extremidade de serviço (o padrão é "controller.contoso.com") para o FQDN do seu computador controlador.

</div>

<div>

## <a name="usage"></a>Uso

Após a conclusão da configuração, abra StressLauncher.exe no computador do controlador. Você pode iniciar o StressLauncher como qualquer usuário. As credenciais sob as quais os processos de carregador começam nas máquinas de carregador devem ser especificadas no arquivo de configuração. Você também deve fornecer uma cadeia de conexão com acesso de leitura ao banco de dados de back-end de chat persistente. Se essa cadeia de conexão usar a autenticação integrada do Windows, você deverá iniciar o StressLauncher como um usuário que tenha esse acesso.

Altere as configurações de modelo de usuário conforme necessário. Clique em **Iniciar carregamento** para iniciar uma execução. Após um minuto, os usuários começarão a entrar, e a barra de progresso começará a ser preenchida. Neste ponto, é possível que a máquina controladora funcione e tenha medidas de desempenho.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>Descrição

ChatUpgradeVerifier é uma ferramenta de comparação de banco de dados específica de chat persistente. A ferramenta compara o banco de dados de chat de grupo 2007 R2 ou de 2010 chat de grupo (2007/2010Db) com o banco de dados de chat persistente 2013 (2013Db).

A ferramenta verificará, uma por um, cada categoria, sala de chat persistente e suplemento em 2007/2010Db para ver se ela aparece no 2013Db. A comparação inclui a verificação de todas as configurações da categoria, da sala de chat ou do suplemento, de qualquer entidade de segurança no escopo da categoria e de qualquer entidade de segurança em uma função na categoria ou na sala de chat. Se uma categoria ou uma sala de chat não aparecer corretamente no 2013Db, as diferenças serão de saída para um arquivo de conflitos. Se, após a atualização ter ocorrido, o 2007/2010Db for alterado e essa ferramenta for executada, haverá uma saída de diferenças para o arquivo de conflitos. Observe que este aplicativo é uma ferramenta de comparação de banco de dados somente e não valida o processo de atualização.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do kit de recursos de chat persistente em uma máquina que ingressou em um domínio que tenha acesso aos bancos de dados de back-end de chat persistente (versões anteriores e atuais para chat persistente).

A conta de usuário sob a qual a ferramenta é executada deve ter acesso de leitura aos bancos de dados de chat persistente.

O arquivo ChatUpgradeVerifier.exe.config deve conter o parâmetro GroupChat2007R2Db ou o parâmetro GroupChat2010Db, com uma cadeia de caracteres de conexão para o banco de dados de chat de grupo apropriado (Groupchat 2007R2 ou 2010). Também deve conter um parâmetro PersistentChat2013Db, com uma cadeia de caracteres de conexão para o banco de dados chat persistente 2013.

</div>

<div>

## <a name="usage"></a>Uso

Execute o **ChatUpgradeVerifier** sem nenhum parâmetro.

</div>

<div>

## <a name="example"></a>Exemplo

![Executando ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Executando ChatUpgradeVerifier.exe.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Relatório de uso de chat persistente

<div>

## <a name="description"></a>Descrição

A ferramenta ChatUsageReport gera um relatório HTML de uso do serviço de chat persistente.

</div>

<div>

## <a name="requirements"></a>Requisitos

Instale as ferramentas do kit de recursos de chat persistente em uma máquina associada a um domínio que tenha acesso ao banco de dados de back-end de chat persistente.

A conta de usuário sob a qual a ferramenta é executada deve ter acesso de leitura ao banco de dados back-end de chat persistente.

O arquivo, ChatUsageReport.exe.config, deve conter uma \<connectionStrings\> seção que define a sequência de conexão para o banco de dados de back-end de chat persistente. O conteúdo do arquivo de configuração padrão é incluído aqui para sua referência.

</div>

<div>

## <a name="usage"></a>Uso

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Estes parâmetros definem a seleção de dados:

**StartDate:** Especifica opcionalmente a data de início UTC do período de seleção. Padrão: data mais antiga

**EndDate:** Especifica opcionalmente a data de término UTC do período de seleção. Padrão: agora

Estes parâmetros definem como e quais dados são exibidos:

**TopActiveUsers:** Se for especificado, o relatório incluirá a n usuários mais ativos em termos do número de mensagens que o usuário publicou na sala de chat para o período selecionado. Padrão: 10

**TopActiveRooms:** Se for especificado, o relatório incluirá a n salas de chat mais ativas em termos do número de mensagens postadas na sala para o período selecionado. Padrão: 10

**LeastActiveRooms:** Se for especificado, o relatório incluirá as n menos salas de chat ativa em termos do número de mensagens postadas na sala de chat para o período selecionado. As salas terão pelo menos uma mensagem postada. Padrão: 10

**RoomsInactiveSince:** Se for especificado, o relatório incluirá uma lista de salas de chat que foram inativas desde a data especificada. Padrão: hora inteira

**OutputFolder:** A pasta na qual as imagens do ChatUsageReport.html e do gráfico serão colocadas. Isso deve ser definido no arquivo de configuração ou na linha de comando.

Todos os valores de parâmetro de linha de comando também podem ser especificados no arquivo de ChatUsageReport.exe.config que está localizado no mesmo diretório que a ferramenta. Se qualquer valor for especificado no arquivo de configuração e na linha de comando, o valor da linha de comando substituirá o valor do arquivo de configuração.

</div>

<div>

## <a name="output"></a>Saída

O relatório sempre incluirá o seguinte resultado:

  - N principais salas de chat ativas por número de postagens de mensagem para o período selecionado.

  - N primeiros usuários ativos por número de postagens de mensagem para o período selecionado.

  - N o máximo de salas de chat ativas por número de postagens de mensagem para o período selecionado.

  - Salas de chat que estão inativas para toda a vida do banco de dados ou desde a data especificada.

  - Tendência da postagem diária da mensagem para o período selecionado.

  - Tendência de postagem de mensagem semanal para o período selecionado.

  - Tendência de post de mensagem mensal para o período selecionado.

  - Total de postagens de mensagem para o período selecionado.

  - Número total de salas habilitadas.

</div>

<div>

## <a name="example"></a>Exemplo

O exemplo a seguir gera um relatório de uso para o ano inteiro 2001 e coloca o relatório no OutputFolder especificado no ChatUsageReport.exe.config.

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport.exe.config:

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>ScheduleADSyncForPrincipal

<div>

## <a name="description"></a>Descrição

ScheduleADSyncForPrincipal é um script do Microsoft SQL Server 2012 que deve ser executado diretamente de dentro do SQL Server Management Studio quando conectado ao banco de dados de back-end de chat persistente. Esse script permite forçar o chat persistente a sincronizar seus registros de um usuário com os serviços de domínio do Active Directory, em vez de aguardar o tempo de sincronização agendado.

</div>

<div>

## <a name="requirements"></a>Requisitos

A conta de usuário sob a qual o script é executado deve ter acesso de proprietário para o banco de dados de back-end de chat persistente.

</div>

<div>

## <a name="usage"></a>Uso

Veja a seguir o conteúdo do script padrão:

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

