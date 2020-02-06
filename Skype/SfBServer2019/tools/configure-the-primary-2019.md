---
title: Configurar o Servidor de Gerenciamento principal
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: configure seu servidor de gerenciamento primário, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.'
ms.openlocfilehash: a4fda367307b99bb952e6673b3b4d1c2967299c6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823995"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="eb7ab-103">Configurar o Servidor de Gerenciamento principal</span><span class="sxs-lookup"><span data-stu-id="eb7ab-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="eb7ab-104">**Resumo:** Configure seu servidor de gerenciamento primário, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="eb7ab-105">Para aproveitar ao máximo os novos recursos de monitoramento de integridade incluídos no Skype for Business Server 2019, você deve primeiro designar um computador para atuar como seu servidor de gerenciamento principal.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="eb7ab-106">Você deve instalar o System Center Operations Manager 2012 SP1 ou R2 ou o System Center Operations Manager 2007 R2 nesse computador.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="eb7ab-107">Além disso, você deve primeiro instalar uma versão com suporte do SQL Server para funcionar como o banco de dados back-end do Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="eb7ab-108">Ao instalar o System Center Operations Manager, você precisará instalar todos os componentes desse produto, incluindo:</span><span class="sxs-lookup"><span data-stu-id="eb7ab-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="eb7ab-109">Banco de dados operacional</span><span class="sxs-lookup"><span data-stu-id="eb7ab-109">Operational database</span></span>

- <span data-ttu-id="eb7ab-110">Servidor</span><span class="sxs-lookup"><span data-stu-id="eb7ab-110">Server</span></span>

- <span data-ttu-id="eb7ab-111">Console</span><span class="sxs-lookup"><span data-stu-id="eb7ab-111">Console</span></span>

- <span data-ttu-id="eb7ab-112">Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb7ab-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="eb7ab-113">Console da Web</span><span class="sxs-lookup"><span data-stu-id="eb7ab-113">Web console</span></span>

- <span data-ttu-id="eb7ab-114">Relatório</span><span class="sxs-lookup"><span data-stu-id="eb7ab-114">Reporting</span></span>

- <span data-ttu-id="eb7ab-115">Data warehouse</span><span class="sxs-lookup"><span data-stu-id="eb7ab-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb7ab-116">O "[pacote redistribuível do Microsoft Report Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" precisa ser instalado antes de instalar o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="eb7ab-117">Para obter detalhes sobre esses produtos e sua instalação, consulte os seguintes links:</span><span class="sxs-lookup"><span data-stu-id="eb7ab-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="eb7ab-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="eb7ab-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="eb7ab-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="eb7ab-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="eb7ab-120">Lembre-se de que você só pode ter um servidor de gerenciamento raiz por implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="eb7ab-121">Importando os pacotes de gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="eb7ab-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="eb7ab-122">Você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento — software que determina quais itens o System Center Operations Manager pode monitorar, como esses itens devem ser monitorados e como os alertas devem ser acionados e menciona.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="eb7ab-123">O Skype for Business Server 2019 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="eb7ab-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="eb7ab-124">**O componente e o pacote de gerenciamento de usuários** (Microsoft.ls.2019.Monitoring.ComponentAndUser.mp) controla os problemas do Skype for Business Server registrados nos logs de eventos, registrados pelos contadores de desempenho, ou registrados nos bancos de dados de registros de detalhes de chamadas (CDRs) ou na Quality of Experience (QoE).</span><span class="sxs-lookup"><span data-stu-id="eb7ab-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="eb7ab-125">Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="eb7ab-126">(SMS é a tecnologia usada para o envio de mensagens de texto de um dispositivo móvel para outro.)</span><span class="sxs-lookup"><span data-stu-id="eb7ab-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="eb7ab-127">Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte [Configurando a notificação](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="eb7ab-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="eb7ab-128">**O pacote de gerenciamento de monitoramento ativo** (Microsoft.ls.2019.Monitoring.ActiveMonitoring.mp) testa proativamente os componentes principais do Skype for Business Server, como entrar no sistema, trocar mensagens de chat ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="eb7ab-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="eb7ab-129">Esses testes são realizados com o uso de cmdlets de transação sintéticos do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="eb7ab-130">Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagens instantâneas entre um par de usuários de teste.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="eb7ab-131">Se essa conversa simulada falhar, um alerta será gerado.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="eb7ab-p105">A importação dos pacotes de gerenciamento é uma etapa crucial. Se os pacotes de gerenciamento não forem importados, você não poderá usar o Operations Manager para monitorar eventos do Skype for Business Server ou executar transações sintéticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-p105">Importing the management packs is a crucial step. If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="eb7ab-134">O pacote de gerenciamento de componentes e usuários é usado para monitorar somente o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="eb7ab-135">Se você estiver em um cenário de coexistência onde o Skype for Business Server 2019 e o Skype for Business Server 2015 estiverem instalados, você deve continuar a usar os pacotes de gerenciamento do Skype for Business Server 2015 para seus computadores com o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="eb7ab-136">Os pacotes de gerenciamento do Skype for Business Server 2019 incluem o componente do Skype for Business Server 2019 e o pacote de gerenciamento do usuário e o pacote de gerenciamento ativo do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="eb7ab-137">Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="eb7ab-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="eb7ab-138">**Gerenciador de operações do System Center** Com esse método, você usa o Operations Manager para adicionar monitoramento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="eb7ab-139">**Shell do Operations Manager** Você pode usar o Shell do Operations Manager para importar diretamente ou solucionar problemas que você encontra quando importa pacotes de gerenciamento usando o console do System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="eb7ab-140">Importando os pacotes de gerenciamento usando o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="eb7ab-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="eb7ab-141">Baixe o SkypeForBusiness2019ManagementPacks. msi do download da Microsoft na Web e instale o MSI.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="eb7ab-142">No System Center Operations Manager, clique em **Administração**.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="eb7ab-143">No painel Administração, clique com o botão direito do mouse em **pacotes de gerenciamento**e, em seguida, clique em **importar pacotes de gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="eb7ab-144">Na caixa de diálogo **Selecionar Pacotes de Gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="eb7ab-145">Na caixa de diálogo **Conexão do Catálogo Online**, clique em **Não**.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="eb7ab-146">Na caixa de diálogo **selecionar pacotes de gerenciamento a serem importados** , localize e selecione os arquivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.ls.2019.Monitoring.ComponentAndUser.MP e, em seguida, clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="eb7ab-147">Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo e, em seguida, mantenha pressionada a tecla CTRL e clique nos arquivos subsequentes.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="eb7ab-p108">Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso significa que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para outra pasta e reinicie o processo de instalação e importação.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="eb7ab-p109">Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. A conclusão do processo de importação e instalação pode levar muitos minutos.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-p109">In the **Select Management Packs** dialog box, click **Close**. The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="eb7ab-153">Importando os pacotes de gerenciamento usando o Shell do Operations Manager</span><span class="sxs-lookup"><span data-stu-id="eb7ab-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="eb7ab-p110">Em geral, é mais fácil importar os pacotes de gerenciamento usando o console do Operations Manager. No entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá relatórios de erro adequados. Em comparação, o Shell do Operations Manager fornece informações detalhadas. Se você estiver usando o Operations Manager e tiver problemas ao importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager. As informações fornecidas pelo Shell do Operations Manager podem ajudá-lo a determinar por que a importação falhou.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-p110">In general, it is easier to import the management packs by using the Operations Manager console. However, if an error occurs and the import fails, the console does not always provide adequate error reports. By comparison, the Operations Manager Shell provides detailed information. If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell. The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="eb7ab-159">Clique em **Iniciar**, **Todos os Programas**, **Microsoft System Center 2012**, **Operations Manager** e **Shell do Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="eb7ab-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="eb7ab-160">No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e, em seguida, pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="eb7ab-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="eb7ab-161">Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho para a sua cópia do arquivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="eb7ab-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
