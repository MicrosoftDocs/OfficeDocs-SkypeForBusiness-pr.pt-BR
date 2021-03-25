---
title: Configurar o Servidor de Gerenciamento Primário
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: configure seu servidor de gerenciamento principal, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.'
ms.openlocfilehash: 02a174fb5c5fd6f06188553d8b2647c7162966e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120462"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="bdf62-103">Configurar o Servidor de Gerenciamento Primário</span><span class="sxs-lookup"><span data-stu-id="bdf62-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="bdf62-104">**Resumo:** Configure seu servidor de gerenciamento principal, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bdf62-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="bdf62-105">Para aproveitar ao máximo os novos recursos de monitoramento de saúde incluídos no Skype for Business Server 2019, você deve primeiro designar um computador para atuar como seu servidor de gerenciamento principal.</span><span class="sxs-lookup"><span data-stu-id="bdf62-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="bdf62-106">Você deve instalar o System Center Operations Manager 2012 SP1 ou R2 ou o System Center Operations Manager 2007 R2 nesse computador.</span><span class="sxs-lookup"><span data-stu-id="bdf62-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="bdf62-107">Além disso, você deve primeiro instalar uma versão com suporte do SQL Server para funcionar como seu banco de dados back-end do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="bdf62-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="bdf62-108">Ao instalar o System Center Operations Manager, você precisará instalar todos os componentes desse produto, incluindo:</span><span class="sxs-lookup"><span data-stu-id="bdf62-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="bdf62-109">Banco de dados operacional</span><span class="sxs-lookup"><span data-stu-id="bdf62-109">Operational database</span></span>

- <span data-ttu-id="bdf62-110">Servidor</span><span class="sxs-lookup"><span data-stu-id="bdf62-110">Server</span></span>

- <span data-ttu-id="bdf62-111">Console</span><span class="sxs-lookup"><span data-stu-id="bdf62-111">Console</span></span>

- <span data-ttu-id="bdf62-112">\s-1 \plain Windows PowerShellcmdlets</span><span class="sxs-lookup"><span data-stu-id="bdf62-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="bdf62-113">Console da Web</span><span class="sxs-lookup"><span data-stu-id="bdf62-113">Web console</span></span>

- <span data-ttu-id="bdf62-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="bdf62-114">Reporting</span></span>

- <span data-ttu-id="bdf62-115">Data warehouse</span><span class="sxs-lookup"><span data-stu-id="bdf62-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdf62-116">O "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" precisa ser instalado antes de instalar o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="bdf62-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="bdf62-117">Para obter detalhes sobre esses produtos e sua instalação, consulte os seguintes links:</span><span class="sxs-lookup"><span data-stu-id="bdf62-117">For details about these products and their installation, see the following links:</span></span>

- <span data-ttu-id="bdf62-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span><span class="sxs-lookup"><span data-stu-id="bdf62-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span></span>

- [<span data-ttu-id="bdf62-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="bdf62-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="bdf62-120">Lembre-se de que você pode ter apenas um Servidor de Gerenciamento Raiz por implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bdf62-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="bdf62-121">Importando os Pacotes de Gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="bdf62-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="bdf62-122">Você pode estender os recursos do System Center Operations Manager instalando pacotes de gerenciamento, software que determina quais itens o System Center Operations Manager pode monitorar, como esses itens devem ser monitorados e como os alertas devem ser disparados e relatados.</span><span class="sxs-lookup"><span data-stu-id="bdf62-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="bdf62-123">O Skype for Business Server 2019 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="bdf62-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="bdf62-124">O **Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) rastreia problemas do Skype for Business Server registrados em logs de eventos, registrados por contadores de desempenho ou registrados nos cdrs (registros de detalhes da chamada) ou nos bancos de dados de Qualidade da Experiência (QoE).</span><span class="sxs-lookup"><span data-stu-id="bdf62-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="bdf62-125">Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS.</span><span class="sxs-lookup"><span data-stu-id="bdf62-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="bdf62-126">(SMS, ou Serviço de Mensagem Curta, é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.)</span><span class="sxs-lookup"><span data-stu-id="bdf62-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="bdf62-127">Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="bdf62-127">For details about configuring Operations Manager notification, see [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).</span></span>

- <span data-ttu-id="bdf62-128">O **Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Skype for Business Server, como entrar no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na PSTN (rede telefônica pública comutado).</span><span class="sxs-lookup"><span data-stu-id="bdf62-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="bdf62-129">Esses testes são conduzidos usando os cmdlets de transação sintética do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bdf62-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="bdf62-130">Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagem instantânea entre um par de usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="bdf62-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="bdf62-131">Se essa conversa simulada falhar, um alerta será gerado.</span><span class="sxs-lookup"><span data-stu-id="bdf62-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="bdf62-132">Importar os pacotes de gerenciamento é uma etapa crucial.</span><span class="sxs-lookup"><span data-stu-id="bdf62-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="bdf62-133">Se os pacotes de gerenciamento não são importados, você não poderá usar o Operations Manager para monitorar eventos do Skype for Business Server ou executar transações sintéticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bdf62-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="bdf62-134">O Component and User Management Pack é usado para monitorar apenas o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bdf62-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="bdf62-135">Se você estiver em um cenário de coexistência em que o Skype for Business Server 2019 e o Skype for Business Server 2015 estão instalados, você deve continuar a usar os pacotes de gerenciamento do Skype for Business Server 2015 para seus computadores do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bdf62-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf62-136">Os pacotes de gerenciamento do Skype for Business Server 2019 incluem o Componente do Skype for Business Server 2019 e o User Management Pack e o Pacote de Gerenciamento de Monitoramento Ativo do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bdf62-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="bdf62-137">Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="bdf62-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="bdf62-138">**System Center Operations Manager** Com esse método, você usa o Operations Manager para adicionar monitoramento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bdf62-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="bdf62-139">**Shell do Operations Manager** Você pode usar o Shell do Operations Manager para importar diretamente ou solucionar problemas que encontrar ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="bdf62-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="bdf62-140">Importando os Pacotes de Gerenciamento usando o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="bdf62-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="bdf62-141">Baixe o SkypeForBusiness2019ManagementPacks.msi dos downloads da Microsoft Web e instale o msi.</span><span class="sxs-lookup"><span data-stu-id="bdf62-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="bdf62-142">No System Center Operations Manager, clique em **Administração**.</span><span class="sxs-lookup"><span data-stu-id="bdf62-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="bdf62-143">No painel Administração, clique com o botão direito do mouse em **Pacotes de gerenciamento** e, em seguida, clique em **Importar pacotes de gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="bdf62-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="bdf62-144">Na caixa de diálogo **Selecinar pacotes de gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.</span><span class="sxs-lookup"><span data-stu-id="bdf62-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="bdf62-145">Na caixa **de diálogo Conexão de** Catálogo Online, clique em **Não**.</span><span class="sxs-lookup"><span data-stu-id="bdf62-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="bdf62-146">Na caixa de diálogo Selecionar Pacotes de Gerenciamento a serem **importados,** localize e selecione os arquivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2019.Monitoring.ComponentAndUser.mp e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="bdf62-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="bdf62-147">Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo e segure a tecla Ctrl e clique nos arquivos subsequentes.</span><span class="sxs-lookup"><span data-stu-id="bdf62-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="bdf62-148">Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bdf62-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="bdf62-149">Se receber uma mensagem de erro e a instalação falhar, geralmente isso signfica que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="bdf62-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="bdf62-150">Se isso ocorrer, copie os arquivos para uma pasta diferente e reinicie o processo de importação e instalação.</span><span class="sxs-lookup"><span data-stu-id="bdf62-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="bdf62-151">Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="bdf62-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="bdf62-152">O processo de importação e instalação pode exigir vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="bdf62-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="bdf62-153">Importando os Pacotes de Gerenciamento usando o Shell do Operations Manager</span><span class="sxs-lookup"><span data-stu-id="bdf62-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="bdf62-154">Em geral, é mais fácil importar os pacotes de gerenciamento usando o console do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="bdf62-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="bdf62-155">No entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá relatórios de erros adequados.</span><span class="sxs-lookup"><span data-stu-id="bdf62-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="bdf62-156">Por comparação, o Shell do Operations Manager fornece informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="bdf62-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="bdf62-157">Se você estiver usando o Operations Manager e encontrar problemas ao importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="bdf62-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="bdf62-158">As informações fornecidas pelo Shell do Operations Manager podem ajudá-lo a determinar por que a importação falhou.</span><span class="sxs-lookup"><span data-stu-id="bdf62-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="bdf62-159">Clique **em Iniciar,** em **Todos os Programas,** em **Microsoft System Center 2012,** em **Operations Manager** e em Operations **Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="bdf62-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="bdf62-160">No Shell do Gerenciador de Operações, digite o seguinte comando no prompt de comando, usando o caminho real para sua cópia do arquivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="bdf62-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="bdf62-161">Depois de importar o primeiro pacote de gerenciamento, repita o processo, usando o caminho para sua cópia do arquivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="bdf62-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```