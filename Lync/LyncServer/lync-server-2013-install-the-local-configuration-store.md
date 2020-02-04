---
title: 'Lync Server 2013: Instalar o repositório de Configuração Local'
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
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="b59a7-102">Instalar o repositório de Configuração Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b59a7-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b59a7-103">_**Tópico da última modificação:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="b59a7-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="b59a7-104">Antes de seguir essas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalReadOnlyAdmin.</span><span class="sxs-lookup"><span data-stu-id="b59a7-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="b59a7-105">Para poder fazer algo com o assistente de implantação do Lync Server, precisamos que o repositório de configuração local exista em um servidor.</span><span class="sxs-lookup"><span data-stu-id="b59a7-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="b59a7-106">O repositório de configuração local é uma cópia somente leitura do repositório de gerenciamento central, que é criado após a instalação local do SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="b59a7-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="b59a7-107">O próprio repositório de gerenciamento central é adicionado ao banco de dados existente do SQL Server instalado no servidor Standard Edition ou no banco de dados baseado no SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="b59a7-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b59a7-108">Se você não tiver executado a instalação do Lync Server 2013 nesse servidor antes, será solicitado que você solicite uma unidade e um caminho para instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b59a7-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="b59a7-109">Isso permitirá que você instale em uma unidade diferente da unidade do sistema, se a sua organização exigir, ou se você tiver problemas de espaço.</span><span class="sxs-lookup"><span data-stu-id="b59a7-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="b59a7-110">Você pode simplesmente alterar o caminho do local de instalação dos arquivos do Lync Server na caixa de diálogo Configurar para uma nova unidade disponível.</span><span class="sxs-lookup"><span data-stu-id="b59a7-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="b59a7-111">Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado.</span><span class="sxs-lookup"><span data-stu-id="b59a7-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="b59a7-112">Para instalar o repositório de configuração local</span><span class="sxs-lookup"><span data-stu-id="b59a7-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="b59a7-113">Na mídia de instalação, navegue até \\Setup\\AMD64\\setup. exe e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b59a7-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="b59a7-114">Se você for solicitado a instalar o Microsoft Visual C++ 2012 Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b59a7-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="b59a7-115">Na página **local de instalação do Lync Server 2013** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b59a7-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="b59a7-116">Na página **contrato de licença de usuário final** , examine os termos de licença, você precisará **aceitar os termos do contrato de licença**e, em seguida, clicar em **OK** para poder continuar.</span><span class="sxs-lookup"><span data-stu-id="b59a7-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="b59a7-117">Na página Assistente de implantação, clique em **instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b59a7-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="b59a7-118">Na página do **Lync Server 2013** , ao lado de **Step1: instalar o repositório de configuração local**, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="b59a7-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="b59a7-119">Na página **Instalar Configurações de Armazenamento Local**, verifique se a opção **Recuperar diretamente do repositório de Gerenciamento Central** está selecionada, e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b59a7-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="b59a7-120">Quando a instalação de configuração do servidor local estiver concluída, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="b59a7-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

