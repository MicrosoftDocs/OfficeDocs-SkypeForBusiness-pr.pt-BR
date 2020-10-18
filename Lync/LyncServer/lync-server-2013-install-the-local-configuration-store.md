---
title: 'Lync Server 2013: instalar o repositório de configuração local'
description: 'Lync Server 2013: instalar o repositório de configuração local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf603704a8e1bdfbe71e0a9b064013d57bceda7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574057"
---
# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="25498-103">Instalar o repositório de configuração local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25498-103">Install the Local Configuration store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25498-104">_**Última modificação do tópico:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="25498-104">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="25498-105">Antes de seguir estas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalReadOnlyAdmin.</span><span class="sxs-lookup"><span data-stu-id="25498-105">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="25498-106">Para poder fazer qualquer coisa com o assistente de implantação do Lync Server, precisamos que o repositório de configuração local exista em um servidor.</span><span class="sxs-lookup"><span data-stu-id="25498-106">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="25498-107">O repositório de configuração local é uma cópia somente leitura do repositório de gerenciamento central, que é criado após a instalação local do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="25498-107">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="25498-108">O repositório de gerenciamento central em si é adicionado ao banco de dados do SQL Server existente instalado no servidor Standard Edition ou no banco de dados baseado no SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="25498-108">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25498-109">Se você não tiver executado a instalação do Lync Server 2013 neste servidor antes, você será solicitado a fornecer uma unidade e um caminho para instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25498-109">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="25498-110">Isso permitirá que você instale em uma unidade diferente da unidade do sistema, se sua organização exigir, ou se você tiver problemas de espaço.</span><span class="sxs-lookup"><span data-stu-id="25498-110">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="25498-111">Você pode apenas alterar o caminho do local de instalação dos arquivos do Lync Server na caixa de diálogo Configurar para uma nova unidade disponível.</span><span class="sxs-lookup"><span data-stu-id="25498-111">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="25498-112">Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore.msi, o restante dos arquivos do Lync Server 2013 também será implantado.</span><span class="sxs-lookup"><span data-stu-id="25498-112">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="25498-113">Para instalar o repositório Configuração Local</span><span class="sxs-lookup"><span data-stu-id="25498-113">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="25498-114">Na mídia de instalação, navegue até \\ instalar \\ AMD64 \\Setup.exe e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="25498-114">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="25498-115">Se você for solicitado a instalar o Microsoft Visual C++ 2012 Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="25498-115">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="25498-116">Na página **local de instalação do Lync Server 2013** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="25498-116">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="25498-117">Na página **contrato de licença de usuário final** , revise os termos de licença, selecione **aceito os termos do contrato de licença**e clique em **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="25498-117">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="25498-118">Na página Assistente de Implantação, clique em **Instalar ou Atualizar o Sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="25498-118">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="25498-119">Na página **Lync Server 2013** , ao lado de **etapa 1: instalar repositório de configuração local**, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="25498-119">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="25498-120">Na página **instalar o repositório de configuração local** , verifique se a opção **recuperar diretamente do repositório de gerenciamento central** está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="25498-120">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="25498-121">Quando a instalação da configuração do servidor local estiver concluída, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="25498-121">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

