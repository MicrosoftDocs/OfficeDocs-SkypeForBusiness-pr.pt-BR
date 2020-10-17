---
title: 'Lync Server 2013: Configurando um nó do inspetor para usar autenticação de credenciais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e05ac48896b50b4b83e4211a5036f6a6d513d43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517684"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="a3a10-102">Configurando um nó do inspetor para usar a autenticação de credenciais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3a10-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3a10-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a3a10-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a3a10-p101">Se seu computador no nó do inspetor estiver fora da rede de perímetro, será necessário seguir um procedimento um pouco diferente para configurar o nó do inspetor a fim de executar transações sintéticas. Especificamente, não crie um pool de aplicativos confiáveis e um aplicativo confiável, e é necessário instalar um certificado que permita ao nó do inspetor enviar alertas a um computador dentro da rede de perímetro. Isso significa que será necessário completar duas tarefas separadas:</span><span class="sxs-lookup"><span data-stu-id="a3a10-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="a3a10-107">Atualize a associação no grupo Administradores locais somente leitura RTC do computador</span><span class="sxs-lookup"><span data-stu-id="a3a10-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="a3a10-108">Instale os arquivos de configuração do nó do inspetor</span><span class="sxs-lookup"><span data-stu-id="a3a10-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="a3a10-109">Atualizando a associação no grupo Administradores locais somente leitura RTC</span><span class="sxs-lookup"><span data-stu-id="a3a10-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="a3a10-p102">Se seu nó de inspetor estiver fora da rede de perímetro, será necessário adicionar a conta Serviço de Rede ao grupo Administradores locais somente leitura RTC no computador no nó do inspetor. Para fazer isso, complete o seguinte procedimento no nó do inspetor:</span><span class="sxs-lookup"><span data-stu-id="a3a10-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="a3a10-112">Clique em **Iniciar**, clique com o botão direito do mouse em **Computador** e clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a3a10-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="a3a10-113">No Gerenciador de Servidor, expanda **Configuração**, expanda **Usuários e Grupos Locais** e clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="a3a10-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="a3a10-114">No painel Grupos, clique duas vezes em **Administradores locais somente leitura RTC**.</span><span class="sxs-lookup"><span data-stu-id="a3a10-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="a3a10-115">Na caixa  de diálogo **Propriedades de Administradores Locais Somente Leitura RTC**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a3a10-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="a3a10-116">Na caixa de diálogo **Selecionar Usuários, Computadores, Contas de Serviço ou Grupos**, clique em **Locais**</span><span class="sxs-lookup"><span data-stu-id="a3a10-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="a3a10-117">Na caixa de diálogo **Locais**, selecione o nome do computador no nó de inspetor e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a10-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="a3a10-118">Na caixa **Digite os nomes de objeto a serem selecionados**, digite **Serviço de Rede** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a10-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="a3a10-119">Na caixa  de diálogo **Propriedades de Administradores Locais Somente Leitura RTC**, clique em **OK** e feche o **Gerenciador de Servidor**.</span><span class="sxs-lookup"><span data-stu-id="a3a10-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="a3a10-120">Reinicie o computador no nó do inspetor.</span><span class="sxs-lookup"><span data-stu-id="a3a10-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="a3a10-121">Instalando os Arquivos de Configuração no Nó do Inspetor</span><span class="sxs-lookup"><span data-stu-id="a3a10-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="a3a10-122">Após a reinicialização do computador no nó de inspetor, sua próxima etapa será executar o arquivo Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="a3a10-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="a3a10-123">Para executar esse arquivo, abra o Shell de gerenciamento do Lync Server 2013 clicando em **Iniciar**, em **todos os programas**, em **Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a3a10-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="a3a10-124">No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER (tenha certeza e especifique o caminho real para a sua cópia do Watchernode.msi):</span><span class="sxs-lookup"><span data-stu-id="a3a10-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="a3a10-p104">Conforme indicado anteriormente, Watchernode.msi também pode ser executado a partir de uma janela de comando. Para abrir uma janela de comando, clique em <STRONG>Iniciar</STRONG>, clique com o botão direito do mouse em <STRONG>Prompt de Comando</STRONG> e clique em <STRONG>Executar como administrador</STRONG>. Quando a janela de comando for aberta, digite o mesmo comando exibido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a3a10-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="a3a10-128">O modo Negociar é usado sempre que o nó de inspetor não podem ser configurado como um pool de aplicativos confiável.</span><span class="sxs-lookup"><span data-stu-id="a3a10-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="a3a10-129">Nesse modo, os administradores precisarão gerenciar as senhas do usuário de teste no nó de inspetor.</span><span class="sxs-lookup"><span data-stu-id="a3a10-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

