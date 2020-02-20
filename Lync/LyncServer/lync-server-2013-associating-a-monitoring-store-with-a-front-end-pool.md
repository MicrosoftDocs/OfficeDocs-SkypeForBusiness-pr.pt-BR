---
title: 'Lync Server 2013: associando um repositório de monitoramento a um pool de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889179c5302a0ff8d59b5cf438c7ba0ab3c489f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Associando um repositório de monitoramento a um pool de front-ends no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-04-22_

Nos dados de monitoramento do Microsoft Lync Server 2013, só podem ser coletados em pools de front-ends que foram associados a um repositório de monitoramento, uma tarefa normalmente executa um pool de front-ends no construtor de topologias. Para associar um repositório de monitoramento a um novo pool de front-ends, selecione o monitoramento de opções **(registro de detalhes de chamadas e registro em log de métricas de qualidade da experiência)** na página **selecionar recursos** do assistente definir novo pool de front-ends. Observe que, se você selecionar essa opção, também deverá especificar um repositório SQL para concluir o assistente; no entanto, esse repositório não precisa existir no momento em que você executar o assistente. Isso significa que você pode primeiro associar um pool a um repositório de monitoramento e, em seguida, instalar o repositório e configurá-lo.

Em alternativa, é possível associar um pool de front-end existente com um repositório de monitoramento novo ou diferente ao concluir o seguinte procedimento:

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.

3.  Na caixa de diálogo **Salvar como**, insira um nome de arquivo da sua topologia atual e clique em **Salvar**. A topologia salva pode ser recuperada posteriormente e republicada em caso que hajam problemas com a nova topologia.

4.  No construtor de topologias, expanda **Lync Server 2013**, expanda o nome do site que contém o pool de front-ends e, em seguida, clique em expandir **pools de front-ends Enterprise Edition**.

5.  Clique com o botão direito no nome do pool a ser associado com o repositório de monitoramento e clique em **Editar Propriedades**.

6.  Na caixa de diálogo **Editar propriedades**, na guia **Geral**, selecione a opção **Monitoramento (CDR e métricas QoE)** e selecione um banco de dados existente do SQL Server da lista suspensa **Monitoramento do repositório do SQL Server**. (Em alternativa, clique em **Novo** para associar o pool com um novo repositório do banco de dados.) Se você escolher usar um novo repositório do banco de dados, na caixa de diálogo **Definir novo repositório SQL**, insira o FQDN do computador do SQL Server na caixa **FQDN do Sql Server**. Se você deseja usar a instância padrão do SQL Server para este repositório, selecione **Instância padrão**; caso contrário, selecione **Instância nomeada** e insira o nome da instância na caixa **Instância nomeada**.
    
    A caixa de diálogo **Editar propriedades** também oferece a opção de criar um espelho SQL para seu banco de dados de monitoramento (um espelho SQL permite manter duas cópias do seu banco de dados de monitoramento, uma cópia armazenada no computador do repositório de monitoramento e outro no computador do SQL espelho). Para habilitar o espelhamento, selecione **Esta instância SQL está na relação de espelho** e insira o número da porta para o servidor espelho na caixa **Número da porta de espelho**.

7.  Na caixa de diálogo **Editar propriedades**, clique em **OK**.

Após associar o repositório de monitoramento com um pool de front-end, você deve publicar a nova topologia antes das alterações entrarem em vigor. Para publicar sua nova topologia, conclua as seguintes etapas no Construtor de Topologia:

1.  Clique em **Ação**, aponte para **Topologia** e clique em **Publicar**.

2.  No assistente Publicar topologia, na página **Publicar a topologia**, clique em **Avançar**.

3.  Na página **Publicar assistente concluído**, clique em **Concluir**.

Após a topologia ser publicada, é possível instalar o banco de dados de monitoramento no computador que irá hospedar o repositório de monitoramento. O banco de dados de monitoramento pode ser instalado usando o Shell de gerenciamento do Lync Server e o Windows PowerShell. Para instalar o banco de dados localmente (ou seja, para instalar o banco de dados no mesmo computador em que você está executando o Shell de gerenciamento do Lync Server), inicie o Shell de gerenciamento no computador apropriado e digite o seguinte comando e pressione ENTER:

    Install-CsDatabase -LocalDatabases

Quando você executar o comando anterior, install-CsDatabase lerá a topologia atual do Lync Server, determinará quais bancos de dados precisam ser instalados no computador local e, em seguida, instalar e configurar automaticamente cada um desses bancos de dados.

Para instalar o banco de dados em um computador remoto (isto é, um computador diferente daquele onde o Shell de Gerenciamento está executando), você deve incluir pelo menos dois parâmetros: o parâmetro ConfiguredDatabases e o parâmetro SqlServerFqdn. Esses parâmetros dizem ao cmdlet Install-CsDatabase para recuperar a topologia do Lync Server e instalar e configurar os bancos de dados necessários no computador especificado pelo parâmetro SqlServerFqdn. O parâmetro SqlServerFqdn deve usar um valor de parâmetro representando o FQDN do computador onde os bancos de dados devem ser instalados.

Por exemplo, este comando instala o banco de dados de monitoramento no computador atl-sql-001.litwareinc.com:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Como alternativa, você pode instalar o banco de dados de monitoramento executando o assistente de implantação do Lync Server no computador que hospedará o repositório de monitoramento. Para fazer isso, faça o login no computador adequado e conclua o seguinte procedimento:

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Assistente de implantação do Lync Server**.

2.  No Assistente de Implantação, clique em **Instalar ou Atualizar o Sistema do Lync Server**.

3.  Na página **Implantar**, em **Etapa 2: Instalar ou remover componentes do Lync Server**, clique em **Executar novamente**.

4.  No assistente de Instalação dos componentes do Lync Server, na página **Instalar componentes do Lync Server**, clique em **Avançar**.

5.  Na página **especificar caminho para MSIs** , digite o caminho para o arquivo OCScore. msi (um arquivo incluído na sua mídia de instalação do Lync Server) e clique em **Avançar**.

6.  Na página **Executando Comandos**, clique em **Concluir**.

Para garantir que todos os serviços necessários do Lync Server tenham sido iniciados, clique em **executar** no cabeçalho **etapa 4: Iniciar serviços** na página **implantar**

</div>

<span> </span>

</div>

</div>

</div>

