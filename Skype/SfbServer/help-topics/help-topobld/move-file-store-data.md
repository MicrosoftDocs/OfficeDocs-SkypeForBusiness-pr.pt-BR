---
title: Mover dados do armazenamento de arquivos para um novo armazenamento de arquivos no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Se você precisar remover o servidor de arquivos que está atuando como o armazenamento de arquivos para sua implantação do Skype for Business Server 2015 ou se precisar fazer outras alterações que indisponíveis o armazenamento de arquivos atual, primeiro você precisará criar um novo compartilhamento. Em seguida, você precisa executar as seguintes etapas:'
ms.openlocfilehash: 2d65e517b10a76013fbeb332b183b5b816e99083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119640"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="b97a8-104">Mover dados do armazenamento de arquivos para um novo armazenamento de arquivos no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b97a8-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="b97a8-105">Se você precisar remover o servidor de arquivos que está atuando como o armazenamento de arquivos para sua implantação do Skype for Business Server 2015 ou se precisar fazer outras alterações que indisponíveis o armazenamento de arquivos atual, primeiro você precisará criar um novo compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="b97a8-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="b97a8-106">Em seguida, você precisa executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b97a8-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="b97a8-107">Feche os serviços do Skype for Business Server 2015 que usam o armazenamento de arquivos que você planeja remover.</span><span class="sxs-lookup"><span data-stu-id="b97a8-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="b97a8-108">Defina o armazenamento de arquivos no Construtor de Topologias e publique as alterações para disponibilizar o novo armazenamento de arquivos para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b97a8-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="b97a8-109">Mova os dados para o novo armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b97a8-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="b97a8-110">Reinicie os servidores ou serviços.</span><span class="sxs-lookup"><span data-stu-id="b97a8-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="b97a8-111">Opcionalmente, remova o compartilhamento de arquivo antigo e a pasta de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b97a8-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="b97a8-112">Para mover os dados do repositório de arquivos de um repositório para o novo</span><span class="sxs-lookup"><span data-stu-id="b97a8-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="b97a8-113">Faça logon em um computador como membro do grupo RTCUniversersalServerAdmins ou CsServerAdministrator onde o Skype for Business Server 2015, Ferramentas Administrativas estão instalados.</span><span class="sxs-lookup"><span data-stu-id="b97a8-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="b97a8-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b97a8-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b97a8-115">Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="b97a8-116">Para cada pool de diretores, diretor, servidor Standard Edition e pool de Front-End que usa o armazenamento de arquivos que você planeja remover, selecione o servidor ou pool, clique em **Ação** e clique em **Parar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="b97a8-117">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b97a8-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="b97a8-118">Iniciar Construtor de Topologias: **clique** em Iniciar, em Todos os **Programas,** em **Skype for Business Server 2015** e em Construtor de Topologia do **Skype for Business Server 2015**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="b97a8-119">Selecione um servidor ou pool que use o armazenamento de arquivos e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b97a8-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="b97a8-120">Clique com o botão direito do mouse no servidor ou pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="b97a8-121">Em **Editar propriedades,** em **Associações**, em **Armazenamento de arquivos,** clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="b97a8-122">Em **Definir Novo Armazenamento de Arquivos,** em **FQDN** do servidor de arquivos, digite o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b97a8-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="b97a8-123">Em **Compartilhamento de** arquivos, digite o nome da pasta para o novo compartilhamento de arquivos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="b97a8-124">Esta etapa define um novo armazenamento de arquivos para uso no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="b97a8-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="b97a8-125">Você o define apenas uma vez, não para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="b97a8-125">You define it only once, not for each server.</span></span> <span data-ttu-id="b97a8-126">Antes de publicar a topologia, você deve criar o compartilhamento de arquivos definido no servidor de arquivos especificado.</span><span class="sxs-lookup"><span data-stu-id="b97a8-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="b97a8-127">Para detalhes, consulte [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="b97a8-127">For details, see [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span></span>

11. <span data-ttu-id="b97a8-128">Para cada servidor ou pool que usa o armazenamento de arquivos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b97a8-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="b97a8-129">Clique com o botão direito do mouse no servidor ou pool e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="b97a8-130">Em **Editar Propriedades,** em **Associações**, no **Armazenamento** de arquivos, selecione o novo compartilhamento de arquivos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="b97a8-131">Publique a topologia, verifique o status da replicação e execute o Assistente de Implantação do Skype for Business Server conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b97a8-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="b97a8-132">Para obter detalhes, consulte [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="b97a8-132">For details, see [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span></span>

15. <span data-ttu-id="b97a8-133">Inicie um prompt de comando: clique em **Iniciar,** clique em **Executar** e digite cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="b97a8-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="b97a8-134">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b97a8-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="b97a8-135">A opção /S copia arquivos, diretórios e subdireções.</span><span class="sxs-lookup"><span data-stu-id="b97a8-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="b97a8-136">A opção /XF ignora todos os arquivos chamados Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="b97a8-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="b97a8-137">Versões atuais do robocopy.exe com a opção /MT aumentam muito a velocidade da cópia usando vários threads.</span><span class="sxs-lookup"><span data-stu-id="b97a8-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="b97a8-138">Para a opção /LOG, use um caminho de diretório e o nome do arquivo de log na forma de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="b97a8-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="b97a8-139">Essa opção cria um arquivo de log de operações no local nomeado.</span><span class="sxs-lookup"><span data-stu-id="b97a8-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="b97a8-140">Quando a cópia de dados estiver concluída, no Painel de Controle do Lync Server, clique em **Topologia** e clique em **Status**.</span><span class="sxs-lookup"><span data-stu-id="b97a8-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="b97a8-141">Para cada servidor ou pool onde você parou serviços, selecione o servidor ou pool, clique em **Ação** e clique em **Iniciar todos os serviços.**</span><span class="sxs-lookup"><span data-stu-id="b97a8-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="b97a8-142">Remova o repositório de arquivos antigo da topologia e publique-a.</span><span class="sxs-lookup"><span data-stu-id="b97a8-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="b97a8-143">Para detalhes, consulte [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="b97a8-143">For details, see [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span></span>

20. <span data-ttu-id="b97a8-144">(Opcional) Faça logon no computador que contém o repositório de arquivos que foi removido como membro do grupo Administradores local ou grupo Admins. de Domínio e remova o compartilhamento de arquivos e o diretório antigos.</span><span class="sxs-lookup"><span data-stu-id="b97a8-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="b97a8-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="b97a8-145">See also</span></span>

<span data-ttu-id="b97a8-146">[Reatribuir um servidor para um repositório de arquivo diferente](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="b97a8-146">[Reassign a Server to a Different File Store](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span></span>

<span data-ttu-id="b97a8-147">[Remover um armazenamento de arquivos](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="b97a8-147">[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span></span>