---
title: 'Lync Server 2013: Instalando o SQL Server Reporting Services'
description: 'Lync Server 2013: Instalando o SQL Server Reporting Services.'
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
ms.openlocfilehash: 70da5e3845d18057b3362fa39953dee6cdc3d9f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573877"
---
# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="7ad28-103">Instalando o SQL Server Reporting Services no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ad28-103">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ad28-104">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="7ad28-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="7ad28-105">Se você pretende usar os relatórios de monitoramento do Microsoft Lync Server 2013 (consulte a próxima seção desta documentação para obter mais informações), primeiro é necessário instalar o SQL Server Reporting Services; O Reporting Services pode ser instalado ao mesmo tempo em que você instala o Microsoft SQL Server ou a qualquer momento após a instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ad28-105">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="7ad28-106">Se você não tiver instalado o SQL Server, siga as instruções fornecidas anteriormente nesta documentação.</span><span class="sxs-lookup"><span data-stu-id="7ad28-106">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="7ad28-107">Ao instalar o SQL Server, certifique-se de que, na página seleção de recursos, você seleciona o Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7ad28-107">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="7ad28-108">Isso instalará o SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7ad28-108">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="7ad28-109">Se você já instalou o SQL Server, mas não o SQL Server Reporting Services, poderá adicionar esse recurso seguindo as instruções correspondentes ao SQL Server 2008 R2 ou ao SQL Server 2012, dependendo da versão desejada.</span><span class="sxs-lookup"><span data-stu-id="7ad28-109">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="7ad28-110">Para verificar se o Reporting Services foi instalado com êxito, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="7ad28-110">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="7ad28-111">Se estiver executando o Microsoft SQL Server 2008 R2, clique em **Iniciar**, em **Todos os Programas**, em **Microsoft SQL Server 2008 R2**, em **Ferramentas de Configuração** e depois em **Gerenciador de Configuração do Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-111">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="7ad28-112">Se estiver executando o Microsoft SQL Server 2012, clique em **Iniciar**, em **Todos os Programas**, em **Microsoft SQL Server 2012**, em **Ferramentas de Configuração** e depois em **Gerenciador de Configuração do Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-112">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="7ad28-p102">Na caixa de diálogo **Conexão de Configuração do Reporting Services**, verifique se o nome do seu servidor aparece na caixa **Nome do Servidor** e se o nome da instância do SQL Server que armazena seus dados de monitoramento aparece na caixa **Instância do Servidor de Relatório**. Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="7ad28-115">No Gerenciador de configuração do Reporting Service, o painel de status do servidor de relatório deve mostrar que o SQL Server Reporting Services foi instalado e que o Reporting Services está sendo executado: o status do servidor de relatório deve ser mostrado como **iniciado** e o botão **Iniciar** deve estar esmaecido e indisponível.</span><span class="sxs-lookup"><span data-stu-id="7ad28-115">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="7ad28-116">Se o Reporting Services não estiver em execução, clique em **Iniciar** para iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="7ad28-116">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="7ad28-117">Se nenhum banco de dados estiver listado ao lado do rótulo Nome do Banco de Dados do Servidor de Relatório, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7ad28-117">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="7ad28-118">No Gerenciador de Configuração do Reporting Services, clique em **Banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-118">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="7ad28-119">No painel Banco de Dados do Servidor de Relatório, clique em **Alterar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-119">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="7ad28-120">No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Ação, selecione **Criar um novo banco de dados do servidor de relatório** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-120">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="7ad28-p104">No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Servidor de Banco de Dados, verifique se as informações listadas nas caixas **Nome do Servidor**, **Tipo de Autenticação** e **Nome de Usuário** estão corretas. Clique em **Testar Conexão** para verificar se é possível estabelecer uma conexão com o servidor de banco de dados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="7ad28-123">No Assistente de Configuração do Banco de Dados do Servidor de Relatório, aceite os valores padrão para **Nome do Banco de Dados**, **Idioma** e **Modo do Servidor de Relatório** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-123">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="7ad28-124">No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Credenciais, verifique se as informações corretas constam na lista suspensa **Tipo de Autenticação** e nas caixas **Nome de Usuário** e **Senha** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-124">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="7ad28-125">No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Resumo, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-125">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="7ad28-126">No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Progresso e Conclusão, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="7ad28-126">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="7ad28-p105">Para verificar se as URLs do Reporting Services estão configuradas, clique em **URL do Serviço Web**. Você deverá ver uma ou mais URLs listadas sob o cabeçalho **URLs do Serviço Web Servidor de Relatórios**. Clique em cada uma dessas URLs para verificar se consegue acessar a home page da instalação local do SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7ad28-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

