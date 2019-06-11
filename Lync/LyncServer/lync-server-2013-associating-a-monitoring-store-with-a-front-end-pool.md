---
title: 'Lync Server 2013: associando um repositório de monitoramento a um pool de front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c1153d0d20cf5a3855a36f8d7aa24a8d9d4680b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Associando um armazenamento de monitoramento a um pool de front-end no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-04-22_

No Microsoft Lync Server 2013, os dados de monitoramento só podem ser coletados em pools front-ends que foram associados a uma loja de monitoramento, uma tarefa geralmente realizada para você definir um pool de front-end no construtor de topologias. Para associar um repositório de monitoramento a um novo pool de front-end, verifique se você selecionou o monitoramento de opções **(a gravação de detalhes da chamada e o registro em log de métricas de qualidade de experiência)** na página **selecionar recursos** do assistente para definir novo pool de front-ends. Observe que, se você selecionar essa opção, também deverá especificar um repositório SQL para concluir o assistente; no entanto, essa loja não precisa existir no momento em que você executar o assistente. Isso significa que você pode primeiro associar um pool a um armazenamento de monitoramento e depois configurar posteriormente e configurar essa loja.

Em alternativa, é possível associar um pool de front-ends existente com um repositório de monitoramento novo ou diferente ao concluir o seguinte procedimento:

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.

3.  Na caixa de diálogo **Salvar como**, insira um nome de arquivo para sua topologia atual e clique em **Salvar**. A topologia salva poderá ser recuperada posteriormente e republicada em caso que haja problemas com a nova topologia.

4.  No construtor de topologias, expanda o **Lync Server 2013**, expanda o nome do site que contém o pool de front-end e clique em expandir **grupos de front-end do Enterprise Edition**.

5.  Clique com o botão direito no nome do pool a ser associado com o repositório de monitoramento e clique em **Editar propriedades**.

6.  Na caixa de diálogo **Editar propriedades**, na guia **Geral**, selecione a opção **Monitoramento (CDR e métricas de QoE)** e selecione um banco de dados existente do SQL Server na lista suspensa **Monitoramento do repositório do SQL Server**. (Você também pode clicar em **Novo** para associar o pool a um novo repositório do banco de dados.) Se você escolher usar um novo repositório do banco de dados, na caixa de diálogo **Definir novo repositório SQL**, insira o FQDN do computador do SQL Server na caixa **FQDN do SQL Server**. Se você deseja usar a instância padrão do SQL Server para esse repositório, selecione **Instância padrão**; caso contrário, selecione **Instância nomeada** e insira o nome da instância na caixa **Instância nomeada**.
    
    A caixa de diálogo **Editar propriedades** também oferece a opção de criar um espelho SQL para seu banco de dados de monitoramento (um espelho SQL permite manter duas cópias do seu banco de dados de monitoramento, uma cópia armazenada no computador do repositório de monitoramento e outra no computador do espelho SQL). Para habilitar o espelhamento, selecione **Essa instância SQL está na relação de espelho** e insira o número da porta para o servidor-espelho na caixa **Número da porta de espelhamento**.

7.  Na caixa de diálogo **Editar propriedades**, clique em **OK**.

Após associar o repositório de monitoramento a um pool de front-ends, você deverá publicar a nova topologia antes de as alterações entrarem em vigor. Para publicar sua nova topologia, complete as seguintes etapas no construtor de topologias:

1.  Clique em **Ação**, aponte para **Topologia** e clique em **Publicar**.

2.  No assistente Publicar topologia, na página **Publicar a topologia**, clique em **Avançar**.

3.  Na página **Assistente de publicação concluído**, clique em **Concluir**.

Após a topologia ser publicada, é possível instalar o banco de dados de monitoramento no computador que hospedará o repositório de monitoramento. O banco de dados de monitoramento pode ser instalado usando o Shell de gerenciamento do Lync Server e o Windows PowerShell. Para instalar o banco de dados localmente (ou seja, instalar o banco de dados no mesmo computador em que você está executando o Shell de gerenciamento do Lync Server), inicie o Shell de gerenciamento no computador apropriado e, em seguida, digite o seguinte comando e pressione ENTER:

    Install-CsDatabase -LocalDatabases

Quando você executar o comando anterior, install-CsDatabase lerá a topologia do Lync Server atual, determinará quais bancos de dados precisam ser instalados no computador local e, em seguida, instalar e configurar automaticamente cada um desses bancos de dados.

Para instalar o banco de dados em um computador remoto (isto é, um computador diferente daquele onde o Shell de Gerenciamento está executando), você deve incluir pelo menos dois parâmetros: o parâmetro ConfiguredDatabases e o parâmetro SqlServerFqdn. Esses parâmetros dizem para o cmdlet Install-CsDatabase recuperar a topologia do Lync Server e instalar e configurar os bancos de dados necessários no computador especificado pelo parâmetro SqlServerFqdn. O parâmetro SqlServerFqdn deve usar um valor de parâmetro representando o FQDN do computador onde os bancos de dados devem ser instalados.

Por exemplo, este comando instala o banco de dados de monitoramento no computador atl-sql-001.litwareinc.com:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

Você também pode instalar o banco de dados de monitoramento executando o assistente de implantação do Lync Server no computador que hospedará a loja de monitoramento. Para fazer isso, faça o login no computador em questão e conclua o seguinte procedimento:

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Assistente de implantação do Lync Server**.

2.  No assistente de implantação, clique em **instalar ou atualizar o sistema do Lync Server**.

3.  Na página **implantar** , em **etapa 2: configurar ou remover componentes do Lync Server**, clique **novamente em executar**.

4.  No assistente de configuração de componentes do Lync Server, na página **configurar componentes do Lync Server** , clique em **Avançar**.

5.  Na página **especificar caminho para MSIs** , digite o caminho para o arquivo OCScore. msi (um arquivo incluído na mídia de instalação do Lync Server) e clique em **Avançar**.

6.  Na página **Executando comandos** clique em **Concluir**.

Para garantir que todos os serviços do Lync Server necessários tenham começado, clique em **executar** abaixo do título **etapa 4: Iniciar serviços** na página **implantar**

</div>

<span> </span>

</div>

</div>

</div>

