---
title: 'Lync Server 2013: Configurando um nó de inspetor para usar a autenticação de credenciais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3746042e0fbf6c7342dd19085f563440b26bb0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="35fcb-102">Configurando um nó de inspetor para usar a autenticação de credenciais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35fcb-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35fcb-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="35fcb-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="35fcb-104">Se o seu computador do nó do Inspetor estiver fora da rede de perímetro, você deve seguir um procedimento levemente diferente para configurar esse nó de inspetor para executar transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="35fcb-104">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions.</span></span> <span data-ttu-id="35fcb-105">Especificamente, você não deve criar um pool de aplicativos confiável e um aplicativo confiável, e deve instalar um certificado que permita que o nó do Inspetor envie alertas para um computador dentro da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="35fcb-105">Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network.</span></span> <span data-ttu-id="35fcb-106">Isso significa que você precisará completar duas tarefas separadas:</span><span class="sxs-lookup"><span data-stu-id="35fcb-106">This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="35fcb-107">Atualize a associação no grupo de administradores somente leitura do RTC do computador local</span><span class="sxs-lookup"><span data-stu-id="35fcb-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="35fcb-108">Instalar os arquivos de configuração do nó do Inspetor</span><span class="sxs-lookup"><span data-stu-id="35fcb-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="35fcb-109">Atualizando associação no grupo de administradores somente leitura local do RTC</span><span class="sxs-lookup"><span data-stu-id="35fcb-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="35fcb-110">Se o nó do Inspetor estiver fora da rede de perímetro, você deve adicionar a conta de serviço de rede ao grupo de administradores somente leitura local do RTC no computador do nó inspetor.</span><span class="sxs-lookup"><span data-stu-id="35fcb-110">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer.</span></span> <span data-ttu-id="35fcb-111">Para fazer isso, conclua o procedimento a seguir no nó inspetor:</span><span class="sxs-lookup"><span data-stu-id="35fcb-111">To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="35fcb-112">Clique em **Iniciar**, clique com o botão direito do mouse em **computador**e clique em **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="35fcb-113">No Gerenciador de servidores, expanda **configuração**, expanda **usuários e grupos locais**e clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="35fcb-114">No painel grupos, clique duas vezes em **RTC somente leitura administradores locais**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="35fcb-115">Na caixa de diálogo **Propriedades de administradores somente leitura do RTC local** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="35fcb-116">Na caixa de diálogo **Selecionar usuários, computadores, contas de serviço ou grupos** , clique em **locais**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="35fcb-117">Na caixa de diálogo **locais** , selecione o nome do computador do nó do Inspetor e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="35fcb-118">Na caixa **digite os nomes de objeto a serem selecionados** , digite **serviço de rede**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="35fcb-119">Na caixa de diálogo **Propriedades de administradores somente leitura do RTC local** , clique em **OK**e feche o **Gerenciador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="35fcb-120">Reinicie o computador no nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="35fcb-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="35fcb-121">Instalando os arquivos de configuração do nó do Inspetor</span><span class="sxs-lookup"><span data-stu-id="35fcb-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="35fcb-122">Após a reinicialização do computador do nó do Inspetor, a próxima etapa é executar o arquivo Watchernode. msi.</span><span class="sxs-lookup"><span data-stu-id="35fcb-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="35fcb-123">Para executar esse arquivo, abra o Shell de gerenciamento do Lync Server 2013 clicando em **Iniciar**, em **todos os programas**, em **Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="35fcb-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="35fcb-124">No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER (certifique-se de especificar o caminho real para a sua cópia do Watchernode. msi):</span><span class="sxs-lookup"><span data-stu-id="35fcb-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="35fcb-125">Conforme observado anteriormente, o Watchernode. msi também pode ser executado em uma janela de comando.</span><span class="sxs-lookup"><span data-stu-id="35fcb-125">As noted previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="35fcb-126">Para abrir uma janela de comando, clique em <STRONG>Iniciar</STRONG>, clique com o botão direito do mouse em <STRONG>Prompt de Comando</STRONG> e clique em <STRONG>Executar como administrador</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="35fcb-126">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="35fcb-127">Quando a janela de comando abrir, digite o mesmo comando mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="35fcb-127">When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="35fcb-p105">O modo Negociar é usado sempre que o nó de inspetor não podem ser configurado como um pool de aplicativos confiável. Nesse modo, os administradores precisarão gerenciar as senhas do usuário de teste no nó de inspetor.</span><span class="sxs-lookup"><span data-stu-id="35fcb-p105">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool. In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

