---
title: 'Lync Server 2013: Instalando o SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6342743486e3a3261e297d602ceb994d421dc13c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Instalando o SQL Server Reporting Services no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-20_

Se você pretende usar os relatórios de monitoramento do Microsoft Lync Server 2013 (consulte a próxima seção desta documentação para obter mais informações), primeiro é necessário instalar o SQL Server Reporting Services; O Reporting Services pode ser instalado ao mesmo tempo em que você instala o Microsoft SQL Server ou a qualquer momento após a instalação do SQL Server. Se você não instalou o SQL Server, siga as instruções fornecidas anteriormente nesta documentação. Ao instalar o SQL Server, certifique-se de que, na página seleção de recursos, selecione Reporting Services. Isso vai instalar o SQL Server Reporting Services.

Se você já instalou o SQL Server, mas não instalou o SQL Server Reporting Services, é possível adicionar esse recurso seguindo o conjunto de instruções apropriado para SQL Server 2008 R2 ou SQL Server 2012, conforme apropriado.

Para verificar se os serviços de relatório foram instalados com êxito, conclua as seguintes etapas:

1.  Se você estiver executando o Microsoft SQL Server 2008 R2, clique em **Iniciar**, clique em **todos os programas**, clique em **Microsoft SQL Server 2008 R2**, em **ferramentas de configuração**e em Gerenciador de configuração do **Reporting Services**.
    
    Se você estiver executando o Microsoft SQL Server 2012, clique em **Iniciar**, clique em **todos os programas**, clique em **Microsoft SQL Server 2012**, em **ferramentas de configuração**e em Gerenciador de configuração do **Reporting Services**.

2.  Na caixa de diálogo **conexão de configuração do Reporting Services** , verifique se o nome do seu servidor é exibido na caixa **nome do servidor** e se o nome da instância do SQL Server que armazena os dados de monitoramento aparece na caixa de instância do **servidor de relatório** . Clique em **conectar**.

No Gerenciador de configuração do Reporting Services, o painel de status do servidor de relatório deve mostrar que o SQL Server Reporting Services foi instalado e que o Reporting Services está em execução: o status do servidor de relatório deve ser mostrado como **iniciado** e o botão **Iniciar** deve estar esmaecido e indisponível. Se o serviço de relatório não estiver em execução, clique em **Iniciar** para iniciar o serviço.

Se nenhum banco de dados estiver listado ao lado do rótulo de nome do banco de dados do servidor de relatório, faça o seguinte:

1.  No Gerenciador de configuração do Reporting Services, clique em **banco de dados**.

2.  No painel banco de dados do servidor de relatório, clique em **alterar banco de dados**.

3.  No assistente de configuração do Report Server Database, no painel Ação, selecione **criar um novo banco de dados do servidor de relatório** e clique em **Avançar**.

4.  No assistente de configuração do Report Server Database, no painel servidor de banco de dados, verifique se as informações listadas nas caixas **nome do servidor**, **tipo de autenticação**e nome de **usuário** estão corretas. Clique em **testar conexão** para verificar se uma conexão pode ser feita com o servidor de banco de dados e clique em **Avançar**.

5.  No assistente de configuração do Report Server Database, no painel banco de dados, aceite os valores padrão para o **nome do banco de dados**, o **idioma**e o **modo servidor de relatório** e clique em **Avançar**.

6.  No assistente de configuração do Report Server Database, no painel credenciais, verifique se as informações corretas estão listadas na lista suspensa **tipo de autenticação** e as caixas **nome de usuário** e **senha** e clique em **Avançar**.

7.  No assistente de configuração do Report Server Database, no painel Resumo, clique em **Avançar**.

8.  No assistente de configuração do Report Server Database, no painel progresso e concluir, clique em **concluir**.

Para verificar se as URLs do serviço de relatório foram configuradas, clique em **URL do serviço Web**. Você deve ver uma ou mais URLs listadas nas **URLs do serviço Web servidor do relatório**de título. Clique em cada uma dessas URLs para verificar se você pode acessar a Home Page para a instalação local do SQL Server Reporting Services.

</div>

<span> </span>

</div>

</div>

</div>

