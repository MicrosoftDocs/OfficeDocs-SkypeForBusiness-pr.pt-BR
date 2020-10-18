---
title: 'Lync Server 2013: usando o Microsoft SQL Server 2008 R2 como banco de dados do System Center Operations Manager'
description: 'Lync Server 2013: usando o Microsoft SQL Server 2008 R2 como banco de dados do System Center Operations Manager.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 870c079e7e5e871fc62358e9bdd21653193fad7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580347"
---
# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="1c92d-103">Usando o Microsoft SQL Server 2008 R2 como seu banco de dados do System Center Operations Manager para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c92d-103">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c92d-104">_**Última modificação do tópico:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="1c92d-104">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="1c92d-105">Para usar o SQL Server 2008 R2 como banco de dados back-end, conclua as etapas detalhadas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1c92d-105">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="1c92d-106">Configurando o SQL Server 2008 R2 e o SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1c92d-106">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="1c92d-107">Antes de começar a instalação do System Center Operations Manager, você deve fazer duas alterações no SQL Server 2008 R2 e na configuração do SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="1c92d-107">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="1c92d-108">(Essas alterações só serão necessárias se você estiver usando o SQL Server 2008 R2 como seu banco de dados do Operations Manager.) Primeiro, faça o seguinte no computador que hospedará o banco de dados do Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="1c92d-108">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="1c92d-109">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-109">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="1c92d-110">Na caixa de diálogo **executar** , digite **C: \\ arquivos de programa \\ Microsoft SQL Server \\ MSRS10 \_ 50. ARCHINST \\ Reporting Services \\ ReportServer** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="1c92d-110">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="1c92d-111">Na pasta **ReportServer**, abra o arquivo **rsreportserver.config** no Bloco de Notas ou em qualquer outro editor de texto.</span><span class="sxs-lookup"><span data-stu-id="1c92d-111">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="1c92d-112">Próximo ao início do arquivo, você verá uma série de nós "Add Key".</span><span class="sxs-lookup"><span data-stu-id="1c92d-112">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="1c92d-113">Encontre a entrada que começa a \*\* \< Adicionar Key = "SecureConnectionLevel"\*\* e defina o valor como **0**:</span><span class="sxs-lookup"><span data-stu-id="1c92d-113">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="1c92d-114">Salve o arquivo **rsreportserver.config** e feche o editor de texto.</span><span class="sxs-lookup"><span data-stu-id="1c92d-114">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="1c92d-p103">Depois de atualizar o arquivo de configuração do Report Server, você deve atribuir o certificado correto ao SQL Server Reporting Services. Para isso:</span><span class="sxs-lookup"><span data-stu-id="1c92d-p103">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services. To do that:</span></span>

1.  <span data-ttu-id="1c92d-117">Clique em **Iniciar**, **em todos os programas**, em **Microsoft SQL Server 2008 R2**, em **ferramentas de configuração**e em Gerenciador de configuração do **Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-117">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="1c92d-118">Na caixa de diálogo **Conexão de Configuração do Reporting Services**, certifique-se de que o nome do seu servidor aparece na caixa **Nome do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-118">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="1c92d-119">Selecione a instância do SQL Server que hospedará o banco de dados do Operations Manager (por exemplo, **ARCHINST**) na lista suspensa **instância do servidor de relatório** e clique em **conectar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-119">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="1c92d-120">No Gerenciador de Configuração do Reporting Services, clique em **URL do Serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-120">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="1c92d-p105">Na página **URL do Serviço Web**, selecione o certificado a ser usado para o seu Reporting Services na lista suspensa **Certificado SSL** e clique em **Aplicar**. Depois de alguns segundos, você verá duas URLs listadas sob **URLs do Serviço Web do Servidor de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p105">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**. After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="1c92d-123">Clique em ambas para verificar se pode acessar o SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="1c92d-123">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="1c92d-124">Feche o Gerenciador de Configuração do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="1c92d-124">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="1c92d-125">Criando um banco de dados do System Center Operations Manager para uso com o SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1c92d-125">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="1c92d-126">Se você quiser configurar o System Center Operations Manager para usar um banco de dados do SQL Server 2008 R2, será necessário criar manualmente o banco de dados do Operations Manager no computador que executa o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="1c92d-126">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="1c92d-127">(Novamente, essas etapas não são necessárias se você estiver usando o SQL Server 2005 ou o SQL Server 2008 como seu banco de dados de back-end.)</span><span class="sxs-lookup"><span data-stu-id="1c92d-127">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="1c92d-128">Para criar um banco de dados do Operations Manager manualmente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1c92d-128">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="1c92d-129">Na mídia de instalação do System Center Operations Manager 2007 R2, na \\ pasta SupportTools AMD64, clique duas vezes em **DBCreateWizard.exe**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-129">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="1c92d-130">No Assistente para Configuração do Banco de Dados, na página **Benvindo ao Assistente para Configuração do Banco de Dados**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-130">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="1c92d-131">Na página **Informações do Banco de Dados**, deixe todas as configurações como estão e clique em **Avançar**</span><span class="sxs-lookup"><span data-stu-id="1c92d-131">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="1c92d-132">Na página **configuração do grupo de gerenciamento** , digite um nome para o grupo de gerenciamento (por exemplo, **monitoramento do Lync Server**) na caixa **nome do grupo de gerenciamento** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-132">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="1c92d-133">Na página **Relatórios de Erros do Operations Manager**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-133">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="1c92d-134">Na página **Resumo**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-134">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="1c92d-135">Criando um data warehouse do System Center Operations Manager para uso com o SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1c92d-135">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="1c92d-136">O Microsoft Lync Server 2013 acompanha três novos relatórios do System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="1c92d-136">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="1c92d-137">**Relatório de disponibilidade de cenário de ponta a ponta**     Este relatório detalha a disponibilidade/tempo de atividade dos serviços principais do Lync Server, como registro ou presença.</span><span class="sxs-lookup"><span data-stu-id="1c92d-137">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="1c92d-138">**Relatório**     de capacidade Usando informações de contador de desempenho, este relatório mostra tendências para componentes do sistema, como disponibilidade de memória e uso do processador.</span><span class="sxs-lookup"><span data-stu-id="1c92d-138">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="1c92d-139">**Relatório**     de componente Este relatório lista os principais geradores de alerta agrupados pelo componente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c92d-139">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="1c92d-140">Para usar esses novos relatórios, você deve instalar um data warehouse do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="1c92d-140">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="1c92d-141">(Um data warehouse fornece um armazenamento de dados de longo prazo de operações.) Para usar um data warehouse com o SQL Server 2008 R2, você deve executar as seguintes etapas no computador que hospeda o banco de dados do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="1c92d-141">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="1c92d-142">Na mídia de instalação do System Center Operations Manager, na \\ pasta Setup SupportTools \\ AMD64, clique duas vezes em **DBCreateWizard.exe**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-142">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="1c92d-143">No Assistente para Configuração do Banco de Dados, na página **Benvindo ao Assistente para Configuração do Banco de Dados**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-143">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="1c92d-144">Na página **Informações do Banco de Dados**, selecione **Banco de Dados Data Warehouse do Operations Manager** na lista suspensa **Tipo de Banco de Dados** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-144">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="1c92d-145">Na página **Resumo**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-145">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="1c92d-146">Instalando o console do System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="1c92d-146">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="1c92d-147">O console do Operations Manager é a principal ferramenta usada para gerenciar o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="1c92d-147">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="1c92d-148">Antes de instalar o console do Operations Manager, verifique se você instalou uma versão com suporte do SQL Server, juntamente com o SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="1c92d-148">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="1c92d-149">Também é recomendado executar o Gerenciador de Configuração do SQL Server Reporting Services para verificar se o Serviço de Relatórios foi instalado e configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="1c92d-149">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="1c92d-150">Para instalar o console do System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="1c92d-150">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="1c92d-151">Na mídia de instalação do System Center Operations Manager, clique duas vezes em **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-151">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="1c92d-152">Na instalação do System Center Operations Manager 2007 R2, clique em **verificar pré-requisitos**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-152">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="1c92d-153">No Visualizador de pré-requisitos do System Center Operations Manager, selecione os componentes do System Center que serão instalados: (**servidor**; **Console**; e **PowerShell**) e clique em **verificar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-153">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="1c92d-154">Verifique se nenhum problema de bloqueio foi identificado e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-154">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="1c92d-155">Se um problema de bloqueio foi identificado, corrija-o e clique em **Verificar** para executar novamente o teste de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="1c92d-155">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="1c92d-156">Na instalação do System Center Operations Manager, clique em **instalar o Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-156">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="1c92d-157">No assistente de instalação do System Center Operations Manager, na página **Bem-vindo ao assistente de instalação do System Center Operations Manager** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-157">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="1c92d-158">Na página **Contrato de Licença do Usuário Final**, selecione **Aceito os termos do contrato de licença** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-158">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="1c92d-159">Na página **Registro do Produto**, digite seu nome na caixa **Nome do Usuário** e o nome da sua organização na caixa **Organização**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-159">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="1c92d-160">Digite sua chave do produto do System Center Operations Manager na caixa **Insira a chave do CD de 25 dígitos** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-160">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="1c92d-p111">Na página **Instalação Personalizada**, selecione as opções do System Center a serem instaladas e clique em **Avançar**. Você deve selecionar **Servidor de Gerenciamento**, **Interfaces de Usuário** e **Console Web**. A opção **Banco de Dados** não deve ser selecionada e não deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p111">On the **Custom Setup** page select the System Center options to be installed and then click **Next**. You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed. **Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="1c92d-164">Na página **instância do servidor de banco de dados SC** , verifique se o nome do computador onde os bancos de dados do Operations Manager estão instalados aparece na caixa **servidor de banco de dados do System Center** .</span><span class="sxs-lookup"><span data-stu-id="1c92d-164">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="1c92d-165">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-165">Click **Next**.</span></span>

10. <span data-ttu-id="1c92d-p113">Na página **Conta de Ação do Servidor de Gerenciamento**, selecione **Conta de Domínio ou do Computador Local** e insira os valores adequados nas caixas **Conta de Usuário**, **Senha** e **Domínio ou computador local**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p113">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

11. <span data-ttu-id="1c92d-p114">Na página **SDK e Conta de Serviço de Configuração**, selecione **Conta de Domínio ou do Computador Local** e insira os valores adequados nas caixas **Conta de Usuário**, **Senha** e **Domínio ou computador local**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p114">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

12. <span data-ttu-id="1c92d-170">Na página **Relatórios de Erros do Operations Manager**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-170">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="1c92d-171">Na página **Programa de Aperfeiçoamento da Experiência do Usuário**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-171">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="1c92d-172">Na página **Pronto para Instalar o Programa**, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-172">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="1c92d-173">Na página **Concluindo a Instalação do System Center Operations Manager**, desmarque as opções **Chave de Criptografia de Backup** e **Iniciar o console** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-173">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="1c92d-174">Na instalação do System Center Operations Manager, clique em **sair**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-174">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="1c92d-175">Como instalar o System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1c92d-175">Installing System Center Reporting Services</span></span>

<span data-ttu-id="1c92d-176">Após instalar e configurar o console do System Center Operations Manager, você deve instalar o System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="1c92d-176">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="1c92d-177">Se você estiver usando o SQL Server 2008 R2 como o banco de dados back-end do Operations Manager, isso significa que você deve primeiro fazer uma alteração temporária no grupo de segurança associado ao SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="1c92d-177">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="1c92d-178">Se você estiver usando o SQL Server 2008 R2, deverá fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1c92d-178">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="1c92d-179">Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciador de Servidores**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-179">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="1c92d-180">No Gerenciador de Servidores, expanda **Configuração**, **Usuários e Grupos Locais** e clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-180">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="1c92d-181">Localize o grupo a seguir, em que ATL-SC-001 representa o nome do seu computador e ARCHINST representa a instância do SQL Server para o banco de dados do System Center: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10 \_ 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-181">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="1c92d-182">Clique com o botão direito no grupo e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-182">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="1c92d-183">Renomeie o grupo excluindo \*\* \_ 50\*\* do nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="1c92d-183">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="1c92d-184">Por exemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-184">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="1c92d-185">Feche o Gerenciador de Servidores.</span><span class="sxs-lookup"><span data-stu-id="1c92d-185">Close Server Manager.</span></span>

<span data-ttu-id="1c92d-p117">Neste ponto, você está pronto para instalar o System Center Reporting Services. Para isso:</span><span class="sxs-lookup"><span data-stu-id="1c92d-p117">At this point you are ready to install System Center Reporting Services. To do this:</span></span>

1.  <span data-ttu-id="1c92d-188">Na mídia de instalação do System Center Operations Manager 2007 R2, clique duas vezes em **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-188">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="1c92d-189">Na instalação do System Center Operations Manager 2007 R2, clique em **instalar o Operations Manager Reporting**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-189">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="1c92d-190">No assistente de instalação de relatórios do System Center Operations Manager 2007 R2, na página **Bem-vindo à instalação de relatórios do Operations Manager** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-190">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="1c92d-191">Na página **Contrato de Licença do Usuário Final**, selecione **Aceito os termos do contrato de licença** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-191">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="1c92d-192">Na página **Registro do Produto**, certifique-se de que seu nome e o nome da sua organização aparecem nas caixas **Nome do Usuário** e **Organização** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-192">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="1c92d-p118">Na página **Instalação Personalizada**, clique em **Servidor de Relatórios** e selecione **Este componente e todos os componentes dependentes serão instalados no disco rígido local**. Clique em **Data Warehouse** e selecione **Este componente não estará disponível** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p118">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**. Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="1c92d-195">Na página **Conectar ao servidor de gerenciamento raiz**, digite o nome do servidor de gerenciamento raiz do seu Operations Manager na caixa **Servidor de Gerenciamento Raiz** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-195">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="1c92d-p119">Na página **Conectar ao Data Warehouse do Operations Manager**, digite a instância do SQL Server em que seu data warehouse está localizado na caixa **Instância do SQL Server** (se seu data warehouse estiver localizado na instância padrão, digite simplesmente o nome do servidor; por exemplo: atl-sql-001). Verifique se o nome do banco de dados **OperationsManagerDW** aparece na caixa **Nome** e se a porta **1433** aparece na caixa **Porta do SQL Server**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p119">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box. (If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box. Click **Next**.</span></span>

9.  <span data-ttu-id="1c92d-199">Na página **Instância dos Relatórios do SQL Server**, selecione o servidor de relatórios do SQL Server na lista suspensa **Insira o Servidor do SQL Server Reporting Services** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-199">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="1c92d-p120">Na página **Conta de Gravação do Data Warehouse**, insira o nome e senha do usuário a quem serão inicialmente atribuídas permissões de gravação no data warehouse nas caixas **Conta de Usuário** e **Senha**. Selecione o domínio do usuário na lista suspensa **Domínio** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p120">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes. Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="1c92d-p121">Na página **Conta do Leitor de Dados**, insira o nome e senha da conta de usuário a ser usada quando o SQL Reporting Services consultar o data warehouse nas caixas **Conta de Usuário** e **Senha**. Selecione o domínio da conta na lista suspensa **Domínio** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p121">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes. Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="1c92d-204">Na página **Relatórios de Dados Operacionais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-204">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="1c92d-205">Na página **Microsoft Update**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-205">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="1c92d-206">Na página **Pronto para instalar o programa**, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-206">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="1c92d-207">Na página **Concluindo o Assistente de Instalação dos Componentes de Relatórios do Operations Manager**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-207">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="1c92d-208">Na instalação do System Center Operations Manager 2007 R2, clique em **sair**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-208">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="1c92d-209">Após a instalação do System Center Reporting, use o procedimento a seguir para redefinir o nome do grupo de segurança associado ao relatório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c92d-209">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="1c92d-210">Novamente, esse procedimento só será necessário se você estiver usando o SQL Server:</span><span class="sxs-lookup"><span data-stu-id="1c92d-210">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="1c92d-211">Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciador de Servidores**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-211">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="1c92d-212">No Gerenciador de Servidores, expanda **Configuração**, **Usuários e Grupos Locais** e clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-212">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="1c92d-213">Localize o grupo a seguir, em que ATL-SC-001 representa o nome do seu computador e ARCHINST representa a instância do SQL Server para os bancos de dados de arquivamento e monitoramento: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-213">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="1c92d-214">Clique com o botão direito no grupo e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-214">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="1c92d-215">Renomeie o grupo adicionando \*\* \_ 50\*\* ao final do nome do grupo, imediatamente antes do nome da instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c92d-215">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="1c92d-216">Por exemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10 \_ 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-216">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="1c92d-217">Feche o Gerenciador de Servidores.</span><span class="sxs-lookup"><span data-stu-id="1c92d-217">Close Server Manager.</span></span>

<span data-ttu-id="1c92d-p124">Se o Console de Operações do System Center estiver aberto, será necessário fechar o aplicativo e reiniciá-lo; se você não o fizer, a guia **Relatórios** não aparecerá na interface do usuário do Console de Operações. Observe que depois de reiniciar o Console de Operações pela primeira vez, pode demorar vários minutos até que todos os Relatórios de Monitoramento apareçam na guia **Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="1c92d-p124">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface. Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

